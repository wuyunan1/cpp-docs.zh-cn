---
title: 编译器错误 C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 137913e0c6909712cbb6745666112d315925ab0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618993"
---
# <a name="compiler-error-c3743"></a>编译器错误 C3743

可以仅挂钩/解除挂钩整个接口当 event_receiver 的 layout_dependent 参数为 true

[__Unhook](../../cpp/unhook.md)函数在它根据采用传递给的值的参数数量发生变化`layout_dependent`中的参数[event_receiver](../../windows/event-receiver.md)类。

下面的示例生成 C3743:

```
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```