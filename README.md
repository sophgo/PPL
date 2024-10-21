# PPL

# 目录
  - [介绍](#介绍)
  - [快速开始](#快速开始)

# 介绍

PPL 是基于 c/c++ 语法扩展的、针对 TPU 编程的专用编程语言(DSL)。开发者可以通过 PPL 编写在设备（TPU）上运行的自定义算子。PPL 代码经过编译后，会生成在能在 TPU 上运行的 c 代码。用户可以将 PPL 生成的代码编译成 so，在主机的应用中利用 runtime 的动态加载接口进行调用，实现利用 TPU 加速计算的目的。

PPL 已支持编程的算能芯片列表如下：
| Chip     |
|:-        |
| BM1684X  |
| BM1688   | 
| BM1690   | 

# 快速开始

选择 release 分支的 Tags 下载 PPL 开发包。

下面是 PPL 开发包的目录结构：

``` shell
    ├── bin/
    │   ├── ppl-compile     # PPL 编译工具：将 ppl 的 host 代码转换成 device 代码
    ├── doc/
    │   ├── PPL快速入门指南.pdf
    │   └── PPL开发参考手册.pdf
    ├── docker/             # PPL 项目镜像生成脚本目录
    │   ├── Dockerfile      # PPL 编译环境的 Dockerfile
    │   └── build.sh        # Dockerfile 的编译脚本
    ├── envsetup.sh         # 环境初始化脚本，设定环境变量
    ├── examples/           # PPL 代码示例
    ├── inc/                # PPL 代码依赖的头文件
    ├── python/             # 使用 python 开发的辅助工具
    ├── runtime/            # 运行时库以及 ppl 生成代码依赖的辅助函数和脚本
    │   ├── bm1684x/        # bm1684x runtime 库
    │   │   ├── lib/        # device 代码依赖的库
    │   │   ├── libsophon/  # device 代码依赖的头文件和库
    │   │   └── TPU1686/    # device 代码依赖的头文件
    │   ├── bm1688/         # bm1688 runtime 库
    │   │   ├── lib/        # device 代码依赖的库
    │   │   ├── libsophon/  # device 代码依赖的头文件和库
    │   │   └── TPU1686/    # device 代码依赖的头文件
    │   ├── bm1690/         # bm1690 runtime 库
    │   │   ├── lib/        # device 代码依赖的库
    │   │   ├── TPU1686/    # device 代码依赖的头文件
    │   │   └── tpuv7-emulator/   # device 代码依赖的头文件和库
    │   ├── sg2380/         # sg2380 runtime 库
    │   │   ├── include/    # device 代码依赖的头文件
    │   │   ├── qemu/       # device 代码依赖的头文件和库
    │   │   ├── samples/    # device 代码依赖的链接配置文件
    │   │   ├── scripts/    # ppl 提供的代码运行脚本文件
    │   │   ├── sifive_x280mc8/   # device 代码依赖的库
    │   │   └── TPU1686/    # device 代码依赖的库
    │   ├── customize/      # ppl 提供的 device、host 端辅助函数
    │   ├── kernel/         # device 代码依赖的头文件
    │   └── scripts/        # ppl 提供的 cmake 模块文件
    └── samples/            # samples
```

具体开发细节和快速入门可参考 doc/ 目录下的 《PPL快速入门指南.pdf》 和 《PPL开发参考手册.pdf》。
