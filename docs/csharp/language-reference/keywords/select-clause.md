---
title: Clausola select (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a><span data-ttu-id="919fb-102">Clausola select (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="919fb-102">select clause (C# Reference)</span></span>
<span data-ttu-id="919fb-103">In un'espressione di query, la clausola `select` specifica il tipo di valori che verranno prodotti quando viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="919fb-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="919fb-104">Il risultato è basato sulla valutazione di tutte le clausole precedenti e su qualsiasi espressione nella clausola `select` stessa.</span><span class="sxs-lookup"><span data-stu-id="919fb-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="919fb-105">Un'espressione di query deve terminare con una clausola `select` o una clausola [group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="919fb-106">Nell'esempio seguente viene illustrata una semplice clausola `select` in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="919fb-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 <span data-ttu-id="919fb-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="919fb-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="919fb-108">Il tipo della sequenza prodotto dalla clausola `select` determina il tipo della variabile di query `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="919fb-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="919fb-109">Nel caso più semplice, la clausola `select` specifica solo la variabile di intervallo.</span><span class="sxs-lookup"><span data-stu-id="919fb-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="919fb-110">In tal modo, la sequenza restituita contiene elementi dello stesso tipo dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="919fb-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="919fb-111">Per altre informazioni, vedere [Relazioni tra i tipi nelle operazioni di query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-111">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="919fb-112">Tuttavia, la clausola `select` fornisce anche un potente meccanismo per la trasformazione (o la *proiezione*) dell'origine dati in nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="919fb-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="919fb-113">Per altre informazioni, vedere [Trasformazioni dati con LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-113">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="919fb-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="919fb-114">Example</span></span>  
 <span data-ttu-id="919fb-115">Nell'esempio seguente sono illustrate tutte le diverse forme che una clausola `select` può avere.</span><span class="sxs-lookup"><span data-stu-id="919fb-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="919fb-116">In ogni query, si noti la relazione tra la clausola `select` e il tipo di *variabile di query* (`studentQuery1`, `studentQuery2` e così via).</span><span class="sxs-lookup"><span data-stu-id="919fb-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 <span data-ttu-id="919fb-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="919fb-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="919fb-118">Come illustrato in `studentQuery8` nell'esempio precedente, in alcuni casi è preferibile che gli elementi della sequenza restituita contengano solo un subset delle proprietà degli elementi di origine.</span><span class="sxs-lookup"><span data-stu-id="919fb-118">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="919fb-119">Riducendo al minimo le dimensioni della sequenza restituita, è possibile ridurre i requisiti di memoria e aumentare la velocità di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="919fb-119">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="919fb-120">A tale scopo, è possibile creare un tipo anonimo nella clausola `select` e usare un inizializzatore di oggetto per inizializzarlo con le proprietà appropriate dall'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="919fb-120">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="919fb-121">Per un esempio di come eseguire questa operazione, vedere [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-121">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="919fb-122">Note</span><span class="sxs-lookup"><span data-stu-id="919fb-122">Remarks</span></span>  
 <span data-ttu-id="919fb-123">In fase di compilazione, la clausola `select` viene convertita in una chiamata al metodo per l'operatore query standard <xref:System.Linq.Enumerable.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="919fb-123">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="919fb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="919fb-124">See Also</span></span>  
 <span data-ttu-id="919fb-125">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="919fb-126">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-126">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="919fb-127">[Clausola From](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-127">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="919fb-128">[parziale (Metodo) (Riferimenti per C#)](../../../csharp/language-reference/keywords/partial-method.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-128">[partial (Method) (C# Reference)](../../../csharp/language-reference/keywords/partial-method.md) </span></span>  
 <span data-ttu-id="919fb-129">[Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-129">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="919fb-130">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="919fb-130">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="919fb-131">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="919fb-131">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

