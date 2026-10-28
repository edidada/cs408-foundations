# 外部代码仓库（git submodule）

本目录下的子目录都是 **submodule 引用的外部仓库**，不是本仓库自己写的代码。目的是用成熟的开源实验来验证你的理解，而不把大段代码塞进主仓库。

## 子模块清单

| 本地路径 | 上游仓库 | 适合哪门课 | 重点看什么 |
|----------|----------|------------|------------|
| external/csapp-labs | github.com/lorendw7/CSAPP-Labs | 组成原理 / 操作系统 | 05-cache-lab（Cache 模拟器 + 矩阵转置优化）、06-shell-lab（Unix shell）、07-malloc-lab（动态内存分配器） |
| external/408-ds-os-code | github.com/Skybluebluede/408-DataStructure-and-OperatingSystem | 数据结构 / 操作系统 | 数据结构各种实现 + 真题代码、操作系统相关代码 |
| external/os-producer-consumer | github.com/Kojavoh/OS-Lab-1 | 操作系统 | pthread + 信号量实现的生产者-消费者（含共享内存），对应 PV 操作实验 |

## 使用方法

克隆本仓库后拉取子模块：

    git submodule update --init --recursive

更新子模块到上游最新：

    git submodule update --remote

> 这些仓库由上游维护，内容可能随时变化；本计划只引用，不修改。若某个仓库失效，直接删掉对应 .gitmodules 条目与目录即可。
