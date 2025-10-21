---
{"dg-publish":true,"permalink":"/CS/计算机语言/Python环境配置/","created":"2024-12-17 20:37","updated":"2025-10-21 15:34"}
---


## uv

```cmd
#创建项目
uv init
uv init hello-world
#创建项目
mkdir hello-world
cd hello-world
uv init
#删除项目
ri hello-world
#安装依赖
uv add requests
uv add 'requests==2.31.0'
uv add requests --git https://github.com/psf/requests
#卸载依赖
uv remove requests
#升级依赖
uv lock --upgrade
#运行脚本
uv run example.py
#使用工具
uvx markitdown
uv tool install markitdown
uv tool upgrade markitdown
uv tool upgrade --all
uv tool uninstall markitdown
```
