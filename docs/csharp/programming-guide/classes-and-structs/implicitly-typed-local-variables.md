---
title: Variabili locali tipizzate in modo implicito (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc02c0f7ef5fbbbf3c60188426a8027f6a60fb89
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="3b68d-102">Variabili locali tipizzate in modo implicito (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3b68d-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="3b68d-103">Le variabili locali possono essere dichiarate senza specificare un tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3b68d-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="3b68d-104">La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="3b68d-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="3b68d-105">Il tipo dedotto può essere un tipo predefinito, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b68d-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="3b68d-106">Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="3b68d-107">Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:</span><span class="sxs-lookup"><span data-stu-id="3b68d-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 <span data-ttu-id="3b68d-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b68d-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span></span>  
  
 <span data-ttu-id="3b68d-109">È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="3b68d-109">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="3b68d-110">Significa semplicemente che il compilatore determina e assegna il tipo più adatto.</span><span class="sxs-lookup"><span data-stu-id="3b68d-110">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="3b68d-111">È possibile usare la parola chiave `var` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b68d-111">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="3b68d-112">Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="3b68d-112">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="3b68d-113">In un'istruzione di inizializzazione [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-113">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="3b68d-114">In un'istruzione di inizializzazione [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-114">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="3b68d-115">In un'istruzione [using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-115">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="3b68d-116">Per altre informazioni, vedere [Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-116">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="3b68d-117">var e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="3b68d-117">var and Anonymous Types</span></span>  
 <span data-ttu-id="3b68d-118">In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica.</span><span class="sxs-lookup"><span data-stu-id="3b68d-118">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="3b68d-119">Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`.</span><span class="sxs-lookup"><span data-stu-id="3b68d-119">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="3b68d-120">Si tratta di uno scenario comune nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b68d-120">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="3b68d-121">Per altre informazioni, vedere [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3b68d-121">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="3b68d-122">Dal punto di vista del codice sorgente, un tipo anonimo non ha nome.</span><span class="sxs-lookup"><span data-stu-id="3b68d-122">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="3b68d-123">Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3b68d-123">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 <span data-ttu-id="3b68d-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b68d-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b68d-125">Note</span><span class="sxs-lookup"><span data-stu-id="3b68d-125">Remarks</span></span>  
 <span data-ttu-id="3b68d-126">Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b68d-126">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="3b68d-127">La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="3b68d-127">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="3b68d-128">Non è possibile usare `var` nei campi nell'ambito della classe.</span><span class="sxs-lookup"><span data-stu-id="3b68d-128">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="3b68d-129">Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="3b68d-129">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="3b68d-130">In altre parole, questa espressione è valida: `: int i = (i = 20);`. Questa invece genera un errore in fase di compilazione: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="3b68d-130">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="3b68d-131">Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="3b68d-131">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="3b68d-132">Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="3b68d-132">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="3b68d-133">`var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query,</span><span class="sxs-lookup"><span data-stu-id="3b68d-133">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="3b68d-134">ad esempio con il raggruppamento e l'ordinamento di operazioni.</span><span class="sxs-lookup"><span data-stu-id="3b68d-134">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="3b68d-135">La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="3b68d-135">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="3b68d-136">`var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3b68d-136">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="3b68d-137">Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="3b68d-137">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="3b68d-138">Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="3b68d-138">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 <span data-ttu-id="3b68d-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b68d-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span></span>  
  
 <span data-ttu-id="3b68d-140">L'uso di `var`, tuttavia, può quanto meno rendere più difficoltosa la comprensione del codice per gli altri sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="3b68d-140">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="3b68d-141">Nella documentazione di C# `var` viene quindi in genere usata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="3b68d-141">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b68d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b68d-142">See Also</span></span>  
 <span data-ttu-id="3b68d-143">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3b68d-144">[Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-144">[Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span></span>  
 <span data-ttu-id="3b68d-145">[Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-145">[How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span></span>  
 <span data-ttu-id="3b68d-146">[Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-146">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="3b68d-147">[Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-147">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="3b68d-148">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-148">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 <span data-ttu-id="3b68d-149">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-149">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="3b68d-150">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="3b68d-150">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="3b68d-151">[for](../../../csharp/language-reference/keywords/for.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-151">[for](../../../csharp/language-reference/keywords/for.md) </span></span>  
 <span data-ttu-id="3b68d-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="3b68d-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="3b68d-153">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="3b68d-153">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

