---
title: Operatore | - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312878"
---
# <a name="-operator-c-reference"></a>Operatore | (Riferimenti per C#)

Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`. Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi. Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.

## <a name="remarks"></a>Osservazioni

L'operatore binario `|` valuta i due operatori indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.

I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../keywords/operator.md)).

## <a name="example"></a>Esempio

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)