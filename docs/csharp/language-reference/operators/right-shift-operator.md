---
title: '>> Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 703d4ee50bb9f49c66df029de9c5a280449d11fa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255315"
---
# <a name="-operator-c-reference"></a>Operatore >> (Riferimenti per C#)

L'operatore di spostamento a destra (`>>`) sposta verso destra il primo operando del numero di bit specificato dal secondo operando.

## <a name="remarks"></a>Note

Se il primo operando è di tipo [int](../keywords/int.md) o [uint](../keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando (secondo operando e 0x1f).

Se il primo operando è di tipo [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando (secondo operando e 0x3f).

Se il primo operando è di tipo [int](../keywords/int.md) o [long](../keywords/long.md), lo spostamento a destra è uno spostamento aritmetico (i bit più significativi vuoti sono impostati sul bit di segno). Se il primo operando è di tipo [uint](../keywords/uint.md) o [ulong](../keywords/ulong.md), lo spostamento a destra è uno spostamento logico (i bit più significativi vengono riempiti con zero).

I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>>`: il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere [int](../keywords/int.md). Per altre informazioni, vedere l'argomento relativo all'[operatore](../keywords/operator.md). Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)