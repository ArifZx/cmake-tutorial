cmake_minimum_required(VERSION 3.23.1)

project(APP)

add_executable(${PROJECT_NAME} main.cpp)

add_subdirectory(Adder)

add_subdirectory(external/cpr)

target_include_directories(${PROJECT_NAME} 
  PUBLIC Adder 
  PUBLIC external/cpr/include
)

target_link_directories(${PROJECT_NAME} 
  PRIVATE Adder
  PRIVATE external/cpr/cpr
)

target_link_libraries(${PROJECT_NAME} 
  adder
  cpr
)