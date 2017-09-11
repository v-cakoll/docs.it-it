---
title: Operazioni quantificatore (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e0c982508640ef1ecb47d477d3e9330198474ca
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="25080-102">Operazioni quantificatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25080-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="25080-103">Operazioni del quantificatore restituiscono un <xref:System.Boolean>valore che indica se alcuni o tutti gli elementi in una sequenza soddisfano una condizione.</xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="25080-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="25080-104">La figura seguente illustra due diverse operazioni del quantificatore due sequenze di origine diversa.</span><span class="sxs-lookup"><span data-stu-id="25080-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="25080-105">La prima operazione viene chiesto se uno o più elementi sono il carattere 'A' e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="25080-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="25080-106">La seconda operazione viene chiesto se tutti gli elementi sono il carattere 'A' e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="25080-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="25080-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="25080-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="25080-108">Nella sezione seguente sono elencati i metodi di operatore query standard che eseguono operazioni con quantificatore.</span><span class="sxs-lookup"><span data-stu-id="25080-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25080-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="25080-109">Methods</span></span>  
  
|<span data-ttu-id="25080-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="25080-110">Method Name</span></span>|<span data-ttu-id="25080-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25080-111">Description</span></span>|<span data-ttu-id="25080-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25080-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="25080-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="25080-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="25080-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="25080-114">All</span></span>|<span data-ttu-id="25080-115">Determina se tutti gli elementi in una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="25080-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<span data-ttu-id="25080-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="25080-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="25080-118">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="25080-118">Any</span></span>|<span data-ttu-id="25080-119">Determina se tutti gli elementi in una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="25080-119">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<span data-ttu-id="25080-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="25080-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="25080-122">Contiene</span><span class="sxs-lookup"><span data-stu-id="25080-122">Contains</span></span>|<span data-ttu-id="25080-123">Determina se una sequenza contiene un elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="25080-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="25080-124">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="25080-124">Not applicable.</span></span>|<span data-ttu-id="25080-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="25080-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="25080-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="25080-127">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="25080-127">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="25080-128">Negli esempi viene utilizzata la `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="25080-128">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="25080-129">Nell'esempio seguente viene utilizzata la `Aggregate` clausola e <xref:System.Linq.Enumerable.All%2A>metodo di estensione per restituire un insieme le persone con animali domestici tutti a una data specificata.</xref:System.Linq.Enumerable.All%2A></span><span class="sxs-lookup"><span data-stu-id="25080-129">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 <span data-ttu-id="25080-130">[!code-vb[CsLINQAnyAll n.&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="25080-130">[!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="25080-131">Nell'esempio successivo viene utilizzata la `Aggregate` clausola e <xref:System.Linq.Enumerable.Any%2A>metodo di estensione per restituire da una raccolta di coloro che hanno almeno un animale che è precedente rispetto a un periodo di validità specificato.</xref:System.Linq.Enumerable.Any%2A></span><span class="sxs-lookup"><span data-stu-id="25080-131">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 <span data-ttu-id="25080-132">[!code-vb[CsLINQAnyAll n.&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="25080-132">[!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25080-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25080-133">See Also</span></span>  
 <span data-ttu-id="25080-134"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="25080-134"><xref:System.Linq></span></span>   
<span data-ttu-id="25080-135"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="25080-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="25080-136"> [Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="25080-136"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="25080-137"> [Procedura: eseguire una Query per trovare frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span><span class="sxs-lookup"><span data-stu-id="25080-137"> [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span></span>
