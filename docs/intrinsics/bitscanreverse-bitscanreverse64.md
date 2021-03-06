---
title: _BitScanReverse、_BitScanReverse64
ms.date: 11/04/2016
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
ms.openlocfilehash: f1c33f90fc8e44388068f0588d33effd80fc203c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586415"
---
# <a name="bitscanreverse-bitscanreverse64"></a>_BitScanReverse、_BitScanReverse64

**Microsoft 专用**

从设置位 (1) 的最高有效位 (MSB) 到最低有效位 (LSB) 搜索掩码数据。

## <a name="syntax"></a>语法

```
unsigned char _BitScanReverse(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanReverse64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>参数

*Tuple*<br/>
[out]使用找到的第一个设置位 (1) 的位位置加载。

*掩码*<br/>
[in]要搜索的 32 位或 64 位值。

## <a name="return-value"></a>返回值

如果设定 `Index`，则为非零，如果未发现设置位，则为 0。

## <a name="requirements"></a>要求

|内部函数|体系结构|Header|
|---------------|------------------|------------|
|`_BitScanReverse`|x86、 ARM、 x64|\<intrin.h>|
|`_BitScanReverse64`|ARM、 x64||

## <a name="example"></a>示例

```
// BitScanReverse.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanReverse)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanReverse(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>输入

```
12
```

## <a name="sample-output"></a>示例输出

```
Enter a positive integer as the mask:
Mask: 12 Index: 3
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)