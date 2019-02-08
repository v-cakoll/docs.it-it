---
title: Operatore <<= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258734"
---
# <a name="-operator-c-reference"></a>Operatore \<\<= (Riferimenti per C#)

Operatore di assegnazione di spostamento a sinistra.

## <a name="remarks"></a>Note

Un'espressione nel formato

```csharp
x <<= y
```

viene valutata come

```csharp
x = x << y
```

con la differenza che `x` viene valutato una sola volta. L'[operatore <<](left-shift-operator.md) sposta `x` verso sinistra del numero di bit specificato da `y`.

L'operatore `<<=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore <<](left-shift-operator.md) (vedere [operator](../keywords/operator.md)).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
