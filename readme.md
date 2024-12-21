## **CMake 学习大纲**

## **一、CMake 基础概念**

### **1.1 CMake 简介**

#### 1.1.1什么是 CMake

CMake 是一个跨平台的开源构建系统，它使用 CMake 脚本语言（CMakeLists.txt 文件）来定义项目的构建过程。CMake 本身并不直接构建项目，它生成构建工具（如 Makefile、Ninja、Visual Studio 工程等）所需要的输入文件，以便构建系统使用这些文件进行实际的构建操作。 

• CMake 是一个构建系统生成工具，它的主要功能是通过解析项目的 CMakeLists.txt 文件，自动化生成具体平台的构建配置（如 Makefile、Ninja 文件等）。 

• CMake 是高度可配置的，可以适用于多种平台（Linux、Windows、macOS、嵌入式系统等），并支持多种编译器和构建工具。



#### 1.1.2CMake 的作用与优势



- 与 Makefile、Ninja 等构建工具的关系

#### 1.1.3**CMake 项目结构**

- `CMakeLists.txt` 文件
- 项目目录结构
- CMake 构建目录与源代码目录的区分

#### 1.1.4**CMake 工作流**

- 创建和配置项目
- 生成构建系统
- 编译和安装

#### 1.1.5**CMake 基本命令**

- `cmake_minimum_required`：定义最低版本
- `project()`：定义项目名称和语言
- `add_executable()`：定义可执行文件
- `add_library()`：定义静态或共享库
- `target_link_libraries()`：链接库



### **二、CMake 变量与基本操作**

1. **变量定义与使用**
   - `set()`：设置变量
   - `CACHE` 变量和常见用法
   - 访问和修改变量值
   - 自动变量：`${CMAKE_SOURCE_DIR}`, `${CMAKE_BINARY_DIR}`, `${CMAKE_CURRENT_LIST_DIR}`
2. **条件语句与循环**
   - `if()`, `elseif()`, `else()`
   - `foreach()` 与 `list()` 操作
   - `while()` 循环
3. **字符串与列表操作**
   - 字符串操作：连接、比较、替换、截取
   - 列表操作：添加、删除、排序、查询
4. **函数与宏**
   - `function()` 与 `endfunction()`：定义函数
   - `macro()` 与 `endmacro()`：定义宏
   - 参数传递和返回值
   - 局部与全局变量的作用域
5. **命令和表达式**
   - `message()` 打印信息
   - `execute_process()` 执行外部命令
   - `find_program()`、`find_library()`、`find_package()` 等查找工具

### **三、CMake 高级特性**

1. **构建目标与依赖管理**
   - `add_dependencies()`：设置构建依赖关系
   - `target_include_directories()`：设置包含目录
   - `target_compile_definitions()`：设置编译宏
   - `target_compile_options()`：设置编译选项
2. **跨平台构建**
   - 设置平台相关的编译选项
   - 针对不同平台设置不同的构建设置（Linux, Windows, macOS）
   - 构建架构的选择：`x86`, `x64`, `arm`, `aarch64`
3. **工具链文件（Toolchain Files）**
   - 使用工具链文件配置交叉编译环境
   - 嵌入式开发中的工具链文件
   - 配置和定制工具链文件
4. **包管理与外部依赖**
   - `find_package()`：查找和使用外部库（如 OpenCV, Boost）
   - 使用 CMake 包管理工具（如 `FetchContent` 和 `ExternalProject`）
   - 使用 CMake 模块管理依赖

### **四、CMake 流程与优化**

1. **构建优化**
   - 使用并行构建（例如，`make -j`）
   - 使用 Ninja 构建系统加速构建过程
   - CMake 内部缓存和预编译头文件的使用
2. **调试与输出**
   - `message()` 输出调试信息
   - `VERBOSE` 模式和 `CMAKE_VERBOSE_MAKEFILE` 选项
   - CMake 日志文件和构建详细信息
3. **自动化构建与 CI/CD 集成**
   - 配置 CMake 与 GitLab CI、Jenkins 等 CI 工具的集成
   - 自动化构建与部署

### **五、CMake 与嵌入式开发**

1. **嵌入式开发中的 CMake**
   - 配置交叉编译环境
   - 生成固件文件（`.bin`, `.elf`, `.hex` 等）
   - 管理外部硬件库（如 STM32 HAL、FreeRTOS）
2. **构建与部署固件**
   - 通过 CMake 与 OpenOCD、JLink 等调试工具配合使用
   - 自动化上传固件到目标设备
3. **CMake 在多平台开发中的应用**
   - 配置跨平台构建，支持 Linux, Windows, macOS 和 ARM 等目标平台
   - 构建调试和发布版本的区别

### **六、CMake 高级模块与自定义工具**

1. **CMake 模块**
   - 创建和使用自定义 CMake 模块
   - 使用 CMake 自带的 `Find<Package>.cmake` 模块
   - `CMakeModules/` 目录的使用
2. **自定义命令与构建过程**
   - `add_custom_command()`：自定义构建命令
   - `add_custom_target()`：自定义构建目标
   - 通过自定义命令生成代码或资源文件
3. **CMake 与 IDE 集成**
   - CMake 与 Visual Studio、CLion 等 IDE 集成
   - 配置 CMake 项目生成 IDE 项目文件

### **七、CMake 工具与最佳实践**

1. **CMake 最佳实践**
   - CMake 构建目录的管理
   - CMake 脚本的组织结构
   - 清晰的构建目标命名规则
2. **使用 CMake 构建大型项目**
   - 多模块项目管理
   - 配置与生成系统的分离
   - 使用 `ExternalProject` 和 `FetchContent` 管理外部依赖
3. **CMake 文档与参考**
   - 官方文档：CMake 官方文档和命令手册
   - 常见的 CMake 错误及其解决方法
   - CMake 社区资源和常用的第三方库





1.最简单的cmake文件

camke主文件 CMakeLists.txt，创建该文件,输入如下内容

```
cmake_minimum_required(VERSION 3.10)  # 设置CMake的最低版本要求
project(HelloWorld)  # 定义项目名称

# 打印 "Hello, CMake!"
message(STATUS "Hello, CMake!")
```

创建一个构建目录并打开

```
mkdir build
cd build
```

运行cmake命令来配置

```
cmake .. -G "MinGW Makefiles"
```



