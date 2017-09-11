---
title: Operazioni di query LINQ di base (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5dbebb7950678a0f40ec774d23b42dfe89cff49
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="basic-linq-query-operations-c"></a><span data-ttu-id="fbd94-102">Operazioni di query LINQ di base (C#)</span><span class="sxs-lookup"><span data-stu-id="fbd94-102">Basic LINQ Query Operations (C#)</span></span>
<span data-ttu-id="fbd94-103">Questo argomento offre una breve introduzione alle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] e ad alcuni tipi di operazioni specifiche eseguite in una query.</span><span class="sxs-lookup"><span data-stu-id="fbd94-103">This topic gives a brief introduction to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions and some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="fbd94-104">Informazioni più specifiche sono disponibili negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbd94-104">More detailed information is in the following topics:</span></span>  
  
 [<span data-ttu-id="fbd94-105">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="fbd94-105">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [<span data-ttu-id="fbd94-106">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="fbd94-106">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [<span data-ttu-id="fbd94-107">Procedura dettagliata: scrittura di query in C#</span><span class="sxs-lookup"><span data-stu-id="fbd94-107">Walkthrough: Writing Queries in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  <span data-ttu-id="fbd94-108">Se si ha già familiarità con un linguaggio di query, ad esempio SQL o XQuery, è possibile ignorare la maggior parte di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fbd94-108">If you already are familiar with a query language such as SQL or XQuery, you can skip most of this topic.</span></span> <span data-ttu-id="fbd94-109">Leggere la sezione sulla "clausola `from`" più avanti per informazioni sull'ordine delle clausole nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbd94-109">Read about the "`from` clause" in the next section to learn about the order of clauses in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span>  
  
## <a name="obtaining-a-data-source"></a><span data-ttu-id="fbd94-110">Ottenere un'origine dei dati</span><span class="sxs-lookup"><span data-stu-id="fbd94-110">Obtaining a Data Source</span></span>  
 <span data-ttu-id="fbd94-111">In una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], il primo passaggio consiste nella specifica dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="fbd94-111">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source.</span></span> <span data-ttu-id="fbd94-112">In C#, come nella maggior parte dei linguaggi di programmazione, una variabile deve essere dichiarata prima di essere usata.</span><span class="sxs-lookup"><span data-stu-id="fbd94-112">In C# as in most programming languages a variable must be declared before it can be used.</span></span> <span data-ttu-id="fbd94-113">In una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], la clausola `from` viene dichiarata per prima per introdurre l'origine dei dati (`customers`) e la *variabile di intervallo* (`cust`).</span><span class="sxs-lookup"><span data-stu-id="fbd94-113">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the `from` clause comes first in order to introduce the data source (`customers`) and the *range variable* (`cust`).</span></span>  
  
 <span data-ttu-id="fbd94-114">[!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-114">[!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_1.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-115">La variabile di intervallo è come la variabile di iterazione in un ciclo `foreach` ad eccezione del fatto che non si verifica alcuna iterazione in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="fbd94-115">The range variable is like the iteration variable in a `foreach` loop except that no actual iteration occurs in a query expression.</span></span> <span data-ttu-id="fbd94-116">Quando viene eseguita la query, la variabile di intervallo verrà usata come riferimento a ogni elemento successivo in `customers`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-116">When the query is executed, the range variable will serve as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="fbd94-117">Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="fbd94-117">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="fbd94-118">Altre variabili di intervallo possono essere introdotte da una clausola `let`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-118">Additional range variables can be introduced by a `let` clause.</span></span> <span data-ttu-id="fbd94-119">Per altre informazioni, vedere [Clausola let](../../../../csharp/language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-119">For more information, see [let clause](../../../../csharp/language-reference/keywords/let-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbd94-120">Per origini dati non generiche, ad esempio <xref:System.Collections.ArrayList>, la variabile di intervallo deve essere tipizzata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="fbd94-120">For non-generic data sources such as <xref:System.Collections.ArrayList>, the range variable must be explicitly typed.</span></span> <span data-ttu-id="fbd94-121">Per altre informazioni, vedere [Procedura: Eseguire una query su un ArrayList con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) e [Clausola from](../../../../csharp/language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-121">For more information, see [How to: Query an ArrayList with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) and [from clause](../../../../csharp/language-reference/keywords/from-clause.md).</span></span>  
  
## <a name="filtering"></a><span data-ttu-id="fbd94-122">Filtro</span><span class="sxs-lookup"><span data-stu-id="fbd94-122">Filtering</span></span>  
 <span data-ttu-id="fbd94-123">Probabilmente l'operazione di query più comune consiste nell'applicazione di un filtro sotto forma di espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="fbd94-123">Probably the most common query operation is to apply a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="fbd94-124">Il filtro fa in modo che la query restituisca solo gli elementi per i quali l'espressione è vera.</span><span class="sxs-lookup"><span data-stu-id="fbd94-124">The filter causes the query to return only those elements for which the expression is true.</span></span> <span data-ttu-id="fbd94-125">Il risultato viene generato utilizzando la clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-125">The result is produced by using the `where` clause.</span></span> <span data-ttu-id="fbd94-126">Il filtro in realtà specifica gli elementi da escludere dalla sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="fbd94-126">The filter in effect specifies which elements to exclude from the source sequence.</span></span> <span data-ttu-id="fbd94-127">Nell'esempio seguente vengono restituiti solo i `customers` che hanno un indirizzo in Londra.</span><span class="sxs-lookup"><span data-stu-id="fbd94-127">In the following example, only those `customers` who have an address in London are returned.</span></span>  
  
 <span data-ttu-id="fbd94-128">[!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-128">[!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_2.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-129">È possibile usare gli operatori logici `AND` e `OR` di C# per applicare tutte le espressioni necessarie nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-129">You can use the familiar C# logical `AND` and `OR` operators to apply as many filter expressions as necessary in the `where` clause.</span></span> <span data-ttu-id="fbd94-130">Ad esempio, per restituire solo i clienti in "Londra" `AND` che si chiamano "Devon", si scrive il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fbd94-130">For example, to return only customers from "London" `AND` whose name is "Devon" you would write the following code:</span></span>  
  
 <span data-ttu-id="fbd94-131">[!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-131">[!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_3.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-132">Per restituire i clienti di Londra o Parigi, si scrive il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fbd94-132">To return customers from London or Paris, you would write the following code:</span></span>  
  
 <span data-ttu-id="fbd94-133">[!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-133">[!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_4.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-134">Per altre informazioni, vedere [Clausola where](../../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-134">For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="ordering"></a><span data-ttu-id="fbd94-135">Ordering</span><span class="sxs-lookup"><span data-stu-id="fbd94-135">Ordering</span></span>  
 <span data-ttu-id="fbd94-136">È spesso utile ordinare i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="fbd94-136">Often it is convenient to sort the returned data.</span></span> <span data-ttu-id="fbd94-137">La clausola `orderby` ordinerà gli elementi della sequenza restituita in base all'operatore di confronto per il tipo che si sta ordinando.</span><span class="sxs-lookup"><span data-stu-id="fbd94-137">The `orderby` clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted.</span></span> <span data-ttu-id="fbd94-138">Ad esempio, la query seguente può essere estesa per ordinare i risultati basati sulla proprietà `Name`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-138">For example, the following query can be extended to sort the results based on the `Name` property.</span></span> <span data-ttu-id="fbd94-139">Poiché `Name` è una stringa, l'operatore di confronto esegue un ordinamento alfabetico da A a Z.</span><span class="sxs-lookup"><span data-stu-id="fbd94-139">Because `Name` is a string, the default comparer performs an alphabetical sort from A to Z.</span></span>  
  
 <span data-ttu-id="fbd94-140">[!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-140">[!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_5.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-141">Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `orderby…descending`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-141">To order the results in reverse order, from Z to A, use the `orderby…descending` clause.</span></span>  
  
 <span data-ttu-id="fbd94-142">Per altre informazioni, vedere [Clausola orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-142">For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).</span></span>  
  
## <a name="grouping"></a><span data-ttu-id="fbd94-143">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="fbd94-143">Grouping</span></span>  
 <span data-ttu-id="fbd94-144">La clausola `group` consente di raggruppare i risultati in base a una chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="fbd94-144">The `group` clause enables you to group your results based on a key that you specify.</span></span> <span data-ttu-id="fbd94-145">Ad esempio, è possibile specificare che i risultati devono essere raggruppati in base a `City` in modo che tutti i clienti di Londra o Parigi siano elencati in gruppi individuali.</span><span class="sxs-lookup"><span data-stu-id="fbd94-145">For example you could specify that the results should be grouped by the `City` so that all customers from London or Paris are in individual groups.</span></span> <span data-ttu-id="fbd94-146">In questo caso, `cust.City` è la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fbd94-146">In this case, `cust.City` is the key.</span></span>  
  
 <span data-ttu-id="fbd94-147">[!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-147">[!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_6.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-148">Quando si termina una query con una clausola `group`, i risultati vengono rappresentati come un elenco di elenchi.</span><span class="sxs-lookup"><span data-stu-id="fbd94-148">When you end a query with a `group` clause, your results take the form of a list of lists.</span></span> <span data-ttu-id="fbd94-149">Ogni elemento nell'elenco è un oggetto che ha un membro `Key` e un elenco di elementi che sono raggruppati sotto tale chiave.</span><span class="sxs-lookup"><span data-stu-id="fbd94-149">Each element in the list is an object that has a `Key` member and a list of elements that are grouped under that key.</span></span> <span data-ttu-id="fbd94-150">Quando si esegue l'iterazione di una query che produce una sequenza di gruppi, è necessario usare un ciclo `foreach` annidato.</span><span class="sxs-lookup"><span data-stu-id="fbd94-150">When you iterate over a query that produces a sequence of groups, you must use a nested `foreach` loop.</span></span> <span data-ttu-id="fbd94-151">Il ciclo esterno esegue l'iterazione di ogni gruppo e il ciclo interno esegue l'iterazione dei membri di ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbd94-151">The outer loop iterates over each group, and the inner loop iterates over each group's members.</span></span>  
  
 <span data-ttu-id="fbd94-152">Se è necessario fare riferimento ai risultati di un'operazione di gruppo, è possibile usare la parola chiave `into` per creare un identificatore sul quale eseguire query addizionali.</span><span class="sxs-lookup"><span data-stu-id="fbd94-152">If you must refer to the results of a group operation, you can use the `into` keyword to create an identifier that can be queried further.</span></span> <span data-ttu-id="fbd94-153">La query seguente restituisce solo i gruppi che contengono più di due clienti:</span><span class="sxs-lookup"><span data-stu-id="fbd94-153">The following query returns only those groups that contain more than two customers:</span></span>  
  
 <span data-ttu-id="fbd94-154">[!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-154">[!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_7.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-155">Per altre informazioni, vedere [Clausola group](../../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-155">For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="joining"></a><span data-ttu-id="fbd94-156">Uso di join</span><span class="sxs-lookup"><span data-stu-id="fbd94-156">Joining</span></span>  
 <span data-ttu-id="fbd94-157">Le operazioni di join creano associazioni tra le sequenze che non sono modellate in modo esplicito nelle origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="fbd94-157">Join operations create associations between sequences that are not explicitly modeled in the data sources.</span></span> <span data-ttu-id="fbd94-158">Ad esempio, è possibile eseguire un join per trovare tutti i clienti e i distributori che hanno la stessa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="fbd94-158">For example you can perform a join to find all the customers and distributors who have the same location.</span></span> <span data-ttu-id="fbd94-159">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], la clausola `join` usa sempre raccolte di oggetti anziché direttamente le tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="fbd94-159">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] the `join` clause always works against object collections instead of database tables directly.</span></span>  
  
 <span data-ttu-id="fbd94-160">[!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd94-160">[!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_8.cs)]</span></span>  
  
 <span data-ttu-id="fbd94-161">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] non è necessario usare `join` così spesso come in SQL poiché le chiavi esterne in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sono rappresentate nel modello a oggetti come proprietà che contengono una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="fbd94-161">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] you do not have to use `join` as often as you do in SQL because foreign keys in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] are represented in the object model as properties that hold a collection of items.</span></span> <span data-ttu-id="fbd94-162">Ad esempio, un oggetto `Customer` contiene una raccolta di oggetti `Order`.</span><span class="sxs-lookup"><span data-stu-id="fbd94-162">For example, a `Customer` object contains a collection of `Order` objects.</span></span> <span data-ttu-id="fbd94-163">Anziché eseguire un join, si accede agli ordini usando la notazione "Dot":</span><span class="sxs-lookup"><span data-stu-id="fbd94-163">Rather than performing a join, you access the orders by using dot notation:</span></span>  
  
```  
from order in Customer.Orders...  
```  
  
 <span data-ttu-id="fbd94-164">Per altre informazioni, vedere [Clausola join](../../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-164">For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="selecting-projections"></a><span data-ttu-id="fbd94-165">Selezione (proiezioni)</span><span class="sxs-lookup"><span data-stu-id="fbd94-165">Selecting (Projections)</span></span>  
 <span data-ttu-id="fbd94-166">La clausola `select` produce i risultati della query e specifica la "forma" o un tipo di ogni elemento restituito.</span><span class="sxs-lookup"><span data-stu-id="fbd94-166">The `select` clause produces the results of the query and specifies the "shape" or type of each returned element.</span></span> <span data-ttu-id="fbd94-167">Ad esempio, è possibile specificare se i risultati saranno costituiti di oggetti `Customer` completi, di un solo membro, di un subset di membri, oppure un tipo di risultato completamente diverso basato su un calcolo o su una creazione nuova di oggetti.</span><span class="sxs-lookup"><span data-stu-id="fbd94-167">For example, you can specify whether your results will consist of complete `Customer` objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation.</span></span> <span data-ttu-id="fbd94-168">Quando la clausola `select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.</span><span class="sxs-lookup"><span data-stu-id="fbd94-168">When the `select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span> <span data-ttu-id="fbd94-169">L'uso di proiezioni per trasformare i dati è una funzionalità efficace delle espressioni delle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbd94-169">The use of projections to transform data is a powerful capability of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="fbd94-170">Per altre informazioni, vedere [Trasformazioni dati con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) e [Clausola select](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbd94-170">For more information, see [Data Transformations with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) and [select clause](../../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd94-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd94-171">See Also</span></span>  
 <span data-ttu-id="fbd94-172">[Introduzione all'uso di LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="fbd94-172">[Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 <span data-ttu-id="fbd94-173">[Espressioni di query LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="fbd94-173">[LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="fbd94-174">[Procedura dettagliata: scrittura di query in C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="fbd94-174">[Walkthrough: Writing Queries in C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 <span data-ttu-id="fbd94-175">[Parole chiave di query (LINQ)](../../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="fbd94-175">[Query Keywords (LINQ)](../../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 [<span data-ttu-id="fbd94-176">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="fbd94-176">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

