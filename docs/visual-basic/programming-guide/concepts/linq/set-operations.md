---
title: Operazioni sui set
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: fe9d910415f30fe672dc702f719fdefdb9c0b3d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350610"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="5d89a-102">Operazioni set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d89a-102">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="5d89a-103">Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.</span><span class="sxs-lookup"><span data-stu-id="5d89a-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="5d89a-104">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.</span><span class="sxs-lookup"><span data-stu-id="5d89a-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="5d89a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d89a-105">Methods</span></span>

|<span data-ttu-id="5d89a-106">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="5d89a-106">Method Name</span></span>|<span data-ttu-id="5d89a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d89a-107">Description</span></span>|<span data-ttu-id="5d89a-108">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="5d89a-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="5d89a-109">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="5d89a-109">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="5d89a-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="5d89a-110">Distinct</span></span>|<span data-ttu-id="5d89a-111">Rimuove i valori duplicati da una Collection.</span><span class="sxs-lookup"><span data-stu-id="5d89a-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="5d89a-112">Eccezione</span><span class="sxs-lookup"><span data-stu-id="5d89a-112">Except</span></span>|<span data-ttu-id="5d89a-113">Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.</span><span class="sxs-lookup"><span data-stu-id="5d89a-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="5d89a-114">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="5d89a-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="5d89a-115">Interseca</span><span class="sxs-lookup"><span data-stu-id="5d89a-115">Intersect</span></span>|<span data-ttu-id="5d89a-116">Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="5d89a-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="5d89a-117">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="5d89a-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="5d89a-118">Unione</span><span class="sxs-lookup"><span data-stu-id="5d89a-118">Union</span></span>|<span data-ttu-id="5d89a-119">Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.</span><span class="sxs-lookup"><span data-stu-id="5d89a-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="5d89a-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="5d89a-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="5d89a-121">Confronto tra le operazioni sui set</span><span class="sxs-lookup"><span data-stu-id="5d89a-121">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="5d89a-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="5d89a-122">Distinct</span></span>

<span data-ttu-id="5d89a-123">Nella figura seguente viene illustrato il comportamento del metodo <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> su una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="5d89a-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="5d89a-124">La sequenza restituita contiene gli elementi univoci dalla sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="5d89a-124">The returned sequence contains the unique elements from the input sequence.</span></span>

![Elemento grafico che illustra il comportamento di Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="5d89a-126">Eccezione</span><span class="sxs-lookup"><span data-stu-id="5d89a-126">Except</span></span>

<span data-ttu-id="5d89a-127">Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d89a-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5d89a-128">La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="5d89a-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="5d89a-129">![Grafico che mostra l'azione di&#40;&#41;except.](./media/set-operations/except-behavior-graphic.png "Mostra il comportamento di eccetto.")</span><span class="sxs-lookup"><span data-stu-id="5d89a-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="5d89a-130">Interseca</span><span class="sxs-lookup"><span data-stu-id="5d89a-130">Intersect</span></span>

<span data-ttu-id="5d89a-131">Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d89a-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5d89a-132">La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="5d89a-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![Grafica che mostra l'intersezione di due sequenze](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="5d89a-134">Unione</span><span class="sxs-lookup"><span data-stu-id="5d89a-134">Union</span></span>

<span data-ttu-id="5d89a-135">La figura seguente illustra un'operazione di unione tra due sequenze di caratteri.</span><span class="sxs-lookup"><span data-stu-id="5d89a-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="5d89a-136">La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.</span><span class="sxs-lookup"><span data-stu-id="5d89a-136">The returned sequence contains the unique elements from both input sequences.</span></span>

![Elemento grafico che illustra l'unione di due sequenze.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="5d89a-138">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="5d89a-138">Query Expression Syntax Example</span></span>

<span data-ttu-id="5d89a-139">Nell'esempio seguente viene utilizzata la clausola `Distinct` in una query LINQ per restituire i numeri univoci da un elenco di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="5d89a-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="5d89a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d89a-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="5d89a-141">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d89a-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5d89a-142">Clausola Distinct</span><span class="sxs-lookup"><span data-stu-id="5d89a-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="5d89a-143">Procedura: combinare e confrontare raccolte di stringhe (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d89a-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="5d89a-144">Procedura: trovare la differenza dei set tra due elenchi (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d89a-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
