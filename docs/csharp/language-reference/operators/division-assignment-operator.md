---
title: Operatore /= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>Operatore /= (Riferimenti per C#)
Operatore di assegnazione di divisione.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `/=`, ad esempio  
  
```csharp  
x /= y  
```  
  
 equivale a  
  
```csharp  
x = x / y  
```  
  
 con la differenza che `x` viene valutato una sola volta. L'[operatore /](../../../csharp/language-reference/operators/division-operator.md) è già definito per i tipi numerici per l'esecuzione di divisioni.  
  
 L'operatore `/=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore /](../../../csharp/language-reference/operators/division-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)). Su tutti gli operatori di assegnazione composti, l'overload dell'operatore binario esegue in modo implicito l'overload dell'assegnazione composta equivalente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
