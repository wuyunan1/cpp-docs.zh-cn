---
title: 编译器警告（等级 1）C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: ed27e6ff63e3d5f3bab4f6d8d9639b84a5606ff2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563928"
---
# <a name="compiler-warning-level-1-c4224"></a>编译器警告（等级 1）C4224

使用了非标准扩展： 形参 identifier 以前被定义为一种类型

以前用作标识符`typedef`。 这将导致 ANSI 兼容性警告 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="example"></a>示例

```
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```