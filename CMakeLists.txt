cmake_minimum_required(VERSION 3.14)

project(fltk-boilerplate)


find_package(fltk REQUIRED PATHS "${FLTK_ROOT}/CMake")

# uncomment this line if using msvc
# SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /subsystem:windows /ENTRY:mainCRTStartup")

# uncomment this line if using clang
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static -Wl,--subsystem,windows")

include_directories(${FLTK_INCLUDE_DIRS})

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

target_link_libraries(${PROJECT_NAME} fltk)