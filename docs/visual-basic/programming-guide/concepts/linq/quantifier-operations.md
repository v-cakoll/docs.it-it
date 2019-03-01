---
title: Operazioni del quantificatore (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 966bc958d6feac77ebe1c229bfe5dbb993031676
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976746"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="ae42b-102">Operazioni del quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae42b-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="ae42b-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="ae42b-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="ae42b-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="ae42b-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="ae42b-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="ae42b-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="ae42b-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="ae42b-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="ae42b-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="ae42b-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="ae42b-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="ae42b-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae42b-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="ae42b-109">Methods</span></span>  
  
|<span data-ttu-id="ae42b-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="ae42b-110">Method Name</span></span>|<span data-ttu-id="ae42b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae42b-111">Description</span></span>|<span data-ttu-id="ae42b-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae42b-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="ae42b-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ae42b-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="ae42b-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="ae42b-114">All</span></span>|<span data-ttu-id="ae42b-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="ae42b-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ae42b-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ae42b-116">Any</span></span>|<span data-ttu-id="ae42b-117">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="ae42b-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ae42b-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="ae42b-118">Contains</span></span>|<span data-ttu-id="ae42b-119">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="ae42b-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="ae42b-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="ae42b-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ae42b-121">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ae42b-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="ae42b-122">Questi esempi usano il `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="ae42b-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="ae42b-123">L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.All%2A> metodo di estensione per restituire da una raccolta le persone cui animali domestici tutto antecedenti a un periodo di validità specificato.</span><span class="sxs-lookup"><span data-stu-id="ae42b-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="ae42b-124">L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.Any%2A> metodo di estensione per restituire da una raccolta di coloro che hanno almeno un animale che è precedente rispetto a un periodo di validità specificato.</span><span class="sxs-lookup"><span data-stu-id="ae42b-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ae42b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae42b-125">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="ae42b-126">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae42b-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="ae42b-127">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="ae42b-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="ae42b-128">Procedura: Eseguire una query per trovare frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae42b-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
