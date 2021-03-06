---
title: 从 DHTML 调用 c + + 代码
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: 0fa4f51f4488be61edb0f01d9fddc956cd7a45b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555189"
---
# <a name="calling-c-code-from-dhtml"></a>从 DHTML 调用 c + + 代码

DHTML 控件可以托管在一个容器，例如测试容器或 Internet 资源管理器。 请参阅[使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md)有关如何访问测试容器的信息。

托管控件的容器与使用普通的控件接口的控件进行通信。 DHTML 使用结尾"UI"与 c + + 代码和 HTML 资源进行通信的调度接口。 在中[修改 ATL DHTML 控件](../atl/modifying-the-atl-dhtml-control.md)，您可以练习添加要由这些不同的接口调用的方法。

若要从 DHTML 调用 c + + 代码的示例，请参阅[创建 DHTML 控件](../atl/creating-an-atl-dhtml-control.md)使用 ATL 控件向导，并检查代码和 HTML 文件中的标头文件。

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>将标头文件中的 WebBrowser 方法声明

若要调用 DHTML UI 中的 c + + 方法，必须将方法添加到控件的 UI 接口。 例如，ATL 控件向导创建的标头文件包含 c + + 方法`OnClick`，这是向导生成控件的 UI 接口的成员。

检查`OnClick`控件的.h 文件中：

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

第一个参数， *pdispBody*，是对正文对象的调度接口的指针。 第二个参数， *varColor*，标识要应用于控件的颜色。

## <a name="calling-c-code-in-the-html-file"></a>调用 HTML 文件中的 c + + 代码

一旦声明的标头文件中的 WebBrowser 方法后，可以调用 HTML 文件中的方法。 请注意，在 HTML 文件 ATL 控件向导将插入三个 Windows 调度方法： 三个`OnClick`调度消息，以便更改该控件的背景色的方法。

检查 HTML 文件中的方法之一：

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

在窗口外部方法，上面的 HTML 代码`OnClick`，作为按钮标记的一部分调用。 该方法具有两个参数： `theBody`，它引用 HTML 文档的正文和`"red"`，指示单击按钮时，该控件的背景色，更改为红色。 `Red`后面标记是按钮的标签。

请参阅[修改 ATL DHTML 控件](../atl/modifying-the-atl-dhtml-control.md)有关提供你自己的方法的详细信息。 请参阅[标识 DHTML 控件项目的元素](../atl/identifying-the-elements-of-the-dhtml-control-project.md)有关 HTML 文件的详细信息。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)

