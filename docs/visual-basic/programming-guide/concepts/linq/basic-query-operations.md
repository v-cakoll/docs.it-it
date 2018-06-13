---
title: Operazioni di query di base (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644121"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="ceb68-102">Operazioni di query di base (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ceb68-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="ceb68-103">In questo argomento fornisce una breve introduzione a [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] espressioni in Visual Basic e ad alcuni dei tipi di operazioni eseguite in una query tipici.</span><span class="sxs-lookup"><span data-stu-id="ceb68-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="ceb68-104">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ceb68-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="ceb68-105">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ceb68-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="ceb68-106">Query</span><span class="sxs-lookup"><span data-stu-id="ceb68-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="ceb68-107">Procedura dettagliata: Scrittura di query in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ceb68-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="ceb68-108">Specifica l'origine dati (da)</span><span class="sxs-lookup"><span data-stu-id="ceb68-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="ceb68-109">In un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, il primo passaggio consiste nel specificare l'origine dati che si desidera eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="ceb68-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="ceb68-110">Pertanto, il `From` sempre in una query per primo.</span><span class="sxs-lookup"><span data-stu-id="ceb68-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="ceb68-111">Gli operatori di query selezionano ed elaborano il risultato in base al tipo dell'origine.</span><span class="sxs-lookup"><span data-stu-id="ceb68-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 <span data-ttu-id="ceb68-112">Il `From` clausola specifica l'origine dati, `customers`e un *variabile di intervallo*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="ceb68-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="ceb68-113">La variabile di intervallo è simile a una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query, si verifica alcuna iterazione effettiva.</span><span class="sxs-lookup"><span data-stu-id="ceb68-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="ceb68-114">Quando viene eseguita la query, spesso utilizzando un `For Each` ciclo, la variabile di intervallo funge da riferimento a ogni elemento successivo `customers`.</span><span class="sxs-lookup"><span data-stu-id="ceb68-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="ceb68-115">Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ceb68-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="ceb68-116">Per esempi di query scritte con e senza la tipizzazione esplicita, vedere [relazioni tra i tipi nelle operazioni di Query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="ceb68-117">Per ulteriori informazioni sull'utilizzo di `From` clausola in Visual Basic, vedere [dalla clausola](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="ceb68-118">Filtraggio dei dati (in)</span><span class="sxs-lookup"><span data-stu-id="ceb68-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="ceb68-119">Probabilmente l'operazione di query più comune è un filtro sotto forma di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="ceb68-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="ceb68-120">Quindi, la query restituisce solo gli elementi per cui l'espressione è true.</span><span class="sxs-lookup"><span data-stu-id="ceb68-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="ceb68-121">Oggetto `Where` clausola viene utilizzata per eseguire l'applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="ceb68-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="ceb68-122">Il filtro specifica quali elementi nell'origine dati da includere nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="ceb68-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="ceb68-123">Nell'esempio seguente, sono inclusi solo i clienti che hanno un indirizzo di Londra.</span><span class="sxs-lookup"><span data-stu-id="ceb68-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 <span data-ttu-id="ceb68-124">È possibile utilizzare gli operatori logici, ad esempio `And` e `Or` per combinare espressioni di filtro in un `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="ceb68-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="ceb68-125">Ad esempio, per restituire solo i clienti di Londra e il cui nome è Devon, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ceb68-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="ceb68-126">Per restituire i clienti di Londra o Parigi, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ceb68-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="ceb68-127">Per ulteriori informazioni sull'utilizzo di `Where` clausola in Visual Basic, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="ceb68-128">Ordinamento di dati (Order By)</span><span class="sxs-lookup"><span data-stu-id="ceb68-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="ceb68-129">Spesso è utile ordinare i dati restituiti in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="ceb68-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="ceb68-130">Il `Order By` clausola consente di ordinare gli elementi nella sequenza restituita per ordinare in base a una o più campi specificati.</span><span class="sxs-lookup"><span data-stu-id="ceb68-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="ceb68-131">Ad esempio, la query seguente consente di ordinare i risultati in base il `Name` proprietà.</span><span class="sxs-lookup"><span data-stu-id="ceb68-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="ceb68-132">Poiché `Name` è una stringa, verranno ordinati alfabeticamente, i dati restituiti da a Z.</span><span class="sxs-lookup"><span data-stu-id="ceb68-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 <span data-ttu-id="ceb68-133">Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="ceb68-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="ceb68-134">Il valore predefinito è `Ascending` quando nessuno `Ascending` né `Descending` specificato.</span><span class="sxs-lookup"><span data-stu-id="ceb68-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="ceb68-135">Per ulteriori informazioni sull'utilizzo di `Order By` clausola in Visual Basic, vedere [clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="ceb68-136">La selezione dei dati (Select)</span><span class="sxs-lookup"><span data-stu-id="ceb68-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="ceb68-137">Il `Select` clausola specifica il formato e il contenuto degli elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="ceb68-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="ceb68-138">Ad esempio, è possibile specificare se i risultati verranno costituiti completo `Customer` oggetti, solo uno `Customer` proprietà, un subset delle proprietà, una combinazione delle proprietà da diverse origini dati o un nuovo tipo di risultati basato su un calcolo.</span><span class="sxs-lookup"><span data-stu-id="ceb68-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="ceb68-139">Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.</span><span class="sxs-lookup"><span data-stu-id="ceb68-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="ceb68-140">Per recuperare una raccolta che include completo `Customer` oggetti, selezionare la variabile di intervallo:</span><span class="sxs-lookup"><span data-stu-id="ceb68-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 <span data-ttu-id="ceb68-141">Se un `Customer` istanza è un oggetto di grandi dimensioni con molti campi, e che si desidera recuperare solo il nome, è possibile selezionare `cust.Name`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ceb68-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="ceb68-142">L'inferenza del tipo locale riconosce che in questo modo il tipo di risultato da una raccolta di `Customer` oggetti da una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="ceb68-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 <span data-ttu-id="ceb68-143">Per selezionare più campi dall'origine dati, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="ceb68-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="ceb68-144">Nel `Select` clausola, specificare i campi che si desidera includere nel risultato.</span><span class="sxs-lookup"><span data-stu-id="ceb68-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="ceb68-145">Il compilatore verrà definiti un tipo anonimo che contiene i campi come proprietà.</span><span class="sxs-lookup"><span data-stu-id="ceb68-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="ceb68-146">Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="ceb68-147">Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, è possibile fare riferimento al tipo di base al nome in un' posizione nel codice.</span><span class="sxs-lookup"><span data-stu-id="ceb68-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="ceb68-148">Il nome definito dal compilatore per il tipo contiene caratteri non validi nel normale codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ceb68-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="ceb68-149">Nell'esempio seguente, gli elementi nella raccolta restituita dalla query in `londonCusts4` sono istanze di un tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="ceb68-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     <span data-ttu-id="ceb68-150">oppure</span><span class="sxs-lookup"><span data-stu-id="ceb68-150">-or-</span></span>  
  
-   <span data-ttu-id="ceb68-151">Definire un tipo denominato che contiene i campi specifici che si desidera includere nel risultato, creare e inizializzare istanze del tipo nel `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="ceb68-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="ceb68-152">Utilizzare questa opzione solo se è necessario utilizzare esterne alla raccolta in cui vengono restituiti i singoli risultati o se devi passarle come parametri nelle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="ceb68-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="ceb68-153">Il tipo di `londonCusts5` nell'esempio seguente è IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="ceb68-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 <span data-ttu-id="ceb68-154">Per ulteriori informazioni sull'utilizzo di `Select` clausola in Visual Basic, vedere [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="ceb68-155">Unione di dati (Join e gruppo)</span><span class="sxs-lookup"><span data-stu-id="ceb68-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="ceb68-156">È possibile combinare più origini dati nel `From` clausola in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="ceb68-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="ceb68-157">Ad esempio, il codice seguente vengono utilizzate due origini dati e combina in modo implicito le proprietà da entrambi gli elementi nel risultato.</span><span class="sxs-lookup"><span data-stu-id="ceb68-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="ceb68-158">La query Seleziona gli studenti il cui cognome iniziano con una vocale.</span><span class="sxs-lookup"><span data-stu-id="ceb68-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="ceb68-159">È possibile eseguire questo codice con l'elenco di studenti creato in [procedura: creare un elenco di elementi di](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="ceb68-160">Il `Join` la parola chiave è equivalente a un `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="ceb68-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="ceb68-161">Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi in due raccolte.</span><span class="sxs-lookup"><span data-stu-id="ceb68-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="ceb68-162">La query restituisce tutto o parte degli elementi della raccolta che hanno valori chiave corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ceb68-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="ceb68-163">Ad esempio, il codice seguente duplica l'azione del join implicito precedente.</span><span class="sxs-lookup"><span data-stu-id="ceb68-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 <span data-ttu-id="ceb68-164">`Group Join` Combina raccolte in un'unica raccolta gerarchica, esattamente come un `LEFT JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="ceb68-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="ceb68-165">Per ulteriori informazioni, vedere [clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [clausola Join gruppo](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="ceb68-166">Raggruppamento di dati (Group By)</span><span class="sxs-lookup"><span data-stu-id="ceb68-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="ceb68-167">È possibile aggiungere un `Group By` clausola per raggruppare gli elementi nel risultato di una query in base a uno o più campi degli elementi.</span><span class="sxs-lookup"><span data-stu-id="ceb68-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="ceb68-168">Ad esempio, il codice seguente Raggruppa gli studenti per anno di classe.</span><span class="sxs-lookup"><span data-stu-id="ceb68-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 <span data-ttu-id="ceb68-169">Se si esegue questo codice utilizzando l'elenco di studenti creato in [procedura: creare un elenco di elementi di](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output il `For Each` istruzione è:</span><span class="sxs-lookup"><span data-stu-id="ceb68-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="ceb68-170">Anno: Junior</span><span class="sxs-lookup"><span data-stu-id="ceb68-170">Year: Junior</span></span>  
  
 <span data-ttu-id="ceb68-171">Figli, Michael</span><span class="sxs-lookup"><span data-stu-id="ceb68-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="ceb68-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="ceb68-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="ceb68-173">Garcia, Eva</span><span class="sxs-lookup"><span data-stu-id="ceb68-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="ceb68-174">Figli, Lance</span><span class="sxs-lookup"><span data-stu-id="ceb68-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="ceb68-175">Anno: Senior</span><span class="sxs-lookup"><span data-stu-id="ceb68-175">Year: Senior</span></span>  
  
 <span data-ttu-id="ceb68-176">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="ceb68-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="ceb68-177">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="ceb68-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="ceb68-178">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="ceb68-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="ceb68-179">Feng, Hanying</span><span class="sxs-lookup"><span data-stu-id="ceb68-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="ceb68-180">Terry Adams:</span><span class="sxs-lookup"><span data-stu-id="ceb68-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="ceb68-181">Anno: seconda superiore</span><span class="sxs-lookup"><span data-stu-id="ceb68-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="ceb68-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="ceb68-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="ceb68-183">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="ceb68-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="ceb68-184">La variazione illustrata nel codice seguente Ordina gli anni di classe e quindi gli studenti gli ordini all'interno di ogni anno in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="ceb68-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 <span data-ttu-id="ceb68-185">Per ulteriori informazioni su `Group By`, vedere [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ceb68-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb68-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceb68-186">See Also</span></span>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="ceb68-187">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ceb68-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="ceb68-188">Query</span><span class="sxs-lookup"><span data-stu-id="ceb68-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="ceb68-189">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ceb68-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="ceb68-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="ceb68-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
