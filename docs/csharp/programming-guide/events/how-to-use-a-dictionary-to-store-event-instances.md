---
title: 'Procedura: utilizzare un dizionario per archiviare istanze di evento (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 97a7b0f168e4a1c81ec396f42b731dabb45b3516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327216"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="41d9e-102">Procedura: utilizzare un dizionario per archiviare istanze di evento (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="41d9e-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="41d9e-103">È possibile usare `accessor-declarations` per esporre numerosi eventi senza allocare un campo per ogni evento, ma usando invece un dizionario per archiviare le istanze degli eventi.</span><span class="sxs-lookup"><span data-stu-id="41d9e-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="41d9e-104">Ciò è utile solo se si hanno molti eventi, ma si prevede che la maggior parte di essi non verrà implementata.</span><span class="sxs-lookup"><span data-stu-id="41d9e-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d9e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="41d9e-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="41d9e-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41d9e-106">See Also</span></span>  
 [<span data-ttu-id="41d9e-107">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="41d9e-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="41d9e-108">Eventi</span><span class="sxs-lookup"><span data-stu-id="41d9e-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="41d9e-109">Delegati</span><span class="sxs-lookup"><span data-stu-id="41d9e-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
