---
{"dg-publish":true,"permalink":"/CS/计算机语言/在Mac OS上使用VS code编写R——痛苦之路/","created":"2025-12-26 18:38","updated":"2026-02-03 10:30"}
---


## 1 安装 R 和 VS code

拥有 [Homebrew](https://brew.sh/) 会让接下来的工作轻松很多。

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

使用 `brew install r` 安装 R 语言，前往 [官网](https://code.visualstudio.com/) 安装 VS code。

## 2. 安装 radian

[radian](https://github.com/randy3k/radian) 是一个使用 Python 编写的 R 语言控制台，提供了丰富的扩展功能。

虽然官方推荐使用 `pipx` 安装，但是使用 Python 最佳包管理器 `uv` 是更好的选择。

```zsh
brew install uv
uv tool install radian
# uv tool upgrade radian
```

为了更方便地在终端调用 radian 或原生控制台，在 `~/.zshrc` 写入别名：

```
alias r="radian"
alias R="R --no-save --no-restore-data"
```

## 3. 使用 `renv` 管理包

通过 [renv](https://rstudio.github.io/renv/articles/renv.html) 可以为 R 项目创建独立的虚拟环境，类似 `uv` 之于 Python 的作用。

为了在 VS code 中获得较好的体验，我们总是希望环境中存在一些起辅助作用的包，但是又不希望将它们写入项目依赖列表。为此，我们可以构建一个独立的用户库安装需要的包，然后允许所有 `renv` 项目从这个库寻找需要的包。

在 R 安装目录下创建 `renv-global-library` 文件夹

- `brew` 安装的 R 默认在 `/opt/homebrew/lib/R`
- 其他情况，可以在 R 控制台输入 `R.home()` 查看

将需要的包安装进去

```r
install.packages(
  c(
    "languageserver",
    "jsonlite",
    "nx10/httpgd",
    "rmarkdown",
    "lintr",
    "pak"
  ),
  lib = "/opt/homebrew/lib/R/renv-global-library"
)
```

用法详见：

- [languageserver](https://github.com/REditorSupport/vscode-R/wiki/R-Language-Service)

创建 `~/.Renviron` 写入

```
RENV_CONFIG_EXTERNAL_LIBRARIES="/opt/homebrew/lib/R/renv-global-library"
RENV_CONFIG_PAK_ENABLED=TRUE
```

这样 `renv` 项目就可以获取外部库，并且使用 [pak]([Another Approach to Package Installation • pak](https://pak.r-lib.org/)) 作为默认下载器。

## 4. 配置 VS code

安装插件：

- [vscode-R](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r)（必备）
- [Air](https://posit-dev.github.io/air/editor-vscode.html)
- [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)（推荐）
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)（推荐）

按下 `command+shift+p` 打开命令面板搜索 `settings`，选择“首选项： 打开用户设置（JSON）”，根据 vscode-R 官方 [wiki](https://github.com/REditorSupport/vscode-R/wiki/Getting-Started) 将下列配置粘贴进去：

```json
// =========================================================================
// R语言设置
// =========================================================================
"r.rterm.mac": "~/.local/bin/radian",
"r.rpath.mac": "/opt/homebrew/bin/R",
"r.alwaysUseActiveTerminal": true,
"r.sessionWatcher": true,
"r.bracketedPaste": true,
"r.plot.useHttpgd": true,
"[r]": {
    "editor.defaultFormatter": "REditorSupport.r",
    "editor.formatOnSave": true,
    "editor.wordSeparators": "`~!@#%$^&*()-=+[{]}\\|;:'\",<>/?",
    "editor.tabSize": 2,
    "editor.detectIndentation": false
},
"[rmd]": {
    "editor.defaultFormatter": "REditorSupport.r",
    "editor.formatOnSave": true
},
"path-autocomplete.pathMappings": {
        "/": "/",
        "./": "${folder}"
}
```
