---
title: Operazioni del quantificatore (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 24c8f9a6b589592c26c8a514bc44ff9623a82d2f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523105"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="d49b1-102">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="d49b1-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="d49b1-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d49b1-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="d49b1-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="d49b1-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="d49b1-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="d49b1-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="d49b1-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="d49b1-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="d49b1-107">![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="d49b1-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="d49b1-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="d49b1-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d49b1-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="d49b1-109">Methods</span></span>  
  
|<span data-ttu-id="d49b1-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="d49b1-110">Method Name</span></span>|<span data-ttu-id="d49b1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d49b1-111">Description</span></span>|<span data-ttu-id="d49b1-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="d49b1-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="d49b1-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="d49b1-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d49b1-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="d49b1-114">All</span></span>|<span data-ttu-id="d49b1-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d49b1-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d49b1-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="d49b1-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d49b1-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d49b1-117">Any</span></span>|<span data-ttu-id="d49b1-118">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="d49b1-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d49b1-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="d49b1-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d49b1-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="d49b1-120">Contains</span></span>|<span data-ttu-id="d49b1-121">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="d49b1-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="d49b1-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="d49b1-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="d49b1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d49b1-123">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="d49b1-124">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="d49b1-124">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="d49b1-125">Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d49b1-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [<span data-ttu-id="d49b1-126">Procedura: Eseguire una query per trovare frasi che contengono un set definito di parole (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d49b1-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
