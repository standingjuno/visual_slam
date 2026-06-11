## Visual SLAM for macOS

### Homebrew

```bash
brew install cmake glew eigen sophus opencv
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