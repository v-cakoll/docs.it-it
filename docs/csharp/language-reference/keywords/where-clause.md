---
title: Clausola where (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 33616e4eacb484b9c6eda3862cd86fdd1e6df165
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173484"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="9d4be-102">Clausola where (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="9d4be-102">where clause (C# Reference)</span></span>

<span data-ttu-id="9d4be-103">La clausola `where` viene usata in un'espressione di query per specificare quali elementi dell'origine dati verranno restituiti nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="9d4be-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="9d4be-104">Viene applicata una condizione booleana (*predicato*) a ogni elemento di origine (a cui fa riferimento la variabile di intervallo) e viene restituita quella per cui la condizione specificata è vera.</span><span class="sxs-lookup"><span data-stu-id="9d4be-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="9d4be-105">Una singola espressione di query può contenere più clausole `where` e una singola clausola può contenere più sottoespressioni di predicato.</span><span class="sxs-lookup"><span data-stu-id="9d4be-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="9d4be-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d4be-106">Example</span></span>

<span data-ttu-id="9d4be-107">Nell'esempio seguente la clausola `where` esclude tutti i numeri tranne quelli minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="9d4be-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="9d4be-108">Se si rimuove la clausola `where`, vengono restituiti tutti i numeri dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9d4be-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="9d4be-109">L'espressione `num < 5` è il predicato che viene applicato a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="9d4be-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="9d4be-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d4be-110">Example</span></span>

<span data-ttu-id="9d4be-111">All'interno `where` di una singola clausola, è possibile specificare tutti i predicati necessari utilizzando gli [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) operatori e [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) .</span><span class="sxs-lookup"><span data-stu-id="9d4be-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="9d4be-112">Nell'esempio seguente la query specifica due predicati per selezionare solo i numeri pari minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="9d4be-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="9d4be-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d4be-113">Example</span></span>

<span data-ttu-id="9d4be-114">Una clausola `where` può contenere uno o più metodi che restituiscono valori booleani.</span><span class="sxs-lookup"><span data-stu-id="9d4be-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="9d4be-115">Nell'esempio seguente la clausola `where` usa un metodo per determinare se il valore corrente della variabile di intervallo è pari o dispari.</span><span class="sxs-lookup"><span data-stu-id="9d4be-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="9d4be-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9d4be-116">Remarks</span></span>

<span data-ttu-id="9d4be-117">La clausola `where` è un meccanismo di filtro.</span><span class="sxs-lookup"><span data-stu-id="9d4be-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="9d4be-118">Può essere posizionata praticamente ovunque in un'espressione di query, ma non può essere la prima o l'ultima clausola.</span><span class="sxs-lookup"><span data-stu-id="9d4be-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="9d4be-119">Una clausola `where` la può apparire prima o dopo una clausola [group](group-clause.md) a seconda se gli elementi di origine devono essere filtrati prima o dopo essere stati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="9d4be-119">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="9d4be-120">Se un predicato specificato non è valido per gli elementi nell'origine dati, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9d4be-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="9d4be-121">Questo è uno dei vantaggi del controllo dei tipi forte fornito da LINQ.</span><span class="sxs-lookup"><span data-stu-id="9d4be-121">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="9d4be-122">In fase di compilazione, la parola chiave `where` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> dell'operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="9d4be-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d4be-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d4be-123">See also</span></span>

- [<span data-ttu-id="9d4be-124">Parole chiave di query (LINQ)Query Keywords (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9d4be-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="9d4be-125">clausola from</span><span class="sxs-lookup"><span data-stu-id="9d4be-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="9d4be-126">clausola select</span><span class="sxs-lookup"><span data-stu-id="9d4be-126">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="9d4be-127">Filtro dei dati</span><span class="sxs-lookup"><span data-stu-id="9d4be-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="9d4be-128">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="9d4be-128">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="9d4be-129">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9d4be-129">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
