---
title: Operatore |= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194507"
---
# <a name="-operator-c-reference"></a>Operatore |= (Riferimenti per C#)
Operatore di assegnazione OR.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `|=`, ad esempio  
  
```csharp  
x |= y  
```  
  
 equivale a  
  
```csharp  
x = x | y  
```  
  
 con la differenza che `x` viene valutato una sola volta. L'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) esegue un'operazione con OR logico bit per bit su operandi integrali e un'operazione con OR logico sugli operandi bool.  
  
 L'operatore `|=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
