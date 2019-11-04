---
title: Parole chiave di query - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 44af3bf1a7c013c16c7b4a4528c3516621bea149
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422544"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="bf674-102">Parole chiave di query (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bf674-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="bf674-103">Questa sezione contiene le parole chiave contestuali usate nelle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="bf674-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bf674-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="bf674-104">In this section</span></span>

|<span data-ttu-id="bf674-105">Clausola</span><span class="sxs-lookup"><span data-stu-id="bf674-105">Clause</span></span>|<span data-ttu-id="bf674-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf674-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="bf674-107">from</span><span class="sxs-lookup"><span data-stu-id="bf674-107">from</span></span>](from-clause.md)|<span data-ttu-id="bf674-108">Specifica un'origine dati e una variabile di intervallo (simile a una variabile di iterazione).</span><span class="sxs-lookup"><span data-stu-id="bf674-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="bf674-109">where</span><span class="sxs-lookup"><span data-stu-id="bf674-109">where</span></span>](where-clause.md)|<span data-ttu-id="bf674-110">Filtra gli elementi di origine in base a una o più espressioni booleane separate da operatori logici AND e OR (`&&` o <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="bf674-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="bf674-111">select</span><span class="sxs-lookup"><span data-stu-id="bf674-111">select</span></span>](select-clause.md)|<span data-ttu-id="bf674-112">Specifica il tipo e la forma che avranno gli elementi nella sequenza restituita quando verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="bf674-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="bf674-113">group</span><span class="sxs-lookup"><span data-stu-id="bf674-113">group</span></span>](group-clause.md)|<span data-ttu-id="bf674-114">Raggruppa i risultati delle query in base a un valore di chiave specificato.</span><span class="sxs-lookup"><span data-stu-id="bf674-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="bf674-115">into</span><span class="sxs-lookup"><span data-stu-id="bf674-115">into</span></span>](into.md)|<span data-ttu-id="bf674-116">Fornisce un identificatore che può servire come riferimento ai risultati di una clausola join, group o select.</span><span class="sxs-lookup"><span data-stu-id="bf674-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="bf674-117">orderby</span><span class="sxs-lookup"><span data-stu-id="bf674-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="bf674-118">Ordina i risultati delle query in ordine crescente o decrescente in base all'operatore di confronto predefinito per il tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="bf674-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="bf674-119">join</span><span class="sxs-lookup"><span data-stu-id="bf674-119">join</span></span>](join-clause.md)|<span data-ttu-id="bf674-120">Unisce due origini dati in base a un confronto di uguaglianza tra due criteri di corrispondenza specificati.</span><span class="sxs-lookup"><span data-stu-id="bf674-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="bf674-121">let</span><span class="sxs-lookup"><span data-stu-id="bf674-121">let</span></span>](let-clause.md)|<span data-ttu-id="bf674-122">Introduce una variabile di intervallo per archiviare i risultati delle sottoespressioni in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="bf674-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="bf674-123">in</span><span class="sxs-lookup"><span data-stu-id="bf674-123">in</span></span>](in.md)|<span data-ttu-id="bf674-124">Parola chiave contestuale in una clausola [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="bf674-125">on</span><span class="sxs-lookup"><span data-stu-id="bf674-125">on</span></span>](on.md)|<span data-ttu-id="bf674-126">Parola chiave contestuale in una clausola [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="bf674-127">equals</span><span class="sxs-lookup"><span data-stu-id="bf674-127">equals</span></span>](equals.md)|<span data-ttu-id="bf674-128">Parola chiave contestuale in una clausola [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="bf674-129">by</span><span class="sxs-lookup"><span data-stu-id="bf674-129">by</span></span>](by.md)|<span data-ttu-id="bf674-130">Parola chiave contestuale in una clausola [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="bf674-131">ascending</span><span class="sxs-lookup"><span data-stu-id="bf674-131">ascending</span></span>](ascending.md)|<span data-ttu-id="bf674-132">Parola chiave contestuale in una clausola [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="bf674-133">descending</span><span class="sxs-lookup"><span data-stu-id="bf674-133">descending</span></span>](descending.md)|<span data-ttu-id="bf674-134">Parola chiave contestuale in una clausola [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bf674-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="bf674-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf674-135">See also</span></span>

- [<span data-ttu-id="bf674-136">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="bf674-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bf674-137">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="bf674-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="bf674-138">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="bf674-138">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="bf674-139">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="bf674-139">Getting Started with LINQ in C#</span></span>](/dotnet/csharp/programming-guide/concepts/linq/)
