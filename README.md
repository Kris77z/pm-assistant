# PM Assistant - 智能产品需求文档助手

这是一个基于AI的产品需求文档(PRD)智能编写助手，帮助产品经理快速、高效地创建专业的PRD文档。

## 🚀 主要功能

### 1. 智能PRD编写
- **结构化表单**：按章节组织的PRD模板，确保内容完整性
- **实时验证**：自动检查必填字段和内容质量
- **动态管理**：支持变更记录、用户场景、迭代历史的动态添加和管理

### 2. AI助手功能 🤖

#### 🔍 用户场景AI扩展
- **功能**：基于需求介绍，自动生成多个用户使用场景
- **输入**：需求介绍内容
- **输出**：包含用户类型、使用场景、痛点分析的结构化数据
- **用途**：帮助产品经理全面理解用户需求，避免场景遗漏

#### 🌐 智能竞品分析
- **功能**：使用AI模型的内置联网搜索技术，分析市面上相关产品竞品
- **技术**：基于GPT-4o、Claude 3.5、Gemini 2.0的原生网络搜索能力
- **输出**：详细的竞品调研报告，包括功能对比、优劣势分析、机会点识别
- **用途**：为产品决策提供市场洞察和竞争情报

#### ✅ 内容质量审查
- **功能**：AI审查PRD内容的完整性和质量
- **评估维度**：
  - 完整性检查（必填字段、关键信息）
  - 质量评估（描述清晰度、方案完善性）
  - 逻辑一致性（内容一致性、逻辑关系）
  - 专业程度（符合PRD标准、表达专业性）
- **输出**：0-100分评分、问题清单、改进建议
- **用途**：确保PRD质量，减少返工

#### 📄 智能PRD生成
- **功能**：基于填写的所有数据，生成完整的Markdown格式PRD文档
- **包含**：项目信息、需求分析、竞品分析、方案设计、实施计划等完整章节
- **特点**：结构清晰、内容详实、格式专业
- **导出**：支持复制到剪贴板和下载为.md文件

## 🛠 技术架构

### 前端技术栈
- **框架**：Next.js 15 (React 19)
- **样式**：Tailwind CSS 4
- **UI组件**：Radix UI + shadcn/ui
- **图标**：Lucide React
- **类型安全**：TypeScript

### AI集成
- **GPT-4o**：主要的文本生成和分析模型，支持搜索预览功能
- **Claude 3.5 Sonnet**：高质量文本生成，支持Web Search API
- **Gemini 2.0 Flash**：快速响应的多模态模型，支持Google Search Grounding
- **DeepSeek R1**：推理增强的开源模型

### API架构
```
/api/ai-prd
├── expand-user-scenarios  # 用户场景扩展
├── competitor-analysis    # 竞品分析
├── generate-prd          # PRD生成
└── review-content        # 内容审查
```

## 📋 使用指南

### 环境配置

1. **复制环境变量文件**
```bash
cp env.example .env.local
```

2. **配置API密钥**
```bash
# 必需的API密钥
GPT4O_API_KEY=your_gpt4o_api_key_here
GPT4O_BASE_URL=https://your-gpt4o-proxy.example.com/v1

# 可选的备用模型（都支持内置网络搜索）
CLAUDE_API_KEY=your_claude_api_key_here
GEMINI_API_KEY=your_gemini_api_key_here
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

3. **安装依赖**
```bash
pnpm install
```

4. **启动开发服务器**
```bash
pnpm dev
```

### 使用流程

1. **填写基本信息**
   - 选择业务线
   - 指定团队成员
   - 填写需求介绍

2. **AI辅助分析**
   - 使用"AI扩展"生成用户场景
   - 使用"AI找竞品"进行市场调研

3. **完善需求方案**
   - 填写功能点和业务逻辑
   - 设置优先级
   - 添加原型链接

4. **质量审查**
   - 点击"AI审查内容"检查质量
   - 根据建议完善内容

5. **生成PRD文档**
   - 点击"AI生成完整PRD"
   - 复制或下载最终文档

## 🔧 开发指南

### 目录结构
```
pm-assistant/
├── src/
│   ├── app/
│   │   ├── api/ai-prd/          # AI功能API接口
│   │   └── test-demos/prd-cards-complete/  # 主要功能页面
│   ├── components/ui/           # UI组件库
│   ├── config/models.ts         # AI模型配置
│   └── types.ts                 # 类型定义
├── env.example                  # 环境变量示例
└── README.md                    # 项目文档
```

### AI功能开发

#### 添加新的AI功能
1. 在`/api/ai-prd/route.ts`中添加新的处理函数
2. 更新`AIFunction`类型定义
3. 在前端调用`callAI`函数

#### 模型配置
```typescript
// src/config/models.ts
export const MODEL_CONFIGS: Record<string, ModelConfig> = {
  'your-model': {
    id: 'your-model',
    name: 'Your Model',
    provider: 'provider-name',
    apiKey: process.env.YOUR_API_KEY || '',
    baseUrl: 'https://api.example.com',
    model: 'model-name',
    supportsStreaming: true,
    hasWebSearch: false, // 是否支持联网搜索
  },
};
```

## 🔍 故障排除

### 常见问题

1. **401错误**
   - 检查API密钥是否正确配置
   - 确认.env.local文件存在且密钥有效

2. **网络超时**
   - 检查网络连接
   - 某些地区可能需要代理访问

3. **AI响应异常**
   - 检查控制台错误日志
   - 确认模型配置正确

### 调试模式
```bash
# 启用详细日志
DEBUG=ai-prd:* pnpm dev
```

## 📈 性能优化

- **并行请求**：多个AI功能可以并行执行
- **缓存机制**：相同请求结果会被缓存
- **流式响应**：支持实时显示AI生成内容
- **错误重试**：自动重试失败的请求

## 🚀 部署指南

### Vercel部署
1. 连接GitHub仓库到Vercel
2. 在Vercel环境变量中配置所有API密钥
3. 部署完成

### 自托管部署
```bash
# 构建生产版本
pnpm build

# 启动生产服务器
pnpm start
```

## 🤝 贡献指南

1. Fork本仓库
2. 创建功能分支：`git checkout -b feature/amazing-feature`
3. 提交更改：`git commit -m 'Add amazing feature'`
4. 推送分支：`git push origin feature/amazing-feature`
5. 开启Pull Request

## 📄 许可证

MIT License - 详见[LICENSE](LICENSE)文件

## 🙏 致谢

- [Next.js](https://nextjs.org/) - React框架
- [Tailwind CSS](https://tailwindcss.com/) - CSS框架
- [Radix UI](https://www.radix-ui.com/) - UI原语
- [OpenAI](https://openai.com/) - GPT模型和搜索预览功能
- [Anthropic](https://www.anthropic.com/) - Claude模型和Web Search API
- [Google AI](https://ai.google.dev/) - Gemini模型和Search Grounding

---

**联系方式**：如有问题或建议，请提交Issue或发送邮件。
