https://www.freertos.org/Community/Blogs/2021/using-visual-studio-code-for-freertos-development

VSCode Extensions Required
1) C/C++
2) Cortex-Debug
3) STM32Cube

Setup for WSL
1) Download cmake and ninja-build
2) Download STM32Cube extension for VSCode
3) Download STM32CubeMX for Linux
4) Use the STM32Cube extension to create a new project with STM32CubeMX.
- Include FreeRTOS as middleware
- Select CMake as the toolchain
5) Download arm-none-eabi-gcc
- Add the path to arm-none-eabi-gcc to your path: export PATH="<path_to_gcc>:$PATH"
6) Update .vscode/c_cpp_properties.json file
- https://www.freertos.org/Community/Blogs/2021/using-visual-studio-code-for-freertos-development
- The first thing you will want to do is update the intelliSenseMode variable to be gcc-arm and provide your cross compiler in the compilerPath variable.
- Copy the INCLUDE list from the STM32CubeMX generated Makefile this into the includePath array in the c_cpp_properties.json file. Prefix each folder location with ${workspaceFolder}
- Add the path to arm-none-eabi-gcc in c_cpp_properties.json
```
export PATH="/opt/gcc-arm-none-eabi-10.3-2021.10/bin:$PATH"
arm-none-eabi-gcc --version
```