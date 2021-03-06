---
title: /homeparams（将寄存器参数复制到堆栈）
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: ffb5ca602feb7a369bb31d0277834786d66ac12a
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627395"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams（将寄存器参数复制到堆栈）

强制参数传入寄存器也写入到其位置在函数入口的堆栈上。

## <a name="syntax"></a>语法

> **/homeparams**

## <a name="remarks"></a>备注

此编译器选项才可用在本机和跨平台编译器面向 x64 的。

X64 调用约定需要堆栈空间，并将其分配的所有参数，甚至在寄存器中传递的参数。 有关详细信息，请参阅[参数传递](../../build/x64-calling-convention.md#parameter-passing)。 默认情况下，将寄存器参数不会复制到发布版本中为它们分配的堆栈空间。 这使得难以调试优化的发布版本的程序。

用于发布版本，可以使用 **/homeparams**选项强制编译器将注册到堆栈，以便确保您可以调试应用程序的参数。 **/homeparams**意味着性能降低，因为它需要一个额外的周期将寄存器参数复制到堆栈上的。

在调试版本中，堆栈是始终填充在寄存器中传递的参数。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 打开**配置属性** > **C/c + +** > **命令行**属性页。

1. 输入中的编译器选项**其他选项**框。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[编译器选项](../../build/reference/compiler-options.md)<br/>
[设置编译器选项](../../build/reference/setting-compiler-options.md)