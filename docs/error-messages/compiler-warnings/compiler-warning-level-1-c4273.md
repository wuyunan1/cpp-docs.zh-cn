---
title: 编译器警告（等级 1）C4273
ms.date: 11/04/2016
f1_keywords:
- C4273
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
ms.openlocfilehash: 4d00ed0113f9954e7400da24f37b51b9fdd247bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544321"
---
# <a name="compiler-warning-level-1-c4273"></a>编译器警告（等级 1）C4273

function： 不一致的 DLL 链接

在使用不同的文件中的两个定义[dllimport](../../cpp/dllexport-dllimport.md)。

## <a name="example"></a>示例

下面的示例生成 C4273。

```
// C4273.cpp
// compile with: /W1 /c
char __declspec(dllimport) c;
char c;   // C4273, delete this line or the line above to resolve
```

## <a name="example"></a>示例

下面的示例生成 C4273。

```
// C4273_b.cpp
// compile with: /W1 /clr /c
#include <stdio.h>
extern "C" int printf_s(const char *, ...);   // C4273
```