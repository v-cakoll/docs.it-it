---
title: Operazioni di query di base
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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266378"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="6439a-102">Operazioni di query di base (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6439a-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="6439a-103">In questo argomento viene fornita una breve introduzione alle espressioni LINQ (Language-Integrated Query) in Visual Basic e ad alcuni dei tipi tipici di operazioni eseguite in una query.</span><span class="sxs-lookup"><span data-stu-id="6439a-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="6439a-104">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6439a-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="6439a-105">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6439a-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="6439a-106">Query</span><span class="sxs-lookup"><span data-stu-id="6439a-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="6439a-107">Procedura dettagliata: Scrittura delle query in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6439a-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="6439a-108">Specifica dell'origine dati (Da)</span><span class="sxs-lookup"><span data-stu-id="6439a-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="6439a-109">In una query LINQ, il primo passaggio consiste nello specificare l'origine dati su cui si desidera eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="6439a-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="6439a-110">Pertanto, `From` la clausola in una query viene sempre prima.</span><span class="sxs-lookup"><span data-stu-id="6439a-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="6439a-111">Gli operatori di query selezionano e modellano il risultato in base al tipo di origine.</span><span class="sxs-lookup"><span data-stu-id="6439a-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="6439a-112">La `From` clausola specifica l'origine dati `customers`, `cust`, e una variabile di *intervallo*, .</span><span class="sxs-lookup"><span data-stu-id="6439a-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="6439a-113">La variabile di intervallo è simile a una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query non si verifica alcuna iterazione effettiva.</span><span class="sxs-lookup"><span data-stu-id="6439a-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="6439a-114">Quando la query viene eseguita, `For Each` spesso utilizzando un ciclo, la variabile `customers`di intervallo funge da riferimento per ogni elemento successivo in .</span><span class="sxs-lookup"><span data-stu-id="6439a-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="6439a-115">Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="6439a-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="6439a-116">Per esempi di query scritte con e senza tipi di digitazione esplicita, vedere Relazioni tra tipi nelle operazioni di [query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="6439a-117">Per ulteriori informazioni sull'utilizzo della `From` clausola in Visual Basic, vedere [Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="6439a-118">Filtraggio dei dati (Dove)</span><span class="sxs-lookup"><span data-stu-id="6439a-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="6439a-119">Probabilmente l'operazione di query più comune consiste nell'applicazione di un filtro sotto forma di espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="6439a-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="6439a-120">La query restituisce quindi solo gli elementi per i quali l'espressione è vera.</span><span class="sxs-lookup"><span data-stu-id="6439a-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="6439a-121">Una `Where` clausola viene utilizzata per eseguire il filtro.</span><span class="sxs-lookup"><span data-stu-id="6439a-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="6439a-122">Il filtro specifica quali elementi nell'origine dati includere nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="6439a-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="6439a-123">Nell'esempio seguente vengono inclusi solo i clienti che dispongono di un indirizzo a Londra.</span><span class="sxs-lookup"><span data-stu-id="6439a-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="6439a-124">È possibile utilizzare operatori `And` `Or` logici, ad `Where` esempio e per combinare espressioni di filtro in una clausola.</span><span class="sxs-lookup"><span data-stu-id="6439a-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="6439a-125">Ad esempio, per restituire solo i clienti che provengono da Londra e il cui nome è Devon, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6439a-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="6439a-126">Per restituire clienti da Londra o Parigi, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6439a-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="6439a-127">Per ulteriori informazioni sull'utilizzo della `Where` clausola in Visual Basic, vedere [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="6439a-128">Ordinare i dati (Ordina per)</span><span class="sxs-lookup"><span data-stu-id="6439a-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="6439a-129">Spesso è conveniente ordinare i dati restituiti in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="6439a-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="6439a-130">La `Order By` clausola farà sì che gli elementi nella sequenza restituita vengano ordinati in base a uno o più campi specificati.</span><span class="sxs-lookup"><span data-stu-id="6439a-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="6439a-131">Ad esempio, la query seguente ordina `Name` i risultati in base alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="6439a-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="6439a-132">Poiché `Name` è una stringa, i dati restituiti verranno ordinati alfabeticamente, dalla A alla .</span><span class="sxs-lookup"><span data-stu-id="6439a-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="6439a-133">Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="6439a-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="6439a-134">Il valore `Ascending` predefinito `Ascending` `Descending` è quando non viene specificato né.</span><span class="sxs-lookup"><span data-stu-id="6439a-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="6439a-135">Per ulteriori informazioni sull'utilizzo della `Order By` clausola in Visual Basic, vedere [Clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="6439a-136">Selezione dei dati (seleziona)</span><span class="sxs-lookup"><span data-stu-id="6439a-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="6439a-137">La `Select` clausola specifica il formato e il contenuto degli elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="6439a-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="6439a-138">Ad esempio, è possibile specificare se `Customer` i risultati `Customer` saranno costituiti da oggetti completi, solo una proprietà, un subset di proprietà, una combinazione di proprietà da varie origini dati o un nuovo tipo di risultato basato su un calcolo.</span><span class="sxs-lookup"><span data-stu-id="6439a-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="6439a-139">Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.</span><span class="sxs-lookup"><span data-stu-id="6439a-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="6439a-140">Per recuperare una raccolta `Customer` costituita da oggetti completi, selezionare la variabile di intervallo stessa:To retrieve a collection that consists of complete objects, select the range variable itself:</span><span class="sxs-lookup"><span data-stu-id="6439a-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="6439a-141">Se `Customer` un'istanza è un oggetto di grandi dimensioni con molti campi e `cust.Name`tutto ciò che si desidera recuperare è il nome, è possibile selezionare , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6439a-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="6439a-142">L'inferenza del tipo locale riconosce che in `Customer` questo modo il tipo di risultato viene modificato da una raccolta di oggetti a una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="6439a-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="6439a-143">Per selezionare più campi dall'origine dati, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="6439a-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="6439a-144">Nella `Select` clausola specificare i campi che si desidera includere nel risultato.</span><span class="sxs-lookup"><span data-stu-id="6439a-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="6439a-145">Il compilatore definirà un tipo anonimo con tali campi come proprietà.</span><span class="sxs-lookup"><span data-stu-id="6439a-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="6439a-146">Per ulteriori informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="6439a-147">Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, non è possibile fare riferimento al tipo in base al nome in un altro punto del codice.</span><span class="sxs-lookup"><span data-stu-id="6439a-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="6439a-148">Il nome designato dal compilatore per il tipo contiene caratteri non validi nel normale codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6439a-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="6439a-149">Nell'esempio seguente, gli elementi nella raccolta restituita `londonCusts4` dalla query in sono istanze di un tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="6439a-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="6439a-150">-oppure-</span><span class="sxs-lookup"><span data-stu-id="6439a-150">-or-</span></span>  
  
- <span data-ttu-id="6439a-151">Definire un tipo denominato che contiene i campi specifici che si desidera includere nel `Select` risultato e creare e inizializzare istanze del tipo nella clausola.</span><span class="sxs-lookup"><span data-stu-id="6439a-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="6439a-152">Utilizzare questa opzione solo se è necessario utilizzare singoli risultati all'esterno della raccolta in cui vengono restituiti o se è necessario passarli come parametri nelle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="6439a-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="6439a-153">Il tipo `londonCusts5` di nell'esempio seguente è IEnumerable(Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="6439a-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="6439a-154">Per ulteriori informazioni sull'utilizzo della `Select` clausola in Visual Basic, vedere [Clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="6439a-155">Unione di dati (Join e Group Join)</span><span class="sxs-lookup"><span data-stu-id="6439a-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="6439a-156">È possibile combinare più di `From` un'origine dati nella clausola in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="6439a-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="6439a-157">Ad esempio, il codice seguente usa due origini dati e combina in modo implicito le proprietà di entrambe nel risultato.</span><span class="sxs-lookup"><span data-stu-id="6439a-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="6439a-158">La query seleziona gli studenti il cui cognome inizia con una vocale.</span><span class="sxs-lookup"><span data-stu-id="6439a-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="6439a-159">È possibile eseguire questo codice con l'elenco di studenti creato in [Procedura: creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="6439a-160">La `Join` parola chiave `INNER JOIN` è equivalente a un in SQL.</span><span class="sxs-lookup"><span data-stu-id="6439a-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="6439a-161">Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi nelle due raccolte.</span><span class="sxs-lookup"><span data-stu-id="6439a-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="6439a-162">La query restituisce tutti o parte degli elementi della raccolta con valori di chiave corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6439a-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="6439a-163">Ad esempio, il codice seguente duplica l'azione del join implicito precedente.</span><span class="sxs-lookup"><span data-stu-id="6439a-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="6439a-164">`Group Join`combina le raccolte in un'unica `LEFT JOIN` raccolta gerarchica, proprio come un in SQL.</span><span class="sxs-lookup"><span data-stu-id="6439a-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="6439a-165">Per ulteriori informazioni, vedere [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="6439a-166">Raggruppamento dei dati (Raggruppa per)</span><span class="sxs-lookup"><span data-stu-id="6439a-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="6439a-167">È possibile `Group By` aggiungere una clausola per raggruppare gli elementi in un risultato della query in base a uno o più campi degli elementi.</span><span class="sxs-lookup"><span data-stu-id="6439a-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="6439a-168">Ad esempio, il codice seguente raggruppa gli studenti in base all'anno della classe.</span><span class="sxs-lookup"><span data-stu-id="6439a-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="6439a-169">Se si esegue questo codice utilizzando l'elenco di studenti creato in [Procedura: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output dell'istruzione `For Each` è:</span><span class="sxs-lookup"><span data-stu-id="6439a-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="6439a-170">Anno: Junior</span><span class="sxs-lookup"><span data-stu-id="6439a-170">Year: Junior</span></span>  
  
 <span data-ttu-id="6439a-171">Tucker</span><span class="sxs-lookup"><span data-stu-id="6439a-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="6439a-172">Garcia</span><span class="sxs-lookup"><span data-stu-id="6439a-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="6439a-173">Garcia</span><span class="sxs-lookup"><span data-stu-id="6439a-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="6439a-174">Tucker</span><span class="sxs-lookup"><span data-stu-id="6439a-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="6439a-175">Anno: Senior</span><span class="sxs-lookup"><span data-stu-id="6439a-175">Year: Senior</span></span>  
  
 <span data-ttu-id="6439a-176">Omelchenko</span><span class="sxs-lookup"><span data-stu-id="6439a-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="6439a-177">Osada</span><span class="sxs-lookup"><span data-stu-id="6439a-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="6439a-178">Fakhouri</span><span class="sxs-lookup"><span data-stu-id="6439a-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="6439a-179">Feng</span><span class="sxs-lookup"><span data-stu-id="6439a-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="6439a-180">Adams</span><span class="sxs-lookup"><span data-stu-id="6439a-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="6439a-181">Anno: Matricola</span><span class="sxs-lookup"><span data-stu-id="6439a-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="6439a-182">Mortensen</span><span class="sxs-lookup"><span data-stu-id="6439a-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="6439a-183">Garcia</span><span class="sxs-lookup"><span data-stu-id="6439a-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="6439a-184">La variazione mostrata nel codice seguente ordina gli anni della classe, quindi ordina gli studenti all'interno di ogni anno in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="6439a-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="6439a-185">Per ulteriori `Group By`informazioni sulla [clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6439a-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6439a-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6439a-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="6439a-187">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6439a-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="6439a-188">Query</span><span class="sxs-lookup"><span data-stu-id="6439a-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6439a-189">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6439a-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6439a-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="6439a-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
