---
title: 'Procedura: combinare delegati multicast (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
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
ms.openlocfilehash: 617af10d3fb5f9371d5893b87a91a48639d44a53
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Procedura: combinare delegati multicast (Guida per programmatori C#)
Questo esempio illustra come creare delegati multicast. Una proprietà utile degli oggetti [delegate](../../../csharp/language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`. Il delegato multicast contiene un elenco dei delegati assegnati. Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine. Solo i delegati dello stesso tipo possono essere combinati.  
  
 L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.MulticastDelegate>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Eventi](../../../csharp/programming-guide/events/index.md)

