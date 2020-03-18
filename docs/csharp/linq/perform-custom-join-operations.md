---
title: Eseguire operazioni di join personalizzate (LINQ in C#)
description: Informazioni su come eseguire operazioni di join LINQ personalizzate in C#.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659852"
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="4f5cb-103">Eseguire operazioni di join personalizzate</span><span class="sxs-lookup"><span data-stu-id="4f5cb-103">Perform custom join operations</span></span>

<span data-ttu-id="4f5cb-104">Questo esempio descrive come eseguire operazioni di join personalizzate non possibili con la clausola `join`.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-104">This example shows how to perform join operations that aren't possible with the `join` clause.</span></span> <span data-ttu-id="4f5cb-105">In un'espressione di query la clausola `join` è limitata e ottimizzata per gli equijoin che sono in assoluto il tipo più comune di operazione di join.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-105">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="4f5cb-106">Quando si esegue un equijoin, è quasi sempre possibile ottenere le prestazioni migliori usando la clausola `join`.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-106">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>

<span data-ttu-id="4f5cb-107">Non è tuttavia possibile usare la clausola `join` nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5cb-107">However, the `join` clause cannot be used in the following cases:</span></span>

- <span data-ttu-id="4f5cb-108">Quando il join viene affermato su un'espressione di ineguaglianza (un non equijoin).</span><span class="sxs-lookup"><span data-stu-id="4f5cb-108">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>

- <span data-ttu-id="4f5cb-109">Quando il join viene affermato su più di un'espressione di eguaglianza o di ineguaglianza.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-109">When the join is predicated on more than one expression of equality or inequality.</span></span>

- <span data-ttu-id="4f5cb-110">Quando è necessario introdurre una variabile di intervallo temporanea per la sequenza del lato destro (interno) prima dell'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-110">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>

 <span data-ttu-id="4f5cb-111">Per eseguire join che non sono equijoin, è possibile usare più clausole `from` per introdurre ogni origine dati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-111">To perform joins that aren't equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="4f5cb-112">Si applica quindi un'espressione di predicato in una clausola `where` alla variabile di intervallo per ogni origine.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-112">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="4f5cb-113">L'espressione può inoltre avere il formato di una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-113">The expression also can take the form of a method call.</span></span>

> [!NOTE]
> <span data-ttu-id="4f5cb-114">Non confondere questo tipo di operazione di join personalizzata con l'uso di più clausole `from` per accedere a raccolte interne.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-114">Don't confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="4f5cb-115">Per ulteriori informazioni, vedere [Clausola join](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f5cb-115">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f5cb-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f5cb-116">Example</span></span>

<span data-ttu-id="4f5cb-117">Il primo metodo nell'esempio seguente illustra un cross join semplice.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-117">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="4f5cb-118">I cross join devono essere usati con attenzione perché possono produrre set di risultati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-118">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="4f5cb-119">Tuttavia, possono essere utili in alcuni scenari per la creazione di sequenze di origine in cui eseguire query aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-119">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>

<span data-ttu-id="4f5cb-120">Il secondo metodo produce una sequenza di tutti i prodotti il cui ID categoria è incluso nell'elenco di categorie sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-120">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="4f5cb-121">Si noti l'uso della clausola `let` e del metodo `Contains` per creare una matrice temporanea.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-121">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="4f5cb-122">È anche possibile creare la matrice prima della query ed eliminare la prima clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-122">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a><span data-ttu-id="4f5cb-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f5cb-123">Example</span></span>

<span data-ttu-id="4f5cb-124">Nell'esempio seguente la query deve creare un join di due sequenze basate su chiavi corrispondenti che, nel caso della sequenza interna (lato destro), non possono essere ottenute prima della clausola join stessa.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-124">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="4f5cb-125">Se il join viene eseguito con una clausola `join`, il metodo `Split` dovrà essere chiamato per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-125">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="4f5cb-126">L'uso di più clausole `from` consente alla query di evitare l'overhead della chiamata al metodo ripetuta.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-126">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="4f5cb-127">Tuttavia, poiché `join` è ottimizzata, in questo caso particolare potrebbe risultare ancora più veloce rispetto all'uso di più clausole `from`.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-127">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="4f5cb-128">I risultati varieranno principalmente in base al costo in termini di utilizzo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4f5cb-128">The results will vary depending primarily on how expensive the method call is.</span></span>

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a><span data-ttu-id="4f5cb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f5cb-129">See also</span></span>

- [<span data-ttu-id="4f5cb-130">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4f5cb-130">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="4f5cb-131">clausola join</span><span class="sxs-lookup"><span data-stu-id="4f5cb-131">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="4f5cb-132">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="4f5cb-132">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
