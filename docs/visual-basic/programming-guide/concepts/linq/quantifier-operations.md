---
title: Operazioni del quantificatore
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346590"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="f9add-102">Operazioni del quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9add-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="f9add-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="f9add-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="f9add-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="f9add-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="f9add-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="f9add-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="f9add-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="f9add-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="f9add-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="f9add-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9add-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="f9add-109">Methods</span></span>  
  
|<span data-ttu-id="f9add-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="f9add-110">Method Name</span></span>|<span data-ttu-id="f9add-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9add-111">Description</span></span>|<span data-ttu-id="f9add-112">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="f9add-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f9add-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f9add-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f9add-114">Tutte</span><span class="sxs-lookup"><span data-stu-id="f9add-114">All</span></span>|<span data-ttu-id="f9add-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="f9add-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f9add-116">Any</span><span class="sxs-lookup"><span data-stu-id="f9add-116">Any</span></span>|<span data-ttu-id="f9add-117">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="f9add-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f9add-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="f9add-118">Contains</span></span>|<span data-ttu-id="f9add-119">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="f9add-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="f9add-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="f9add-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f9add-121">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="f9add-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="f9add-122">In questi esempi viene utilizzata la clausola `Aggregate` in Visual Basic come parte della condizione di filtro in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="f9add-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="f9add-123">Nell'esempio seguente viene utilizzata la clausola `Aggregate` e il metodo di estensione <xref:System.Linq.Enumerable.All%2A> per restituire da una raccolta le persone i cui animali sono di età superiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="f9add-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="f9add-124">Nell'esempio seguente viene usata la clausola `Aggregate` e il metodo di estensione <xref:System.Linq.Enumerable.Any%2A> per restituire da una raccolta le persone che hanno almeno un animale che è antecedente a una determinata età.</span><span class="sxs-lookup"><span data-stu-id="f9add-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f9add-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9add-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f9add-126">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9add-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="f9add-127">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="f9add-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="f9add-128">Procedura: eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9add-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
