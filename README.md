# CS408 底层功底补齐计划（有 10 年 CRUD 经验的实践路线）

> 定位：你不是考研，而是**借 408 的考纲和真题，系统性地把计算机底层功底补齐**。
> 核心信条：408 考的是「懂原理」，而你 10 年 CRUD 经验带来的是「会用」——本计划就是要填平这道鸿沟。
> 检验标准：学完一门课后，能不能**不看书画出知识框架图**，并给同样有开发经验但没学过的人**讲明白关键原理**。能，就算补上了。

---

## 先认清处境：壁垒 vs 舒适区

**舒适区（快速过）**：C 语言基础语法、基本编程逻辑、简单算法实现。

**真正的壁垒**：

- 计算机组成原理：对 CPU、Cache、流水线、指令系统几乎无感知——最大短板
- 操作系统底层机制：PV 操作、页表映射、inode 结构未必系统学过
- 数据结构手动模拟：会调库，但未必能手推 B+ 树分裂、图的非递归 DFS
- 网络分层细节：TCP 拥塞控制状态机、IP 子网划分计算需专门练

---

## 学习路线总览（按你的目标重新排序）

| 阶段 | 科目 | 周期 | 定位 |
|------|------|------|------|
| 阶段一 | 数据结构 | 3–4 周 | 用「手写代码」检验，不靠「感觉」 |
| 阶段二 | 计算机组成原理 | 6–8 周 | **主战场**，慢慢啃 |
| 阶段三 | 操作系统 | 4–5 周 | 用工程经验反推原理 |
| 阶段四 | 计算机网络 | 3–4 周 | 记忆 + 计算，细节最容易丢分 |
| | **总计** | **约 4–5 个月** | 组成原理卡住允许延长，不赶进度 |

> 调整原因：组成原理是你最大短板，需要最长时间消化，所以提前。

---

## 资料清单（精简，不囤积）

| 类别 | 推荐 |
|------|------|
| 教材 | 严蔚敏《数据结构》、唐朔飞《组成原理》、汤小丹《操作系统》、谢希仁《计算机网络》 |
| 辅导书 | 王道四本辅导书（408 事实标准） |
| 真题 | 王道历年真题（近 10 年）——核心检验工具，不考研也要做 |
| 视频 | 王道全程班（选看；组成原理和 PV 操作建议完整看） |

---

## 目录索引（每科 5 个维度）

每个科目文件夹下都有 5 个文件：**学习计划 / 知识点 / 重难点 / 实践规划 / 检测**。实践规划里的代码实验统一放在 external/ 下的 submodule 仓库中（见下方「外部代码仓库」），不污染主仓库。

- 数据结构 datastructure/
  - [学习计划](./datastructure/学习计划.md)
  - [知识点](./datastructure/知识点.md)
  - [重难点](./datastructure/重难点.md)
  - [实践规划](./datastructure/实践规划.md)
  - [检测](./datastructure/检测.md)
- 计算机组成原理 computer-organization/
  - [学习计划](./computer-organization/学习计划.md)
  - [知识点](./computer-organization/知识点.md)
  - [重难点](./computer-organization/重难点.md)
  - [实践规划](./computer-organization/实践规划.md)
  - [检测](./computer-organization/检测.md)
- 操作系统 operating-system/
  - [学习计划](./operating-system/学习计划.md)
  - [知识点](./operating-system/知识点.md)
  - [重难点](./operating-system/重难点.md)
  - [实践规划](./operating-system/实践规划.md)
  - [检测](./operating-system/检测.md)
- 计算机网络 computer-network/
  - [学习计划](./computer-network/学习计划.md)
  - [知识点](./computer-network/知识点.md)
  - [重难点](./computer-network/重难点.md)
  - [实践规划](./computer-network/实践规划.md)
  - [检测](./computer-network/检测.md)

---

## 全局自测清单

- [ ] 数据结构：手写链表反转/非递归遍历/图DFS-BFS/快排partition；手推 B 树分裂、AVL 旋转、哈希 ASL
- [ ] 组成原理：算补码/IEEE754/溢出；算 Cache 地址划分；讲清指令数据通路与流水线周期
- [ ] 操作系统：默写 PV 伪代码；讲清页表/TLB/缺页流程；说出 inode 内容与文件分配方式
- [ ] 计算机网络：画 TCP 状态机；算拥塞窗口与 CIDR；区分 DNS 递归/迭代、HTTP 状态码

> 每门课的自测细节见对应文件夹的「检测.md」。

---

## 外部代码仓库（git submodule）

代码实验不写进主仓库，而是以 submodule 形式引用成熟的开源实验仓库，便于「借别人的实现验证自己的理解」：

| 路径 | 仓库 | 对应实验 |
|------|------|----------|
| external/csapp-labs | lorendw7/CSAPP-Labs | 组成原理：05-cache-lab（Cache 局部性/模拟器）；操作系统：06-shell-lab、07-malloc-lab |
| external/408-ds-os-code | Skybluebluede/408-DataStructure-and-OperatingSystem | 数据结构 + 操作系统 408 代码实现与真题 |
| external/os-producer-consumer | Kojavoh/OS-Lab-1 | 操作系统：pthread + 信号量生产者-消费者 |

> 克隆本仓库后如需拉取子模块：git submodule update --init --recursive
> 各科目「实践规划.md」末尾都有「代码实验（外部仓库，submodule）」小节，指明用哪个仓库的哪一部分。

## 时间预期与心态

以每周 10–12 小时估算，总计约 4–5 个月。组成原理卡住允许延长，不要赶进度。

> 目标是「补功底」，不是「拿高分」。偏题怪题可以放过，但核心机制必须能自己讲清楚。
