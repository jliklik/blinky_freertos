https://www.freertos.org/Community/Blogs/2021/using-visual-studio-code-for-freertos-development

VSCode Extensions Required
1) C/C++
2) Cortex-Debug

Setup
1) Create a new project with STM32CubeMX.
- Include FreeRTOS as middleware
- Select Makefile as the toolchain
2) Update VSCode c_cpp_properties.json file
- https://www.freertos.org/Community/Blogs/2021/using-visual-studio-code-for-freertos-development
- The first thing you will want to do is update the intelliSenseMode variable to be gcc-arm and provide your cross compiler in the compilerPath variable.
- Copy the INCLUDE list from the STM32CubeMX generated Makefile this into the includePath array in the c_cpp_properties.json file. Prefix each folder location with $  {workspaceFolder}
3) 