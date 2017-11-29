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
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="242e3-102">Procedura: combinare delegati multicast (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="242e3-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="242e3-103">Questo esempio illustra come creare delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="242e3-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="242e3-104">Una proprietà utile degli oggetti [delegate](../../../csharp/language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="242e3-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="242e3-105">Il delegato multicast contiene un elenco dei delegati assegnati.</span><span class="sxs-lookup"><span data-stu-id="242e3-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="242e3-106">Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine.</span><span class="sxs-lookup"><span data-stu-id="242e3-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="242e3-107">Solo i delegati dello stesso tipo possono essere combinati.</span><span class="sxs-lookup"><span data-stu-id="242e3-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="242e3-108">L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.</span><span class="sxs-lookup"><span data-stu-id="242e3-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="242e3-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="242e3-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="242e3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="242e3-110">See Also</span></span>  
 <xref:System.MulticastDelegate>  
 [<span data-ttu-id="242e3-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="242e3-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="242e3-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="242e3-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
