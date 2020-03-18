---
title: Clausola group (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 75a366ec24e4e48af7e87d3372950aad8d76435b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713464"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="f22fd-102">Clausola group (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="f22fd-102">group clause (C# Reference)</span></span>

<span data-ttu-id="f22fd-103">La clausola `group` restituisce una sequenza di oggetti <xref:System.Linq.IGrouping%602> che contengono zero o più elementi corrispondenti al valore chiave per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="f22fd-104">Ad esempio, è possibile raggruppare una sequenza di stringhe in base alla prima lettera di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="f22fd-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="f22fd-105">In questo caso, la prima lettera è la chiave con tipo [char](../builtin-types/char.md) e viene archiviata nella proprietà `Key` di ogni oggetto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="f22fd-105">In this case, the first letter is the key and has a type [char](../builtin-types/char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="f22fd-106">Il compilatore deduce automaticamente il tipo della chiave.</span><span class="sxs-lookup"><span data-stu-id="f22fd-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="f22fd-107">È possibile terminare un'espressione di query con una clausola `group`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f22fd-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="f22fd-108">Per eseguire operazioni di query aggiuntive per ogni gruppo, è possibile specificare un identificatore temporaneo usando la parola chiave contestuale [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="f22fd-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="f22fd-109">Quando si usa `into`, è necessario continuare a eseguire la query ed eventualmente terminarla con un'istruzione `select` o un'altra clausola `group`, come illustrato nel seguente estratto di codice:</span><span class="sxs-lookup"><span data-stu-id="f22fd-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="f22fd-110">Esempi di utilizzo di più completi di `group` con e senza `into` sono disponibili nella sezione Esempio di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="f22fd-111">Enumerazione dei risultati di una query con raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f22fd-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="f22fd-112">Poiché gli oggetti <xref:System.Linq.IGrouping%602> prodotti da una query `group` sono essenzialmente un elenco di elenchi, è necessario usare un ciclo [foreach](foreach-in.md) nidificato per accedere agli elementi di ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="f22fd-113">Il ciclo esterno esegue l'iterazione delle chiavi del gruppo e il ciclo interno esegue l'iterazione di ogni voce nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="f22fd-114">Un gruppo può avere una chiave ma non elementi.</span><span class="sxs-lookup"><span data-stu-id="f22fd-114">A group may have a key but no elements.</span></span> <span data-ttu-id="f22fd-115">Di seguito è riportato il ciclo `foreach` che esegue la query negli esempi di codice precedenti:</span><span class="sxs-lookup"><span data-stu-id="f22fd-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="f22fd-116">Tipi di chiave</span><span class="sxs-lookup"><span data-stu-id="f22fd-116">Key types</span></span>

<span data-ttu-id="f22fd-117">Le chiavi di raggruppamento possono essere di qualsiasi tipo, ad esempio una stringa, un tipo numerico incorporato, un tipo con nome definito dall'utente o un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="f22fd-118">Raggruppamento per stringa</span><span class="sxs-lookup"><span data-stu-id="f22fd-118">Grouping by string</span></span>

<span data-ttu-id="f22fd-119">Negli esempi di codice precedenti è stato usato un oggetto `char`.</span><span class="sxs-lookup"><span data-stu-id="f22fd-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="f22fd-120">Si potrebbe specificare in alternativa una chiave di stringa, ad esempio il cognome completo:</span><span class="sxs-lookup"><span data-stu-id="f22fd-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="f22fd-121">Raggruppamento per valore booleano</span><span class="sxs-lookup"><span data-stu-id="f22fd-121">Grouping by bool</span></span>

<span data-ttu-id="f22fd-122">L'esempio seguente illustra l'uso di un valore booleano per una chiave in modo da dividere i risultati in due gruppi.</span><span class="sxs-lookup"><span data-stu-id="f22fd-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="f22fd-123">Si noti che il valore è generato da una sottoespressione nella clausola `group`.</span><span class="sxs-lookup"><span data-stu-id="f22fd-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="f22fd-124">Raggruppamento per intervallo numerico</span><span class="sxs-lookup"><span data-stu-id="f22fd-124">Grouping by numeric range</span></span>

<span data-ttu-id="f22fd-125">Nell'esempio seguente viene usata un'espressione per creare le chiavi di raggruppamento numeriche che rappresentano un intervallo percentile.</span><span class="sxs-lookup"><span data-stu-id="f22fd-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="f22fd-126">Si noti l'uso di [let](let-clause.md) come comoda posizione di archiviazione del risultato della chiamata a un metodo, in modo da non dover chiamare il metodo due volte nella clausola `group`.</span><span class="sxs-lookup"><span data-stu-id="f22fd-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="f22fd-127">Per ulteriori informazioni su come utilizzare in modo sicuro i metodi nelle espressioni di query, vedere [Gestire le eccezioni nelle espressioni](../../linq/handle-exceptions-in-query-expressions.md)di query.</span><span class="sxs-lookup"><span data-stu-id="f22fd-127">For more information about how to safely use methods in query expressions, see [Handle exceptions in query expressions](../../linq/handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="f22fd-128">Raggruppamento per chiavi composte</span><span class="sxs-lookup"><span data-stu-id="f22fd-128">Grouping by composite keys</span></span>

<span data-ttu-id="f22fd-129">Usare una chiave composta se si vuole raggruppare gli elementi in base a più di una chiave.</span><span class="sxs-lookup"><span data-stu-id="f22fd-129">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="f22fd-130">Per creare una chiave composta, usare un tipo anonimo o un tipo denominato per contenere l'elemento key.</span><span class="sxs-lookup"><span data-stu-id="f22fd-130">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="f22fd-131">Nell'esempio seguente si suppone che una classe `Person` sia stata dichiarata con i membri denominati `surname` e `city`.</span><span class="sxs-lookup"><span data-stu-id="f22fd-131">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="f22fd-132">La clausola `group` determina la creazione di un gruppo separato per ogni insieme di persone con lo stesso cognome e la stessa città.</span><span class="sxs-lookup"><span data-stu-id="f22fd-132">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="f22fd-133">Usare un tipo denominato se è necessario passare la variabile di query a un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="f22fd-133">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="f22fd-134">Creare una classe speciale usando proprietà implementate automaticamente per le chiavi e quindi eseguire l'override dei metodi <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f22fd-134">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="f22fd-135">È anche possibile usare uno struct e in questo caso non è strettamente necessario eseguire l'override dei metodi.</span><span class="sxs-lookup"><span data-stu-id="f22fd-135">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="f22fd-136">Per ulteriori informazioni, vedere [Come implementare una classe leggera con proprietà implementate automaticamente](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) e Come eseguire query per i file duplicati in una struttura di [directory.](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f22fd-136">For more information see [How to implement a lightweight class with auto-implemented properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to query for duplicate files in a directory tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="f22fd-137">Il secondo articolo contiene un esempio di codice che illustra come usare una chiave composta con un tipo denominato.</span><span class="sxs-lookup"><span data-stu-id="f22fd-137">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="f22fd-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="f22fd-138">Example</span></span>

<span data-ttu-id="f22fd-139">Nell'esempio seguente viene illustrato il modello standard per l'ordinamento dei dati di origine nei gruppi quando non viene applicata una logica di query aggiuntiva ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="f22fd-139">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="f22fd-140">L'operazione è definita raggruppamento senza continuazione.</span><span class="sxs-lookup"><span data-stu-id="f22fd-140">This is called a grouping without a continuation.</span></span> <span data-ttu-id="f22fd-141">Gli elementi in una matrice di stringhe vengono raggruppati in base alla prima lettera.</span><span class="sxs-lookup"><span data-stu-id="f22fd-141">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="f22fd-142">Il risultato della query è un tipo <xref:System.Linq.IGrouping%602> che contiene una proprietà pubblica `Key` di tipo `char` e una raccolta <xref:System.Collections.Generic.IEnumerable%601> che contiene ogni elemento nel raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="f22fd-142">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="f22fd-143">Il risultato di una clausola `group` è una sequenza di sequenze.</span><span class="sxs-lookup"><span data-stu-id="f22fd-143">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="f22fd-144">Di conseguenza, per accedere ai singoli elementi all'interno di ogni gruppo restituito, usare un ciclo `foreach` nidificato all'interno del ciclo che esegue l'iterazione delle chiavi di raggruppamento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f22fd-144">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="f22fd-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="f22fd-145">Example</span></span>

<span data-ttu-id="f22fd-146">In questo esempio viene illustrato come eseguire la logica aggiuntiva per i gruppi dopo che sono stati creati, usando una *continuazione* con `into`.</span><span class="sxs-lookup"><span data-stu-id="f22fd-146">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="f22fd-147">Per altre informazioni, vedere [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="f22fd-147">For more information, see [into](into.md).</span></span> <span data-ttu-id="f22fd-148">Nell'esempio seguente viene eseguita una query di ogni gruppo per selezionare solo quelli il cui valore della chiave è una vocale.</span><span class="sxs-lookup"><span data-stu-id="f22fd-148">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="f22fd-149">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f22fd-149">Remarks</span></span>

<span data-ttu-id="f22fd-150">In fase di compilazione le clausole `group` vengono convertite in chiamate al metodo <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="f22fd-150">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="f22fd-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f22fd-151">See also</span></span>

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [<span data-ttu-id="f22fd-152">Parole chiave per le query</span><span class="sxs-lookup"><span data-stu-id="f22fd-152">Query Keywords</span></span>](query-keywords.md)
- [<span data-ttu-id="f22fd-153">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="f22fd-153">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="f22fd-154">Creare un gruppo nidificato</span><span class="sxs-lookup"><span data-stu-id="f22fd-154">Create a nested group</span></span>](../../linq/create-a-nested-group.md)
- [<span data-ttu-id="f22fd-155">Raggruppare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="f22fd-155">Group query results</span></span>](../../linq/group-query-results.md)
- [<span data-ttu-id="f22fd-156">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f22fd-156">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
