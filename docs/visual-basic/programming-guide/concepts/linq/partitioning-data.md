---
title: Partizionamento dei dati
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 34749f9d7b137bade66b6103650871246c3cc532
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406846"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="4188c-102">Partizionamento dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4188c-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="4188c-103">Il partizionamento in LINQ è l'operazione di divisione di una sequenza di input in due sezioni senza ridisposizione degli elementi e la successiva restituzione di una delle sezioni.</span><span class="sxs-lookup"><span data-stu-id="4188c-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="4188c-104">La figura seguente illustra i risultati di tre diverse operazioni di partizionamento in una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="4188c-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="4188c-105">La prima operazione restituisce i primi tre elementi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="4188c-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="4188c-106">La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="4188c-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="4188c-107">La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.</span><span class="sxs-lookup"><span data-stu-id="4188c-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Figura che illustra tre operazioni di partizionamento LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="4188c-109">Nella sezione seguente sono elencati i metodi degli operatori di query standard che eseguono la partizione delle sequenze.</span><span class="sxs-lookup"><span data-stu-id="4188c-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="4188c-110">Operatori</span><span class="sxs-lookup"><span data-stu-id="4188c-110">Operators</span></span>  
  
|<span data-ttu-id="4188c-111">Nome operatore</span><span class="sxs-lookup"><span data-stu-id="4188c-111">Operator Name</span></span>|<span data-ttu-id="4188c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4188c-112">Description</span></span>|<span data-ttu-id="4188c-113">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="4188c-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4188c-114">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="4188c-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="4188c-115">Ignora</span><span class="sxs-lookup"><span data-stu-id="4188c-115">Skip</span></span>|<span data-ttu-id="4188c-116">Ignora gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="4188c-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4188c-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4188c-117">SkipWhile</span></span>|<span data-ttu-id="4188c-118">Ignora gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="4188c-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4188c-119">Take</span><span class="sxs-lookup"><span data-stu-id="4188c-119">Take</span></span>|<span data-ttu-id="4188c-120">Accetta gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="4188c-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4188c-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4188c-121">TakeWhile</span></span>|<span data-ttu-id="4188c-122">Accetta gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="4188c-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="4188c-123">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="4188c-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="4188c-124">Ignora</span><span class="sxs-lookup"><span data-stu-id="4188c-124">Skip</span></span>  
 <span data-ttu-id="4188c-125">Nell'esempio di codice seguente viene usata la `Skip` clausola in Visual Basic per ignorare le prime quattro stringhe in una matrice di stringhe prima di restituire le altre stringhe nella matrice.</span><span class="sxs-lookup"><span data-stu-id="4188c-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="4188c-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4188c-126">SkipWhile</span></span>  
 <span data-ttu-id="4188c-127">Nell'esempio di codice seguente viene usata la `Skip While` clausola in Visual Basic per ignorare le stringhe in una matrice mentre la prima lettera della stringa è "a".</span><span class="sxs-lookup"><span data-stu-id="4188c-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="4188c-128">Vengono restituite le stringhe rimanenti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="4188c-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="4188c-129">Take</span><span class="sxs-lookup"><span data-stu-id="4188c-129">Take</span></span>  
 <span data-ttu-id="4188c-130">Nell'esempio di codice seguente viene usata la `Take` clausola in Visual Basic per restituire le prime due stringhe in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="4188c-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="4188c-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4188c-131">TakeWhile</span></span>  
 <span data-ttu-id="4188c-132">Nell'esempio di codice seguente viene usata la `Take While` clausola in Visual Basic per restituire stringhe da una matrice mentre la lunghezza della stringa è cinque o meno.</span><span class="sxs-lookup"><span data-stu-id="4188c-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4188c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4188c-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="4188c-134">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4188c-134">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="4188c-135">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="4188c-135">Skip Clause</span></span>](../../../language-reference/queries/skip-clause.md)
- [<span data-ttu-id="4188c-136">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="4188c-136">Skip While Clause</span></span>](../../../language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="4188c-137">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="4188c-137">Take Clause</span></span>](../../../language-reference/queries/take-clause.md)
- [<span data-ttu-id="4188c-138">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="4188c-138">Take While Clause</span></span>](../../../language-reference/queries/take-while-clause.md)
