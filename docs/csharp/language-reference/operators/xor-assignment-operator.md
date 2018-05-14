---
title: Operatore ^= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 0315cab66729d8169527c4b0ba7e00ab3b5ad5da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operatore ^= (Riferimenti per C#)
Operatore di assegnazione OR esclusivo.  
  
## <a name="remarks"></a>Note  
 Un'espressione nel formato  
  
```  
x ^= y  
```  
  
 viene valutata come  
  
```  
x = x ^ y  
```  
  
 con la differenza che `x` viene valutato una sola volta. L'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
