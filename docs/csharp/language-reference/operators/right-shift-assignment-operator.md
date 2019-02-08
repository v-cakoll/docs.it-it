---
title: '>>Operatore = - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278980"
---
# <a name="-operator-c-reference"></a>Operatore >>= (Riferimenti per C#)

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