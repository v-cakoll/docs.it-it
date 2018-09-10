---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190228"
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

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
