---
title: Variabili locali tipizzate in modo implicito - Guida per programmatori C#
description: La parola chiave var in C# indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 6badb8588dedda80227ab38bee027cf2890c8672
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864215"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="bcd0e-103">Variabili locali tipizzate in modo implicito - Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bcd0e-103">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="bcd0e-104">Le variabili locali possono essere dichiarate senza specificare un tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-104">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="bcd0e-105">La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-105">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="bcd0e-106">Il tipo derivato può essere un tipo incorporato, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-106">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET class library.</span></span> <span data-ttu-id="bcd0e-107">Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-107">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="bcd0e-108">Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:</span><span class="sxs-lookup"><span data-stu-id="bcd0e-108">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="bcd0e-109">È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-109">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="bcd0e-110">Significa semplicemente che il compilatore determina e assegna il tipo più adatto.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-110">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="bcd0e-111">È possibile usare la parola chiave `var` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcd0e-111">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="bcd0e-112">Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-112">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="bcd0e-113">In un'istruzione di inizializzazione [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-113">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="bcd0e-114">In un'istruzione di inizializzazione [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-114">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach (var item in list) {...}
    ```

- <span data-ttu-id="bcd0e-115">In un'istruzione [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-115">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="bcd0e-116">Per ulteriori informazioni, vedere [come utilizzare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-116">For more information, see [How to use implicitly typed local variables and arrays in a query expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="bcd0e-117">var e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="bcd0e-117">var and anonymous types</span></span>

<span data-ttu-id="bcd0e-118">In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-118">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="bcd0e-119">Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-119">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="bcd0e-120">Si tratta di uno scenario comune nelle espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-120">This is a common scenario in LINQ query expressions.</span></span> <span data-ttu-id="bcd0e-121">Per ulteriori informazioni, vedere [tipi anonimi](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="bcd0e-121">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="bcd0e-122">Dal punto di vista del codice sorgente, un tipo anonimo non ha nome.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-122">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="bcd0e-123">Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-123">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="bcd0e-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="bcd0e-124">Remarks</span></span>

<span data-ttu-id="bcd0e-125">Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcd0e-125">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="bcd0e-126">La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-126">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="bcd0e-127">Non è possibile usare `var` nei campi nell'ambito della classe.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-127">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="bcd0e-128">Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-128">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="bcd0e-129">In altre parole, questa espressione è valida: `int i = (i = 20);` ma questa espressione genera un errore in fase di compilazione:`var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="bcd0e-129">In other words, this expression is legal: `int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="bcd0e-130">Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-130">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="bcd0e-131">Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-131">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="bcd0e-132">La tipizzazione implicita con la parola chiave `var` può essere applicata solo alle variabili nell'ambito del metodo locale.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-132">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="bcd0e-133">La tipizzazione implicita non è disponibile per i campi di classe perché il compilatore C# riscontrerebbe un paradosso logico durante l'elaborazione del codice: il compilatore deve conoscere il tipo del campo, ma è in grado di determinare il tipo solo dopo che l'espressione di assegnazione è stata analizzata e l'espressione non può essere valutata senza conoscere il tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-133">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="bcd0e-134">Osservare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="bcd0e-134">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="bcd0e-135">`bookTitles` è un campo di classe a cui è stato assegnato il tipo `var`.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-135">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="bcd0e-136">Poiché il campo non ha alcuna espressione da valutare, è impossibile per il compilatore dedurre quale tipo dovrebbe essere `bookTitles`.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-136">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="bcd0e-137">Inoltre, anche l'aggiunta di un'espressione al campo, come si farebbe per una variabile locale, risulta insufficiente:</span><span class="sxs-lookup"><span data-stu-id="bcd0e-137">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="bcd0e-138">Quando il compilatore rileva i campi durante la compilazione del codice, registra il tipo di ogni campo prima di elaborare le espressioni a esso associate.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-138">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="bcd0e-139">Durante il tentativo di analisi di `bookTitles`, il compilatore rileva lo stesso paradosso: ha necessità di conoscere il tipo del campo, ma il compilatore normalmente determina il tipo di `var` tramite l'analisi dell'espressione, operazione che non è possibile eseguire senza conoscere prima il tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-139">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="bcd0e-140">`var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query,</span><span class="sxs-lookup"><span data-stu-id="bcd0e-140">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="bcd0e-141">ad esempio con il raggruppamento e l'ordinamento di operazioni.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-141">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="bcd0e-142">La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-142">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="bcd0e-143">`var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-143">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="bcd0e-144">Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-144">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="bcd0e-145">Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-145">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="bcd0e-146">L'uso di `var` consente di semplificare il codice, ma il suo uso dovrebbe essere limitato ai casi in cui è necessario o quando rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-146">The use of `var` helps simplify your code, but its use should be restricted to cases where it is required, or when it makes your code easier to read.</span></span> <span data-ttu-id="bcd0e-147">Per altre informazioni su quando usare `var` correttamente, vedere la sezione [variabili locali tipizzate in modo implicito](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) nell'articolo linee guida per il codice C#.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-147">For more information about when to use `var` properly, see the [Implicitly typed local variables](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) section on the C# Coding Guidelines article.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcd0e-148">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bcd0e-148">See also</span></span>

- [<span data-ttu-id="bcd0e-149">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bcd0e-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="bcd0e-150">Matrici tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="bcd0e-150">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="bcd0e-151">Come usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="bcd0e-151">How to use implicitly typed local variables and arrays in a query expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="bcd0e-152">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="bcd0e-152">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="bcd0e-153">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="bcd0e-153">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="bcd0e-154">var</span><span class="sxs-lookup"><span data-stu-id="bcd0e-154">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="bcd0e-155">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="bcd0e-155">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="bcd0e-156">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="bcd0e-156">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="bcd0e-157">for</span><span class="sxs-lookup"><span data-stu-id="bcd0e-157">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="bcd0e-158">foreach, in</span><span class="sxs-lookup"><span data-stu-id="bcd0e-158">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="bcd0e-159">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="bcd0e-159">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
