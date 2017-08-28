---
title: Operatore += (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
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
ms.openlocfilehash: 42567b2d8e7d9b694ce64ccb88e0fd4bfe05b020
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operatore += (Riferimenti per C#)
Operatore di assegnazione di addizione.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `+=`, ad esempio  
  
```  
x += y  
```  
  
 equivale a  
  
```  
x = x + y  
```  
  
 con la differenza che `x` viene valutato una sola volta. Il significato dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) dipende dai tipi di `x` e `y` (addizione per gli operandi numerici, concatenazione per gli operandi stringa e così via).  
  
 L'operatore `+=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 L'operatore `+=` viene usato anche per specificare un metodo che verrà chiamato in risposta a un evento. I metodi di questo tipo sono chiamati gestori eventi. L'uso dell'operatore `+=` in questo contesto è detto *sottoscrizione di un evento*. Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) e [Delegati](../../../csharp/programming-guide/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

