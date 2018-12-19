---
title: 'Procedura: Usare un dizionario per archiviare istanze di evento - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245142"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="58dd4-102">Procedura: Usare un dizionario per archiviare istanze di evento (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="58dd4-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="58dd4-103">È possibile usare `accessor-declarations` per esporre numerosi eventi senza allocare un campo per ogni evento, ma usando invece un dizionario per archiviare le istanze degli eventi.</span><span class="sxs-lookup"><span data-stu-id="58dd4-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="58dd4-104">Ciò è utile solo se si hanno molti eventi, ma si prevede che la maggior parte di essi non verrà implementata.</span><span class="sxs-lookup"><span data-stu-id="58dd4-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58dd4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="58dd4-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="58dd4-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58dd4-106">See Also</span></span>

- [<span data-ttu-id="58dd4-107">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="58dd4-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="58dd4-108">Eventi</span><span class="sxs-lookup"><span data-stu-id="58dd4-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="58dd4-109">Delegati</span><span class="sxs-lookup"><span data-stu-id="58dd4-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
