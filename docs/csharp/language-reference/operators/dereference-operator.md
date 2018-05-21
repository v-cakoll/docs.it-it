---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 037229b2081a43077cb4b5d02a8929b06ba9e077
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-gt-operator-c-reference"></a>-&gt; Operatore (Riferimenti per C#)
L'operatore `->` combina la deferenziazione del puntatore e l'accesso ai membri.  
  
## <a name="remarks"></a>Note  
 Un'espressione nel formato  
  
```csharp  
x->y  
```  
  
 (dove `x` è un puntatore di tipo `T*` e `y` è un membro di `T`) è equivalente a  
  
```csharp  
(*x).y  
```  
  
 L'operatore `->` può essere usato solo nel codice contrassegnato come [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Non è possibile sottoporre l'operatore `->` a overload.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
