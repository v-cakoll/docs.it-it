---
title: Operatore -= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333330"
---
# <a name="--operator-c-reference"></a>Operatore -= (Riferimenti per C#)

Operatore di assegnazione di sottrazione.

## <a name="remarks"></a>Note

Un'espressione che usa l'operatore di assegnazione `-=`, ad esempio

```csharp
x -= y
```

 equivale a

```csharp
x = x - y
```

con la differenza che `x` viene valutato una sola volta. Il significato dell'[operatore -](subtraction-operator.md) dipende dai tipi di `x` e `y` (sottrazione per gli operandi numerici, rimozione del delegato per gli operandi delegati e così via).

L'operatore `-=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore -](subtraction-operator.md) (vedere [operator](../keywords/operator.md)).

L'operatore -= viene anche usato in C# per annullare la sottoscrizione a un evento. Per altre informazioni, vedere [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
