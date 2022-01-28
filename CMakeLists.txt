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

file(COPY "${SDL2_LIBRARY_DIR}/SDL2.dll" DESTINATION "${CMAKE_BINARY_DIR}/Debug")
file(COPY "${SDL2_LIBRARY_DIR}/SDL2.dll" DESTINATION "${CMAKE_BINARY_DIR}/Release")
file(COPY "${SDL2_LIBRARY_DIR}/SDL2.dll" DESTINATION "${CMAKE_BINARY_DIR}")

file(COPY "${SDL2_IMAGE_PATH}/lib/x64/SDL2_image.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_IMAGE_PATH}/lib/x64/libjpeg-9.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_IMAGE_PATH}/lib/x64/libtiff-5.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_IMAGE_PATH}/lib/x64/libwebp-7.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_IMAGE_PATH}/lib/x64/libpng16-16.dll" DESTINATION "${CMAKE_BINARY_DIR}")

file(COPY "${SDL2_TTF_PATH}/lib/x64/SDL2_ttf.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_TTF_PATH}/lib/x64/libfreetype-6.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_TTF_PATH}/lib/x64/zlib1.dll" DESTINATION "${CMAKE_BINARY_DIR}")

file(COPY "${SDL2_MIXER_PATH}/lib/x64/libFLAC-8.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libmodplug-1.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libmpg123-0.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libogg-0.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libopus-0.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libopusfile-0.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libvorbis-0.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/libvorbisfile-3.dll" DESTINATION "${CMAKE_BINARY_DIR}")
file(COPY "${SDL2_MIXER_PATH}/lib/x64/SDL2_mixer.dll" DESTINATION "${CMAKE_BINARY_DIR}")
