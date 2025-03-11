# gcsj

## 项目库组织结构说明

### 核心目录
- `core/` - AT32F407开发板启动文件
  - `startup_at32f403a_407.s` - 处理器启动汇编代码
    - 包含中断向量表
    - 系统初始化代码
    - 复位处理程序
    - 异常和中断处理程序

### 硬件相关目录
- `device/` - AT32F407设备相关代码
  - `at32f403a_407_board.c` - 开发板底层驱动实现
  - `at32f403a_407_clock.c` - 时钟配置和管理
  - `at32f403a_407_int.c` - 中断处理函数
  - `system_at32f403a_407.c` - 系统初始化和配置

- `drivers/` - AT32F407驱动程序
  - 基础外设驱动：
    - `at32f403a_407_gpio.c` - GPIO通用输入输出
    - `at32f403a_407_dma.c` - DMA直接内存访问
    - `at32f403a_407_crm.c` - 时钟重置管理
    - `at32f403a_407_misc.c` - 杂项功能
  
  - 通信接口驱动：
    - `at32f403a_407_usart.c` - 串口通信
    - `at32f403a_407_spi.c` - SPI接口
    - `at32f403a_407_i2c.c` - I2C接口
    - `at32f403a_407_can.c` - CAN通信
    - `at32f403a_407_emac.c` - 以太网MAC
    - `at32f403a_407_usb.c` - USB接口
    - `at32f403a_407_sdio.c` - SD卡接口

  - 模拟和数字转换：
    - `at32f403a_407_adc.c` - 模数转换
    - `at32f403a_407_dac.c` - 数模转换

  - 定时器和时钟：
    - `at32f403a_407_tmr.c` - 定时器
    - `at32f403a_407_rtc.c` - 实时时钟
    - `at32f403a_407_wdt.c` - 看门狗定时器
    - `at32f403a_407_wwdt.c` - 窗口看门狗

  - 存储和调试：
    - `at32f403a_407_flash.c` - Flash存储器
    - `at32f403a_407_xmc.c` - 外部存储控制器
    - `at32f403a_407_debug.c` - 调试接口
    - `at32f403a_407_bpr.c` - 备份寄存器

  - 其他功能：
    - `at32f403a_407_acc.c` - 自动时钟校准
    - `at32f403a_407_pwc.c` - 电源控制
    - `at32f403a_407_exint.c` - 外部中断
    - `at32f403a_407_crc.c` - CRC校验

### 系统目录
- `include/` - 头文件目录
  - `core/` - ARM Cortex-M4核心头文件
    - `core_cm4.h` - Cortex-M4核心功能定义
    - CMSIS相关头文件：
      - `cmsis_compiler.h` - CMSIS编译器通用定义
      - `cmsis_gcc.h` - GCC编译器特定定义
      - `cmsis_armcc.h` - ARMCC编译器特定定义
      - `cmsis_armclang.h` - ARM Clang编译器定义
    - ARM数学库头文件：
      - `arm_math.h` - DSP数学库主头文件
      - `arm_math_types.h` - 数学库类型定义
      - `arm_vec_math.h` - 向量数学运算
    - MPU和PMU相关：
      - `mpu_armv7.h` - ARMv7内存保护单元
      - `mpu_armv8.h` - ARMv8内存保护单元
      - `pmu_armv8.h` - ARMv8性能监控单元

  - `device/` - AT32F407设备特定头文件
  - `drivers/` - 外设驱动头文件
  - AT32F407硬件抽象层(HAL)头文件
  - 用户应用头文件
  - 配置头文件

- `user/` - 用户应用代码
  - `main.c` - 程序入口文件
    - 系统初始化
    - 主程序循环
    - 用户应用逻辑

### 编译输出目录
- `Listings/` - 编译生成的列表文件
  - 汇编列表
  - 链接映射文件
  
- `Objects/` - 编译生成的目标文件
  - 目标文件(.o)
  - 可执行文件(.hex/.bin)

### 生成的其他文件
- `gcsj.uvprojx` - Keil MDK项目主文件，定义了项目配置和编译选项
- `gcsj.uvoptx` - Keil MDK调试和优化配置
- `gcsj.uvguix.<username>` - Keil MDK用户界面布局配置

