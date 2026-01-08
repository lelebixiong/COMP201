# COMP201 复习大纲 & 速查笔记 📚

<p align="center">
  <img src="https://img.shields.io/badge/course-COMP201-blue" />
  <img src="https://img.shields.io/badge/topic-Software%20Engineering-informational" />
  <img src="https://img.shields.io/badge/focus-Requirements%20%7C%20UML%20%7C%20Testing%20%7C%20PM-success" />
  <img src="https://img.shields.io/badge/type-Revision%20Outline-lightgrey" />
</p>

> 本仓库整理了 COMP201（Software Engineering）核心讲义知识点，覆盖：软件过程、需求工程、系统建模、UML、V&V、测试、项目管理、成本估算等。  
> 内容整理自个人复习大纲文档（见来源说明）。  

---

## 目录
- [如何使用](#如何使用)
- [快速速查](#快速速查)
  - [需求类型：FR / NFR / Domain](#需求类型fr--nfr--domain)
  - [Include vs Extend（用例题必考）](#include-vs-extend用例题必考)
  - [V&V：Verification vs Validation](#vvverification-vs-validation)
  - [测试：Black-box vs White-box](#测试black-box-vs-white-box)
  - [圈复杂度 Cyclomatic Complexity](#圈复杂度-cyclomatic-complexity)
  - [PERT / Critical Path / Slack](#pert--critical-path--slack)
  - [成本估算 5 种方法](#成本估算-5-种方法)
- [按 Lecture 整理](#按-lecture-整理)
  - [Lecture 2：Software Process & Lifecycle](#lecture-2software-process--lifecycle)
  - [Lecture 3：Design & Implementation](#lecture-3design--implementation)
  - [Lecture 4：Requirements（FR/NFR/Domain）](#lecture-4requirementsfrnfrdomain)
  - [Lecture 5：Use Cases](#lecture-5use-cases)
  - [Lecture 7/8：Requirements Engineering + Security](#lecture-78requirements-engineering--security)
  - [Lecture 9：System Models](#lecture-9system-models)
  - [Lecture 10：FSM & Petri Nets](#lecture-10fsm--petri-nets)
  - [Lecture 11/12：Petri Nets（扩展概念）](#lecture-1112petri-nets扩展概念)
  - [Lecture 13：Design Methodology & Modularity](#lecture-13design-methodology--modularity)
  - [Lecture 14：Interfaces / Encapsulation / Cohesion](#lecture-14interfaces--encapsulation--cohesion)
  - [Lecture 15：Architectural Design](#lecture-15architectural-design)
  - [Lecture 16：Distributed / Layered / C-S](#lecture-16distributed--layered--c-s)
  - [Lecture 17：OO 基础（State/Behavior/Identity）](#lecture-17oo-基础statebehavioridentity)
  - [Lecture 20：Class Diagram 规则 + 名词法](#lecture-20class-diagram-规则--名词法)
  - [Lecture 21：Aggregation / Composition / OCL](#lecture-21aggregation--composition--ocl)
  - [Lecture 22：Interaction（Sequence / Collaboration）](#lecture-22interactionsequence--collaboration)
  - [Lecture 23：V&V](#lecture-23vv)
  - [Lecture 24：Testing（黑盒/白盒/分区/边界）](#lecture-24testing黑盒白盒分区边界)
  - [Lecture 25：Integration Testing & Stubs](#lecture-25integration-testing--stubs)
  - [Lecture 26：Project Management（PERT/风险）](#lecture-26project-managementpert风险)
  - [Lecture 27：Cost Estimation](#lecture-27cost-estimation)
- [来源与声明](#来源与声明)

---

## 如何使用
1. **考前冲刺**：先看「快速速查」，把高频概念记牢（include/extend、FR/NFR、V&V、圈复杂度、PERT）。
2. **刷题定位**：题目问到哪块，直接在目录里跳到对应 Lecture。
3. **写题模板化**：把“定义 + 判别规则 + 例子”固定成回答结构，减少失误。

---

## 快速速查

### 需求类型：FR / NFR / Domain
- **Functional Requirements（功能需求）**：系统提供什么服务、对输入如何反应、在场景中如何行为。
- **Non-functional Requirements（非功能需求）**：性能/可靠性/安全/标准/流程/法律等（可能比 FR 更关键）。
  - Product（速度/可靠性/安全）
  - Organisational（必须用 Java、必须遵循组织流程）
  - External（法律/标准/互操作/兼容性）
- **Domain Requirements（领域需求）**：来自银行/医疗等领域规则或法规，可能既是 FR 也可能是 NFR。

### Include vs Extend（用例题必考）
- `<<include>>`：**总是发生**、主用例必做的一部分（“必经步骤”）。
- `<<extend>>`：**有条件才发生**、可选/异常/分支流程（“某些情况才触发”）。
- 箭头方向也不同：**include 指向被包含用例**；**extend 从扩展用例指向被扩展用例**。

### V&V：Verification vs Validation
- **Verification（验证）**：把产品做对——符合 specification（含 FR/NFR）。
- **Validation（确认）**：做对的产品——满足用户真正想要的需求（spec 不一定等于用户想要）。

### 测试：Black-box vs White-box
- **Black-box（黑盒）**：不看源码，按规格说明测试输入输出；常用 **等价类分区 + 边界值**。
- **White-box / Structural（白盒）**：看结构/控制流，追求 statement/branch/path/loop 覆盖。

### 圈复杂度 Cyclomatic Complexity
- 用途：估算路径数/测试工作量。
- 公式（流图）：`CC = E - N + 2`  
- 快速法：`CC = 决策点数量 + 1`（if/while/for 等条件节点）

### PERT / Critical Path / Slack
- **Critical path（关键路径）**：项目最短完成时间 = **最长路径长度**。
- **Early Start/End**：在依赖满足条件下最早能开始/结束。
- **Late Start/End**：不影响最终 deadline 的最晚开始/结束。
- **Slack**：`LS - ES = LE - EE`，Slack=0 表示关键任务（critical）。

### 成本估算 5 种方法
1. Algorithmic cost modelling（基于历史数据/规模模型）
2. Expert judgement（专家共识）
3. Estimation by analogy（类比估算）
4. Parkinson’s law（成本=可用资源，容易“做不完”）
5. Pricing to win（为了拿合同定价，风险是范围/质量受损）

---

## 按 Lecture 整理

### Lecture 2：Software Process & Lifecycle
- 通用过程：specifying / designing / implementing / testing
- Waterfall：需求→设计→实现与单测→集成与系统测→运行维护  
  缺点：阶段划分死板（inflexible partition）
- Evolutionary：先 initial implementation 给用户用，再迭代改进  
  缺点：过程可见性差、系统结构可能变差
- Agile / Scrum：增量交付；sprint 内需求冻结；先写测试再写代码（XP 思路）

### Lecture 3：Design & Implementation
- 架构设计→抽象规格说明→接口设计→组件/数据结构/算法设计
- 两极思路：data-driven vs responsibility-driven
- 测试层级：Unit → Module → Sub-system → System → Acceptance

### Lecture 4：Requirements（FR/NFR/Domain）
- User req / System req / Software specification：面向对象不同，表达粒度不同
- NFR 三类：Product / Organisational / External
- Goals vs Verifiable NFR：目标要落成可测试指标（客观可验证）

### Lecture 5：Use Cases
- Use case 要写 alternative cases（异常/分支）
- Actor inheritance：actor 也能继承
- include/extend：见速查区（重点：**用例描述外部行为，不写内部实现**）

### Lecture 7/8：Requirements Engineering + Security
- RE 流程：elicitation → analysis → validation → management
- 可行性：技术/经济/法律/进度
- Viewpoints：用不同相关方视角组织需求
- 安全 4+1：C/I/A/N + Availability
- Bell–LaPadula：no read-up；no write-down；trusted subjects
- 需求检查：Validity/Consistency/Completeness/Realism/Verifiability
- Cucumber/Gherkin：Feature/Scenario，把需求落到可执行测试

### Lecture 9：System Models
- System models：把需求抽象成图形模型（沟通桥梁）
- 视角：external / behavioural / structural
- Context model：系统边界
- Statechart：状态、转换、guard、do:、复合状态等

### Lecture 10：FSM & Petri Nets
- FSM：Mealy / Moore；NFA（非确定性）
- Petri net：places/transitions/arcs/tokens；marking=token 分布  
  enabled 条件：输入 place token ≥ arc weight  
  适合分布式/并发（非确定性）

### Lecture 11/12：Petri Nets（扩展概念）
- 高层 Petri 网：colour / time / hierarchy
- transition active；place/token passive
- reachable state、deadlock state 定义要会用

### Lecture 13：Design Methodology & Modularity
- 设计阶段可重叠：理解问题→方案→评估→描述→迭代细化
- 系统=模块交互；模块要 robust/coherent/autonomous
- 模块化标准：decomposability / composability / understandability / continuity / protection
- Repository model vs message passing

### Lecture 14：Interfaces / Encapsulation / Cohesion
- 接口：对外承诺“做什么”，不暴露“怎么做”
- Encapsulation：能 private 就 private
- Cohesion 等级：coincidental → … → functional/object cohesion
- 目标：High cohesion + Low coupling

### Lecture 15：Architectural Design
- 结构划分 + 控制建模 + 模块分解
- Client-server、集中控制、事件驱动（广播/中断驱动）
- Pipe-and-filter 适合功能变换，不适合强交互系统

### Lecture 16：Distributed / Layered / C-S
- 系统类型：personal / embedded / distributed
- 三层：presentation / application processing / data management
- Thin vs Fat client；3-tier 可部署到不同机器

### Lecture 17：OO 基础（State/Behavior/Identity）
- 对象三要素：state / behavior / identity
- 接口：public vs private interface
- 继承有耦合风险；常见建议：composition over inheritance
- 多态 & 动态绑定（运行时决定调用）

### Lecture 20：Class Diagram 规则 + 名词法
- 类命名：单数名词，不用动词
- 关联判别：需要引用/接触就有关联
- 可见性：`+ public`、`- private`、`# protected`
- operation signature：方法名(参数:类型):返回类型
- generalization vs inheritance：建模关系 vs 实现关系

### Lecture 21：Aggregation / Composition / OCL
- aggregation（空心菱形）概念整体-部分
- composition（实心菱形）强拥有：整体没了部分也没意义（整体端 multiplicity 常为 1/0..1）
- derived association、qualified association
- constraint / OCL；xor 互斥约束
- association class、interface、abstract class

### Lecture 22：Interaction（Sequence / Collaboration）
- sequence：实线消息、虚线返回；可标 timing constraints
- collaboration：对象+链接+消息编号
- self-message、子协作（隐藏细节）
- 创建/销毁标注（{new}/{destroyed}）

### Lecture 23：V&V
- 目标：建立“置信度”，不是保证无缺陷
- verification：静态 inspection + 动态 testing（互补）
- regression test：修复后用旧数据回归
- testing ≠ debugging：测试找缺陷存在；调试定位与修复

### Lecture 24：Testing（黑盒/白盒/分区/边界）
- 缺陷测试：成功=让程序出现异常行为
- 测试层次：component / integration（黑盒为主，难点是定位）
- 黑盒：等价类分区 + 边界值（边界最易错）
- 白盒：statement/loop/path；flow graph；CC 计算

### Lecture 25：Integration Testing & Stubs
- 回归测试：每加模块都要跑旧测（或用 test harness 自动化）
- Top-down：用 stubs 补底层；利于架构验证/早演示
- Bottom-up：更易写测试；适合 OO/实时/性能敏感
- Interface testing：集成阶段重点

### Lecture 26：Project Management（PERT/风险）
- 计划类型：quality / validation / configuration / maintenance / staff development
- Milestones vs Deliverables
- 排期：任务拆分、并行、减少依赖、留缓冲
- 风险管理：识别→分析→计划→监控（project/product/business）

### Lecture 27：Cost Estimation
- cost vs price；人力成本是大头（含 overheads）
- 生产率度量：LOC / function points / object points（各有坑）
- “项目会被预算塑形”：先定预算再缩范围很常见
- 估算方法：见速查区（5 种），建议多方法交叉验证

---

## 来源与声明
- 本仓库内容整理自个人复习大纲文档：`COMP201 复习大纲.docx` :contentReference[oaicite:1]{index=1}  
- 仅用于学习与复习交流；如需引用课程官方表述，请以课程讲义/课堂材料为准。
