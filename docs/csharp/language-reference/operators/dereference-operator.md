---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a>-&gt; Operatore (Riferimenti per C#)
L'operatore `->` combina la deferenziazione del puntatore e l'accesso ai membri.  
  
## <a name="remarks"></a>Note  
 Un'espressione nel formato  
  
```  
x->y  
```  
  
 (dove `x` è un puntatore di tipo `T*` e `y` è un membro di `T`) è equivalente a  
  
```  
(*x).y  
```  
  
 L'operatore `->` può essere usato solo nel codice contrassegnato come [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Non è possibile eseguire l'overload dell'operatore `->`.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

