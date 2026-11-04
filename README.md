# DSH-plugin

我的 [DeepSeek Harness](https://github.com/deepseek-ai) 插件集合。每个插件都是**独立仓库**，
通过 git submodule 挂在本仓库下，方便单独 clone、安装和更新。

## 插件列表

| 插件 | 说明 | 仓库 |
| --- | --- | --- |
| `dsh-panellist-collapse` | 左侧栏「全局面板」列表的展开/收起；折叠时只保留前 N 行（默认只留「插件」按钮），不影响皮肤动图 | [asdw159632/dsh-panellist-collapse](https://github.com/asdw159632/dsh-panellist-collapse) |
| `dsh-git-plugin` | 可视化仓库的 Git 历史，并在 GUI 里做 add / commit / pull / push / merge | [asdw159632/dsh-git-plugin](https://github.com/asdw159632/dsh-git-plugin) |

## 克隆

```bash
git clone --recurse-submodules https://github.com/asdw159632/DSH-plugin.git
```

已经有克隆时，同步子模块：

```bash
git submodule update --init --recursive
git pull --recurse-submodules
```

## 安装插件

每个插件目录本身就是一个 DSH bundle。在 DSH 会话里让 Agent 用插件管理器安装：

```
plugin_manager install_bundle target="<插件目录的绝对路径>"
```

卸载：

```
plugin_manager remove_bundle target="<插件包名>"
```

> 本地目录安装是 pnpm link，改插件源码后刷新页面即可生效。

## 目录结构

```
DSH-plugin/
└── plugins/
    ├── dsh-panellist-collapse/   # submodule → 独立仓库
    └── dsh-git-plugin/           # submodule → 独立仓库
```

## 许可

各插件仓库自带许可，默认 MIT。