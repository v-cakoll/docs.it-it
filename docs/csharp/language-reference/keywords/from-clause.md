---
title: Clausola from (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- from_CSharpKeyword
- from
dev_langs:
- CSharp
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: 27
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
ms.openlocfilehash: f0165144acfa8d0928015e8222179f7e69f19644
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="from-clause-c-reference"></a><span data-ttu-id="8e2ff-102">Clausola from (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="8e2ff-102">from clause (C# Reference)</span></span>
<span data-ttu-id="8e2ff-103">Un'espressione di query deve iniziare con una clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-103">A query expression must begin with a `from` clause.</span></span> <span data-ttu-id="8e2ff-104">Inoltre, un'espressione di query può contenere sottoquery che iniziano anch'esse con una clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-104">Additionally, a query expression can contain sub-queries, which also begin with a `from` clause.</span></span> <span data-ttu-id="8e2ff-105">La clausola `from` specifica gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e2ff-105">The `from` clause specifies the following:</span></span>  
  
-   <span data-ttu-id="8e2ff-106">Origine dati su cui verrà eseguita la query o la sottoquery.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-106">The data source on which the query or sub-query will be run.</span></span>  
  
-   <span data-ttu-id="8e2ff-107">*Variabile di intervallo* locale che rappresenta ogni elemento nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-107">A local *range variable* that represents each element in the source sequence.</span></span>  
  
 <span data-ttu-id="8e2ff-108">Sia la variabile di intervallo che l'origine dati sono fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-108">Both the range variable and the data source are strongly typed.</span></span> <span data-ttu-id="8e2ff-109">L'origine dati a cui si fa riferimento nella clausola `from` deve essere di tipo <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> o di un tipo derivato, <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-109">The data source referenced in the `from` clause must have a type of <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span>  
  
 <span data-ttu-id="8e2ff-110">Nell'esempio seguente `numbers` è l'origine dati e `num` è la variabile di intervallo.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-110">In the following example, `numbers` is the data source and `num` is the range variable.</span></span> <span data-ttu-id="8e2ff-111">Si noti che entrambe le variabili sono fortemente tipizzate anche se viene usata la parola chiave [var](../../../csharp/language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-111">Note that both variables are strongly typed even through the [var](../../../csharp/language-reference/keywords/var.md) keyword is used.</span></span>  
  
 <span data-ttu-id="8e2ff-112">[!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e2ff-112">[!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]</span></span>  
  
## <a name="the-range-variable"></a><span data-ttu-id="8e2ff-113">Variabile di intervallo</span><span class="sxs-lookup"><span data-stu-id="8e2ff-113">The Range Variable</span></span>  
 <span data-ttu-id="8e2ff-114">Tramite l'inferenza, il compilatore deriva il tipo della variabile di intervallo quando l'origine dati implementa <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-114">The compiler infers the type of the range variable when the data source implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="8e2ff-115">Se, ad esempio, l'origine è di tipo `IEnumerable<Customer>`, la variabile di intervallo derivata tramite inferenza sarà `Customer`.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-115">For example, if the source has a type of `IEnumerable<Customer>`, then the range variable is inferred to be `Customer`.</span></span> <span data-ttu-id="8e2ff-116">È necessario specificare il tipo in modo esplicito solo quando l'origine è un tipo `IEnumerable` non generico, ad esempio <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-116">The only time that you must specify the type explicitly is when the source is a non-generic `IEnumerable` type such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="8e2ff-117">Per altre informazioni, vedere [Procedura: eseguire una query su un ArrayList con LINQ](http://msdn.microsoft.com/library/c318b79a-fa4d-4de3-b62d-c1162beb267e).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-117">For more information, see [How to: Query an ArrayList with LINQ](http://msdn.microsoft.com/library/c318b79a-fa4d-4de3-b62d-c1162beb267e).</span></span>  
  
 <span data-ttu-id="8e2ff-118">Nell'esempio precedente si deriva tramite inferenza che `num` è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-118">In the previous example `num` is inferred to be of type `int`.</span></span> <span data-ttu-id="8e2ff-119">Poiché la variabile di intervallo è fortemente tipizzata, è possibile chiamare metodi su di essa o usarla in altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-119">Because the range variable is strongly typed, you can call methods on it or use it in other operations.</span></span> <span data-ttu-id="8e2ff-120">Ad esempio, invece di scrivere `select num`, è possibile scrivere `select num.ToString()` per fare in modo che l'espressione di query restituisca una sequenza di stringhe invece che di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-120">For example, instead of writing `select num`, you could write `select num.ToString()` to cause the query expression to return a sequence of strings instead of integers.</span></span> <span data-ttu-id="8e2ff-121">Oppure è possibile scrivere `select n + 10` per fare in modo che l'espressione restituisca la sequenza 14, 11, 13, 12 10.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-121">Or you could write `select n + 10` to cause the expression to return the sequence 14, 11, 13, 12, 10.</span></span> <span data-ttu-id="8e2ff-122">Per altre informazioni, vedere [Clausola select](../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-122">For more information, see [select clause](../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
 <span data-ttu-id="8e2ff-123">La variabile di intervallo è analoga a una variabile di iterazione in un'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md) eccetto che per una differenza molto importante: una variabile di intervallo non archivia effettivamente mai i dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-123">The range variable is like an iteration variable in a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement except for one very important difference: a range variable never actually stores data from the source.</span></span> <span data-ttu-id="8e2ff-124">Si tratta semplicemente di un pratico aspetto sintattico che consente alla query di descrivere ciò che si verificherà quando la query verrà eseguita.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-124">It just a syntactic convenience that enables the query to describe what will occur when the query is executed.</span></span> <span data-ttu-id="8e2ff-125">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-125">For more information, see [Introduction to LINQ Queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="compound-from-clauses"></a><span data-ttu-id="8e2ff-126">Clausole from composte</span><span class="sxs-lookup"><span data-stu-id="8e2ff-126">Compound from Clauses</span></span>  
 <span data-ttu-id="8e2ff-127">In alcuni casi, ogni elemento nella sequenza di origine può essere esso stesso una sequenza o contenere una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-127">In some cases, each element in the source sequence may itself be either a sequence or contain a sequence.</span></span> <span data-ttu-id="8e2ff-128">Ad esempio, l'origine dati può essere un oggetto `IEnumerable<Student>` in cui ogni oggetto studente della sequenza contiene un elenco di punteggi dei test.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-128">For example, your data source may be an `IEnumerable<Student>` where each student object in the sequence contains a list of test scores.</span></span> <span data-ttu-id="8e2ff-129">Per accedere all'elenco interno in ogni elemento `Student` è possibile usare clausole `from` composte.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-129">To access the inner list within each `Student` element, you can use compound `from` clauses.</span></span> <span data-ttu-id="8e2ff-130">La tecnica è analoga all'uso di istruzioni [foreach](../../../csharp/language-reference/keywords/foreach-in.md) nidificate.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-130">The technique is like using nested [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statements.</span></span> <span data-ttu-id="8e2ff-131">È possibile aggiungere clausole [where](../../../csharp/language-reference/keywords/partial-method.md) o [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) a una delle due clausole `from` per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-131">You can add [where](../../../csharp/language-reference/keywords/partial-method.md) or [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clauses to either `from` clause to filter the results.</span></span> <span data-ttu-id="8e2ff-132">L'esempio seguente mostra una sequenza di oggetti `Student`, ognuno dei quali contiene un oggetto `List` interno di numeri interi che rappresentano i punteggi dei test.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-132">The following example shows a sequence of `Student` objects, each of which contains an inner `List` of integers representing test scores.</span></span> <span data-ttu-id="8e2ff-133">Per accedere all'elenco interno, usare una clausola `from` composta.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-133">To access the inner list, use a compound `from` clause.</span></span> <span data-ttu-id="8e2ff-134">Se necessario, è possibile inserire clausole tra le due clausole `from`.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-134">You can insert clauses between the two `from` clauses if necessary.</span></span>  
  
 <span data-ttu-id="8e2ff-135">[!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e2ff-135">[!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]</span></span>  
  
## <a name="using-multiple-from-clauses-to-perform-joins"></a><span data-ttu-id="8e2ff-136">Uso di più clausole from per eseguire join</span><span class="sxs-lookup"><span data-stu-id="8e2ff-136">Using Multiple from Clauses to Perform Joins</span></span>  
 <span data-ttu-id="8e2ff-137">Una clausola `from` composta viene usata per accedere a raccolte interne in una singola origine dati.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-137">A compound `from` clause is used to access inner collections in a single data source.</span></span> <span data-ttu-id="8e2ff-138">Una query può tuttavia contenere anche più clausole `from` che generano query supplementari da origini dati indipendenti.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-138">However, a query can also contain multiple `from` clauses that generate supplemental queries from independent data sources.</span></span> <span data-ttu-id="8e2ff-139">Questa tecnica consente di eseguire determinati tipi di operazioni di join che non sono possibili usando la [clausola join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-139">This technique enables you to perform certain types of join operations that are not possible by using the [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
 <span data-ttu-id="8e2ff-140">L'esempio seguente mostra in che modo due clausole `from` possono essere usate per formare un cross join completo di due origini dati.</span><span class="sxs-lookup"><span data-stu-id="8e2ff-140">The following example shows how two `from` clauses can be used to form a complete cross join of two data sources.</span></span>  
  
 <span data-ttu-id="8e2ff-141">[!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e2ff-141">[!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]</span></span>  
  
 <span data-ttu-id="8e2ff-142">Per altre informazioni sulle operazioni di join che usano più clausole `from`, vedere [Procedura: eseguire operazioni di join personalizzate](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ff-142">For more information about join operations that use multiple `from` clauses, see [How to: Perform Custom Join Operations](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2ff-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e2ff-143">See Also</span></span>  
 <span data-ttu-id="8e2ff-144">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8e2ff-144">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 [<span data-ttu-id="8e2ff-145">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="8e2ff-145">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

