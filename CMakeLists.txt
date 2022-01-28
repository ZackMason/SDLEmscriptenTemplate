cmake_minimum_required(VERSION 3.10)

set(APP_EXE Game)
project(${APP_EXE})

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")

file(GLOB src_files
    "game/src/*.h"
    "game/src/main.cpp"
)
add_executable(${APP_EXE} ${src_files})

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_mixer REQUIRED)
include_directories(game/src)
include_directories(${SDL2_INCLUDE_DIRS} ${SDL2_IMAGE_INCLUDE_DIRS} ${SDL2_TTF_INCLUDE_DIRS} ${SDL2_MIXER_INCLUDE_DIRS})

target_link_libraries(${APP_EXE} ${SDL2_LIBRARIES} ${SDL2_IMAGE_LIBRARY} ${SDL2_TTF_LIBRARY} ${SDL2_MIXER_LIBRARY})

file(COPY "game/res" DESTINATION ${CMAKE_BINARY_DIR})

