cmake_minimum_required(VERSION 3.10)
project(visualSLAM)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Eigen3 REQUIRED)
find_package(Pangolin REQUIRED)
find_package(Sophus REQUIRED)
find_package(OpenCV REQUIRED)

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