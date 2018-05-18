---
title: Operatore &gt;&gt;= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 41203f6e7c9929bb349d29c40cf7cc6c24550c36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-c-reference"></a>Operatore &gt;&gt;= (Riferimenti per C#)
Operatore di assegnazione di spostamento a destra.  
  
## <a name="remarks"></a>Note  
 Un'espressione nel formato  
  
```  
x >>= y  
```  
  
 viene valutata come  
  
```  
x = x >> y  
```  
  
 con la differenza che `x` viene valutato una sola volta. L'[operatore >>](../../../csharp/language-reference/operators/right-shift-operator.md) sposta `x` verso destra di una quantità specificata da `y`.  
  
 L'operatore >>= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
