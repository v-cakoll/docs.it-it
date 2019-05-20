---
title: Clausola where (Riferimento C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: fc259f0e0a83d2f55bf2d50fa336c9201b8b5bef
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633209"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="d81d5-102">Clausola where (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="d81d5-102">where clause (C# Reference)</span></span>

<span data-ttu-id="d81d5-103">La clausola `where` viene usata in un'espressione di query per specificare quali elementi dell'origine dati verranno restituiti nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="d81d5-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="d81d5-104">Viene applicata una condizione booleana (*predicato*) a ogni elemento di origine (a cui fa riferimento la variabile di intervallo) e viene restituita quella per cui la condizione specificata è vera.</span><span class="sxs-lookup"><span data-stu-id="d81d5-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="d81d5-105">Una singola espressione di query può contenere più clausole `where` e una singola clausola può contenere più sottoespressioni di predicato.</span><span class="sxs-lookup"><span data-stu-id="d81d5-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="d81d5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d81d5-106">Example</span></span>

<span data-ttu-id="d81d5-107">Nell'esempio seguente la clausola `where` esclude tutti i numeri tranne quelli minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="d81d5-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="d81d5-108">Se si rimuove la clausola `where`, vengono restituiti tutti i numeri dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d81d5-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="d81d5-109">L'espressione `num < 5` è il predicato che viene applicato a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="d81d5-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="d81d5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d81d5-110">Example</span></span>

<span data-ttu-id="d81d5-111">In una singola clausola `where` è possibile specificare tutti i predicati necessari usando gli operatori [ && ](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) e [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="d81d5-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="d81d5-112">Nell'esempio seguente la query specifica due predicati per selezionare solo i numeri pari minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="d81d5-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="d81d5-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d81d5-113">Example</span></span>

<span data-ttu-id="d81d5-114">Una clausola `where` può contenere uno o più metodi che restituiscono valori booleani.</span><span class="sxs-lookup"><span data-stu-id="d81d5-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="d81d5-115">Nell'esempio seguente la clausola `where` usa un metodo per determinare se il valore corrente della variabile di intervallo è pari o dispari.</span><span class="sxs-lookup"><span data-stu-id="d81d5-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="d81d5-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d81d5-116">Remarks</span></span>

<span data-ttu-id="d81d5-117">La clausola `where` è un meccanismo di filtro.</span><span class="sxs-lookup"><span data-stu-id="d81d5-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="d81d5-118">Può essere posizionata praticamente ovunque in un'espressione di query, ma non può essere la prima o l'ultima clausola.</span><span class="sxs-lookup"><span data-stu-id="d81d5-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="d81d5-119">Una clausola `where` la può apparire prima o dopo una clausola [group](group-clause.md) a seconda se gli elementi di origine devono essere filtrati prima o dopo essere stati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="d81d5-119">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="d81d5-120">Se un predicato specificato non è valido per gli elementi nell'origine dati, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d81d5-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="d81d5-121">Questo è uno dei vantaggi del controllo efficace del tipo offerto da [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d81d5-121">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>

<span data-ttu-id="d81d5-122">In fase di compilazione, la parola chiave `where` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> dell'operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="d81d5-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="d81d5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d81d5-123">See also</span></span>

- [<span data-ttu-id="d81d5-124">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d81d5-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="d81d5-125">Clausola from</span><span class="sxs-lookup"><span data-stu-id="d81d5-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="d81d5-126">Clausola select</span><span class="sxs-lookup"><span data-stu-id="d81d5-126">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="d81d5-127">Filtraggio dei dati</span><span class="sxs-lookup"><span data-stu-id="d81d5-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="d81d5-128">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="d81d5-128">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="d81d5-129">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="d81d5-129">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
