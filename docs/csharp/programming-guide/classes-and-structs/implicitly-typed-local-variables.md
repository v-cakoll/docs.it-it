---
title: Variabili locali tipizzate in modo implicito - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 72114233044fbf0e9910048343806eb542ed7ea5
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063746"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="51aa9-102">Variabili locali tipizzate in modo implicito - Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="51aa9-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="51aa9-103">Le variabili locali possono essere dichiarate senza specificare un tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="51aa9-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="51aa9-104">La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="51aa9-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="51aa9-105">Il tipo dedotto può essere un tipo predefinito, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51aa9-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="51aa9-106">Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="51aa9-107">Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:</span><span class="sxs-lookup"><span data-stu-id="51aa9-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="51aa9-108">È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="51aa9-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="51aa9-109">Significa semplicemente che il compilatore determina e assegna il tipo più adatto.</span><span class="sxs-lookup"><span data-stu-id="51aa9-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="51aa9-110">È possibile usare la parola chiave `var` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="51aa9-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="51aa9-111">Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="51aa9-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="51aa9-112">In un'istruzione di inizializzazione [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for(var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="51aa9-113">In un'istruzione di inizializzazione [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach(var item in list){...}
    ```

- <span data-ttu-id="51aa9-114">In un'istruzione [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="51aa9-115">Per altre informazioni, vedere [Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="51aa9-116">var e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="51aa9-116">var and anonymous types</span></span>

<span data-ttu-id="51aa9-117">In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica.</span><span class="sxs-lookup"><span data-stu-id="51aa9-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="51aa9-118">Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`.</span><span class="sxs-lookup"><span data-stu-id="51aa9-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="51aa9-119">Si tratta di uno scenario comune nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51aa9-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="51aa9-120">Per altre informazioni, vedere [Tipi anonimi](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="51aa9-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="51aa9-121">Dal punto di vista del codice sorgente, un tipo anonimo non ha nome.</span><span class="sxs-lookup"><span data-stu-id="51aa9-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="51aa9-122">Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="51aa9-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="51aa9-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="51aa9-123">Remarks</span></span>

<span data-ttu-id="51aa9-124">Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51aa9-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="51aa9-125">La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="51aa9-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="51aa9-126">Non è possibile usare `var` nei campi nell'ambito della classe.</span><span class="sxs-lookup"><span data-stu-id="51aa9-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="51aa9-127">Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="51aa9-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="51aa9-128">In altre parole, questa espressione è valida: `: int i = (i = 20);`. Questa invece genera un errore in fase di compilazione: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="51aa9-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="51aa9-129">Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="51aa9-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="51aa9-130">Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="51aa9-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="51aa9-131">La tipizzazione implicita con la parola chiave `var` può essere applicata solo alle variabili nell'ambito del metodo locale.</span><span class="sxs-lookup"><span data-stu-id="51aa9-131">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="51aa9-132">La tipizzazione implicita non è disponibile per i campi di classe perché il compilatore C# riscontrerebbe un paradosso logico durante l'elaborazione del codice: il compilatore deve conoscere il tipo del campo, ma è in grado di determinare il tipo solo dopo che l'espressione di assegnazione è stata analizzata e l'espressione non può essere valutata senza conoscere il tipo.</span><span class="sxs-lookup"><span data-stu-id="51aa9-132">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="51aa9-133">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="51aa9-133">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="51aa9-134">`bookTitles` è un campo di classe a cui è stato assegnato il tipo `var`.</span><span class="sxs-lookup"><span data-stu-id="51aa9-134">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="51aa9-135">Poiché il campo non ha alcuna espressione da valutare, è impossibile per il compilatore dedurre quale tipo dovrebbe essere `bookTitles`.</span><span class="sxs-lookup"><span data-stu-id="51aa9-135">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="51aa9-136">Inoltre, anche l'aggiunta di un'espressione al campo, come si farebbe per una variabile locale, risulta insufficiente:</span><span class="sxs-lookup"><span data-stu-id="51aa9-136">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="51aa9-137">Quando il compilatore rileva i campi durante la compilazione del codice, registra il tipo di ogni campo prima di elaborare le espressioni a esso associate.</span><span class="sxs-lookup"><span data-stu-id="51aa9-137">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="51aa9-138">Durante il tentativo di analisi di `bookTitles`, il compilatore rileva lo stesso paradosso: ha necessità di conoscere il tipo del campo, ma il compilatore normalmente determina il tipo di `var` tramite l'analisi dell'espressione, operazione che non è possibile eseguire senza conoscere prima il tipo.</span><span class="sxs-lookup"><span data-stu-id="51aa9-138">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="51aa9-139">`var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query,</span><span class="sxs-lookup"><span data-stu-id="51aa9-139">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="51aa9-140">ad esempio con il raggruppamento e l'ordinamento di operazioni.</span><span class="sxs-lookup"><span data-stu-id="51aa9-140">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="51aa9-141">La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="51aa9-141">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="51aa9-142">`var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="51aa9-142">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="51aa9-143">Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="51aa9-143">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="51aa9-144">Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="51aa9-144">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="51aa9-145">L'uso di `var`, tuttavia, può quanto meno rendere più difficoltosa la comprensione del codice per gli altri sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="51aa9-145">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="51aa9-146">Nella documentazione di C# `var` viene quindi in genere usata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="51aa9-146">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="51aa9-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51aa9-147">See also</span></span>

- [<span data-ttu-id="51aa9-148">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="51aa9-148">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="51aa9-149">Matrici tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="51aa9-149">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="51aa9-150">Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="51aa9-150">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="51aa9-151">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="51aa9-151">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="51aa9-152">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="51aa9-152">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="51aa9-153">var</span><span class="sxs-lookup"><span data-stu-id="51aa9-153">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="51aa9-154">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="51aa9-154">LINQ Query Expressions</span></span>](../linq-query-expressions/index.md)
- [<span data-ttu-id="51aa9-155">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="51aa9-155">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="51aa9-156">for</span><span class="sxs-lookup"><span data-stu-id="51aa9-156">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="51aa9-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="51aa9-157">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="51aa9-158">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="51aa9-158">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
