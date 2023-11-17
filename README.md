# `yi` 宏包

`yi` 是一个用于绘制《易经》中各种符号的 `LaTeX` 宏包（基于 `LaTeX3` 实现），可绘制的符号包括：太极、两仪、四象、八卦、由八卦上下重叠而成的重卦以及由太极和八卦组合而成的先天/后天太极八卦图。

## 基本用法

该宏包提供了如下几个命令来绘制上述所说的各种符号：
```latex
\taiji[<options>]
\yao[<options>]{<number>}
\taijibagua[<options>]{<xiantian/houtian>}
\liangyi[<options>]{<name>}
\sixiang[<options>]{<name>}
\bagua[<options>]{<name>}
\chonggua[<options>]{<name>}
```

## 宏包文件与说明文档的获取方法

- 用命令 `xetex `编译 `yi.dtx` 文件可从中释放得到 `README.md`（非本文件）、`yi.ins` 和 `yi.sty` 文件：
  ```
  xetex yi.dtx
  ```

- 用命令 `xelatex` 编译 `yi.dtx` 文件可得到宏包说明文档 `yi.pdf` 及其他辅助文件（此处不一一列举）：
  ```
  xelatex yi.dtx
  ```
  **注意：** 在使用 `xelatex` 编译 `yi.dtx` 文件时，请先在您电脑内的TeX发行版本地目录中找到 `ctxdoc.cls`，并将其内的 `\__codedoc_get_hyper_target:xN` 函数改为 `\__codedoc_get_hyper_target:eN`，否则在“代码实现”部分编译无法正常通过。因为 `yi.dtx` 是用 `ctxdoc` 文类编写的，`ctxdoc` 又改自 `l3doc`，而 `l3doc` 在最近的更新中将原本 `\__codedoc_get_hyper_target:xN` 函数的第一个参数说明符由 `x` 改为了 `e`，但 `ctxdoc.cls` 还尚未同步改动。这一小问题待后续的更新应当会解决。

- 宏包说明文档中索引文本的生成需指定专门的索引格式 `gind.ist` （`makeindex` 命令的`-s` 选项用于设定格式文件）：
  ```
  makeindex -s gind.ist yi.idx
  ```
  之后再用 `xelatex` 编译 `yi.dtx` 文件两次方可得到一份完整的宏包说明文档：
  ```
  xelatex yi.dtx
  xelatex yi.dtx
  ```

## 贡献

如果您对该宏包有任何改进意见，欢迎提交 [Issues](https://github.com/123dyu/yi/issues) 或 [pull requests](https://github.com/123dyu/yi/pulls) 。

## 许可证

本模板的发布遵守 [LaTeX Project Public License](http://www.latex-project.org/lppl.txt)（版本 1.3c 或更高）。

<br>

# The `yi` package

The `yi` package provides commands for drawing various symbols in the I Ching.

## Basic usage

This package provides the following commands:
```latex
\taiji[<options>]
\yao[<options>]{<number>}
\taijibagua[<options>]{<xiantian/houtian>}
\liangyi[<options>]{<name>}
\sixiang[<options>]{<name>}
\bagua[<options>]{<name>}
\chonggua[<options>]{<name>}
```
## Contributing

[Issues](https://github.com/123dyu/yi/issues) and [pull requests](https://github.com/123dyu/yi/pulls) are welcome.

## License

This work may be distributed and/or modified under the conditions of
the [LaTeX Project Public License](http://www.latex-project.org/lppl.txt),
either version 1.3c of this license or (at your option) any later
version.

-----

Copyright (C) 2023 by Yu Du <3531243657@qq.com>

