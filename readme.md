# Seele Embedded System Core (Seele-ESC)

## 项目概述

`Seele Embedded System Core (Seele-ESC)` 是一个轻量级的嵌入式系统核心框架，旨在为多种嵌入式应用提供灵活的 RTOS 支持和易于扩展的模块化结构。通过 Seele-ESC，开发者可以快速构建基于不同 RTOS（如 FreeRTOS、RTOS2 等）的嵌入式应用程序，确保系统的高效性和可移植性。

Seele-ESC 提供了统一的 RTOS 接口抽象层，简化了 RTOS 间的切换，并确保代码在不同硬件平台和操作系统之间的兼容性。这个框架的设计重点是最大程度地简化配置和开发流程，让开发者更专注于业务逻辑，而不是环境配置和工具链管理。

## 项目特性

- **尽量支持多种 RTOS**: Seele-ESC 通过抽象层支持多种 RTOS（如 FreeRTOS、RTOS2），让开发者可以轻松切换 RTOS，而无需修改业务逻辑代码。
- **尽量模块化架构**: 项目基于模块化设计，所有特定的实现都位于专门的目录中，易于扩展和替换。公共代码模块和 RTOS 相关模块分开，减少了相互依赖。
- **尽量支持跨平台构建**: 通过 CMake，Seele-ESC 支持跨平台构建，兼容多种硬件平台（如 ARM、RISC-V 等），开发者可以轻松迁移到不同的硬件架构。
- **简化的构建配置**: 使用 CMake 配置文件

## 项目结构

```plaintext
seele-ESC/    # 项目根目录
├── CMakeLists.txt             # 顶层 CMake 配置文件
├── toolchain/                 # 工具链文件
│   ├── toolchain-arm.cmake    # ARM 交叉编译工具链配置
├── src/                       # 源代码目录
│   ├── main.c                 # 主程序文件
│   ├── os_abstraction.c       # RTOS 抽象层
│   ├── os_abstraction.h       # RTOS 抽象层头文件
│   ├── freertos/              # FreeRTOS 实现目录
│   │   ├── os_abstraction_freeRTOS.c
│   ├── rtos2/                 # RTOS2 实现目录
│   │   ├── os_abstraction_rtos2.c
│   ├── common/                # 公共代码
│       ├── task.c
│       ├── queue.c
│       └── task.h             # 公共头文件
└── build/                     # 构建输出目录
```


