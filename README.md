# SDLEmscriptenTemplate
A starter template for building SDL2 games in c++ 20 with support for emscripten

## Set Up Instructions

- Download SDL2 + libraries (Image, TTF, and Mixer are currently set up)
- Create build folder
- Open cmake-gui
- Configure project for desired compiler
- Set SDL*_dir variable when prompted
- Generate build files
- Add SDL dlls to PATH for windows
- To build emscripten run web_build/EmscriptenBuild.(bat|sh)
