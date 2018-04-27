---
title: Relazioni tra i tipi nelle operazioni di query (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e38f51d77869dcca8a81fdcbc70aed32c4146935
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="12387-102">Relazioni tra i tipi nelle operazioni di query (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12387-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="12387-103">Le variabili utilizzate [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operazioni sono fortemente tipizzate e devono essere compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="12387-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="12387-104">Tipizzazione forte viene utilizzata nell'origine dati, nella query stessa e nell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="12387-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="12387-105">Nella figura seguente identifica i termini utilizzati per descrivere un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span><span class="sxs-lookup"><span data-stu-id="12387-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="12387-106">Per ulteriori informazioni sulle parti di una query, vedere [operazioni di Query di base (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="12387-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 <span data-ttu-id="12387-107">![Query pseudocodice con elementi evidenziati. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span><span class="sxs-lookup"><span data-stu-id="12387-107">![Pseudocode query with elements highlighted.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span></span>  
<span data-ttu-id="12387-108">Parti di una query LINQ</span><span class="sxs-lookup"><span data-stu-id="12387-108">Parts of a LINQ query</span></span>  
  
 <span data-ttu-id="12387-109">Il tipo della variabile di intervallo nella query deve essere compatibile con il tipo degli elementi nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="12387-109">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="12387-110">Il tipo della variabile di query deve essere compatibile con l'elemento della sequenza definito nel `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="12387-110">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="12387-111">Infine, il tipo degli elementi sequenza anche deve essere compatibile con il tipo della variabile di controllo del ciclo che viene utilizzata la `For Each` istruzione che esegue la query.</span><span class="sxs-lookup"><span data-stu-id="12387-111">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="12387-112">La tipizzazione forte semplifica l'identificazione degli errori di tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="12387-112">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 <span data-ttu-id="12387-113">Visual Basic consente la tipizzazione forte facilmente implementando l'inferenza del tipo locale, noto anche come *tipizzazione implicita*.</span><span class="sxs-lookup"><span data-stu-id="12387-113">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="12387-114">Che funzionalità viene utilizzata nell'esempio precedente, per visualizzare tutti i [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esempi e documentazione.</span><span class="sxs-lookup"><span data-stu-id="12387-114">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="12387-115">In Visual Basic, l'inferenza del tipo locale viene eseguita tramite un `Dim` istruzione senza un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="12387-115">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="12387-116">Nell'esempio seguente, `city` è fortemente tipizzata come una stringa.</span><span class="sxs-lookup"><span data-stu-id="12387-116">In the following example, `city` is strongly typed as a string.</span></span>  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="12387-117">L'inferenza del tipo locale funziona solo quando `Option Infer` è impostato su `On`.</span><span class="sxs-lookup"><span data-stu-id="12387-117">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="12387-118">Per ulteriori informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="12387-118">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="12387-119">Tuttavia, anche se si utilizza l'inferenza del tipo locale in una query, le stesse relazioni di tipo presenti tra le variabili nell'origine dati, la variabile di query e il ciclo di esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="12387-119">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="12387-120">È utile avere una conoscenza di base di queste relazioni di tipo durante la scrittura di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query o lavoro con gli esempi e gli esempi di codice nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="12387-120">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="12387-121">Si potrebbe essere necessario specificare un tipo esplicito per una variabile di intervallo che corrisponde al tipo restituito dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="12387-121">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="12387-122">È possibile specificare il tipo della variabile di intervallo mediante un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="12387-122">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="12387-123">Tuttavia, il risultato un errore se la conversione è un [conversione di restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e `Option Strict` è impostato su `On`.</span><span class="sxs-lookup"><span data-stu-id="12387-123">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="12387-124">È pertanto consigliabile eseguire la conversione i valori recuperati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="12387-124">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="12387-125">È possibile convertire i valori dall'origine dati per il tipo di variabile di intervallo esplicito utilizzando il <xref:System.Linq.Enumerable.Cast%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="12387-125">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="12387-126">È anche possibile eseguire il cast dei valori selezionati nel `Select` clausola per un tipo esplicito è diverso dal tipo della variabile di intervallo.</span><span class="sxs-lookup"><span data-stu-id="12387-126">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="12387-127">Questi punti vengono illustrati nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="12387-127">These points are illustrated in the following code.</span></span>  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="12387-128">Query che restituiscono gli elementi completi dei dati di origine</span><span class="sxs-lookup"><span data-stu-id="12387-128">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="12387-129">Nell'esempio seguente un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operazione che restituisce una sequenza di elementi selezionati dall'origine dei dati di query.</span><span class="sxs-lookup"><span data-stu-id="12387-129">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="12387-130">L'origine, `names`, contiene una matrice di stringhe, e l'output di query è una sequenza contenente stringhe che iniziano con la lettera M.</span><span class="sxs-lookup"><span data-stu-id="12387-130">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 <span data-ttu-id="12387-131">Equivale al codice seguente, ma è molto più brevi e facili da scrivere.</span><span class="sxs-lookup"><span data-stu-id="12387-131">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="12387-132">Inferenza dei tipi locali nelle query l'affidabilità è lo stile preferito in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12387-132">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 <span data-ttu-id="12387-133">Le relazioni seguenti disponibili in entrambi gli esempi di codice precedenti, se i tipi sono determinati in modo implicito o esplicito.</span><span class="sxs-lookup"><span data-stu-id="12387-133">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="12387-134">Il tipo degli elementi nell'origine dati, `names`, è il tipo della variabile di intervallo, `name`, nella query.</span><span class="sxs-lookup"><span data-stu-id="12387-134">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="12387-135">Il tipo di oggetto selezionato, `name`, determina il tipo di variabile di query `mNames`.</span><span class="sxs-lookup"><span data-stu-id="12387-135">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="12387-136">Qui `name` è una stringa, pertanto la variabile di query è IEnumerable (Of String) in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12387-136">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="12387-137">La query definita in `mNames` viene eseguita nel `For Each` ciclo.</span><span class="sxs-lookup"><span data-stu-id="12387-137">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="12387-138">Il ciclo si scorre il risultato dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="12387-138">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="12387-139">Poiché `mNames`, quando eseguita, restituisce una sequenza di stringhe, la variabile di iterazione del ciclo, `nm`, è anche una stringa.</span><span class="sxs-lookup"><span data-stu-id="12387-139">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="12387-140">Query che restituiscono un campo da elementi selezionati</span><span class="sxs-lookup"><span data-stu-id="12387-140">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="12387-141">Nell'esempio seguente un [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operazione che restituisce una sequenza che contiene solo una parte di ogni elemento selezionato dall'origine dati di query.</span><span class="sxs-lookup"><span data-stu-id="12387-141">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="12387-142">La query accetta una raccolta di `Customer` oggetti come origine dati e proietta solo la `Name` proprietà nel risultato.</span><span class="sxs-lookup"><span data-stu-id="12387-142">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="12387-143">Poiché il nome del cliente è una stringa, la query produce una sequenza di stringhe come output.</span><span class="sxs-lookup"><span data-stu-id="12387-143">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 <span data-ttu-id="12387-144">Le relazioni tra le variabili sono analoghe a quelle di esempio più semplice.</span><span class="sxs-lookup"><span data-stu-id="12387-144">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="12387-145">Il tipo degli elementi nell'origine dati, `customers`, è il tipo della variabile di intervallo, `cust`, nella query.</span><span class="sxs-lookup"><span data-stu-id="12387-145">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="12387-146">In questo esempio, il tipo è `Customer`.</span><span class="sxs-lookup"><span data-stu-id="12387-146">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="12387-147">Il `Select` istruzione restituisce il `Name` proprietà di ogni `Customer` oggetto anziché l'intero oggetto.</span><span class="sxs-lookup"><span data-stu-id="12387-147">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="12387-148">Poiché `Name` è una stringa, la variabile di query, `custNames`, verrà nuovamente essere IEnumerable (Of String), non di `Customer`.</span><span class="sxs-lookup"><span data-stu-id="12387-148">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="12387-149">Poiché `custNames` rappresenta una sequenza di stringhe, il `For Each` variabile di iterazione del ciclo, `custName`, deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="12387-149">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="12387-150">Senza l'inferenza del tipo locale, l'esempio precedente sarebbe più complesso per scrivere e per comprendere, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="12387-150">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="12387-151">Query che richiedono tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="12387-151">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="12387-152">Nell'esempio seguente viene illustrata una situazione più complessa.</span><span class="sxs-lookup"><span data-stu-id="12387-152">The following example shows a more complex situation.</span></span> <span data-ttu-id="12387-153">Nell'esempio precedente, non era utile specificare tipi per tutte le variabili in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12387-153">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="12387-154">In questo esempio, non è possibile.</span><span class="sxs-lookup"><span data-stu-id="12387-154">In this example, it is impossible.</span></span> <span data-ttu-id="12387-155">Anziché selezionare l'intera `Customer` elementi dall'origine dei dati, o un singolo campo di ogni elemento, il `Select` clausola in questa query restituisce due proprietà dell'originale `Customer` oggetto: `Name` e `City`.</span><span class="sxs-lookup"><span data-stu-id="12387-155">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="12387-156">In risposta al `Select` clausola, il compilatore definisce un tipo anonimo che contiene queste due proprietà.</span><span class="sxs-lookup"><span data-stu-id="12387-156">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="12387-157">Il risultato dell'esecuzione `nameCityQuery` nel `For Each` ciclo è una raccolta di istanze del nuovo tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="12387-157">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="12387-158">Poiché il tipo anonimo ha un nome utilizzabile, è possibile specificare il tipo di `nameCityQuery` o `custInfo` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12387-158">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="12387-159">Ovvero, con un tipo anonimo, è non avere alcun nome di tipo da utilizzare al posto di `String` in `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="12387-159">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="12387-160">Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="12387-160">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 <span data-ttu-id="12387-161">Anche se non è possibile specificare tipi per tutte le variabili nell'esempio precedente, le relazioni rimangono invariati.</span><span class="sxs-lookup"><span data-stu-id="12387-161">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="12387-162">Il tipo degli elementi nell'origine dati è nuovamente il tipo della variabile di intervallo nella query.</span><span class="sxs-lookup"><span data-stu-id="12387-162">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="12387-163">In questo esempio, `cust` è un'istanza di `Customer`.</span><span class="sxs-lookup"><span data-stu-id="12387-163">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="12387-164">Poiché il `Select` istruzione produce un tipo anonimo, la variabile di query, `nameCityQuery`, deve essere tipizzata in modo implicito come un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="12387-164">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="12387-165">Un tipo anonimo ha un nome utilizzabile e pertanto non può essere specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12387-165">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="12387-166">Il tipo della variabile di iterazione nel `For Each` ciclo è il tipo anonimo creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="12387-166">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="12387-167">Poiché il tipo ha un nome utilizzabile, il tipo della variabile di iterazione del ciclo deve essere determinato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="12387-167">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12387-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12387-168">See Also</span></span>  
 [<span data-ttu-id="12387-169">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12387-169">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="12387-170">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="12387-170">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="12387-171">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="12387-171">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="12387-172">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12387-172">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="12387-173">LINQ</span><span class="sxs-lookup"><span data-stu-id="12387-173">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="12387-174">Query</span><span class="sxs-lookup"><span data-stu-id="12387-174">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)
