---
title: Operazioni del quantificatore (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f82df05693dffec64bcbc66cc2c0b9db2a7deb20
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="quantifier-operations-c"></a><span data-ttu-id="e3308-102">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="e3308-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="e3308-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="e3308-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="e3308-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="e3308-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="e3308-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="e3308-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="e3308-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="e3308-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="e3308-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="e3308-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="e3308-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="e3308-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3308-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="e3308-109">Methods</span></span>  
  
|<span data-ttu-id="e3308-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="e3308-110">Method Name</span></span>|<span data-ttu-id="e3308-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3308-111">Description</span></span>|<span data-ttu-id="e3308-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="e3308-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="e3308-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="e3308-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e3308-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="e3308-114">All</span></span>|<span data-ttu-id="e3308-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="e3308-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e3308-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="e3308-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|<span data-ttu-id="e3308-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e3308-117">Any</span></span>|<span data-ttu-id="e3308-118">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="e3308-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e3308-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="e3308-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|<span data-ttu-id="e3308-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="e3308-120">Contains</span></span>|<span data-ttu-id="e3308-121">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="e3308-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="e3308-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="e3308-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="e3308-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3308-123">See Also</span></span>  
 <span data-ttu-id="e3308-124"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="e3308-124"><xref:System.Linq></span></span>   
 <span data-ttu-id="e3308-125">[Panoramica degli operatori query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e3308-125">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="e3308-126">[Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="e3308-126">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 [<span data-ttu-id="e3308-127">Procedura: Eseguire una query per trovare frasi che contengono un set definito di parole (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e3308-127">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

