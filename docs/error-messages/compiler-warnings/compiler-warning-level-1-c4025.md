---
title: 编译器警告（等级 1）C4025
ms.date: 11/04/2016
f1_keywords:
- C4025
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
ms.openlocfilehash: 50e5ad586a754723cbb66685a14de2e23f0bdb7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605213"
---
# <a name="compiler-warning-level-1-c4025"></a>编译器警告（等级 1）C4025

“编号”: 基指针传递给带变量参数的函数: 参数号

将基指针传递给使用变量参数的函数会导致指针被规范化，结果不可预知。 请勿将基指针传递给带变量参数的函数。