---
title: Operazioni sugli elementi (C#)
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
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
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
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a><span data-ttu-id="af145-102">Operazioni sugli elementi (C#)</span><span class="sxs-lookup"><span data-stu-id="af145-102">Element Operations (C#)</span></span>
<span data-ttu-id="af145-103">Le operazioni sugli elementi restituiscono un singolo elemento specifico di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="af145-103">Element operations return a single, specific element from a sequence.</span></span>  
  
 <span data-ttu-id="af145-104">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="af145-104">The standard query operator methods that perform element operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af145-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="af145-105">Methods</span></span>  
  
|<span data-ttu-id="af145-106">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="af145-106">Method Name</span></span>|<span data-ttu-id="af145-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af145-107">Description</span></span>|<span data-ttu-id="af145-108">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="af145-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="af145-109">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="af145-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="af145-110">ElementAt</span><span class="sxs-lookup"><span data-stu-id="af145-110">ElementAt</span></span>|<span data-ttu-id="af145-111">Restituisce l'elemento in corrispondenza dell'indice specificato in una Collection.</span><span class="sxs-lookup"><span data-stu-id="af145-111">Returns the element at a specified index in a collection.</span></span>|<span data-ttu-id="af145-112">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-113">ElementAtOrDefault</span><span class="sxs-lookup"><span data-stu-id="af145-113">ElementAtOrDefault</span></span>|<span data-ttu-id="af145-114">Restituisce l'elemento in corrispondenza di un indice specificato in una Collection o un valore predefinito se l'indice è esterno all'intervallo.</span><span class="sxs-lookup"><span data-stu-id="af145-114">Returns the element at a specified index in a collection or a default value if the index is out of range.</span></span>|<span data-ttu-id="af145-115">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-116">First</span><span class="sxs-lookup"><span data-stu-id="af145-116">First</span></span>|<span data-ttu-id="af145-117">Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-117">Returns the first element of a collection, or the first element that satisfies a condition.</span></span>|<span data-ttu-id="af145-118">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-119">FirstOrDefault</span><span class="sxs-lookup"><span data-stu-id="af145-119">FirstOrDefault</span></span>|<span data-ttu-id="af145-120">Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-120">Returns the first element of a collection, or the first element that satisfies a condition.</span></span> <span data-ttu-id="af145-121">Restituisce un valore predefinito se questo tipo di elemento non esiste.</span><span class="sxs-lookup"><span data-stu-id="af145-121">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="af145-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|<span data-ttu-id="af145-123">Ultimo</span><span class="sxs-lookup"><span data-stu-id="af145-123">Last</span></span>|<span data-ttu-id="af145-124">Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-124">Returns the last element of a collection, or the last element that satisfies a condition.</span></span>|<span data-ttu-id="af145-125">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-126">LastOrDefault</span><span class="sxs-lookup"><span data-stu-id="af145-126">LastOrDefault</span></span>|<span data-ttu-id="af145-127">Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-127">Returns the last element of a collection, or the last element that satisfies a condition.</span></span> <span data-ttu-id="af145-128">Restituisce un valore predefinito se questo tipo di elemento non esiste.</span><span class="sxs-lookup"><span data-stu-id="af145-128">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="af145-129">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-130">Single</span><span class="sxs-lookup"><span data-stu-id="af145-130">Single</span></span>|<span data-ttu-id="af145-131">Restituisce l'unico elemento di una Collection o l'unico elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-131">Returns the only element of a collection, or the only element that satisfies a condition.</span></span>|<span data-ttu-id="af145-132">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|<span data-ttu-id="af145-133">SingleOrDefault</span><span class="sxs-lookup"><span data-stu-id="af145-133">SingleOrDefault</span></span>|<span data-ttu-id="af145-134">Restituisce l'unico elemento di una Collection o l'unico elemento che soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="af145-134">Returns the only element of a collection, or the only element that satisfies a condition.</span></span> <span data-ttu-id="af145-135">Restituisce un valore predefinito se tale elemento non esiste o la Collection non contiene esattamente un elemento.</span><span class="sxs-lookup"><span data-stu-id="af145-135">Returns a default value if no such element exists or the collection does not contain exactly one element.</span></span>|<span data-ttu-id="af145-136">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="af145-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="af145-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af145-137">See Also</span></span>  
 <span data-ttu-id="af145-138"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="af145-138"><xref:System.Linq></span></span>   
 <span data-ttu-id="af145-139">[Cenni preliminari sugli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="af145-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="af145-140">Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="af145-140">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

