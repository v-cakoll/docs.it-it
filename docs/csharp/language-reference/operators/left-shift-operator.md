---
title: Operatore << - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 0271c97bc624a8946b90508e9ce39d217a128c05
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261750"
---
# <a name="-operator-c-reference"></a>Operatore \<\< (Riferimenti per C#)

L'operatore di spostamento a sinistra (`<<`) sposta verso sinistra il primo operando del numero di bit specificato dal secondo operando. Il tipo del secondo operando deve essere un [int](../keywords/int.md) o un tipo con una conversione numerica implicita predefinita in `int`.

## <a name="remarks"></a>Note

Se il primo operando è di tipo [int](../keywords/int.md) o [uint](../keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando. Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 31 bit.

Se il primo operando è di tipo [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando. Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 63 bit.

Tutti i bit più significativi che non rientrano nell'intervallo del tipo del primo operando dopo lo spostamento vengono scartati, mentre i bit vuoti meno significativi vengono riempiti con zero. Le operazioni di spostamento non provocano mai overflow.

I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<<` (vedere [operator](../keywords/operator.md)): il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere `int`. Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>Commenti

Osservare come `i<<1` e `i<<33` generino lo stesso risultato, poiché 1 e 33 hanno gli stessi cinque bit meno significativi.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
