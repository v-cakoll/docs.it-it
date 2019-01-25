---
title: Operatore ^= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333551"
---
# <a name="-operator-c-reference"></a>Operatore ^= (Riferimenti per C#)

Operatore di assegnazione OR esclusivo.

## <a name="remarks"></a>Note

Un'espressione nel formato

```csharp
x ^= y
```

viene valutata come

```csharp
x = x ^ y
```

con la differenza che `x` viene valutato una sola volta. L'[operatore ^](xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../keywords/bool.md).

L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](xor-operator.md) (vedere [operator](../keywords/operator.md)).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)