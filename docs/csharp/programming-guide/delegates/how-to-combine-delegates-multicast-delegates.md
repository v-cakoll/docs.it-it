---
title: Come combinare delegati multicast (Guida per C# programmatori)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 1a552c0203a4307994b80a1d3d37d12f577c02c4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346391"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="86e54-102">Come combinare delegati multicast (Guida perC# programmatori)</span><span class="sxs-lookup"><span data-stu-id="86e54-102">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="86e54-103">Questo esempio illustra come creare delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="86e54-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="86e54-104">Una proprietà utile degli oggetti [delegate](../../language-reference/builtin-types/reference-types.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="86e54-104">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="86e54-105">Il delegato multicast contiene un elenco dei delegati assegnati.</span><span class="sxs-lookup"><span data-stu-id="86e54-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="86e54-106">Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine.</span><span class="sxs-lookup"><span data-stu-id="86e54-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="86e54-107">Solo i delegati dello stesso tipo possono essere combinati.</span><span class="sxs-lookup"><span data-stu-id="86e54-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="86e54-108">L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.</span><span class="sxs-lookup"><span data-stu-id="86e54-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86e54-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="86e54-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="86e54-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86e54-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="86e54-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="86e54-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="86e54-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="86e54-112">Events</span></span>](../events/index.md)
