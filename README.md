# Skill Box - 技能仓库

这是一个技能（Skill）仓库，用于存储和管理各种自动化任务和工具，支持在开发过程中提供智能辅助。

## 项目结构

```
skill-box/
├── .agents/            # 代理相关技能
│   └── skills/         # 代理技能目录
│       └── brainstorming/  # 头脑风暴技能
├── .trae/              # Trae 相关配置
│   ├── rules/          # 项目规则
│   │   ├── general.md  # 通用规则
│   │   ├── git.md      # Git 工作流规则
│   │   └── skill.md    # 技能规范
│   └── skills/         # Trae 技能目录
│       ├── class-to-function-converter/  # 类组件转函数组件技能
│       └── create-scene/                 # 创建场景技能
├── README.md           # 项目说明文档
└── skills-lock.json    # 技能锁定文件
```

## 技能规范

每个技能目录应包含以下文件：

- `index.ts` - 入口文件（类似 npm 包规范）
- `SKILL.md` - 技能的说明文档
- `package.json` - 技能的配置文件

### 入口文件要求

入口文件必须导出默认函数，该函数接收一个包含以下属性的参数对象：

- `input`: 用户的输入字符串
- `workspace`: 工作空间信息，包含 `uri.fsPath` 表示项目根目录路径

示例：

```typescript
interface ITask {
  input: string
  workspace: {
    uri: {
      fsPath: string
    }
  }
}

export default async function skillName($task: ITask) {
  // Skill 逻辑实现
}
```

### SKILL.md 格式

SKILL.md 文件应包含以下内容：

```markdown
---
name: "<skill-name>"
description: "<简短描述，说明技能功能和调用时机>"
---

# 技能标题

技能详细说明...

## 使用方法

## 功能特性

## 使用示例

## 实现说明
```

## 现有技能

### 1. 头脑风暴 (brainstorming)
- 位于：`.agents/skills/brainstorming/`
- 功能：提供创意生成和思维发散能力

### 2. 类组件转函数组件 (class-to-function-converter)
- 位于：`.trae/skills/class-to-function-converter/`
- 功能：将 React 类组件转换为函数组件

### 3. 创建场景 (create-scene)
- 位于：`.trae/skills/create-scene/`
- 功能：在 Phaser 3 项目中创建新场景

## 开发新技能

1. 在适当的目录下创建技能文件夹
2. 创建必要的文件：`index.ts`、`SKILL.md` 和 `package.json`
3. 实现技能逻辑
4. 测试技能功能
5. 更新 `skills-lock.json` 文件

## 技术栈

- TypeScript
- React 18
- Taro4 + taro-ui (相关项目技术栈)
- Zustand (状态管理)
- ESLint + Prettier (代码规范)

## 代码风格

- 组件：PascalCase（Button.tsx）
- 文件：kebab-case（user-profile.ts）
- 命名：新定义的 interface 命名必须以 `I` 开头，新定义的 Type 命名必须以 `Type` 结尾
- 缩进：2 空格，分号必须
- 类型：显式返回类型，Props 必须 interface
- Props 需要先解构再使用

## 路径引用规范

- 所有文件引用必须使用绝对路径（如 `@/scenes/GameScene`），禁止使用相对路径（如 `./GameScene`）
- 绝对路径基于 webpack.config.ts 中的 alias 配置

## Git 工作流

- **main/master**：只用于发布版本，禁止直接开发和提交
- **develop**：主开发分支，所有新功能都从这里分支
- **feature/***：特性分支，用于开发具体功能
- **hotfix/***：热修复分支，用于紧急修复

## 贡献指南

1. Fork 本仓库
2. 创建特性分支：`git checkout -b feature/your-feature-name`
3. 开发完成后，提交代码
4. 创建 Pull Request
5. 等待代码审查
6. 合并到 develop 分支

## 许可证

MIT License

## 联系方式

如有问题或建议，请联系项目维护者。
