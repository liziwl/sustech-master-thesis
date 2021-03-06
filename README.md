# 南方科技大学研究生毕业论文模板 sustechthesis

[![Actions Status](https://github.com/SUSTech-CRA/sustech-master-thesis/actions/workflows/verify-compile.yml/badge.svg)](https://github.com/SUSTech-CRA/sustech-master-thesis/actions/workflows/verify-compile.yml)
[![GitHub downloads](https://img.shields.io/github/downloads/SUSTech-CRA/sustech-master-thesis/total)](https://github.com/SUSTech-CRA/sustech-master-thesis/releases)
[![GitHub commits](https://img.shields.io/github/commits-since/SUSTech-CRA/sustech-master-thesis/latest)](https://github.com/SUSTech-CRA/sustech-master-thesis/commits/master)
[![GitHub release](https://img.shields.io/github/v/release/SUSTech-CRA/sustech-master-thesis)](https://github.com/SUSTech-CRA/sustech-master-thesis/releases/latest)

## 下载

推荐下载**发布版**模板，里面包括具体使用说明以及示例文档：

* 模板使用说明（sustechthesis.pdf）*本模版使用说明尚不完善，仅供参考。主要功能在 `sustech-setup.tex` 示例文档基本配置文件中已经进行注释。*
* 示例文档（sustechthesis-example.pdf）

开发版中不提供预生成的 `cls` 文件和文档，仅包含源码。其仅供开发者与需要尚未发布的功能的有经验的 TeX 用户使用，不提供任何保证。

下载途径：

* 发布版：
  * [GitHub Releases](https://github.com/SUSTech-CRA/sustech-master-thesis/releases)：最新版的及时发布途径。
  * [SUSTech 镜像站](https://mirrors.sustech.edu.cn/github-release/SUSTech-CRA/sustech-master-thesis/)：GitHub Releases 的镜像。
* 开发版：
  * [GitHub](https://github.com/SUSTech-CRA/sustech-master-thesis)
  * [SUSTech-Git](https://mirrors.sustech.edu.cn/git/liziwl/sustech-master-thesis)
  * 预构建 [Dev Build](https://github.com/SUSTech-CRA/sustech-master-thesis/releases/tag/dev-latest)

## 更新日志

每个版本的详细更新日志，请见 [CHANGELOG.md](CHANGELOG.md)。使用文档中也包含了这一内容。

## 升级
### 发布版

下载发布版的的 zip 包，使用其中的 `sustechthesis.cls` 等文件覆盖原有的即可，无须额外操作。

### 开发版

从 GitHub clone 项目源码或者下载源码 zip 包，执行命令（Windows 用户在文件夹空白处按 `Shift + 鼠标右键`，点击“在此处打开命令行窗口”）：

```shell
xetex sustechthesis.ins
```

即可得到 `sustechthesis.cls` 等模板文件。

## 反馈与QA

1. 南科大LaTeX学习交流群：119667812
2. 提交 [GitHub Issue](https://github.com/SUSTech-CRA/sustech-master-thesis/issues/new/choose)
3. [讨论区 Discussions](https://github.com/SUSTech-CRA/sustech-master-thesis/discussions)

## 使用
### Windows 中编译，使用 `latexmk`
1. `latexmk sustechthesis-example.tex` 生成示例论文 sustechthesis-example.pdf；
2. `latexmk sustechthesis.dtx` 生成说明文档 sustechthesis.pdf；
3. `latexmk -c` 清理编译生成的辅助文件；

### 使用 Makefile 编译
* `make thesis`     生成论文；
* `make viewthesis` 生成论文，编译完成开启预览；
* `make all`        生成论文，与 `make thesis` 等效；
* `make clean`      删除示例文件的中间文件（不含 pdf）；
* `make cleanall`   删除示例文件的中间文件和 pdf；
* `make wordcount`  论文字数统计。
* `make doc`     生成文档；
* `make cls`        仅生成 cls 模版类文件；

### 使用 LaTex 在线编辑器
* 使用 [Overleaf](https://www.overleaf.com/)（需要科学上网保证稳定使用），上传 zip 压缩包后，更改编译器为 `XeLaTex`
* 使用 [南科大 ShareLaTex](https://sharelatex.cra.moe/)，使用方式与Overleaf相同，上传 zip 压缩包后，更改编译器为 `XeLaTex`，并在主文档的头部 `\documentclass[degree=master,language=english,fontset=fandol]` 设置 `fontset` 参数 为 `fandol`.


### 编译前的建议

1. 在撰写论文时，我们不推荐使用原有的 `sustechthesis-example.tex` 这一名称。建议将其复制一份，改为其他的名字(如 `thesis.tex` 或者 `main.tex`)。需要注意，如果使用了来 自 `data` 目录中的 `tex` 文件，则重命名主文件后，其顶端的 `!TeX root` 选项也需要相应修改。
2. 需要注意，如果更改了主文件的名称，则需要修改 `Makefile` 顶端的 `THESIS` 变量定义；或修改 `latexmk` 命令后的参数。
3. ⚠️ 提交最终正式版本时，建议在 Windows 下本地编译且设置 `fontset` 参数 为 `windows`，以保证字体正确。

## 模板结构

### 文档内容
* `sustech-setup.tex` 示例文档基本配置（论文标题、作者等元数据）
* `sustechthesis-example.tex` 示例文档主文件
* `data/` 示例文档章节具体内容
* `figures/` 示例文档图片路径
* `ref/` 示例文档参考文献目录

### 样式控制
* `sustechthesis.cls` 模板类文件，由同名 dtx 文件和 ins 文件，（开发版不含，需要运行生成）。
* `thuthesis-*.bst` BIBTEX 参考文献表样式文件
* `thuthesis-*.bbx` BibLaTeX 参考文献表样式文件
* `thuthesis-*.cbx` BibLaTeX 参考文献引用样式文件

### 编译脚本
* `Makefile` Makefile
* `latexmkrc` latexmk 配置文件
* `README.md` Readme

## 致谢

* 本模板基于清华大学模板 [ThuThesis v7.1](https://github.com/tuna/thuthesis/releases/tag/v7.1.0) 修改。
* 本模版根据南方科技大学研究生院发布的相关 [学位授予的政策文件](https://gs.sustech.edu.cn/xueweishouyuzhengce) 编写，如有冲突以官网规定为准。
