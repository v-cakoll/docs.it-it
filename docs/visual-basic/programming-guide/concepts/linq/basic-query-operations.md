---
title: Operazioni di Query di base (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1ced446d6646bd26b9169f5894138e12a38efde7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="73924-102">Operazioni di query di base (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73924-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="73924-103">In questo argomento fornisce una breve introduzione a [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] espressioni in Visual Basic e di alcuni tipi di operazioni eseguite in una query tipici.</span><span class="sxs-lookup"><span data-stu-id="73924-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="73924-104">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="73924-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="73924-105">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73924-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="73924-106">Query</span><span class="sxs-lookup"><span data-stu-id="73924-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="73924-107">Procedura dettagliata: Scrittura di query in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73924-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="73924-108">Specificare l'origine dati (da)</span><span class="sxs-lookup"><span data-stu-id="73924-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="73924-109">In un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, il primo passaggio consiste nel specificare l'origine dati che si desidera eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="73924-109">In a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="73924-110">Pertanto, il `From` sempre in una query per primo.</span><span class="sxs-lookup"><span data-stu-id="73924-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="73924-111">Operatori di query selezionano ed elaborano il risultato in base al tipo dell'origine.</span><span class="sxs-lookup"><span data-stu-id="73924-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 <span data-ttu-id="73924-112">[!code-vb[VbLINQBasicOps n.&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-112">[!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="73924-113">Il `From` clausola specifica l'origine dati, `customers`e un *variabile di intervallo*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="73924-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="73924-114">La variabile di intervallo è come una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query, si verifica alcun iterazione effettiva.</span><span class="sxs-lookup"><span data-stu-id="73924-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="73924-115">Quando viene eseguita la query, spesso utilizzando un `For Each` ciclo, la variabile di intervallo funge da riferimento a ogni elemento successivo in `customers`.</span><span class="sxs-lookup"><span data-stu-id="73924-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="73924-116">Poiché il compilatore è in grado di dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="73924-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="73924-117">Per esempi di query scritte con e senza la tipizzazione esplicita, vedere [relazioni tra i tipi nelle operazioni di Query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="73924-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="73924-118">Per ulteriori informazioni sull'utilizzo di `From` clausola in Visual Basic, vedere [dalla clausola](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="73924-119">Filtraggio dei dati (in)</span><span class="sxs-lookup"><span data-stu-id="73924-119">Filtering Data (Where)</span></span>  
 <span data-ttu-id="73924-120">Probabilmente l'operazione di query più comune è un filtro sotto forma di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="73924-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="73924-121">Quindi, la query restituisce solo gli elementi per cui l'espressione è true.</span><span class="sxs-lookup"><span data-stu-id="73924-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="73924-122">Oggetto `Where` clausola viene utilizzata per eseguire l'applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="73924-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="73924-123">Il filtro specifica quali elementi nell'origine dati da includere nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="73924-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="73924-124">Nell'esempio seguente, sono inclusi solo i clienti che dispongono di un indirizzo di Londra.</span><span class="sxs-lookup"><span data-stu-id="73924-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 <span data-ttu-id="73924-125">[!code-vb[VbLINQBasicOps n.&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-125">[!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span></span>  
  
 <span data-ttu-id="73924-126">È possibile utilizzare gli operatori logici, ad esempio `And` e `Or` per combinare le espressioni di filtro in un `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="73924-126">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="73924-127">Ad esempio, per restituire solo i clienti di Londra e il cui nome è Devon, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="73924-127">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="73924-128">Per restituire i clienti di Londra o Parigi, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="73924-128">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="73924-129">Per ulteriori informazioni sull'utilizzo di `Where` clausola in Visual Basic, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-129">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="73924-130">Ordinamento di dati (Order By)</span><span class="sxs-lookup"><span data-stu-id="73924-130">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="73924-131">Spesso è utile ordinare i dati restituiti in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="73924-131">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="73924-132">Il `Order By` clausola consente di ordinare gli elementi della sequenza restituita per ordinare in base a una o più campi specificati.</span><span class="sxs-lookup"><span data-stu-id="73924-132">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="73924-133">Ad esempio, la query seguente consente di ordinare i risultati in base la `Name` proprietà.</span><span class="sxs-lookup"><span data-stu-id="73924-133">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="73924-134">Poiché `Name` è una stringa, i dati restituiti verranno ordinati in ordine alfabetico da a Z.</span><span class="sxs-lookup"><span data-stu-id="73924-134">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 <span data-ttu-id="73924-135">[!code-vb[VbLINQBasicOps n.&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-135">[!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span></span>  
  
 <span data-ttu-id="73924-136">Per ordinare i risultati in ordine inverso, da Z ad A, utilizzare il `Order By...Descending` clausola.</span><span class="sxs-lookup"><span data-stu-id="73924-136">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="73924-137">Il valore predefinito è `Ascending` quando nessuno `Ascending` né `Descending` specificato.</span><span class="sxs-lookup"><span data-stu-id="73924-137">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="73924-138">Per ulteriori informazioni sull'utilizzo di `Order By` clausola in Visual Basic, vedere [clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-138">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="73924-139">La selezione dei dati (Select)</span><span class="sxs-lookup"><span data-stu-id="73924-139">Selecting Data (Select)</span></span>  
 <span data-ttu-id="73924-140">Il `Select` clausola specifica la forma e il contenuto di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="73924-140">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="73924-141">Ad esempio, è possibile specificare se i risultati saranno costituiti completo `Customer` oggetti, uno `Customer` proprietà, un subset di proprietà, una combinazione di proprietà da diverse origini dati o un nuovo tipo di risultati basato su un calcolo.</span><span class="sxs-lookup"><span data-stu-id="73924-141">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="73924-142">Quando il `Select` clausola produce un valore diverso da una copia dell'elemento di origine, l'operazione viene chiamata una *proiezione*.</span><span class="sxs-lookup"><span data-stu-id="73924-142">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="73924-143">Per recuperare un insieme costituito da completo `Customer` oggetti, selezionare la variabile di intervallo stessa:</span><span class="sxs-lookup"><span data-stu-id="73924-143">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 <span data-ttu-id="73924-144">[!code-vb[VbLINQBasicOps n.&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-144">[!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span></span>  
  
 <span data-ttu-id="73924-145">Se un `Customer` istanza è un oggetto di grandi dimensioni con molti campi, e che si desidera recuperare solo il nome, è possibile selezionare `cust.Name`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="73924-145">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="73924-146">Inferenza del tipo locale riconosce che in questo modo il tipo di risultato da una raccolta di `Customer` oggetti da una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="73924-146">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 <span data-ttu-id="73924-147">[!code-vb[VbLINQBasicOps n.&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-147">[!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span></span>  
  
 <span data-ttu-id="73924-148">Per selezionare più campi dall'origine dati, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="73924-148">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="73924-149">Nel `Select` clausola, specificare i campi che si desidera includere nel risultato.</span><span class="sxs-lookup"><span data-stu-id="73924-149">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="73924-150">Il compilatore definirà un tipo anonimo con tali campi come proprietà.</span><span class="sxs-lookup"><span data-stu-id="73924-150">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="73924-151">Per ulteriori informazioni, vedere [tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="73924-151">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="73924-152">Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, è possibile fare riferimento al tipo di base al nome in un' posizione nel codice.</span><span class="sxs-lookup"><span data-stu-id="73924-152">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="73924-153">Il nome definito dal compilatore per il tipo contiene caratteri non validi nel normale codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="73924-153">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="73924-154">Nell'esempio seguente, gli elementi nella raccolta restituita dalla query in `londonCusts4` sono istanze di un tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="73924-154">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     <span data-ttu-id="73924-155">[!code-vb[6 VbLINQBasicOps](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-155">[!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span></span>  
  
     <span data-ttu-id="73924-156">-oppure-</span><span class="sxs-lookup"><span data-stu-id="73924-156">-or-</span></span>  
  
-   <span data-ttu-id="73924-157">Definire un tipo denominato che contiene i campi specifici che si desidera includere nel risultato e creare e inizializzare istanze del tipo nel `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="73924-157">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="73924-158">Utilizzare questa opzione solo se è necessario utilizzare i singoli risultati esterne alla raccolta in cui vengono restituiti o se si dispone di passarle come parametri nelle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="73924-158">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="73924-159">Il tipo di `londonCusts5` nell'esempio seguente è IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="73924-159">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     <span data-ttu-id="73924-160">[!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-160">[!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span></span>  
  
     <span data-ttu-id="73924-161">[!code-vb[VbLINQBasicOps n.&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-161">[!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span></span>  
  
 <span data-ttu-id="73924-162">Per ulteriori informazioni sull'utilizzo di `Select` clausola in Visual Basic, vedere [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-162">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="73924-163">Dati join (Join e Group Join)</span><span class="sxs-lookup"><span data-stu-id="73924-163">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="73924-164">È possibile combinare più origini dati nel `From` clausola in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="73924-164">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="73924-165">Ad esempio, il codice seguente vengono utilizzate due origini dati e in modo implicito combina le proprietà da entrambi gli elementi nel risultato.</span><span class="sxs-lookup"><span data-stu-id="73924-165">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="73924-166">La query Seleziona gli studenti il cui cognome iniziano con una vocale.</span><span class="sxs-lookup"><span data-stu-id="73924-166">The query selects students whose last names start with a vowel.</span></span>  
  
 <span data-ttu-id="73924-167">[!code-vb[9 VbLINQBasicOps](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-167">[!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73924-168">È possibile eseguire questo codice con l'elenco di studenti creato in [procedura: creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="73924-168">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="73924-169">Il `Join` parola chiave è equivalente a un `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="73924-169">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="73924-170">Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi in due raccolte.</span><span class="sxs-lookup"><span data-stu-id="73924-170">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="73924-171">La query restituisce tutto o parte del elementi della raccolta che hanno valori chiave corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="73924-171">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="73924-172">Ad esempio, il codice seguente consente di duplicare l'azione del join implicito precedente.</span><span class="sxs-lookup"><span data-stu-id="73924-172">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 <span data-ttu-id="73924-173">[!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-173">[!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span></span>  
  
 <span data-ttu-id="73924-174">`Group Join`Combina le raccolte in un'unica raccolta gerarchica, come un `LEFT JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="73924-174">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="73924-175">Per ulteriori informazioni, vedere [clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-175">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="73924-176">Raggruppamento di dati (Group By)</span><span class="sxs-lookup"><span data-stu-id="73924-176">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="73924-177">È possibile aggiungere un `Group By` clausola per raggruppare gli elementi nel risultato di una query in base a uno o più campi degli elementi.</span><span class="sxs-lookup"><span data-stu-id="73924-177">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="73924-178">Ad esempio, il codice seguente Raggruppa gli studenti per anno di classe.</span><span class="sxs-lookup"><span data-stu-id="73924-178">For example, the following code groups students by class year.</span></span>  
  
 <span data-ttu-id="73924-179">[!code-vb[VbLINQBasicOps&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-179">[!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span></span>  
  
 <span data-ttu-id="73924-180">Se si esegue questo codice utilizzando l'elenco di studenti creato in [procedura: creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output di `For Each` istruzione:</span><span class="sxs-lookup"><span data-stu-id="73924-180">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="73924-181">Anno: Junior</span><span class="sxs-lookup"><span data-stu-id="73924-181">Year: Junior</span></span>  
  
 <span data-ttu-id="73924-182">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="73924-182">Tucker, Michael</span></span>  
  
 <span data-ttu-id="73924-183">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="73924-183">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="73924-184">Garcia, Eva</span><span class="sxs-lookup"><span data-stu-id="73924-184">Garcia, Debra</span></span>  
  
 <span data-ttu-id="73924-185">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="73924-185">Tucker, Lance</span></span>  
  
 <span data-ttu-id="73924-186">Anno: Senior</span><span class="sxs-lookup"><span data-stu-id="73924-186">Year: Senior</span></span>  
  
 <span data-ttu-id="73924-187">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="73924-187">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="73924-188">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="73924-188">Osada, Michiko</span></span>  
  
 <span data-ttu-id="73924-189">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="73924-189">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="73924-190">Feng, Hanying</span><span class="sxs-lookup"><span data-stu-id="73924-190">Feng, Hanying</span></span>  
  
 <span data-ttu-id="73924-191">Terry Adams</span><span class="sxs-lookup"><span data-stu-id="73924-191">Adams, Terry</span></span>  
  
 <span data-ttu-id="73924-192">Anno: seconda superiore</span><span class="sxs-lookup"><span data-stu-id="73924-192">Year: Freshman</span></span>  
  
 <span data-ttu-id="73924-193">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="73924-193">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="73924-194">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="73924-194">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="73924-195">La variazione illustrata nel codice seguente Ordina gli anni di classe e quindi ordinati gli studenti all'interno di ogni anno in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="73924-195">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 <span data-ttu-id="73924-196">[!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="73924-196">[!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span></span>  
  
 <span data-ttu-id="73924-197">Per ulteriori informazioni su `Group By`, vedere [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73924-197">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73924-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73924-198">See Also</span></span>  
 <span data-ttu-id="73924-199"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="73924-199"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="73924-200"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="73924-200"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="73924-201"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="73924-201"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="73924-202"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="73924-202"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="73924-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="73924-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span></span>
