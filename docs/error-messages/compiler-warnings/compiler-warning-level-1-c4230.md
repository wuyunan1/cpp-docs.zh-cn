---
title: 编译器警告（等级 1）C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: c8d223a286b8d42ca404fbfe7cbc51b67b3dd497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529646"
---
# <a name="compiler-warning-level-1-c4230"></a>编译器警告（等级 1）C4230

使用了记时错误： 修饰符/限定符交错; 忽略忽略限定符

使用 Microsoft 修饰符之前限定符，例如`__cdecl`是过时的做法。

## <a name="example"></a>示例

```
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```