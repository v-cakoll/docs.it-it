---
title: Operazioni del quantificatore (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635483"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="c11e4-102">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="c11e4-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="c11e4-103">Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="c11e4-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="c11e4-104">La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="c11e4-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="c11e4-105">La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="c11e4-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="c11e4-106">La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.</span><span class="sxs-lookup"><span data-stu-id="c11e4-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="c11e4-108">La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.</span><span class="sxs-lookup"><span data-stu-id="c11e4-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c11e4-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="c11e4-109">Methods</span></span>  
  
|<span data-ttu-id="c11e4-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="c11e4-110">Method Name</span></span>|<span data-ttu-id="c11e4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c11e4-111">Description</span></span>|<span data-ttu-id="c11e4-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="c11e4-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="c11e4-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c11e4-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="c11e4-114">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c11e4-114">All</span></span>|<span data-ttu-id="c11e4-115">Determina se tutti gli elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="c11e4-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="c11e4-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="c11e4-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c11e4-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c11e4-117">Any</span></span>|<span data-ttu-id="c11e4-118">Determina se alcuni elementi di una sequenza soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="c11e4-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="c11e4-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="c11e4-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c11e4-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="c11e4-120">Contains</span></span>|<span data-ttu-id="c11e4-121">Determina se una sequenza contiene un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="c11e4-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="c11e4-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="c11e4-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c11e4-123">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="c11e4-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="c11e4-124">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c11e4-124">All</span></span>  
<span data-ttu-id="c11e4-125">Nell'esempio seguente viene usato il `All` per verificare che tutte le stringhe abbiano una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="c11e4-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="c11e4-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c11e4-126">Any</span></span>  
<span data-ttu-id="c11e4-127">Nell'esempio seguente viene usato il `Any` per verificare che le stringhe inizino con "o".</span><span class="sxs-lookup"><span data-stu-id="c11e4-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="c11e4-128">Contiene</span><span class="sxs-lookup"><span data-stu-id="c11e4-128">Contains</span></span>  
<span data-ttu-id="c11e4-129">Nell'esempio seguente viene usato il `Contains` per verificare che una matrice disponga di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="c11e4-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="c11e4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c11e4-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c11e4-131">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="c11e4-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="c11e4-132">Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c11e4-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="c11e4-133">Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ)C#()</span><span class="sxs-lookup"><span data-stu-id="c11e4-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
