---
title: __noop
ms.date: 11/04/2016
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 074ab4c6ea51c8b3a2543d9b43248a8da37567cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613000"
---
# <a name="noop"></a>__noop

**Microsoft 专用**

`__noop`内部函数，则指定应忽略函数和参数列表进行分析，但没有代码生成的自变量。 它被适用于在采用可变数量的参数的全局调试函数中使用。

编译器将为`__noop`0 在编译时的内部。

## <a name="example"></a>示例

下面的代码演示如何使用`__noop`。

```
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)<br/>
[关键字](../cpp/keywords-cpp.md)