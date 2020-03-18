---
title: Clausola select - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: 68ea7ad6fc7cf5580dbdd0ae7f012f36566db0dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173510"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="94548-102">Clausola select (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="94548-102">select clause (C# Reference)</span></span>

<span data-ttu-id="94548-103">In un'espressione di query, la clausola `select` specifica il tipo di valori che verranno prodotti quando viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="94548-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="94548-104">Il risultato è basato sulla valutazione di tutte le clausole precedenti e su qualsiasi espressione nella clausola `select` stessa.</span><span class="sxs-lookup"><span data-stu-id="94548-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="94548-105">Un'espressione di query deve terminare con una clausola `select` o una clausola [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="94548-105">A query expression must terminate with either a `select` clause or a [group](group-clause.md) clause.</span></span>

<span data-ttu-id="94548-106">Nell'esempio seguente viene illustrata una semplice clausola `select` in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="94548-106">The following example shows a simple `select` clause in a query expression.</span></span>

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

<span data-ttu-id="94548-107">Il tipo della sequenza prodotto dalla clausola `select` determina il tipo della variabile di query `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="94548-107">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="94548-108">Nel caso più semplice, la clausola `select` specifica solo la variabile di intervallo.</span><span class="sxs-lookup"><span data-stu-id="94548-108">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="94548-109">In tal modo, la sequenza restituita contiene elementi dello stesso tipo dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="94548-109">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="94548-110">Per ulteriori informazioni, vedere Relazioni tra tipi [in Operazioni di query LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="94548-110">For more information, see [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="94548-111">Tuttavia, la clausola `select` fornisce anche un potente meccanismo per la trasformazione (o la *proiezione*) dell'origine dati in nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="94548-111">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="94548-112">Per altre informazioni, vedere [Trasformazioni dati con LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="94548-112">For more information, see [Data Transformations with LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="94548-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="94548-113">Example</span></span>

<span data-ttu-id="94548-114">Nell'esempio seguente sono illustrate tutte le diverse forme che una clausola `select` può avere.</span><span class="sxs-lookup"><span data-stu-id="94548-114">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="94548-115">In ogni query prendere nota della relazione tra `select` la `studentQuery2`clausola e il tipo della variabile di *query* (`studentQuery1`, e così via).</span><span class="sxs-lookup"><span data-stu-id="94548-115">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

<span data-ttu-id="94548-116">Come illustrato in `studentQuery8` nell'esempio precedente, in alcuni casi è preferibile che gli elementi della sequenza restituita contengano solo un subset delle proprietà degli elementi di origine.</span><span class="sxs-lookup"><span data-stu-id="94548-116">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="94548-117">Riducendo al minimo le dimensioni della sequenza restituita, è possibile ridurre i requisiti di memoria e aumentare la velocità di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="94548-117">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="94548-118">A tale scopo, è possibile creare un tipo anonimo nella clausola `select` e usare un inizializzatore di oggetto per inizializzarlo con le proprietà appropriate dall'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="94548-118">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="94548-119">Per un esempio di come eseguire questa operazione, vedere [Inizializzatori di oggetto e di raccolta](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="94548-119">For an example of how to do this, see [Object and Collection Initializers](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="94548-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="94548-120">Remarks</span></span>

<span data-ttu-id="94548-121">In fase di compilazione, la clausola `select` viene convertita in una chiamata al metodo per l'operatore query standard <xref:System.Linq.Enumerable.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="94548-121">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="94548-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94548-122">See also</span></span>

- [<span data-ttu-id="94548-123">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="94548-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="94548-124">Parole chiave di query (LINQ)Query Keywords (LINQ)</span><span class="sxs-lookup"><span data-stu-id="94548-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="94548-125">clausola from</span><span class="sxs-lookup"><span data-stu-id="94548-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="94548-126">parziale (Metodo) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="94548-126">partial (Method) (C# Reference)</span></span>](partial-method.md)
- [<span data-ttu-id="94548-127">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="94548-127">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="94548-128">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="94548-128">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="94548-129">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="94548-129">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
