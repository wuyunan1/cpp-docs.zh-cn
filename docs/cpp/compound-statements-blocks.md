---
title: 复合语句（块）
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 6aef2a0b5716ab501fabe80f0dda15080abe3ff5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591781"
---
# <a name="compound-statements-blocks"></a>复合语句（块）

复合语句包含零个或多个语句包含在大括号 (**{}**)。 可以在任何期望语句出现的位置使用复合语句。 复合语句通常称为“块”。

## <a name="syntax"></a>语法

```
{ [ statement-list ] }
```

## <a name="remarks"></a>备注

下面的示例使用复合语句作为*语句*的一部分**如果**语句 (请参阅[if 语句](../cpp/if-else-statement-cpp.md)有关语法的详细信息):

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
>  声明是一个语句，因为一个声明可以是中的语句之一*语句列表*。 因此，复合语句内声明的名称（而不是显式声明为静态的名称）具有局部范围和（对于对象）生存期。 请参阅[作用域](../cpp/scope-visual-cpp.md)具有局部范围的名称的处理方式有关的详细信息。

## <a name="see-also"></a>请参阅

[ 语句概述](../cpp/overview-of-cpp-statements.md)