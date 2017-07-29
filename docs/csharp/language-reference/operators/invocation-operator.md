---
title: Operatore () (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operatore () (Riferimenti per C#)
Oltre a specificare l'ordine in cui devono essere eseguite le operazioni di un'espressione, le parentesi vengono usate per eseguire le operazioni seguenti:  
  
1.  Specificare i cast, ovvero le conversioni di tipi.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Richiamare metodi o delegati.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>Note  
 Un cast richiama l'operatore di conversione in modo esplicito da un tipo a un altro. Se tale operatore di conversione non viene definito, il cast non sarà eseguito correttamente. Per informazioni sulla definizione di un operatore di conversione, vedere [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).  
  
 Non è possibile sottoporre l'operatore `()` a overload.  
  
 Per altre informazioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Un'espressione cast può determinare una sintassi ambigua. Ad esempio, l'espressione `(x)–y` potrebbe essere interpretata come espressione cast (un cast di -y sul tipo x) oppure come espressione di addizione combinata con un'espressione tra parentesi che calcola il valore x - y.  
  
 Per altre informazioni sulla chiamata al metodo, vedere [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

