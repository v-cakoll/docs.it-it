---
title: Operazioni di proiezione
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: 4795bdaba53949b34fe380ea9c51025ce43c40db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396337"
---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="72ba1-102">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72ba1-102">Projection Operations (Visual Basic)</span></span>

<span data-ttu-id="72ba1-103">La proiezione si riferisce all'operazione di trasformazione di un oggetto in un nuovo form costituito spesso solo dalle proprietà che verranno usate successivamente.</span><span class="sxs-lookup"><span data-stu-id="72ba1-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="72ba1-104">Utilizzando la proiezione, è possibile costruire un nuovo tipo compilato in base a ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="72ba1-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="72ba1-105">È possibile proiettare una proprietà ed eseguirvi una funzione matematica.</span><span class="sxs-lookup"><span data-stu-id="72ba1-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="72ba1-106">È anche possibile proiettare l'oggetto originale senza modificarlo.</span><span class="sxs-lookup"><span data-stu-id="72ba1-106">You can also project the original object without changing it.</span></span>

<span data-ttu-id="72ba1-107">Nella sezione seguente sono elencati i metodi dell'operatore query standard che eseguono la proiezione.</span><span class="sxs-lookup"><span data-stu-id="72ba1-107">The standard query operator methods that perform projection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="72ba1-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="72ba1-108">Methods</span></span>

|<span data-ttu-id="72ba1-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="72ba1-109">Method Name</span></span>|<span data-ttu-id="72ba1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72ba1-110">Description</span></span>|<span data-ttu-id="72ba1-111">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="72ba1-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="72ba1-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="72ba1-112">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="72ba1-113">Select</span><span class="sxs-lookup"><span data-stu-id="72ba1-113">Select</span></span>|<span data-ttu-id="72ba1-114">Proietta i valori che si basano su una funzione di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="72ba1-114">Projects values that are based on a transform function.</span></span>|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|<span data-ttu-id="72ba1-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="72ba1-115">SelectMany</span></span>|<span data-ttu-id="72ba1-116">Proietta le sequenze di valori che si basano su una funzione di trasformazione semplificandoli in un'unica sequenza.</span><span class="sxs-lookup"><span data-stu-id="72ba1-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="72ba1-117">Usare più clausole `From`</span><span class="sxs-lookup"><span data-stu-id="72ba1-117">Use multiple `From` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="72ba1-118">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="72ba1-118">Query Expression Syntax Examples</span></span>

### <a name="select"></a><span data-ttu-id="72ba1-119">Select</span><span class="sxs-lookup"><span data-stu-id="72ba1-119">Select</span></span>

<span data-ttu-id="72ba1-120">L'esempio seguente usa la clausola `Select` per proiettare la prima lettera di ogni stringa di un elenco di stringhe.</span><span class="sxs-lookup"><span data-stu-id="72ba1-120">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a><span data-ttu-id="72ba1-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="72ba1-121">SelectMany</span></span>

<span data-ttu-id="72ba1-122">Nell'esempio seguente vengono utilizzate più `From` clausole per proiettare ogni parola da ogni stringa in un elenco di stringhe.</span><span class="sxs-lookup"><span data-stu-id="72ba1-122">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a><span data-ttu-id="72ba1-123">Confronto tra Select e SelectMany</span><span class="sxs-lookup"><span data-stu-id="72ba1-123">Select versus SelectMany</span></span>

<span data-ttu-id="72ba1-124">La funzione di `Select()` e `SelectMany()` è produrre uno o più valori risultato dai valori di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="72ba1-125">`Select()` produce un valore risultato per ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="72ba1-126">Il risultato complessivo è pertanto una raccolta contenente lo stesso numero di elementi della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="72ba1-127">Al contrario, `SelectMany()` produce un singolo risultato complessivo che contiene sottoraccolte concatenate di ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="72ba1-128">La funzione di trasformazione passata come argomento a `SelectMany()` deve restituire una sequenza enumerabile di valori per ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="72ba1-129">Queste sequenze enumerabili vengono quindi concatenate da `SelectMany()` per creare un'unica grande sequenza.</span><span class="sxs-lookup"><span data-stu-id="72ba1-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>

<span data-ttu-id="72ba1-130">Le due figure seguenti illustrano la differenza concettuale tra le azioni di questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="72ba1-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="72ba1-131">In ogni caso, si supponga che la funzione del selettore (trasformazione) selezioni la matrice di fiori di ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>

<span data-ttu-id="72ba1-132">La figura mostra che `Select()` restituisce una raccolta contenente lo stesso numero di elementi della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>

![Elemento grafico che illustra l'azione di Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

<span data-ttu-id="72ba1-134">La figura mostra che `SelectMany()` concatena la sequenza intermedia di matrici in un unico valore risultato finale contenente tutti i valori di ogni matrice intermedia.</span><span class="sxs-lookup"><span data-stu-id="72ba1-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>

![Elemento grafico che illustra l'azione di SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a><span data-ttu-id="72ba1-136">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="72ba1-136">Code Example</span></span>

<span data-ttu-id="72ba1-137">L'esempio seguente confronta il comportamento di `Select()` e `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="72ba1-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="72ba1-138">Il codice crea un "bouquet" di fiori prendendo i primi due elementi di ogni elenco di nomi di fiori nella raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="72ba1-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="72ba1-139">In questo esempio, il "valore singolo" usato dalla funzione di trasformazione <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> è anch'esso una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="72ba1-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="72ba1-140">Questo richiede il ciclo `For Each` aggiuntivo in modo da enumerare tutte le stringhe di ogni sottosequenza.</span><span class="sxs-lookup"><span data-stu-id="72ba1-140">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a><span data-ttu-id="72ba1-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72ba1-141">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="72ba1-142">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72ba1-142">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="72ba1-143">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="72ba1-143">Select Clause</span></span>](../../../language-reference/queries/select-clause.md)
- [<span data-ttu-id="72ba1-144">Procedura: Combinare dati utilizzando join</span><span class="sxs-lookup"><span data-stu-id="72ba1-144">How to: Combine Data with Joins</span></span>](../../language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)
- [<span data-ttu-id="72ba1-145">Procedura: popolare raccolte di oggetti da più origini (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72ba1-145">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="72ba1-146">Procedura: restituire un risultato di query LINQ come tipo specifico</span><span class="sxs-lookup"><span data-stu-id="72ba1-146">How to: Return a LINQ Query Result as a Specific Type</span></span>](../../language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [<span data-ttu-id="72ba1-147">Procedura: suddividere un file in molti file usando i gruppi (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72ba1-147">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
