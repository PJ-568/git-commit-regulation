# PJ568 提交说明规范 `v 0.1.2`

本规范旨在格式化提交说明，以在方便阅读理解的同时，保证其能被程序一致地解析。

简见[简例](#简例)。

## 格式

提交的格式的构成：

- 标题：标题须为单行文本，并包含：
  - [类型](#类型)：具体提交类型；
  - [范围](#范围)（可选）：提交的对象所属范围；
  - [摘要](#摘要)：描述提交内容的短句；
- [描述](#描述)（可选）：可包含多行详细信息的文本。

### 简例

```markdown
【类型，范围】摘要

可选描述。
若有必要可使用多行。

可选多行信息：

1. 第一条
2. 第二条

相关问题编号：

#568
```

## 内容

尽量使每一次提交都只针对单个目标功能的修改。

### 多语言混排

汉字两侧与阿拉伯数字和字母和非汉语符号之间用空格分隔。

### 类型

**类型**是提交说明的中心内容，也是程序解析提交说明的依据。

类型的长度为二个汉字。类型必须被包含在实心方头括号（鱼尾括号：`【】`）中，以防与[摘要](#摘要)混淆。

一切标题必须包含一个类型，且类型的内容必须是以下之一：

|内容|代码相关|描述|
|:-:|:-:|:--|
|初始|视情况|当且仅当仓库第一次提交。|
|更改|是|重大改变或移除功能。|
|新增|是|影响使用或生产的新功能。|
|修复|是|对现有错误的修复。|
|格式|视情况|不影响功能和生产的代码格式、文档或注释更改。|
|文档|否|对文档、自述（Readme）等的更改。|
|测试|是|新增或编辑测试。|
|维护|否|对诸如模板文件、样式表等非生产代码更改。|

以上类型按照优先级从高到低排列。

当提交符合多项类型时，代码相关的项目应使用契合提交代码相关性的高优先级的类型；
完全代码无关的项目可忽略代码相关性。

需注意相应类型的提交和[版本控制](https://semver.org/lang/zh-CN)间的对应关系，如：

- `【更改】`：提升主版本号；
- `【新增】`：提升次版本号；
- 其它：提升修订号。

简例：

```markdown
【修复，核心】解决内存泄漏问题
```

```markdown
【格式】修改 README 的样式
```

```markdown
【维护】更新默认配置
```

### 范围

范围由项目负责人划分，并确保一致性。
项目负责人应在项目文档中定义范围列表。
大部分情况下，项目可以用子目录、包、模块等单位划分。

范围位于实心方头括号内，紧接在[类型](#类型)内容之后，与[类型](#类型)内容以逗号（`，`）分隔。

范围是可选的：

- 当项目规模较小时可不使用范围。当项目达到一定规模时引入范围。
- 当提交不限于单个范围或与任意范围无关时可不使用范围。

### 摘要

简练地描述更改，尽量不超过 30 个汉字或 60 个字符。超出的重要信息应写入[描述](#描述)。

用祈使句，如：`添加功能至目标`。

请勿直接引用如 `#568` 的问题编号，这会降低可读性且导致项目难以溯源。请将问题编号添加至[描述](#描述)。

### 描述

描述是可选的。

描述应紧接在[摘要](#摘要)后，与[摘要](#摘要)用两个换行符相隔。

用祈使句。

描述可包含以下内容：

- 提交的理由；
- 在代码中未标明的潜在因素，如副作用或迁移提示；
- 注意事项；
- 相关问题编号。

## 许可

本规范基于 [CC BY-SA 4.0](LICENSE) 许可协议发布。
