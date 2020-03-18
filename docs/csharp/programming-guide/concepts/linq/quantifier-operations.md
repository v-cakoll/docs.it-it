---
title: Operazioni del quantificatore (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635483"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="33d5d-102">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="33d5d-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="33d5d-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="33d5d-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="33d5d-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="33d5d-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="33d5d-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="33d5d-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="33d5d-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="33d5d-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="33d5d-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="33d5d-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33d5d-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="33d5d-109">Methods</span></span>  
  
|<span data-ttu-id="33d5d-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="33d5d-110">Method Name</span></span>|<span data-ttu-id="33d5d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33d5d-111">Description</span></span>|<span data-ttu-id="33d5d-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="33d5d-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="33d5d-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="33d5d-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="33d5d-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="33d5d-114">All</span></span>|<span data-ttu-id="33d5d-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="33d5d-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="33d5d-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="33d5d-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33d5d-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="33d5d-117">Any</span></span>|<span data-ttu-id="33d5d-118">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="33d5d-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="33d5d-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="33d5d-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33d5d-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="33d5d-120">Contains</span></span>|<span data-ttu-id="33d5d-121">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="33d5d-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="33d5d-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="33d5d-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="33d5d-123">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="33d5d-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="33d5d-124">Tutti</span><span class="sxs-lookup"><span data-stu-id="33d5d-124">All</span></span>  
<span data-ttu-id="33d5d-125">Nell'esempio seguente `All` viene utilizzato l'oggetto per verificare che tutte le stringhe siano di una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="33d5d-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="33d5d-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="33d5d-126">Any</span></span>  
<span data-ttu-id="33d5d-127">Nell'esempio seguente `Any` viene utilizzato l'oggetto per verificare che tutte le stringhe inizino con 'o'.</span><span class="sxs-lookup"><span data-stu-id="33d5d-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="33d5d-128">Contiene</span><span class="sxs-lookup"><span data-stu-id="33d5d-128">Contains</span></span>  
<span data-ttu-id="33d5d-129">Nell'esempio seguente `Contains` viene utilizzato il per verificare che una matrice disponga di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="33d5d-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="33d5d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33d5d-130">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="33d5d-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="33d5d-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="33d5d-132">Specificare dinamicamente i filtri dei predicati in fase di esecuzioneDynamically specify predicate filters at runtime</span><span class="sxs-lookup"><span data-stu-id="33d5d-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="33d5d-133">Come eseguire una query per frasi che contengono un set specificato di parole (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="33d5d-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
