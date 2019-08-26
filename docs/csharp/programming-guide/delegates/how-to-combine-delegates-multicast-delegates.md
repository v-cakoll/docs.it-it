---
title: 'Procedura: Combinare delegati multicast - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d9430021e6a9b438822f1a6dc201f64adf4fdb0f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590659"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="bf2c8-102">Procedura: Combinare delegati multicast (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bf2c8-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="bf2c8-103">Questo esempio illustra come creare delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="bf2c8-104">Una proprietà utile degli oggetti [delegate](../../language-reference/keywords/delegate.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-104">A useful property of [delegate](../../language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="bf2c8-105">Il delegato multicast contiene un elenco dei delegati assegnati.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="bf2c8-106">Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="bf2c8-107">Solo i delegati dello stesso tipo possono essere combinati.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="bf2c8-108">L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.</span><span class="sxs-lookup"><span data-stu-id="bf2c8-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf2c8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf2c8-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="bf2c8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf2c8-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="bf2c8-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bf2c8-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bf2c8-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="bf2c8-112">Events</span></span>](../events/index.md)
