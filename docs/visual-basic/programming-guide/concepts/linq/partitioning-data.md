---
title: Partizionamento dei dati
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 2ab4e27ef6d825b9100fc3c15b7a9554ae49e516
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353146"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="b6ed8-102">Partitioning Data (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6ed8-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="b6ed8-103">Il partizionamento in LINQ è l'operazione di divisione di una sequenza di input in due sezioni senza ridisposizione degli elementi e la successiva restituzione di una delle sezioni.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="b6ed8-104">La figura seguente illustra i risultati di tre diverse operazioni di partizionamento in una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="b6ed8-105">La prima operazione restituisce i primi tre elementi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="b6ed8-106">La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="b6ed8-107">La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Figura che illustra tre operazioni di partizionamento LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="b6ed8-109">Nella sezione seguente sono elencati i metodi degli operatori di query standard che eseguono la partizione delle sequenze.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="b6ed8-110">Operatori</span><span class="sxs-lookup"><span data-stu-id="b6ed8-110">Operators</span></span>  
  
|<span data-ttu-id="b6ed8-111">Nome dell'operatore</span><span class="sxs-lookup"><span data-stu-id="b6ed8-111">Operator Name</span></span>|<span data-ttu-id="b6ed8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6ed8-112">Description</span></span>|<span data-ttu-id="b6ed8-113">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="b6ed8-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b6ed8-114">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b6ed8-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="b6ed8-115">Skip</span><span class="sxs-lookup"><span data-stu-id="b6ed8-115">Skip</span></span>|<span data-ttu-id="b6ed8-116">Ignora gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b6ed8-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="b6ed8-117">SkipWhile</span></span>|<span data-ttu-id="b6ed8-118">Ignora gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b6ed8-119">Take</span><span class="sxs-lookup"><span data-stu-id="b6ed8-119">Take</span></span>|<span data-ttu-id="b6ed8-120">Accetta gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b6ed8-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="b6ed8-121">TakeWhile</span></span>|<span data-ttu-id="b6ed8-122">Accetta gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b6ed8-123">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b6ed8-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="b6ed8-124">Skip</span><span class="sxs-lookup"><span data-stu-id="b6ed8-124">Skip</span></span>  
 <span data-ttu-id="b6ed8-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="b6ed8-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="b6ed8-126">SkipWhile</span></span>  
 <span data-ttu-id="b6ed8-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span><span class="sxs-lookup"><span data-stu-id="b6ed8-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="b6ed8-128">The remaining strings in the array are returned.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="b6ed8-129">Take</span><span class="sxs-lookup"><span data-stu-id="b6ed8-129">Take</span></span>  
 <span data-ttu-id="b6ed8-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="b6ed8-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="b6ed8-131">TakeWhile</span></span>  
 <span data-ttu-id="b6ed8-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span><span class="sxs-lookup"><span data-stu-id="b6ed8-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b6ed8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6ed8-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b6ed8-134">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6ed8-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b6ed8-135">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="b6ed8-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="b6ed8-136">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="b6ed8-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="b6ed8-137">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="b6ed8-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="b6ed8-138">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="b6ed8-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
