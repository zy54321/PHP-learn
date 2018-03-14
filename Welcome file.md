＃欢迎来到StackEdit！

嗨！我是** StackEdit **中的第一个Markdown文件。如果你想了解StackEdit，你可以阅读我。如果你想玩Markdown，你可以编辑我。如果你已经完成了，你可以通过打开导航栏左边的**文件浏览器**来创建新文件。


＃文件

StackEdit将您的文件存储在浏览器中，这意味着您的所有文件都会自动保存在本地，并且可以脱机访问**！**

## 创建文件和文件夹

文件浏览器可通过导航栏左侧的按钮访问。您可以通过单击文件资源管理器中的** New file **按钮创建一个新文件。您也可以通过点击**新建文件夹**按钮来创建文件夹。

## 切换到另一个文件

所有文件都列在文件资源管理器中。您可以通过单击列表中的文件从一个切换到另一个。

## 重命名一个文件

您可以通过单击导航栏中的文件名或单击文件资源管理器中的**重命名**按钮来重命名当前文件。

## 删除一个文件

您可以通过单击文件资源管理器中的** Remove **按钮来删除当前文件。该文件将被移入** Trash **文件夹，并在闲置7天后自动删除。

## 导出文件

您可以通过单击当前文件导出**导出到磁盘**在菜单中。您可以选择将文件以简单的Markdown格式导出，如使用Handlebars模板的HTML格式或PDF格式。


＃同步

同步是StackEdit的最大功能之一。它使您可以将工作区中的任何文件与存储在您的** Google Drive **，您的** Dropbox **和** ** GitHub **帐户中的其他文件同步。这使您可以继续在其他设备上撰写文档，与您共享文件的人员协作，轻松集成到工作流程中......同步机制每分钟在后台进行，下载，合并和上传文件修改。

有两种类型的同步，它们可以相互补充：

- 工作区同步将自动同步所有文件，文件夹和设置。这将允许您在任何其他设备上获取您的工作区。	> 要开始同步您的工作区，只需在菜单中使用Google登录即可。- 文件同步将保持与一个或多个文件同步的工作区的一个文件**谷歌驱动器**，** Dropbox的**或** GitHub的**。	> 开始同步文件之前，您必须在**同步**子菜单中链接一个帐户。





## 打开一个文件

您可以打开** Google Drive **，** Dropbox **或** GitHub **中的文件，方法是打开**同步**子菜单并单击**从**打开。一旦在工作区中打开，文件中的任何修改都将自动同步。

## 保存一个文件

您可以保存工作区中的任何文件**谷歌驱动器**，** Dropbox的**或** GitHub的**通过打开**同步**子菜单，然后点击**节省**。即使工作区中的文件已经同步，您也可以将其保存到其他位置。StackEdit可以将一个文件与多个位置和帐户同步。

## 同步文件

一旦你的文件被链接到一个同步位置，StackEdit会定期通过下载/上传任何修改来同步它。合并将在必要时执行，冲突将得到解决。

如果您刚刚修改了文件并且想要强制同步，请单击导航栏中的**现在同步**按钮。

> **注：**的**立即同步**按钮是无效的，如果你没有文件同步。 

## 管理文件同步

由于一个文件可以与多个位置进行同步，你可以列出并通过单击管理同步位置**文件同步**的**同步**子菜单。这使您可以列出并删除链接到文件的同步位置。


＃出版物

通过StackEdit发布，您可以轻松地在线发布文件。一旦你对一个文件感到满意，你可以将它发布到不同的主机平台，如** Blogger **，** Dropbox **，** Gist **，** GitHub **，** Google Drive **，* * WordPress **和** Zendesk **。通过[ Handlebars模板 ]（http://handlebarsjs.com/），您可以完全控制您输出的内容。

> Before starting to publish, you must link an account in the **Publish** sub-menu.

## Publish a File

You can publish your file by opening the **Publish** sub-menu and by clicking **Publish to**. For some locations, you can choose between the following formats:

- Markdown: publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML: publish the file converted to HTML via a Handlebars template (on a blog for example).

## Update a publication

发布后，StackEdit会将您的文件链接到该出版物，以便您重新发布它。一旦你修改了你的文件，你想更新你的出版物，点击导航栏中的**立即发布**按钮。

> **注意：**现在**发布**按钮被禁用，如果您的文件尚未发布。 

## 管理文件发布

由于一个文件可以被发布到多个位置，你可以列出和管理通过点击发布位置**文件发布**的**发布**子菜单。这使您可以列出并删除链接到文件的发布位置。


＃降价扩展

StackEdit通过添加额外的** Markdown扩展**来扩展标准的Markdown语法，为您提供一些不错的功能。

> ** ProTip：**您可以在**文件属性**对话框中禁用任何** Markdown扩展**。 


## SmartyPants

SmartyPants将ASCII标点字符转换为“智能”印刷标点HTML实体。例如：

| | ASCII                           | HTML                          | | ---------------- | ------------------------------- | ----------------------------- | | 单个反引号| “这不是很有趣吗？” ` | “这不是很有趣吗？”            | | 行情           | ` “这不是很有趣吗？” ` | “这不是很有趣吗？”            | | Dashes           | ` - 是短划线，---是短划线` | - 是虚线，---是em-dash |                

            
            



## Katex公司

您可以使用[ KaTeX ]（https://khan.github.io/KaTeX/）渲染LaTeX数学表达式：

在*伽玛功能*满足$ \伽玛（ ñ ） = （ N-1 ）！ \四\ FORALL ñ \中\ mathbb ñ $是通过欧拉积分

$$ \伽玛（ ż ） = \ INT _0 ^ \ infty吨^ { Z-1 } E 1 { -t } dt的\， 。$$



> 您可以找到更多关于** LaTeX **数学表达式[ here ]（http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference）的信息。


## UML图

你可以使用[ Mermaid ]（https://mermaidjs.github.io/）来渲染UML图。例如，这将产生一个序列图：

```美人鱼
序列图片
爱丽丝 -  >>鲍勃：你好鲍勃，你好吗？
鲍勃 -  >>约翰：约翰，你呢？
Bob  -  x Alice：我很好，谢谢！
Bob-x John：我很好，谢谢！
注意约翰的权利：鲍勃想了很长时间，很久以前，文本不适合连续。Bob  - > Alice：与John 约会... Alice  - > John：是的...... John，你好吗？```





这将产生一个流程图：

```美人鱼
图LR 
A [Square Rect]  - 链接文字 - > B（（Circle））
A  - > C（Round Rect）
B  - > D {Rhombus} 
C  - > D```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyMzMxOTE3Ml19
-->