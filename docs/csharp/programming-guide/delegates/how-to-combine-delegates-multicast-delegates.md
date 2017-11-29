---
title: 'Procedura: combinare delegati multicast (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ddb4ecbbf456179e91aa0003c2dc5653f153411f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Procedura: combinare delegati multicast (Guida per programmatori C#)
Questo esempio illustra come creare delegati multicast. Una proprietà utile degli oggetti [delegate](../../../csharp/language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`. Il delegato multicast contiene un elenco dei delegati assegnati. Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine. Solo i delegati dello stesso tipo possono essere combinati.  
  
 L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.MulticastDelegate>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Eventi](../../../csharp/programming-guide/events/index.md)
