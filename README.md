# PenguinVision

## 介绍
小企鹅的视觉系统PV

## 相关文件
[视觉系统概述.md](/Description/视觉系统概述.md)

## 一些问题
1. 如果串口没有使用权限，先输入开启串口权限
    ```
    sudo chmod 777 /dev/ttyACM0
    ```
2. 如果遇到串口中没有`/dev/ttyACM0`，但是有`/dev/ttyACM1`等串口，则是ubuntu自动分配串口号的问题，参照[配置udev规则](https://gitee.com/SMBU-POLARBEAR/knowledge_base/blob/master/%E5%85%B3%E4%BA%8EUbuntu%E7%9A%84%E4%B8%80%E4%BA%9B%E6%93%8D%E4%BD%9C.md#%E9%85%8D%E7%BD%AEudev%E8%A7%84%E5%88%99)配置udev即可解决问题