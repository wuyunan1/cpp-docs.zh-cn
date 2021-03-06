---
title: 在以前版本的运行时上运行 C++ -clr 应用程序
ms.date: 11/04/2016
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
ms.openlocfilehash: effcda9de1cb1005855f5752060dc61e28dcebf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581514"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>在以前版本的运行时上运行 C++ /clr 应用程序

除非另行指定，否则 C++.NET Framework 应用程序将在编译器用于生成该应用程序的公共语言运行时 (CLR) 版本上运行。 但是，针对一个版本生成的.exe 应用程序可以在提供必需功能的任何其他版本上运行。

若要完成此操作，请提供包含 `supportedRuntime` 标记中运行时版本信息的 app.config 文件。

在运行时，app.config 文件必须具有 filename.ext.config 形式的名称，其中 filename.ext 是启动该应用程序的可执行文件的名称，并且它必须与可执行文件位于同一目录。 例如，如果应用程序名为 TestApp.exe，则 app.config 文件的名称应为 TestApp.exe.config。

如果指定多个运行时版本，并且应用程序在已安装多个运行时版本的计算机上运行，应用程序将使用在配置文件中指定且已安装的第一个版本。

## <a name="see-also"></a>请参阅

[部署桌面应用程序](../ide/deploying-native-desktop-applications-visual-cpp.md)