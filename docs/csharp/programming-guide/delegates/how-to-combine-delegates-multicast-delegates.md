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
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="2ada8-102">Procedura: combinare delegati multicast (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2ada8-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="2ada8-103">Questo esempio illustra come creare delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="2ada8-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="2ada8-104">Una proprietà utile degli oggetti [delegate](../../../csharp/language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="2ada8-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="2ada8-105">Il delegato multicast contiene un elenco dei delegati assegnati.</span><span class="sxs-lookup"><span data-stu-id="2ada8-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="2ada8-106">Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine.</span><span class="sxs-lookup"><span data-stu-id="2ada8-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="2ada8-107">Solo i delegati dello stesso tipo possono essere combinati.</span><span class="sxs-lookup"><span data-stu-id="2ada8-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="2ada8-108">L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.</span><span class="sxs-lookup"><span data-stu-id="2ada8-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ada8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ada8-109">Example</span></span>  
 <span data-ttu-id="2ada8-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2ada8-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ada8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ada8-111">See Also</span></span>  
 <span data-ttu-id="2ada8-112"><xref:System.MulticastDelegate></span><span class="sxs-lookup"><span data-stu-id="2ada8-112"><xref:System.MulticastDelegate></span></span>   
 <span data-ttu-id="2ada8-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2ada8-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2ada8-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="2ada8-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)

