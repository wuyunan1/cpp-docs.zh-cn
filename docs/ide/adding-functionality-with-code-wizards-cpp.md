---
title: 用代码向导添加功能 (C++)
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.classes
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: d96b02317f88abd426ceaca4a239e59b2c88b585
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629861"
---
# <a name="adding-functionality-with-code-wizards-c"></a>用代码向导添加功能 (C++)

创建项目后，你会需要更改或添加该项目的功能。 这类任务包括创建新类、添加新成员函数和变量以及添加自动化方法和属性。 可使用代码向导执行所有这些操作。

> [!WARNING]
> 多个 ATL 和 MFC 代码向导现已弃用，并将从 Visual Studio 的将来版本中删除。 很少使用这些向导。 对 ATL 和 MFC 的常规支持不会受到删除这些向导的影响。 如果你想要共享对此弃用的反馈，请完成[此调查](https://www.surveymonkey.com/r/QDWKKCN)。 你的反馈对我们很重要。

> [!NOTE]
>  现在可以添加消息处理程序并将消息映射到它们，然后使用[属性窗口](/visualstudio/ide/reference/properties-window)替代 MFC 虚函数。

## <a name="accessing-visual-c-code-wizards"></a>访问 Visual C++ 代码向导

可从三个位置访问 Visual C++ 代码向导：

- 使用“项目”菜单上的“添加新项”命令打开 `Add New Item` 对话框，此对话框有助于将新文件添加到你的项目。 “添加类”命令显示[添加类](../ide/add-class-dialog-box.md)对话框，对于可以添加到项目的每个类类型，此对话框可为依次打开向导。 “添加资源”命令显示[添加资源](../windows/add-resource-dialog-box.md)对话框，可以从该对话框创建或选择要添加到项目的资源。

   如果在类视图中突出显示项目中的一个类或接口，则“项目”菜单还会显示以下命令：

   - **实现接口**（仅从控件类实现）

   - **添加函数**

   - **添加变量**

   - **添加连接点**（仅适用于 ATL 类）

   - **添加方法**（仅从接口添加）

   - **添加属性**（仅从接口添加）

   - **添加事件**（仅从控件类添加）

- 在“解决方案资源管理器”中，右键单击任一文件夹并单击快捷菜单中的“添加”，可将新文件或现有文件、更多文件夹、项、类、资源和 Web 引用添加到项目。

- 从[类视图窗口](/visualstudio/ide/viewing-the-structure-of-code)，右键单击适当的节点并单击快捷菜单中的“添加”，可将函数、变量、类、属性、方法、事件、接口、连接点或其他代码添加到项目。

   > [!NOTE]
   > Visual Studio 不提供将接口添加到项目的向导。 可将接口添加到 ATL 项目或通过使用 [ATL 简单对象向导](../atl/reference/atl-simple-object-wizard.md)添加一个简单项目，从而[向 MFC 项目添加 ATL 支持](../mfc/reference/adding-atl-support-to-your-mfc-project.md)。 或者打开项目的 .idl 文件并通过键入以下内容创建接口：

    ```IDL
    interface IMyInterface {
    };
    ```

   有关详细信息，请参阅[实现接口](../ide/implementing-an-interface-visual-cpp.md)和[向 ATL 项目添加对象和控件](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)。

   |访问代码向导的途径|描述|
   |-----------------------------|-----------------|
   |添加新项|“添加新项”代码向导将源文件添加到项目。 如有必要，创建其他目录来包含项目生成引擎所需的文件。 可从添加项图标访问的代码向导包括：<br /><br />- 添加 C++ 源文件（.cpp、.h、.idl、.rc、.srf、.def 和 .rgs）。<br />- 添加 Web 开发文件（.html、.asp、.css 和 .xml）。<br />- 添加实用工具和资源文件（.bmp、.cur、.ico、.rct、.sql 和 .txt）。<br /><br />这些代码向导通常会将文件添加到你的开发树但不会询问任何信息。 你可以重命名属性窗口中的文件。|
   |“解决方案资源管理器”|解决方案资源管理器中可用的代码向导取决于右键单击某项时光标焦点的位置。 如果右键单击某项时没有出现“添加”选项，请在开发树中将光标向上移动一级并重试。 代码向导会始终将其他代码放在开发树中适当的位置，且不受光标位置的影响。 可从解决方案资源管理器访问的代码向导包括：<br /><br />- 添加类（打开包含新代码向导的“添加类”对话框）。<br />- 添加资源（新建、导入或自定义）。<br />- 添加 Web 引用。|
   |类视图|类视图中可用的代码向导取决于右键单击某个项时光标焦点的位置。 如果右键单击某项时没有出现“添加”选项，请在类树中将光标向上移动一级并重试。 代码向导会始终将其他代码放在开发树中适当的位置，且不受光标位置的影响。 可从类视图访问的代码向导包括：<br /><br />- [添加成员函数](../ide/adding-a-member-function-visual-cpp.md)。<br />- [添加成员变量](../ide/adding-a-member-variable-visual-cpp.md)。<br />- [添加类](../ide/adding-a-class-visual-cpp.md)。<br />- [实现接口](../ide/implement-interface-wizard.md)（仅从控件类实现）<br />- [添加连接点](../ide/implement-connection-point-wizard.md)（仅适用于 ATL 类）<br />- [添加方法](../ide/add-method-wizard.md)（仅从接口添加）<br />- [添加属性](../ide/names-add-property-wizard.md)（仅从接口添加）<br />- [添加事件](../ide/add-event-wizard.md)（仅从控件类添加）<br /><br />选择“添加类”打开“添加类”对话框，此对话框能让你访问所有新的“添加类”代码向导。|

## <a name="see-also"></a>请参阅

[重写虚函数](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[导航类结构](../ide/navigating-the-class-structure-visual-cpp.md)<br>
[使用应用程序向导创建桌面项目](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
[Visual C++ 项目类型](../ide/visual-cpp-project-types.md)<br>
[为 Visual C++ 项目创建的文件类型](../ide/file-types-created-for-visual-cpp-projects.md)
