# UIEvents-cn

UIEvents中文翻译计划

此仓库用于对[用户界面事件规范](https://w3c.github.io/uievents/)（以前称为DOM 3事件）进行翻译。

除非特殊表明，以下是对源地址中README.md内容的翻译

## 目标

UI/DOM事件子组是Web应用程序工作组的一部分，其目标是根据市场需求完成
制定UI事件规范，以推动（用户代理）采用和实施，本项目也提供
一个全面的测试套件（至少是为了可实现性，也希望对互操作性验证有效），并将其沿着**推荐路线**（Recommendation Trac）移动到W3C推荐的状态。

## 交流

为了讨论与DOM事件相关的问题，该小组使用 <www-dom@w3.org> 邮件列表（[归档](http://lists.w3.org/Archives/Public/www-dom/)）。

## 文档

* 已发行文档（英文原档）
  * [UI Events - Last Published WD](http://www.w3.org/TR/uievents/)
  * [DOM Level 3 KeyboardEvent key Values](http://www.w3.org/TR/DOM-Level-3-Events-key/)
  * [DOM Level 3 KeyboardEvent code Values](http://www.w3.org/TR/DOM-Level-3-Events-code/)
* 编辑者的草稿（英文草稿）
  * [UI Events](https://w3c.github.io/uievents/)
  * [UI Events KeyboardEvent key Values](https://w3c.github.io/uievents-key/)
  * [UI Events KeyboardEvent code Values](https://w3c.github.io/uievents-code/)

## 公开问题

* [UI Events Issues Database](https://github.com/w3c/uievents/issues)
  * 实现者需要进行详细审查
  * 需要全面的测试套件
* [key Values Issues](https://github.com/w3c/uievents-key/issues)
* [code Values Issues](https://github.com/w3c/uievents-code/issues)

## 构建

此规范是使用[bikeshed](https://github.com/tabatkins/bikeshed)创建的。
如果您想贡献编辑，请确保您的更改正确生成。

要**构建**此规范，必须：

1. 将此仓库克隆到本地目录中。
1. 安装 [bikeshed](https://github.com/tabatkins/bikeshed)。
1. 在本地目录中运行 `python build.py` 。

要对本规范**进行编辑**，请执行以下操作：

1. 编辑 ```index.bs``` 文件或任何 ```sections\*.txt``` 文件。
2. 构建 (上面的构建步骤). 这将为每个 ```sections\*.txt``` 文件创建一个 ```sections\*.include``` 文件，然后创建 ```index.html``` 。

在提交拉取请求时，请确保您的更改列表中没有包含 ```sections\*.include``` 文件的任何部分——它们都已添加到 ```.gitignore``` 文件中，这样您就不会意外包含它们。所有更改都应在 ```sections\*.txt``` 文件和 ```index.bs``` 部分中进行。

## 测试

* [DomEventViewer](https://domeventviewer.com/) 网站用于测试（用户代理实现的）UIEvents
* Web平台测试
  * [GitHub web-platform-tests/wpt uievents](https://github.com/web-platform-tests/wpt/tree/master/uievents)
  * 挂载的网站镜像： [wpt.live/uievents/](https://wpt.live/uievents/)

## 建议

如果你喜欢这个规格，你可能会对同一发布者（w3c）的其他规范感兴趣：:

* UI Events 键盘事件码值规范: [GitHub 项目地址](https://github.com/w3c/uievents-code/), [规范文档地址](https://w3c.github.io/uievents-code/)
* UI Events 键盘事件键值规范: [GitHub 项目地址](https://github.com/w3c/uievents-key/), [规范文档地址](https://w3c.github.io/uievents-key/)

## 合并记录

此部分并非源地址中的README内容，而是对源项目进行更新之后，本翻译项目进行追踪更新的记录

| 源项目更新                                                                                                                                                                                                                                                               |             源项目更新的SHA码             |             本项目更新的SHA码             | 更新内容                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------------: | :---------------------------------------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Merge pull request](https://github.com/w3c/uievents/commit/01d97fd3f0c6fa1bbb87cd4b8c4a78ac364b6383) [#329](https://github.com/w3c/uievents/pull/329) [from flackr/dblclick-no-select](https://github.com/w3c/uievents/commit/01d97fd3f0c6fa1bbb87cd4b8c4a78ac364b6383) | 01d97fd3f0c6fa1bbb87 cd4b8c4a78ac364b6383 | b79d9199a7868f7f1944 3a4eba84ed92e5d86a8f | 双击事件的默认行为不再包含对文本的选中：<br/>1. `event-types.txt` 文件中的 `event-type-dblclick` 内容最后一段对默认行为的描述修改<br/>2. `event-interface.txt` 文件中的 `event-types-list` 内容关于 `dblclick` 事件类型的默认行为删除文本选中相关内容                                                                                                                                                                                                                                  |
| [Reflect the reality for the focus event order](https://github.com/w3c/uievents/commit/c1d10be0a64f765f5721efd00be3adcf2105e291)                                                                                                                                         | c1d10be0a64f765f5721 efd00be3adcf2105e291 | 4f6ebb113a6a6c1aa5aa 8e32bc05e0e469d3569c | 关于焦点事件的发生顺序更正: <br/>1. `event-types.txt` 文件中的`events-focusevent-event-order` 表格中，`focusin` 事件应该紧随 `focus`  事件发生，二者都在目标元素接收焦点后被派发<br/>2. 与1.中同样的位置表格，`focusout` 事件应该紧随 `blur` 事件发生，二者都在第一个目标元素失去焦点后被派发<br/>3. `event-types.txt` 文件中的各个焦点事件( `event-type-blur` ，`event-type-focus`，`event-type-focusin`，`event-type-focusout`)的定义描述中，修改关于发生顺序的说法(本条目共4处修改) |
