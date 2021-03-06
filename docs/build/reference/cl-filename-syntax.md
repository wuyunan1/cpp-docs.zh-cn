---
title: CL 文件名语法
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: 929096ed169a33e0876c3afb68f3594757d61e4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438930"
---
# <a name="cl-filename-syntax"></a>CL 文件名语法

CL 接受具有遵循 FAT、HPFS 或 NTFS 命名约定的名称的文件。 任何文件名均可以包含完整或部分路径。 完整路径包括驱动器名和一个或多个目录名。 CL 接受文件名分隔由反斜杠 (\\) 或正斜杠 （/）。 包含空格文件名必须用双引号字符引起来。 部分路径忽略 CL 假定为当前驱动器的驱动器名。 如果不指定路径，则 CL 假定该文件位于当前目录。

文件扩展名确定处理文件的方式。 已编译具有扩展名 .c、.cxx 或 .cpp 的 C 和 C++ 文件。 将其他文件（包括 .obj 文件、库 (.lib) 和模块定义 (.def) 文件）传递给链接器而无需处理。

## <a name="see-also"></a>请参阅

[编译器命令行语法](../../build/reference/compiler-command-line-syntax.md)