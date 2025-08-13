---
title: 全新的Python包管理工具----UV
publishDate: 2026-08-13
description: 'UV是由Rust构建的新颖的Python包管理工具，通过pyproject.toml进行虚拟环境管理，并且实现远超Pip的安装速度，同时提供了全面的依赖管理，不需要通过pip进行复杂的版本管理。'
tags:
  - 环境处理
  - Python venv
heroImage: { src: './fu-shi-shan-he-ka-wa-gu-qi-ke-hu-zai-ri-luo-shi-qiu-ji-zai-ri-ben-deyamanachi-de-fu-shi-shan.jpg', color: '#15526eff' }
language: 'Chinese'
---
# UV的特性
+ 安装Python包速度远超Pip，同时对Pip兼容较好
+ 包版本依赖管理方便
+ 为每个项目创建每个虚拟环境，实现各个项目相互隔离

# 安装与卸载
+ 本机安装(macos)
```bash
brew install uv
```
+ 服务器安装(Linux)
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

# 简单功能
## Python版本管理
安装和管理Python版本
+ `uv python install (3.10 3.11 3.12)` 安装Python版本
+ `uv python list` 查看可用的Python版本
+ `uv python find` 查找已经安装的Python版本
+ `uv python pin` 为当前项目指定使用的Python版本
+ `uv python uninstall` 卸载Python
## 脚本
运行独立的Python脚本
+ `uv run` 运行某个脚本
+ `uv add --script` 为脚本添加依赖
+ `uv remove --script` 从脚本中移除依赖
## 项目
uv 通过创建并管理一个pyproject.toml的Python项目。
+ `uv init` 创建一个项目，建立虚拟环境以及pyproject.toml
+ `uv add` 向项目中添加依赖包
+ `uv remove` 从项目中移除依赖包
+ `uv sync` 根据提供的pyproject.toml建立虚拟环境
+ `uv lock` 为项目依赖创建lock文件
+ `uv run` 在项目环境中运行命令
+ `uv tree` 查看项目的依赖树
+ `uv build` 构建项目的分发包
+ `uv publish` 将项目发布到包索引
## 工具
安装和运行发布到Python包索引的工具(如 ruff 和 black)
+ `uv tool run` 在临时环境中运行工具
+ `uv tool install` 全局环境中安装工具
+ `uv tool uninstall` 卸载工具
+ `uv tool list` 列出已经安装的工具
+ `uv tool update-shell` 更新shell，使工具生效
