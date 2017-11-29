---
title: Operazioni sui set (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5b546d9df8752fd7afd6e0db4525bc923a74bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="set-operations-c"></a><span data-ttu-id="f8305-102">Operazioni sui set (C#)</span><span class="sxs-lookup"><span data-stu-id="f8305-102">Set Operations (C#)</span></span>
<span data-ttu-id="f8305-103">Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.</span><span class="sxs-lookup"><span data-stu-id="f8305-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="f8305-104">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.</span><span class="sxs-lookup"><span data-stu-id="f8305-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8305-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8305-105">Methods</span></span>  
  
|<span data-ttu-id="f8305-106">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="f8305-106">Method Name</span></span>|<span data-ttu-id="f8305-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8305-107">Description</span></span>|<span data-ttu-id="f8305-108">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="f8305-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="f8305-109">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f8305-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f8305-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="f8305-110">Distinct</span></span>|<span data-ttu-id="f8305-111">Rimuove i valori duplicati da una Collection.</span><span class="sxs-lookup"><span data-stu-id="f8305-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="f8305-112">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="f8305-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f8305-113">Eccezione</span><span class="sxs-lookup"><span data-stu-id="f8305-113">Except</span></span>|<span data-ttu-id="f8305-114">Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.</span><span class="sxs-lookup"><span data-stu-id="f8305-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="f8305-115">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="f8305-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f8305-116">Interseca</span><span class="sxs-lookup"><span data-stu-id="f8305-116">Intersect</span></span>|<span data-ttu-id="f8305-117">Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="f8305-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="f8305-118">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="f8305-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f8305-119">Unione</span><span class="sxs-lookup"><span data-stu-id="f8305-119">Union</span></span>|<span data-ttu-id="f8305-120">Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="f8305-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="f8305-121">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="f8305-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="f8305-122">Confronto tra le operazioni sui set</span><span class="sxs-lookup"><span data-stu-id="f8305-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="f8305-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="f8305-123">Distinct</span></span>  
 <span data-ttu-id="f8305-124">Nella figura seguente viene illustrato il comportamento del metodo <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> su una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="f8305-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="f8305-125">La sequenza restituita contiene gli elementi univoci dalla sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="f8305-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="f8305-126">![Grafico che mostra il comportamento di Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="f8305-126">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="f8305-127">Eccezione</span><span class="sxs-lookup"><span data-stu-id="f8305-127">Except</span></span>  
 <span data-ttu-id="f8305-128">Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f8305-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f8305-129">La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="f8305-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="f8305-130">![Grafico che mostra l'azione di Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="f8305-130">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="f8305-131">Interseca</span><span class="sxs-lookup"><span data-stu-id="f8305-131">Intersect</span></span>  
 <span data-ttu-id="f8305-132">Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f8305-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f8305-133">La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="f8305-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="f8305-134">![Grafico che mostra l'intersezione di due sequenze.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="f8305-134">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="f8305-135">Unione</span><span class="sxs-lookup"><span data-stu-id="f8305-135">Union</span></span>  
 <span data-ttu-id="f8305-136">La figura seguente illustra un'operazione di unione tra due sequenze di caratteri.</span><span class="sxs-lookup"><span data-stu-id="f8305-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="f8305-137">La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="f8305-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="f8305-138">![Grafico che mostra l'unione di due sequenze.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="f8305-138">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8305-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8305-139">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="f8305-140">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="f8305-140">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="f8305-141">Procedura: Combinare e confrontare raccolte di stringhe (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f8305-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 [<span data-ttu-id="f8305-142">Procedura: Trovare la differenza dei set tra due elenchi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f8305-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
