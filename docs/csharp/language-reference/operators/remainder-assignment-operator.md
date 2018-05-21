---
title: Operatore %= (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: aadcb5ef969ff408cc1e738fc0f5b67152fdc78b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>Operatore %= (Riferimenti per C#)
Operatore di assegnazione di resto.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `%=`, ad esempio  
  
```csharp  
x %= y  
```  
  
 equivale a  
  
```csharp  
x = x % y  
```  
  
 con la differenza che `x` viene valutato una sola volta. Per i tipi numerici, l'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) è predefinito per calcolare il resto dopo una divisione.  
  
 L'operatore `%=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) (vedere [operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
