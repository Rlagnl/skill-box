# AI Coding Package - AI 辅助编程技能仓库

这是一个 AI 辅助编程相关的配置集合包，用于存储和管理各种自动化任务和工具，在开发过程中提供智能辅助能力。

## 项目结构

```
ai-coding-package/
├── .agents/                    # AI Agent 相关技能
│   └── skills/
│       └── brainstorming/      # 头脑风暴技能
│           ├── scripts/        # 辅助脚本
│           ├── SKILL.md        # 技能说明文档
│           └── ...
├── .trae/                      # Trae IDE 相关配置
│   ├── rules/                  # 项目规则配置
│   │   ├── general.md          # 通用技术栈和代码风格规则
│   │   ├── git.md              # Git 工作流规则
│   │   └── skill.md            # 技能开发规范
│   └── skills/                 # Trae 技能目录
│       ├── class-to-function-converter/  # React 类组件转函数组件
│       └── create-scene/                 # Phaser 3 场景创建
├── AGENTS.md                   # AI Agent 规则配置
├── README.md                   # 项目说明文档
└── skills-lock.json            # 技能锁定文件
```

## 核心功能

本项目提供以下 AI 辅助编程技能：

### 1. 头脑风暴 (brainstorming)

- **位置**：`.agents/skills/brainstorming/`
- **描述**：在任何创意工作之前使用，通过自然协作对话将想法转化为完整的设计和规格说明
- **调用时机**：创建功能、构建组件、添加功能或修改行为之前
- **功能特点**：
  - 探索项目上下文
  - 提供可视化辅助
  - 提出澄清问题
  - 提供 2-3 种方案及权衡建议
  - 生成设计文档

### 2. 类组件转函数组件 (class-to-function-converter)

- **位置**：`.trae/skills/class-to-function-converter/`
- **描述**：将 React Class Component 转换为 Function Component
- **调用时机**：用户要求将类组件重构为函数组件时
- **功能特点**：
  - 全项目扫描或单文件转换
  - 自动识别 Class Component
  - state 转换为 useState
  - 生命周期方法转换为 useEffect
  - 生成转换报告

### 3. 创建场景 (create-scene)

- **位置**：`.trae/skills/create-scene/`
- **描述**：在 Phaser 3 项目中创建新的场景文件
- **调用时机**：用户想要添加新场景到项目时
- **功能特点**：
  - 在 `src/scenes` 目录创建 TypeScript 文件
  - 自动继承 GameScene
  - 包含必需的 init 和 create 方法
  - 支持自定义或随机场景名称

## 项目规则配置

### 通用规则 (general.md)

- **技术栈**：Taro4 + taro-ui + TypeScript + React 18 + Zustand
- **代码风格**：
  - 组件：PascalCase（Button.tsx）
  - 文件：kebab-case（user-profile.ts）
  - 命名：interface 以 `I` 开头，Type 以 `Type` 结尾
  - 缩进：2 空格，必须分号
  - 类型：显式返回类型，Props 必须 interface
- **路径引用**：必须使用绝对路径（如 `@/scenes/GameScene`）

### Git 工作流规则 (git.md)

- **分支管理**：main/master（发布）、develop（开发）、feature/_（特性）、hotfix/_（热修复）
- **工作流程**：从 develop 分支创建特性分支，完成后合并回 develop
- **严格禁止**：直接提交到 main/master 分支

### 技能开发规范 (skill.md)

每个 Skill 目录应包含：

- `index.ts` - 入口文件
- `SKILL.md` - 技能说明文档
- `package.json` - 技能配置文件

## 开发新技能

1. 在 `.trae/skills/` 或 `.agents/skills/` 目录下创建技能文件夹
2. 创建必要文件：`index.ts`、`SKILL.md`、`package.json`
3. 按照 SKILL.md 规范编写文档
4. 实现技能逻辑
5. 测试技能功能
6. 更新 `skills-lock.json` 文件

## 使用方式

在 Trae IDE 中，当满足技能的调用条件时，系统会自动加载并执行相应的技能。

## 许可证

[添加许可证信息]
