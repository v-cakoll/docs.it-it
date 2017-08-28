---
title: Delegati con metodi denominati e anonimi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
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
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Delegati con metodi denominati e anonimi (Guida per programmatori C#)
È possibile associare un [delegato](../../../csharp/language-reference/keywords/delegate.md) a un metodo denominato. Quando si crea un'istanza di un delegato usando un metodo denominato, il metodo viene passato come parametro, ad esempio:  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 La chiamata viene eseguita usando un metodo denominato. I delegati costruiti con un metodo denominato possono incapsulare un metodo [statico](../../../csharp/language-reference/keywords/static.md) o un metodo di istanza. I metodi denominati rappresentano l'unico modo per creare un'istanza di un delegato nelle versioni precedenti di C#. In una situazione in cui la creazione di un nuovo metodo rappresenta un sovraccarico inutile, tuttavia, C# consente di creare un'istanza di un delegato e di specificare immediatamente un blocco di codice che verrà elaborato dal delegato al momento della chiamata. Il blocco può contenere un'espressione lambda oppure un metodo anonimo. Per altre informazioni, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Note  
 La firma del metodo che viene passato come parametro del delegato deve essere uguale a quella della dichiarazione del delegato.  
  
 Un'istanza di delegato può incapsulare un metodo statico o un metodo di istanza.  
  
 Anche se il delegato può usare un parametro [out](../../../csharp/language-reference/keywords/out.md), è consigliabile non usarlo con delegati di eventi multicast perché non è possibile sapere quale delegato verrà chiamato.  
  
## <a name="example-1"></a>Esempio 1  
 Di seguito è illustrato un semplice esempio di dichiarazione e uso di un delegato. Si noti che sia il delegato, `Del`, che il metodo associato, `MultiplyNumbers`, hanno la stessa firma  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a>Esempio 2  
 Nell'esempio che segue un delegato viene mappato sia al metodo statico che al metodo di istanza e restituisce informazioni specifiche da ciascuno di essi.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Delegati](../../../csharp/programming-guide/delegates/index.md)   
 [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [Procedura: Combinare delegati multicast](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [Eventi](../../../csharp/programming-guide/events/index.md)

