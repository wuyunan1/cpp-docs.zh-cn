---
title: 编译器错误 C3017
ms.date: 11/04/2016
f1_keywords:
- C3017
helpviewer_keywords:
- C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
ms.openlocfilehash: 7172d870c509e79bf0900604302c38bc6ca9cd77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506712"
---
# <a name="compiler-error-c3017"></a>编译器错误 C3017

OpenMP“for”语句中的终止测试格式不正确

必须完全或显式指定 OpenMP 语句中的 `for` 循环。

下面的示例生成 C3017：

```
// C3017.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i; ++i)   // C3017
      // Try the following line instead:
      // for (i = 0; i < 10; ++i)
         ;
   }
}
```