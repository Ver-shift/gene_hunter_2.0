# 基因猎人整合包构建教程

## 前置准备

### 开发工具
- **Visual Studio Code**
  - 本体：[下载链接](https://code.visualstudio.com/download)
  - 必要插件：
    - [TypeScript Next](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-next) - 版本6.0以下
    - [ProbeJS](https://marketplace.visualstudio.com/items?itemName=Prunoideae.probejs)（可选）- 最新版本，带来快速热重载和自动导包功能

### 版本控制
- **Git**：[下载链接](https://git-scm.com/)
- **GitHub Desktop**（可选）：[下载链接](https://desktop.github.com/download/) - 带来高速的git推送速度

### 网络工具
- **Clash**：稳定的网络连接

### 游戏启动器
- **Polymerium**：[GitHub仓库](https://github.com/d3ara1n/Polymerium) - 游戏启动器，提供关键构建选项

## 快速构建

### 使用 Polymerium

```bash
git clone https://github.com/Ver-shift/gene_hunter_2.0.git ~/.trident/instances/gene_hunter_2.0
```

克隆完成后，在 Polymerium 中就能看到 **Gene Hunter 2.0** 实例，直接运行即可开始构建。



## 初级开发入门

1. 在启动器内找到整合包实例。使用vscode打开`.trident\instances\gene_hunter_2.0\build`文件夹作为vscode的工作区，即可正常开发。

2. 提交准备：
   1. 配置文件：将更改后的配置文件手动放入`import/config`文件夹(不要将所有配置文件全部放入)。
   2. kubejs文件脚本：通常会自动同步进入`import`文件夹。

3. 提交或者导出整合包：将需要导出或者提交的文件放入`import`文件夹，即可同步或者导出为整合包压缩文件。

## 高级开发

### 📁 项目结构

```
gene_hunter_2.0/
├── build/          # 构建相关文件
├── import/         # 导出为整合包压缩文件时的内容文件夹
├── live/           # 缓存层
├── persist/        # 持久化层
├── .gitignore      # Git忽略配置
├── profile.json    # 关键资源mod配置文件
└── README.md       # 项目说明文档
```

见以下信息
https://github.com/d3ara1n/Polymerium/discussions/60#discussioncomment-15355545



## 分支保护策略

### 分支类型与用途

1. **main分支**
   - 由管理员控制，始终保持项目的最新稳定版本
   - 仅接受通过PR（Pull Request）合并的代码
   - 所有更改必须经过代码审查

2. **version/* 分支**（如：version/1.21.1neoforge+1.0）
   - 特定版本的开发分支
   - 用于版本特定的功能开发和bug修复
   - 从main分支创建，最终合并回main分支

3. **dev/* 分支**（如：dev/YourGithubName）
   - 开发者个人分支
   - 每位开发者创建自己的开发分支
   - 用于日常开发工作

### 工作流程

1. **开始开发**
   - 从main分支创建个人开发分支：`dev/YourGithubName`
   - 示例：`git checkout -b dev/YourGithubName main`

2. **提交代码**
   - 在个人分支上进行开发
   - 定期提交更改，保持提交信息清晰
   - 示例提交信息格式：`feat: 添加新功能` 或 `fix: 修复某个bug`

3. **创建PR（Pull Request）**
   - 开发完成后，创建PR到当前版本的开发分支（如：version/1.21.1neoforge+1.0）
   - PR标题应清晰描述更改内容
   - PR描述应详细说明更改原因、测试方法等

4. **代码审查**
   - 至少需要一名其他开发者审查代码
   - 审查通过后，由管理员或具有权限的成员合并
   - 解决所有审查意见后才能合并

### 分支保护规则

1. **main分支保护**
   - 禁止直接推送（force push）
   - 要求通过PR合并
   - 要求至少一名审查者批准
   - 要求分支保持最新（无冲突）

2. **version/* 分支保护**
   - 禁止直接推送
   - 要求通过PR从dev/*分支合并
   - 要求代码审查
   - 建议进行测试验证

3. **分支命名规范**
   - main：主分支
   - version/{版本号}：版本分支
   - dev/{GitHub用户名}：开发者个人分支



> 💡 **提示**: 确保所有工具都正确安装并配置好网络连接，以获得最佳构建体验。
