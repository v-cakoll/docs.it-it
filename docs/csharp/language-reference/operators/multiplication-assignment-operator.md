---
title: Operatore *= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333434"
---
# <a name="-operator-c-reference"></a>Operatore \*= (Riferimenti per C#)

Operatore di assegnazione di moltiplicazione binario.

## <a name="remarks"></a>Note

Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio

```csharp
x *= y
```

equivale a

```csharp
x = x * y
```

con la differenza che `x` viene valutato una sola volta. Per i tipi numerici l'[operatore \*](multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.

L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore \*](multiplication-operator.md) (vedere [operator](../keywords/operator.md)).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
