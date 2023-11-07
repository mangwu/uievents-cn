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

如果你喜欢这个规范，你可能会对同一发布者（w3c）的其他规范感兴趣：:

* UI Events 键盘事件码值规范: [GitHub 项目地址](https://github.com/w3c/uievents-code/), [规范文档地址](https://w3c.github.io/uievents-code/)
* UI Events 键盘事件键值规范: [GitHub 项目地址](https://github.com/w3c/uievents-key/), [规范文档地址](https://w3c.github.io/uievents-key/)

## 合并记录

此部分并非源地址中的README内容，而是对源项目进行更新之后，本翻译项目进行追踪更新的记录

| 源项目更新                                                   |             源项目更新的SHA码             |                      本项目更新的SHA码                       | 更新内容                                                     |
| ------------------------------------------------------------ | :---------------------------------------: | :----------------------------------------------------------: | ------------------------------------------------------------ |
| [Merge pull request](https://github.com/w3c/uievents/commit/01d97fd3f0c6fa1bbb87cd4b8c4a78ac364b6383) [#329](https://github.com/w3c/uievents/pull/329) [from flackr/dblclick-no-select](https://github.com/w3c/uievents/commit/01d97fd3f0c6fa1bbb87cd4b8c4a78ac364b6383) | 01d97fd3f0c6fa1bbb87 cd4b8c4a78ac364b6383 |          b79d9199a7868f7f1944 3a4eba84ed92e5d86a8f           | 双击事件的默认行为不再包含对文本的选中：<br/>1. `event-types.txt` 文件中的 `event-type-dblclick` 内容最后一段对默认行为的描述修改<br/>2. `event-interface.txt` 文件中的 `event-types-list` 内容关于 `dblclick` 事件类型的默认行为删除文本选中相关内容 |
| [Reflect the reality for the focus event order](https://github.com/w3c/uievents/commit/c1d10be0a64f765f5721efd00be3adcf2105e291) | c1d10be0a64f765f5721 efd00be3adcf2105e291 |          4f6ebb113a6a6c1aa5aa 8e32bc05e0e469d3569c           | 关于焦点事件的发生顺序更正: <br/>1. `event-types.txt` 文件中的`events-focusevent-event-order` 表格中，`focusin` 事件应该紧随 `focus`  事件发生，二者都在目标元素接收焦点后被派发<br/>2. 与1.中同样的位置表格，`focusout` 事件应该紧随 `blur` 事件发生，二者都在第一个目标元素失去焦点后被派发<br/>3. `event-types.txt` 文件中的各个焦点事件( `event-type-blur` ，`event-type-focus`，`event-type-focusin`，`event-type-focusout`)的定义描述中，修改关于发生顺序的说法(本条目共4处修改) |
| [Fix](https://github.com/w3c/uievents/commit/bd803f3a52a72606488b6dfbdcb6d2aa6dc8d9a2) [#340](https://github.com/w3c/uievents/issues/340) [- Broken references to key and code specs](https://github.com/w3c/uievents/commit/bd803f3a52a72606488b6dfbdcb6d2aa6dc8d9a2) | bd803f3a52a72606488b 6dfbdcb6d2aa6dc8d9a2 | [6b7f43c47809cdcc3e73 09bc172e0ccf0b32ff5c](https://github.com/mangwu/uievents-cn/commit/6b7f43c47809cdcc3e7309bc172e0ccf0b32ff5c) | 修正 `keyboard.txt` 文件中KEY和CODE的不正确引用，包括：<br/>1. 'KEY{AltGr}'替换成'KEY{AltGraph}' <br/>2. 在example-key-shift-2（例子20）中的'CODE{}'替换成'CODE{Digit2}'<br/>3. 'KEY{FullWidth}'替换成'KEY{Zenkaku (FullWidth)'，'KEY{HalfWidth}'替换成'KEY{Hankaku} (HalfWidth)' |
| [Fix](https://github.com/w3c/uievents/commit/2614abf2b4d0c5fe3d7dc046a774af63ace3db57) [#312](https://github.com/w3c/uievents/issues/312) [- Restore custom CSS style](https://github.com/w3c/uievents/commit/2614abf2b4d0c5fe3d7dc046a774af63ace3db57) | 2614abf2b4d0c5fe3d7d c046a774af63ace3db57 | [305883d9ac1fb6868d61 04cececf053202f86dbb](https://github.com/mangwu/uievents-cn/commit/305883d9ac1fb6868d6104cececf053202f86dbb) | 在项目根目录下添加 `stylesheet-extra.include` 样式文件，并在 `index.bs` 主文件中引入，以渲染官方定义的注释，警告，定义等样式 |
| [Fix](https://github.com/w3c/uievents/commit/e47b95e88e8bd94944da29f6b371b34efeff17cd) [#135](https://github.com/w3c/uievents/issues/135)[: Add definitions for MouseEvent layerX\|Y](https://github.com/w3c/uievents/commit/e47b95e88e8bd94944da29f6b371b34efeff17cd) | e47b95e88e8bd94944d a29f6b371b34efeff17cd | [92c035fa102daac92cf2 c56087c9ec49ea68f6d3](https://github.com/mangwu/uievents-cn/commit/92c035fa102daac92cf2c56087c9ec49ea68f6d3) | 为 `MouseEvent `接口新增 `layerX` 和 `layerY` 属性并进行定义，在`event-types.txt` 文件中添加了如下:<br/>1.  `MouseEvent`  IDL定义代码中添加 `layerX|Y` 属性<br/>2. 在上述的IDL代码下对 `layerX|Y` 属性加以定义和描述<br/>3. 在鼠标事件的每个事件定义的可信事件上下文中添加 `MouseEvent.layerX|Y` 的描述 |

