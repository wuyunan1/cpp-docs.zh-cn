---
title: 常规 MBCS 编程建议
ms.date: 11/04/2016
f1_keywords:
- _mbcs
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
ms.openlocfilehash: 800e94bfb8a52b806ad45368499f126fbf163389
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626690"
---
# <a name="general-mbcs-programming-advice"></a>常规 MBCS 编程建议

使用以下提示：

- 对于大的灵活性，如使用运行宏`_tcschr`和`_tcscpy`在可能的情况。 有关详细信息，请参阅[tchar.h 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。

- 使用 C 运行时`_getmbcp`函数以获取有关当前代码页的信息。

- 不要重复使用字符串资源。 根据目标语言中，给定的字符串可能具有不同的含义时转换。 例如，"文件"上应用程序的主菜单中可能转换以不同的方式从"文件"对话框中的字符串。 如果您需要使用多个字符串具有相同的名称，为每个使用不同的字符串 Id。

- 你可能想要查看是否已启用 MBCS 的操作系统上运行你的应用程序。 为此，请设置一个标志，在程序启动时;不要依赖于 API 调用。

- 在设计时对话框，允许约 30%的 MBCS 转换为静态文本控件末尾的额外空间。

- 要为应用程序中，选择字体时小心因为某些字体不可用的所有系统上。

- 选择时对话框的字体，请使用[MS Shell Dlg](/windows/desktop/Intl/using-ms-shell-dlg-and-ms-shell-dlg-2)而不是 MS Sans Serif 或 Helvetica。 MS Shell Dlg 将被替换为正确的字体由系统创建对话框的之前。 使用 MS Shell Dlg 可确保的要处理此字体的操作系统中的任何更改将自动在可用。 （MFC 替换 MS Shell Dlg DEFAULT_GUI_FONT 或 Windows 95、 Windows 98 和 Windows NT 4 中的系统字体因为这些系统未正确地处理 MS Shell Dlg。）

- 在设计你的应用程序时，决定进行本地化的字符串。 如果有疑问，假定任何给定的字符串会被本地化。 在这种情况下，不要使用不能混合可本地化的字符串。

## <a name="see-also"></a>请参阅

[MBCS 编程提示](../text/mbcs-programming-tips.md)<br/>
[递增和递减指针](../text/incrementing-and-decrementing-pointers.md)
