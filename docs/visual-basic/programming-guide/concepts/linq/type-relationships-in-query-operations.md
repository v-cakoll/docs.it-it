---
title: Relazioni tra i tipi nelle operazioni di query
ms.date: 07/20/2015
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
ms.openlocfilehash: 8c201abef924766d52b1adb084970a24ebea2b50
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350558"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="ffa48-102">Relazioni tra i tipi nelle operazioni di query (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffa48-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="ffa48-103">Le variabili utilizzate in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] operazioni di query sono fortemente tipizzate e devono essere compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="ffa48-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="ffa48-104">La tipizzazione forte viene utilizzata nell'origine dati, nella query stessa e nell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="ffa48-105">Nell'illustrazione seguente vengono identificati i termini utilizzati per descrivere una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffa48-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="ffa48-106">Per ulteriori informazioni sulle parti di una query, vedere [operazioni di query di base (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ffa48-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>

![Screenshot che mostra una query pseudocodice con elementi evidenziati.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="ffa48-108">Il tipo della variabile di intervallo nella query deve essere compatibile con il tipo degli elementi nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ffa48-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="ffa48-109">Il tipo della variabile di query deve essere compatibile con l'elemento Sequence definito nella clausola `Select`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="ffa48-110">Infine, anche il tipo degli elementi di sequenza deve essere compatibile con il tipo della variabile di controllo del ciclo utilizzata nell'istruzione `For Each` che esegue la query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="ffa48-111">Questa tipizzazione forte facilita l'identificazione degli errori di tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ffa48-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="ffa48-112">Visual Basic rende comoda la tipizzazione forte implementando l'inferenza del tipo locale, nota anche come *tipizzazione implicita*.</span><span class="sxs-lookup"><span data-stu-id="ffa48-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="ffa48-113">Questa funzionalità viene usata nell'esempio precedente e verrà usata in tutti i [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esempi e la documentazione.</span><span class="sxs-lookup"><span data-stu-id="ffa48-113">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="ffa48-114">In Visual Basic, l'inferenza del tipo locale viene eseguita semplicemente utilizzando un'istruzione `Dim` senza una clausola `As`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="ffa48-115">Nell'esempio seguente `city` è fortemente tipizzato come stringa.</span><span class="sxs-lookup"><span data-stu-id="ffa48-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="ffa48-116">L'inferenza del tipo locale funziona solo quando `Option Infer` è impostato su `On`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="ffa48-117">Per altre informazioni, vedere [istruzione Option dedurre](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ffa48-117">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="ffa48-118">Tuttavia, anche se si usa l'inferenza del tipo locale in una query, le stesse relazioni di tipo sono presenti tra le variabili nell'origine dati, la variabile di query e il ciclo di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="ffa48-119">È utile avere una conoscenza di base di queste relazioni tra i tipi durante la scrittura di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query o l'utilizzo degli esempi e degli esempi di codice nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="ffa48-119">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="ffa48-120">Potrebbe essere necessario specificare un tipo esplicito per una variabile di intervallo che non corrisponde al tipo restituito dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ffa48-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="ffa48-121">È possibile specificare il tipo della variabile di intervallo utilizzando una clausola `As`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="ffa48-122">Tuttavia, si verifica un errore se la conversione è una conversione verso un tipo di dati più [piccolo](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e `Option Strict` è impostata su `On`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-122">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="ffa48-123">Pertanto, è consigliabile eseguire la conversione sui valori recuperati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ffa48-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="ffa48-124">È possibile convertire i valori dall'origine dati al tipo di variabile di intervallo esplicito usando il metodo <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffa48-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="ffa48-125">È anche possibile eseguire il cast dei valori selezionati nella clausola `Select` a un tipo esplicito diverso dal tipo della variabile di intervallo.</span><span class="sxs-lookup"><span data-stu-id="ffa48-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="ffa48-126">Questi punti vengono illustrati nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ffa48-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="ffa48-127">Query che restituiscono interi elementi dei dati di origine</span><span class="sxs-lookup"><span data-stu-id="ffa48-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="ffa48-128">Nell'esempio seguente viene illustrata un'operazione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] che restituisce una sequenza di elementi selezionati dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="ffa48-128">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="ffa48-129">Il codice sorgente, `names`, contiene una matrice di stringhe e l'output della query è una sequenza contenente stringhe che iniziano con la lettera M.</span><span class="sxs-lookup"><span data-stu-id="ffa48-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="ffa48-130">Questo è equivalente al codice seguente, ma è molto più breve e più facile da scrivere.</span><span class="sxs-lookup"><span data-stu-id="ffa48-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="ffa48-131">La dipendenza dall'inferenza del tipo locale nelle query è lo stile preferito in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ffa48-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="ffa48-132">Le relazioni seguenti sono presenti in entrambi gli esempi di codice precedenti, indipendentemente dal fatto che i tipi vengano determinati in modo implicito o esplicito.</span><span class="sxs-lookup"><span data-stu-id="ffa48-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="ffa48-133">Il tipo degli elementi nell'origine dati, `names`, è il tipo della variabile di intervallo, `name`, nella query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="ffa48-134">Il tipo dell'oggetto selezionato, `name`, determina il tipo della variabile di query `mNames`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="ffa48-135">Qui `name` è una stringa, quindi la variabile di query è IEnumerable (Of String) nel Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ffa48-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="ffa48-136">La query definita in `mNames` viene eseguita nel ciclo `For Each`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="ffa48-137">Il ciclo scorre il risultato dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="ffa48-138">Poiché `mNames`, quando viene eseguita, restituirà una sequenza di stringhe, anche la variabile di iterazione del ciclo, `nm`, è una stringa.</span><span class="sxs-lookup"><span data-stu-id="ffa48-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="ffa48-139">Query che restituiscono un campo da elementi selezionati</span><span class="sxs-lookup"><span data-stu-id="ffa48-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="ffa48-140">Nell'esempio seguente viene illustrata un'operazione di query [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] che restituisce una sequenza contenente solo una parte di ogni elemento selezionato dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ffa48-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="ffa48-141">La query accetta una raccolta di oggetti `Customer` come origine dati e proietta solo la proprietà `Name` nel risultato.</span><span class="sxs-lookup"><span data-stu-id="ffa48-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="ffa48-142">Poiché il nome del cliente è una stringa, la query genera una sequenza di stringhe come output.</span><span class="sxs-lookup"><span data-stu-id="ffa48-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

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

<span data-ttu-id="ffa48-143">Le relazioni tra le variabili sono simili a quelle nell'esempio più semplice.</span><span class="sxs-lookup"><span data-stu-id="ffa48-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="ffa48-144">Il tipo degli elementi nell'origine dati, `customers`, è il tipo della variabile di intervallo, `cust`, nella query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="ffa48-145">In questo esempio, il tipo è `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="ffa48-146">L'istruzione `Select` restituisce la proprietà `Name` di ogni oggetto `Customer` anziché l'intero oggetto.</span><span class="sxs-lookup"><span data-stu-id="ffa48-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="ffa48-147">Poiché `Name` è una stringa, la variabile di query, `custNames`, sarà di nuovo IEnumerable (Of String), non di `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="ffa48-148">Poiché `custNames` rappresenta una sequenza di stringhe, la variabile di iterazione del ciclo `For Each`, `custName`, deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="ffa48-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="ffa48-149">Senza inferenza del tipo locale, l'esempio precedente sarebbe più complesso da scrivere e comprendere, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ffa48-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

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

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="ffa48-150">Query che richiedono tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="ffa48-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="ffa48-151">Nell'esempio seguente viene illustrata una situazione più complessa.</span><span class="sxs-lookup"><span data-stu-id="ffa48-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="ffa48-152">Nell'esempio precedente, non era pratico specificare i tipi per tutte le variabili in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ffa48-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="ffa48-153">In questo esempio, non è possibile.</span><span class="sxs-lookup"><span data-stu-id="ffa48-153">In this example, it is impossible.</span></span> <span data-ttu-id="ffa48-154">Anziché selezionare interi elementi `Customer` dall'origine dati o un singolo campo da ogni elemento, la clausola `Select` in questa query restituisce due proprietà dell'oggetto `Customer` originale: `Name` e `City`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="ffa48-155">In risposta alla clausola `Select`, il compilatore definisce un tipo anonimo che contiene queste due proprietà.</span><span class="sxs-lookup"><span data-stu-id="ffa48-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="ffa48-156">Il risultato dell'esecuzione di `nameCityQuery` nel ciclo `For Each` è costituito da una raccolta di istanze del nuovo tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="ffa48-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="ffa48-157">Poiché il tipo anonimo non ha un nome utilizzabile, non è possibile specificare il tipo di `nameCityQuery` o `custInfo` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ffa48-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="ffa48-158">Ovvero, con un tipo anonimo, non è disponibile alcun nome di tipo da usare al posto di `String` in `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="ffa48-159">Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ffa48-159">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

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

<span data-ttu-id="ffa48-160">Sebbene non sia possibile specificare i tipi per tutte le variabili nell'esempio precedente, le relazioni rimangono invariate.</span><span class="sxs-lookup"><span data-stu-id="ffa48-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="ffa48-161">Il tipo degli elementi nell'origine dati è di nuovo il tipo della variabile di intervallo nella query.</span><span class="sxs-lookup"><span data-stu-id="ffa48-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="ffa48-162">In questo esempio `cust` è un'istanza di `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ffa48-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="ffa48-163">Poiché l'istruzione `Select` produce un tipo anonimo, la variabile di query, `nameCityQuery`, deve essere tipizzata in modo implicito come tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="ffa48-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="ffa48-164">Un tipo anonimo non ha un nome utilizzabile e pertanto non può essere specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ffa48-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="ffa48-165">Il tipo della variabile di iterazione nel ciclo `For Each` è il tipo anonimo creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ffa48-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="ffa48-166">Poiché il tipo non ha un nome utilizzabile, il tipo della variabile di iterazione del ciclo deve essere determinato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ffa48-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffa48-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffa48-167">See also</span></span>

- [<span data-ttu-id="ffa48-168">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffa48-168">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="ffa48-169">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="ffa48-169">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="ffa48-170">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="ffa48-170">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="ffa48-171">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffa48-171">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ffa48-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="ffa48-172">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="ffa48-173">Query</span><span class="sxs-lookup"><span data-stu-id="ffa48-173">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
