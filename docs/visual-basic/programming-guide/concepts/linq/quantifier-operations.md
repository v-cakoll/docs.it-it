---
title: Operazioni quantificatore (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0a0a5fae35a14ab6451f2f56fb2eedd92ac437e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645834"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="d62e6-102">Operazioni quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d62e6-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="d62e6-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d62e6-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="d62e6-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="d62e6-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="d62e6-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="d62e6-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="d62e6-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="d62e6-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="d62e6-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="d62e6-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="d62e6-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="d62e6-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d62e6-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="d62e6-109">Methods</span></span>  
  
|<span data-ttu-id="d62e6-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="d62e6-110">Method Name</span></span>|<span data-ttu-id="d62e6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d62e6-111">Description</span></span>|<span data-ttu-id="d62e6-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d62e6-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d62e6-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="d62e6-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d62e6-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="d62e6-114">All</span></span>|<span data-ttu-id="d62e6-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d62e6-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d62e6-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d62e6-116">Any</span></span>|<span data-ttu-id="d62e6-117">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d62e6-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d62e6-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="d62e6-118">Contains</span></span>|<span data-ttu-id="d62e6-119">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="d62e6-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="d62e6-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="d62e6-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d62e6-121">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="d62e6-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="d62e6-122">Negli esempi viene utilizzata la `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="d62e6-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="d62e6-123">L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.All%2A> metodo di estensione per restituire da una raccolta le persone con animali domestici tutti più vecchi di un periodo di memorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="d62e6-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="d62e6-124">L'esempio seguente viene utilizzata la `Aggregate` clausola e <xref:System.Linq.Enumerable.Any%2A> metodo di estensione per restituire una raccolta coloro che hanno almeno un animale che è antecedente a un periodo di memorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="d62e6-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d62e6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d62e6-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="d62e6-126">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d62e6-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="d62e6-127">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="d62e6-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="d62e6-128">Procedura: eseguire una Query per frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d62e6-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
