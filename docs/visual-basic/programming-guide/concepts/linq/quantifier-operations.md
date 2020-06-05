---
title: Operazioni del quantificatore
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 9a2e35e0511915cb17b99550a8bf382bd9d46526
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396311"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="a5eae-102">Operazioni del quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5eae-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="a5eae-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="a5eae-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="a5eae-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="a5eae-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="a5eae-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="a5eae-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="a5eae-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="a5eae-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="a5eae-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="a5eae-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5eae-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="a5eae-109">Methods</span></span>  
  
|<span data-ttu-id="a5eae-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="a5eae-110">Method Name</span></span>|<span data-ttu-id="a5eae-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5eae-111">Description</span></span>|<span data-ttu-id="a5eae-112">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="a5eae-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a5eae-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a5eae-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a5eae-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="a5eae-114">All</span></span>|<span data-ttu-id="a5eae-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="a5eae-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a5eae-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a5eae-116">Any</span></span>|<span data-ttu-id="a5eae-117">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="a5eae-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a5eae-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="a5eae-118">Contains</span></span>|<span data-ttu-id="a5eae-119">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="a5eae-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="a5eae-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a5eae-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="a5eae-121">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="a5eae-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="a5eae-122">In questi esempi viene utilizzata la `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="a5eae-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="a5eae-123">Nell'esempio seguente vengono utilizzate la `Aggregate` clausola e il <xref:System.Linq.Enumerable.All%2A> metodo di estensione per restituire da una raccolta le persone i cui animali sono di età superiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="a5eae-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="a5eae-124">Nell'esempio seguente viene usata la `Aggregate` clausola e il <xref:System.Linq.Enumerable.Any%2A> metodo di estensione per restituire da una raccolta le persone che hanno almeno un animale che è antecedente a una determinata età.</span><span class="sxs-lookup"><span data-stu-id="a5eae-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a5eae-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5eae-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a5eae-126">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5eae-126">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="a5eae-127">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="a5eae-127">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="a5eae-128">Procedura: eseguire una query per trovare frasi che contengono un set definito di parole (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5eae-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
