![test](https://img.shields.io/badge/test-passing-green.svg)
![docs](https://img.shields.io/badge/docs-passing-green.svg)
![platform](https://img.shields.io/badge/platform-Quartus|Vivado-blue.svg)

[English version README](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/README_en.md)

FPGA SDcard File Reader
===========================
**基于 FPGA 的 SD卡文件读取器**

* **基本功能** ：FPGA作为 **SD-host** ， 指定文件名 **读取文件内容** ；或指定扇区号 **读取扇区内容**。
* **性能** : 使用 **SD总线** 实现，而不是 **SPI总线** 。 读取速度更快。
* **兼容性强** : 自动适配 **SD卡版本** ，自动适配 **FAT16/FAT32文件系统**。
* **RTL实现** ：完全使用 **SystemVerilog**  ,便于移植和仿真。

|                      |  SDv1.1 card       |  SDv2 card          | SDHCv2 card        |
| :-----               | :------------:     |   :------------:    | :------------:     |
| **读取扇区**         | :heavy_check_mark: |  :heavy_check_mark: | :heavy_check_mark: |
| **读取文件 (FAT16)** | :heavy_check_mark: |  :heavy_check_mark: | :heavy_check_mark: |
| **读取文件 (FAT32)** | :heavy_check_mark: |  :heavy_check_mark: | :heavy_check_mark: |




# 核心代码

详见 [RTL目录](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/RTL/) ，它包含**本库的核心代码** ， 可以被用户调用，实现二次开发。



# Xilinx FPGA 示例

以下示例基于 [Nexys4-DDR 开发板](http://www.digilent.com.cn/products/product-nexys-4-ddr-artix-7-fpga-trainer-board.html) (Xilinx Artix-7)。

* [读取文件示例](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/Nexys4-ReadFile/) : 读取SD卡中的文件，通过串口打印文件内容
* [读取扇区示例](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/Nexys4-ReadSector/) : 读取SD卡中的扇区，通过串口打印扇区内容



# Altera FPGA 示例

以下示例基于 [**DE0-CV 开发板**](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=163&No=921) (Altera Cyclone V)。

* [读取文件示例](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/DE0-CV-ReadFile/) : 读取SD卡中的文件，通过VGA屏幕显示文件内容
* [读取扇区示例](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/DE0-CV-ReadSector/) : 读取SD卡中的扇区

| ![读取文件后显示在VGA](https://github.com/WangXuan95/FPGA-SDcard-Reader/blob/master/images/screen.jpg) |
| :------: |
| 图：FPGA 读取文件后显示在 VGA 上 |


# 相关链接

* [FPGA SD卡读取器 (SPI版本)](https://github.com/WangXuan95/FPGA-SDcard-Reader-SPI/) : 与该库功能相同，但使用 **SPI总线**。

* [FPGA SD卡模拟器](https://github.com/WangXuan95/FPGA-SDcard-Simulator/) : FPGA模仿SD卡行为，实现FPGA 模拟 **SDHC v2 ROM卡**
