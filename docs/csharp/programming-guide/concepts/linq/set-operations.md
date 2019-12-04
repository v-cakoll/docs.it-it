---
title: Operazioni sui set (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 22079b1d41533803f694af210f98bc9fb8a5b322
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711877"
---
# <a name="set-operations-c"></a><span data-ttu-id="72907-102">Operazioni sui set (C#)</span><span class="sxs-lookup"><span data-stu-id="72907-102">Set Operations (C#)</span></span>
<span data-ttu-id="72907-103">Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.</span><span class="sxs-lookup"><span data-stu-id="72907-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="72907-104">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.</span><span class="sxs-lookup"><span data-stu-id="72907-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72907-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="72907-105">Methods</span></span>  
  
|<span data-ttu-id="72907-106">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="72907-106">Method Name</span></span>|<span data-ttu-id="72907-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72907-107">Description</span></span>|<span data-ttu-id="72907-108">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="72907-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="72907-109">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="72907-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="72907-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="72907-110">Distinct</span></span>|<span data-ttu-id="72907-111">Rimuove i valori duplicati da una Collection.</span><span class="sxs-lookup"><span data-stu-id="72907-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="72907-112">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="72907-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="72907-113">Eccezione</span><span class="sxs-lookup"><span data-stu-id="72907-113">Except</span></span>|<span data-ttu-id="72907-114">Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.</span><span class="sxs-lookup"><span data-stu-id="72907-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="72907-115">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="72907-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="72907-116">Interseca</span><span class="sxs-lookup"><span data-stu-id="72907-116">Intersect</span></span>|<span data-ttu-id="72907-117">Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="72907-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="72907-118">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="72907-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="72907-119">Union</span><span class="sxs-lookup"><span data-stu-id="72907-119">Union</span></span>|<span data-ttu-id="72907-120">Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="72907-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="72907-121">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="72907-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="72907-122">Confronto tra le operazioni sui set</span><span class="sxs-lookup"><span data-stu-id="72907-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="72907-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="72907-123">Distinct</span></span>  
 <span data-ttu-id="72907-124">Nell'esempio seguente viene illustrato il comportamento del metodo <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> su una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="72907-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="72907-125">La sequenza restituita contiene gli elementi univoci dalla sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="72907-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Elemento grafico che illustra il comportamento di Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="72907-127">Eccezione</span><span class="sxs-lookup"><span data-stu-id="72907-127">Except</span></span>  
 <span data-ttu-id="72907-128">Nell'esempio seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72907-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="72907-129">La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="72907-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="72907-130">![Grafico che mostra l'azione di&#40;&#41;except.](./media/set-operations/except-behavior-graphic.png "Mostra il comportamento di eccetto.")</span><span class="sxs-lookup"><span data-stu-id="72907-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="72907-131">Interseca</span><span class="sxs-lookup"><span data-stu-id="72907-131">Intersect</span></span>  
 <span data-ttu-id="72907-132">Nell'esempio seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72907-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="72907-133">La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="72907-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafica che mostra l'intersezione di due sequenze](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="72907-135">Union</span><span class="sxs-lookup"><span data-stu-id="72907-135">Union</span></span>  
 <span data-ttu-id="72907-136">Nell'esempio seguente viene illustrata un'operazione di Unione su due sequenze di caratteri.</span><span class="sxs-lookup"><span data-stu-id="72907-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="72907-137">La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="72907-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafica che mostra l'unione di due sequenze](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a><span data-ttu-id="72907-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72907-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="72907-140">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="72907-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="72907-141">Come combinare e confrontare raccolte di stringhe (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="72907-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="72907-142">Procedura: Trovare la differenza dei set tra due elenchi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="72907-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
