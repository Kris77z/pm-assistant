# PRD 工具 设计方案

## 1. 核心理念：AI驱动的智能PRD协作助手

本工具的核心目标是：**将团队现有的、标准的PRD模板工作流产品化，并深度融合AI能力，打造一个从需求分析到文档生成的智能协作伙伴**。

AI的角色不仅仅是"助理"，更是"副驾驶"，在关键环节（如用户分析、竞品研究、方案设计）提供洞察和建议，帮助产品经理提升工作深度和效率。

## 2. 核心工作流：AI增强的五步法

我们将整个PRD撰写过程定义为五个核心阶段，每个阶段都有AI能力的深度参与。

### 阶段一：需求定义 (卡片1)
- **用户操作**: 输入`所属业务线`和`需求介绍`。
- **AI能力**: 这是整个工作流的起点，为后续所有AI分析提供核心上下文。

### 阶段二：用户洞察与目标确立 (卡片2)
- **AI能力 (扩展用户场景)**: 基于第一步的输入，AI自动分析并生成多个`用户使用场景`，每个场景包含`用户类型`、`具体场景`和`痛点`。
- **用户决策**: 产品经理根据AI生成的场景，手动提炼和撰写`需求目标`，明确本次迭代的焦点。

### 阶段三：市场与竞品分析 (卡片3)
- **AI能力 (竞品分析)**: AI结合`需求介绍`和已确立的`需求目标`，主动联网搜索，提供一份深度竞品分析报告，内容包括：
    - **竞品列表**: 识别市场上的主要竞争者。
    - **功能对标**: 分析竞品如何实现相似功能。
    - **优劣势评估**: 总结每个竞品方案的优缺点。
    - **机会点挖掘**: 结合我方产品背景，提出可借鉴的`机会点`。

### 阶段四：AI辅助方案设计 (卡片4)
- **用户主导**: 产品经理基于机会点，开始拆解和撰写`需求方案`。
- **AI能力 (智能副驾驶)**: 在用户撰写过程中，AI提供"建议"和"补全"能力：
    - **辅助拆解**: 针对一个高阶需求，AI建议更细化的`功能点/流程`。
    - **补充规则**: AI根据功能点，主动建议相关的`业务逻辑`、`数据需求`和`校验规则`。
    - **预想边缘**: AI主动提示需要考虑的`特殊状态`和`边缘处理`场景，帮助查漏补缺。

### 阶段五：AI审查与文档生成
- **AI能力 (内容审查)**: 在用户完成所有内容后，AI会对PRD进行一次全面"体检"，从逻辑完整性、方案可行性、内容清晰度等维度进行评估，给出`评分`和`优化建议`。
- **用户决策**: 产品经理可根据AI的建议，选择性地对内容进行完善。
- **AI能力 (一键生成)**: 最终，AI将所有结构化信息整合，生成一份专业、格式精美、语言润色的完整PRD（Markdown格式）。AI会自动处理排版、生成摘要、并将部分内容（如竞品分析）格式化为表格。

---

## 3. 已有功能与实现 (V1)

*此部分记录了已完成的基础版本功能，作为新方案的基石。*

- ✅ **卡片式界面**: 每个章节对应一个可展开的卡片，引导用户分步完成。
- ✅ **五个核心章节**:
    - **【1. 需求介绍】**: 业务线选择、团队成员、需求介绍、变更记录管理。
    - **【2. 需求分析】**: 用户场景动态管理、需求目标。
    - **【3. 竞品分析】**: AI竞品分析功能。
    - **【4. 需求方案】**: 详细的方案设计表单，包括优先级选择。
    - **【5. 其余事项】**: 文档链接、功能迭代历史管理。
- ✅ **动态表单**: 支持动态添加/删除记录（变更记录、用户场景、迭代历史）。
- ✅ **基础AI生成**: 支持将表单内容拼接为Markdown文档。
- ✅ **导出功能**: 支持复制和下载Markdown格式文档。
- ✅ **技术实现**: 基于`ExpandableCard`、`Stepper`等现有UI组件，拥有完整的TypeScript类型定义和状态管理逻辑。
