# AI 编码指南：为 AI 提供清晰的开发蓝图

为了让 AI 产品经理助手能够更准确、高效地生成符合预期的代码，我们需要为其提供一系列清晰、结构化的文档作为输入。以下是推荐的 6 类核心文档：

## 1. PRD (产品需求文档 - Project Requirements Document)

这是项目的基础，设定了整体基调。PRD 应该清晰地传达产品的核心目标和范围。

**包含内容:**
*   **应用概述 (App Overview):** 产品是什么，解决什么问题，核心价值是什么？
*   **用户流程 (User Flows):** 描述用户如何与产品交互以完成关键任务。可以使用流程图或文字描述。
*   **技术栈与 API (Tech Stack & APIs):** 初步规划或确定的技术选型（语言、框架、数据库等）以及依赖的第三方 API。
*   **核心功能 (Core Features):** 列出产品必须具备的关键功能点。
*   **范围定义 (In-scope vs Out-of-scope Items):** 明确哪些功能或需求包含在当前版本/阶段，哪些不包含，避免范围蔓延。

**目的:** 为 AI 提供项目的高层理解，明确"做什么"和"为什么做"。

## 2. 应用流程文档 (App Flow Doc)

这是应用的"地图"，需要极度清晰和具体，以指导 AI 理解页面间的导航和交互逻辑。

**关键要求:**
*   **描述每一页 (Describe every page):** 清晰说明应用中的每一个主要页面或视图。
*   **页面跳转逻辑 (How users move):** 详细描述用户如何从一个页面导航到另一个页面，触发条件是什么（点击按钮、完成操作等）。
*   **使用简单语言 (Simple language):** 避免使用模糊或技术性过强的术语。
*   **具体明确 (Be painfully specific):** 不要留有歧义，AI 容易对模糊描述感到困惑。避免使用项目符号，尽量用连贯的语句描述流程。

**目的:** 让 AI 精确理解用户在应用中的完整路径和交互方式。

## 3. 技术栈文档 (Tech Stack Doc)

明确告知 AI 需要使用的具体技术工具和资源。

**列出内容:**
*   **所有包和依赖 (All packages & dependencies):** 列出项目将使用的所有库、框架和外部依赖项，最好包含版本号。
*   **API 文档链接 (Links to API docs):** 提供所有需要集成的内部或第三方 API 的文档链接。
*   **偏好的库或工具 (Preferred libraries or tools):** 指明特定的技术选择，例如后端服务 (Supabase, Firebase)、支付集成 (Stripe)、认证方案 (NextAuth) 等。

**目的:** 约束 AI 的技术选择，确保使用符合项目要求的、统一的技术栈，避免其"即兴创作"。

## 4. 前端规范 (Frontend Guidelines)

定义应用的视觉和交互风格，确保 AI 生成的前端代码符合设计要求。

**包含内容:**
*   **字体 (Fonts):** 使用的字体名称、字重、大小规则。
*   **颜色面板 (Color palette):** 主要颜色、次要颜色、状态颜色（成功、错误、警告等）及其色值。
*   **间距与布局规则 (Spacing & layout rules):** 组件间距、网格系统、布局原则等。
*   **偏好的 UI 库或框架 (Preferred UI library or framework):** 例如 Material UI, Ant Design, Tailwind CSS 等。
*   **图标集 (Icon set):** 使用的图标库及其规范。

**目的:** 指导 AI 生成视觉一致、符合设计规范的前端界面。

## 5. 后端结构文档 (Backend Structure Doc)

详细说明后端的数据存储、业务逻辑和规则，对于使用 BaaS (如 Supabase, Firebase) 或自建后端都非常重要。

**告知 AI:**
*   **数据库模式 (DB schema):** 数据表的结构、字段、类型、关系等。
*   **认证逻辑 (Auth logic):** 用户注册、登录、权限控制等流程和规则。
*   **存储规则 (Storage rules):** 文件（如用户头像、上传内容）的存储方式和访问权限。
*   **任何边缘情况 (Any edge cases):** 需要特殊处理的业务逻辑或数据规则。

**目的:** 让 AI 能够编写正确的后端逻辑（包括数据库操作如 SQL），处理数据持久化和业务规则。

## 6. 实施计划 (Implementation Plan)

这是对抗 AI "幻觉"的有力武器，将高层需求分解为具体、可执行的步骤列表。

**关键要求:**
*   **分解任务 (Break down tasks):** 将大的功能或模块分解成至少 50 个以上（根据项目复杂度调整）非常具体的小步骤。
*   **明确步骤 (Specific steps):** 每个步骤都应描述一个清晰、单一的操作，就像你自己在手动编码时会执行的那样。例如："创建用户登录表单组件"、"实现邮箱格式验证逻辑"、"添加登录按钮点击事件处理函数"、"调用后端登录 API"等。
*   **顺序逻辑 (Sequential logic):** 步骤之间最好能体现一定的实现顺序或依赖关系。

**目的:** 为 AI 提供一份详细的"操作指南"，使其能够按部就班地执行任务，而不是基于模糊的需求进行猜测，从而大大提高代码生成的稳定性和准确性。

---

通过准备和维护这六类文档，我们可以极大地提升与 AI 协作开发产品的效率和质量。 