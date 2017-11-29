---
title: Operazioni del quantificatore (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d6152cbbd390508a8ffce732f6cbdf1f2e1aa0f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="65dc4-102">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="65dc4-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="65dc4-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="65dc4-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="65dc4-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="65dc4-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="65dc4-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="65dc4-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="65dc4-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="65dc4-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="65dc4-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="65dc4-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="65dc4-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="65dc4-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65dc4-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="65dc4-109">Methods</span></span>  
  
|<span data-ttu-id="65dc4-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="65dc4-110">Method Name</span></span>|<span data-ttu-id="65dc4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65dc4-111">Description</span></span>|<span data-ttu-id="65dc4-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="65dc4-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="65dc4-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="65dc4-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="65dc4-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="65dc4-114">All</span></span>|<span data-ttu-id="65dc4-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="65dc4-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="65dc4-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="65dc4-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="65dc4-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="65dc4-117">Any</span></span>|<span data-ttu-id="65dc4-118">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="65dc4-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="65dc4-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="65dc4-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="65dc4-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="65dc4-120">Contains</span></span>|<span data-ttu-id="65dc4-121">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="65dc4-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="65dc4-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="65dc4-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="65dc4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65dc4-123">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="65dc4-124">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="65dc4-124">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="65dc4-125">Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="65dc4-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
 [<span data-ttu-id="65dc4-126">Procedura: Eseguire una query per trovare frasi che contengono un set definito di parole (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="65dc4-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
