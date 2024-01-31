# STM32F103C8T6-VSCode
[![License](https://img.shields.io/badge/license-MPL%202.0-brightgreen?style=flat-square)](https://mozilla.org/MPL/2.0) [![Pull Requests](https://img.shields.io/github/issues-pr-closed/katorlys/STM32F103C8T6-VSCode?style=flat-square)](https://github.com/katorlys/STM32F103C8T6-VSCode/pulls) [![Issues](https://img.shields.io/github/issues-closed/katorlys/STM32F103C8T6-VSCode?style=flat-square)](https://github.com/katorlys/STM32F103C8T6-VSCode/issues) [![Lines](https://img.shields.io/tokei/lines/github/katorlys/STM32F103C8T6-VSCode?style=flat-square)](https://github.com/katorlys/STM32F103C8T6-VSCode)

## 简介
可直接在 Visual Studio Code 中使用的 STM32F103C8T6 项目工程模板。  

环境配置教程：https://blog.katorly.work/STM32-VSCode-with-Keil-Studio  

**库类型:** STM32标准库  
**平台:** Keil Studio  
**调试器:** ST-Link  

*注: 启动文件存放在电脑的个人用户文件夹内，所有项目共用同一份启动文件。其由 CMSIS 的 Software Components 生成和管理，因此若要将项目迁移到 Keil MDK 5及以下的 IDE，需要添加 Keil MDK 5 及以下专用的启动文件，否则无法编译通过。*  


## 使用方法
1. 复制`Project`文件夹 (路径不能有中文)
2. 用 VSCode 打开
3. 新建文件、修改文件名、删除文件时, 要在`Project.cproject.yml`里的`project.groups.files`处一个个地手动添加文件, 如下例子所示:
```yml
groups:
    - group: Source Files
      files:
        - file: ./main.c
        - file: ./System/Delay.c
        - file: ./System/Delay.h
```
4. 在侧栏的`CMSIS`中点击`Build`或`Build (clean)`Build即可在`out/Project/STM32F103C8/`文件夹中获取到编译后的文件 (目前仅支持`.axf`)
5. 点击`Run`即可把编译后的文件通过ST-LINK下载到STM32中, 若此前未构建则需先点击`Build`, 先构建再下载
6. 点击`Debug`即可开始调试, 与 Keil MDK 一样
7. 发送项目文件给别人时, 可以把`out`和`tmp`文件夹删除, 其它文件则不能删除

