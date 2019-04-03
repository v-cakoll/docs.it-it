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
ms.openlocfilehash: ed5ed56366911c3676c4413711207ac0a8f85765
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826197"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="53438-102">Operazioni di query di base (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53438-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="53438-103">In questo argomento fornisce una breve introduzione alla [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] espressioni in Visual Basic e ad alcuni dei tipi di operazioni eseguite in una query tipici.</span><span class="sxs-lookup"><span data-stu-id="53438-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="53438-104">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="53438-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="53438-105">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53438-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="53438-106">Query</span><span class="sxs-lookup"><span data-stu-id="53438-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="53438-107">Procedura dettagliata: Scrittura di query in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53438-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="53438-108">Specifica l'origine dati (da)</span><span class="sxs-lookup"><span data-stu-id="53438-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="53438-109">In un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, il primo passaggio consiste nello specificare l'origine dati che si desidera eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="53438-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="53438-110">Pertanto, il `From` clausola in una query di verifica sempre per prima.</span><span class="sxs-lookup"><span data-stu-id="53438-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="53438-111">Gli operatori di query selezionano e organizzare i risultati in base al tipo dell'origine.</span><span class="sxs-lookup"><span data-stu-id="53438-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="53438-112">Il `From` clausola specifica l'origine dati `customers`e una *variabile di intervallo*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="53438-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="53438-113">La variabile di intervallo è simile a una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query, si verifica alcuna iterazione effettivo.</span><span class="sxs-lookup"><span data-stu-id="53438-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="53438-114">Quando viene eseguita la query, spesso usando un `For Each` ciclo, la variabile di intervallo viene usato come un riferimento a ogni elemento successivo in `customers`.</span><span class="sxs-lookup"><span data-stu-id="53438-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="53438-115">Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="53438-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="53438-116">Per esempi di query scritte con e senza tipizzazione esplicita, vedere [relazioni tra i tipi nelle operazioni di Query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="53438-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="53438-117">Per altre informazioni su come usare il `From` clausola in Visual Basic, vedere [clausola From](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="53438-118">Filtro dei dati (in)</span><span class="sxs-lookup"><span data-stu-id="53438-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="53438-119">L'operazione di query più comune è probabilmente applicando un filtro sotto forma di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="53438-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="53438-120">Quindi, la query restituisce solo gli elementi per cui l'espressione è true.</span><span class="sxs-lookup"><span data-stu-id="53438-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="53438-121">Oggetto `Where` clausola viene utilizzata per eseguire le operazioni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="53438-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="53438-122">Il filtro consente di specificare quali elementi nell'origine dati da includere nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="53438-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="53438-123">Nell'esempio seguente, sono inclusi solo i clienti che hanno un indirizzo in Londra.</span><span class="sxs-lookup"><span data-stu-id="53438-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="53438-124">È possibile usare gli operatori logici, ad esempio `And` e `Or` combinare le espressioni di filtro in un `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="53438-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="53438-125">Ad esempio, per restituire solo i clienti di Londra e il cui nome è Devon, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="53438-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="53438-126">Per restituire i clienti di Londra o Parigi, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="53438-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="53438-127">Per altre informazioni su come usare il `Where` clausola in Visual Basic, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="53438-128">Ordinamento dei dati (Order By)</span><span class="sxs-lookup"><span data-stu-id="53438-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="53438-129">Spesso è utile organizzare i dati restituiti in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="53438-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="53438-130">Il `Order By` clausola consente di ordinare gli elementi nella sequenza restituita di ordinamento una o più campi specificati.</span><span class="sxs-lookup"><span data-stu-id="53438-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="53438-131">Ad esempio, la query seguente consente di ordinare i risultati in base il `Name` proprietà.</span><span class="sxs-lookup"><span data-stu-id="53438-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="53438-132">Poiché `Name` è una stringa, i dati restituiti verranno ordinati in ordine alfabetico, da A Z.</span><span class="sxs-lookup"><span data-stu-id="53438-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="53438-133">Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="53438-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="53438-134">Il valore predefinito è `Ascending` quando non si `Ascending` né `Descending` è specificato.</span><span class="sxs-lookup"><span data-stu-id="53438-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="53438-135">Per altre informazioni su come usare il `Order By` clausola in Visual Basic, vedere [clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="53438-136">Selezione dei dati (Select)</span><span class="sxs-lookup"><span data-stu-id="53438-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="53438-137">Il `Select` clausola che specifica il formato e il contenuto di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="53438-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="53438-138">Ad esempio, è possibile specificare se i risultati saranno costituiti completa `Customer` oggetti, solo uno `Customer` proprietà, un subset delle proprietà, una combinazione delle proprietà da varie origini dati o un nuovo tipo di risultati basato su un calcolo.</span><span class="sxs-lookup"><span data-stu-id="53438-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="53438-139">Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.</span><span class="sxs-lookup"><span data-stu-id="53438-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="53438-140">Per recuperare un insieme costituito da completa `Customer` oggetti, selezionare la variabile di intervallo se stessa:</span><span class="sxs-lookup"><span data-stu-id="53438-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="53438-141">Se un `Customer` istanza è un oggetto di grandi dimensioni contenente molti campi, e tutto ciò che si desidera recuperare è il nome, è possibile selezionare `cust.Name`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="53438-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="53438-142">L'inferenza del tipo locale riconosce che questa operazione modificherà il tipo di risultato da una raccolta di `Customer` oggetti da una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="53438-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="53438-143">Per selezionare più campi dall'origine dati, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="53438-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="53438-144">Nel `Select` clausola, specificare i campi da includere nel risultato.</span><span class="sxs-lookup"><span data-stu-id="53438-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="53438-145">Il compilatore verrà definiti un tipo anonimo che include i campi come le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="53438-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="53438-146">Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="53438-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="53438-147">Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, è possibile fare riferimento al tipo di base al nome in un' posizione nel codice.</span><span class="sxs-lookup"><span data-stu-id="53438-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="53438-148">Il nome definito dal compilatore per il tipo contiene caratteri non validi in normale codice di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="53438-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="53438-149">Nell'esempio seguente, gli elementi nella raccolta restituita dalla query in `londonCusts4` sono istanze di un tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="53438-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="53438-150">-oppure-</span><span class="sxs-lookup"><span data-stu-id="53438-150">-or-</span></span>  
  
-   <span data-ttu-id="53438-151">Definire un tipo denominato che contiene i campi specifici che si desidera includere nel risultato e creare e inizializzare istanze del tipo nel `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="53438-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="53438-152">Usare questa opzione solo se è necessario utilizzare esterne alla raccolta in cui vengono restituiti i singoli risultati o se è necessario passarli come parametri nelle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="53438-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="53438-153">Il tipo di `londonCusts5` nell'esempio seguente è IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="53438-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="53438-154">Per altre informazioni su come usare il `Select` clausola in Visual Basic, vedere [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="53438-155">Dati unita tramite join (Join e Join di gruppo)</span><span class="sxs-lookup"><span data-stu-id="53438-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="53438-156">È possibile combinare più di un'origine dati nel `From` clausola in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="53438-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="53438-157">Ad esempio, il codice seguente usa due origini dati e in modo implicito combina le proprietà da entrambi gli elementi nel risultato.</span><span class="sxs-lookup"><span data-stu-id="53438-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="53438-158">La query Seleziona gli studenti il cui cognome iniziano con una vocale.</span><span class="sxs-lookup"><span data-stu-id="53438-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  <span data-ttu-id="53438-159">È possibile eseguire questo codice con l'elenco degli studenti creati in [come: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="53438-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="53438-160">Il `Join` parola chiave è equivalente a un `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="53438-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="53438-161">Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi nelle due raccolte.</span><span class="sxs-lookup"><span data-stu-id="53438-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="53438-162">La query restituisce tutto o parte degli elementi della raccolta che hanno valori della chiave corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="53438-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="53438-163">Ad esempio, il codice seguente consente di duplicare l'azione di join implicite precedente.</span><span class="sxs-lookup"><span data-stu-id="53438-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="53438-164">`Group Join` Combina le raccolte in un'unica raccolta gerarchica, come un `LEFT JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="53438-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="53438-165">Per altre informazioni, vedere [clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="53438-166">Raggruppamento dei dati (Raggruppa per)</span><span class="sxs-lookup"><span data-stu-id="53438-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="53438-167">È possibile aggiungere un `Group By` clausola per raggruppare gli elementi in un risultato della query in base a uno o più campi degli elementi.</span><span class="sxs-lookup"><span data-stu-id="53438-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="53438-168">Ad esempio, il codice seguente Raggruppa gli studenti per anno di classe.</span><span class="sxs-lookup"><span data-stu-id="53438-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="53438-169">Se si esegue questo codice utilizzando l'elenco degli studenti creati in [come: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output di `For Each` istruzione è:</span><span class="sxs-lookup"><span data-stu-id="53438-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="53438-170">Anno: Junior</span><span class="sxs-lookup"><span data-stu-id="53438-170">Year: Junior</span></span>  
  
 <span data-ttu-id="53438-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="53438-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="53438-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="53438-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="53438-173">Garcia, Debra</span><span class="sxs-lookup"><span data-stu-id="53438-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="53438-174">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="53438-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="53438-175">Anno: Senior</span><span class="sxs-lookup"><span data-stu-id="53438-175">Year: Senior</span></span>  
  
 <span data-ttu-id="53438-176">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="53438-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="53438-177">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="53438-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="53438-178">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="53438-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="53438-179">Feng, Hanying</span><span class="sxs-lookup"><span data-stu-id="53438-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="53438-180">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="53438-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="53438-181">Anno: Seconda superiore</span><span class="sxs-lookup"><span data-stu-id="53438-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="53438-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="53438-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="53438-183">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="53438-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="53438-184">La variazione illustrata nel codice seguente Ordina gli anni di classe e quindi ordini gli studenti all'interno di ogni anno in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="53438-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="53438-185">Per altre informazioni sulle `Group By`, vedere [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53438-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53438-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53438-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="53438-187">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53438-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="53438-188">Query</span><span class="sxs-lookup"><span data-stu-id="53438-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="53438-189">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53438-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="53438-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="53438-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
