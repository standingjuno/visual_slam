## Visual SLAM for macOS

### Homebrew

```bash
brew install cmake glew eigen sophus opencv ceres-solver g2o
```

### Pangolin 

```bash
mkdir -p 3rdparty && cd 3rdparty
git clone --recursive https://github.com/stevenlovegrove/Pangolin.git
cd Pangolin
git checkout v0.9.5
cmake -B build -DCMAKE_INSTALL_PREFIX=$HOME/.local
cmake --build build
cmake --install build
```

`~/.zshrc`에 추가:

```bash
export CMAKE_PREFIX_PATH="$HOME/.local:$CMAKE_PREFIX_PATH"
```

### 챕터별 예제

| 챕터 | 타깃 | 설명 |
| --- | --- | --- |
| ch03 | `useEigen`, `useGeometry`, `coordinateTransform`, `plotTrajectory` | Eigen 기초, 좌표 변환, 궤적 시각화 |
| ch04 | `useSophus`, `trajectoryError` | Lie 군/대수(Sophus), 궤적 오차 |
| ch05 | `imageBasics`, `undistortImage` | 이미지 처리, 왜곡 보정 |
| ch06 | `gaussNewton`, `ceresCurveFitting`, `g2oCurveFitting` | 비선형 최적화 (수동 Gauss-Newton / Ceres / g2o) |