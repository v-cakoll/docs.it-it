---
title: 'Procedura: Combinare delegati multicast - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d835f9b22fef550d6e73cbd620a283bd71e393ec
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237792"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="132f2-102">Procedura: Combinare delegati multicast (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="132f2-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="132f2-103">Questo esempio illustra come creare delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="132f2-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="132f2-104">Una proprietà utile degli oggetti [delegate](../../../csharp/language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="132f2-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="132f2-105">Il delegato multicast contiene un elenco dei delegati assegnati.</span><span class="sxs-lookup"><span data-stu-id="132f2-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="132f2-106">Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine.</span><span class="sxs-lookup"><span data-stu-id="132f2-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="132f2-107">Solo i delegati dello stesso tipo possono essere combinati.</span><span class="sxs-lookup"><span data-stu-id="132f2-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="132f2-108">L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.</span><span class="sxs-lookup"><span data-stu-id="132f2-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="132f2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="132f2-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="132f2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="132f2-110">See Also</span></span>

- <xref:System.MulticastDelegate>  
- [<span data-ttu-id="132f2-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="132f2-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="132f2-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="132f2-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
