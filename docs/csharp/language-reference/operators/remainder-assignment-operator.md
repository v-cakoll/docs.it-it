---
title: Operatore %= (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998656"
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

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
