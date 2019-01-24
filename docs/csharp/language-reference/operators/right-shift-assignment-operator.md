---
title: Operatore &gt;&gt;= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333689"
---
# <a name="gtgt-operator-c-reference"></a>Operatore &gt;&gt;= (Riferimenti per C#)

Operatore di assegnazione di spostamento a destra.

## <a name="remarks"></a>Note

Un'espressione nel formato

```csharp
x >>= y
```

viene valutata come

```csharp
x = x >> y
```

con la differenza che `x` viene valutato una sola volta. L'[operatore >>](right-shift-operator.md) sposta `x` verso destra di una quantità specificata da `y`.

L'operatore >>= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore >>](right-shift-operator.md) (vedere [operator](../keywords/operator.md)).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)