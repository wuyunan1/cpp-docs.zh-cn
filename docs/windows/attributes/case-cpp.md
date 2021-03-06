---
title: 用例 （c + + COM 属性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: 1ed107b78ea5638d93a773e19de13b4c1fe1036c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648404"
---
# <a name="case-c"></a>case (C++)

用于[switch_type](switch-type.md)属性中**union**。

## <a name="syntax"></a>语法

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>参数

*value*<br/>
你想要提供的处理可能输入的值。 类型**值**可以是以下类型之一：

- `int`

- `char`

- `boolean`

- `enum`

或此类类型的标识符。

## <a name="remarks"></a>备注

**用例**c + + 属性具有相同的功能**用例**MIDL 特性。 此属性仅用于[switch_type](switch-type.md)属性。

## <a name="example"></a>示例

下面的代码演示的一种用法**用例**属性：

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|成员**类**或**结构**|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)<br/>
[类特性](class-attributes.md)