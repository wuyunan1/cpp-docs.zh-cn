---
title: /MANIFEST（创建并行程序集清单）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: 226deb9e8f7273e122e1b9074d2afca8970fc366
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508051"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST（创建并行程序集清单）

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>备注

/MANIFEST 指定链接器应创建通过并行清单文件。 有关清单文件的详细信息，请参阅[清单文件参考](/windows/desktop/SbsCs/manifest-files-reference)。

默认值为 /MANIFEST。

/MANIFEST:EMBED 选项指定链接器应该将清单文件作为 RT_MANIFEST 类型的资源嵌入映像。 可选 `ID` 参数是要用于清单的资源 ID。 对可执行文件使用值 1。 对 DLL 使用值 2 以使其能够指定专用依赖项。 如果未指定 `ID` 参数，当设置了 /DLL 选项时，默认值为 2；否则，默认值为 1。

从 Visual Studio 2008 开始，可执行文件的清单文件包含指定用户帐户控制 (UAC) 信息的节。 如果指定了 /MANIFEST 但未指定[/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)也不[/DLL](../../build/reference/dll-build-a-dll.md)，已将 UAC 级别设置为默认 UAC 片段*asInvoker*插入到清单。 有关 UAC 级别的详细信息，请参阅[/MANIFESTUAC （将 UAC 信息嵌入在清单中）](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)。

若要更改 UAC 的默认行为，请执行以下操作之一：

- 指定 /MANIFESTUAC 选项并将 UAC 级别设置为所需的值。

- 或者也可以指定 /MANIFESTUAC:NO 选项（如果不想在清单中生成 UAC 片段）。

如果未指定 /MANIFEST 但指定[/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)注释，将创建一个清单文件。 如果指定了 /MANIFEST:NO，则不会创建清单文件。

如果指定了 /MANIFEST，则清单文件的名称与输出文件的名称相同，并且会将 .manifest 追加到文件名。 例如，如果输出文件名是 MyFile.exe，则清单文件名是 MyFile.exe.manifest。  如果指定了 /MANIFESTFILE:*名称*，清单的名称是你在中指定*名称*。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 展开“配置属性”节点。

1. 展开**链接器**节点。

1. 选择**清单文件**属性页。

1. 修改**Generate Manifest**属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>。

## <a name="see-also"></a>请参阅

[设置链接器选项](../../build/reference/setting-linker-options.md)<br/>
[链接器选项](../../build/reference/linker-options.md)