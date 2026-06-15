cmake_minimum_required(VERSION 3.10)
project(visualSLAM)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Eigen3 REQUIRED)
find_package(Pangolin REQUIRED)
find_package(Sophus REQUIRED)
find_package(OpenCV REQUIRED)
find_package(Ceres REQUIRED)
find_package(g2o REQUIRED)

add_executable(useEigen ch03/useEigen.cpp)
target_link_libraries(useEigen Eigen3::Eigen)

add_executable(useGeometry ch03/useGeometry.cpp)
target_link_libraries(useGeometry Eigen3::Eigen)

add_executable(coordinateTransform ch03/coordinateTransform.cpp)
target_link_libraries(coordinateTransform Eigen3::Eigen)

add_executable(plotTrajectory ch03/plotTrajectory.cpp)
target_link_libraries(plotTrajectory Eigen3::Eigen pango_display)

add_executable(useSophus ch04/useSophus.cpp)
target_link_libraries(useSophus Eigen3::Eigen Sophus::Sophus)

add_executable(trajectoryError ch04/trajectoryError.cpp)
target_link_libraries(trajectoryError Eigen3::Eigen Sophus::Sophus pango_display)

add_executable(imageBasics ch05/imageBasics.cpp)
target_link_libraries(imageBasics ${OpenCV_LIBS})

add_executable(undistortImage ch05/undistortImage.cpp)
target_link_libraries(undistortImage ${OpenCV_LIBS})

add_executable(gaussNewton ch06/gaussNewton.cpp)
target_link_libraries(gaussNewton Eigen3::Eigen ${OpenCV_LIBS})

add_executable(ceresCurveFitting ch06/ceresCurveFitting.cpp)
target_link_libraries(ceresCurveFitting Eigen3::Eigen ${OpenCV_LIBS} Ceres::ceres)

add_executable(g2oCurveFitting ch06/g2oCurveFitting.cpp)
target_link_libraries(g2oCurveFitting Eigen3::Eigen ${OpenCV_LIBS} g2o::core g2o::stuff g2o::solver_dense)