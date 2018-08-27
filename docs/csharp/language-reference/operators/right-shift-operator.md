---
title: '&gt;&gt; Operatore (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 7a2992befcacfdc1d9bb968b611051e15702cca8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924824"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt; Operatore (Riferimenti per C#)
L'operatore di spostamento a destra (`>>`) sposta verso destra il primo operando del numero di bit specificato dal secondo operando.  
  
## <a name="remarks"></a>Note  
 Se il primo operando è di tipo [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando (secondo operando e 0x1f).  
  
 Se il primo operando è di tipo [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando (secondo operando e 0x3f).  
  
 Se il primo operando è di tipo [int](../../../csharp/language-reference/keywords/int.md) o [long](../../../csharp/language-reference/keywords/long.md), lo spostamento a destra è uno spostamento aritmetico (i bit più significativi vuoti sono impostati sul bit di segno). Se il primo operando è di tipo [uint](../../../csharp/language-reference/keywords/uint.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md), lo spostamento a destra è uno spostamento logico (i bit più significativi vengono riempiti con zero).  
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>>`: il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere [int](../../../csharp/language-reference/keywords/int.md). Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md). Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
