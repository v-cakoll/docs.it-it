---
title: Modificatore del parametro in - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/12/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 5a765a330e4d9efe22943538503c0822e1c9dfdb
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219555"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="e40f9-102">Modificatore del parametro in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e40f9-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="e40f9-103">La parola chiave `in` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="e40f9-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="e40f9-104">È simile alle parole chiave [ref](ref.md) o [out](out-parameter-modifier.md), ma gli argomenti `in` non possono essere modificati dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="e40f9-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="e40f9-105">Mentre gli argomenti `ref` possono essere modificati, gli argomenti `out` devono essere modificati dal metodo chiamato e queste modifiche sono osservabili nel contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e40f9-105">Whereas `ref` arguments may be modified,  `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="e40f9-106">L'esempio precedente dimostra che il modificatore `in` non è in genere necessario nel sito di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e40f9-106">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="e40f9-107">Viene richiesto soltanto nella dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="e40f9-107">It is only required in the method declaration.</span></span>


> [!NOTE] 
> <span data-ttu-id="e40f9-108">La parola chiave `in` può essere usata anche con un parametro di tipo generico per specificare che il parametro è di tipo controvariante, quale parte di un'istruzione `foreach` o parte di una clausola `join` in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="e40f9-108">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="e40f9-109">Per altre informazioni sull'uso della parola chiave `in` in questi contesti, vedere la pagina [in](in.md), in cui sono presenti collegamenti a tutti gli usi.</span><span class="sxs-lookup"><span data-stu-id="e40f9-109">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="e40f9-110">Le variabili passate come argomenti `in` devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e40f9-110">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="e40f9-111">Tuttavia, il metodo chiamato non può assegnare un valore o modificare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="e40f9-111">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="e40f9-112">Il modificatore di parametro `in` è disponibile in C# 7.2 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e40f9-112">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="e40f9-113">Nelle versioni precedenti viene generato l'errore del compilatore `CS8107` ("La funzionalità 'riferimenti di sola lettura' non è disponibile in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="e40f9-113">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="e40f9-114">Usare la versione 7.2 o versioni successive del linguaggio.") Per configurare la versione del linguaggio del compilatore, vedere [Selezionare la versione del linguaggio C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="e40f9-114">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

 <span data-ttu-id="e40f9-115">Nonostante le parole chiave `in`, `ref` e `out` determinino un comportamento differente in fase di esecuzione, non sono considerate parte della firma del metodo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e40f9-115">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="e40f9-116">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-116">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="e40f9-117">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="e40f9-117">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="e40f9-118">È consentito l'overload in base alla presenza di `in`:</span><span class="sxs-lookup"><span data-stu-id="e40f9-118">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="e40f9-119">Regole di risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="e40f9-119">Overload resolution rules</span></span>

<span data-ttu-id="e40f9-120">È possibile comprendere le regole di risoluzione dell'overload per i metodi con argomenti per valore rispetto ai metodi con argomenti `in` se si comprende la motivazione per gli argomenti `in`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-120">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="e40f9-121">La definizione di metodi tramite parametri `in` costituisce un'ottimizzazione potenziale delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e40f9-121">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="e40f9-122">Alcuni argomenti di tipo `struct` possono essere di grandi dimensioni e quando vengono chiamati metodi all'interno di cicli ristretti o in percorsi di codice critici, il costo della copia di tali strutture ha una rilevanza fondamentale.</span><span class="sxs-lookup"><span data-stu-id="e40f9-122">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="e40f9-123">I metodi dichiarano parametri `in` per specificare che è possibile passare argomenti per riferimento in modo sicuro, perché il metodo chiamato non modifica lo stato degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="e40f9-123">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="e40f9-124">Il passaggio di tali argomenti per riferimento consente di evitare una copia potenzialmente dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="e40f9-124">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="e40f9-125">Specificare `in` per gli argomenti presso il sito di chiamata è in genere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e40f9-125">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="e40f9-126">Non esiste alcuna differenza semantica tra il passaggio di argomenti per valore e il passaggio per riferimento tramite il modificatore `in`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-126">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="e40f9-127">Il modificatore `in` presso il sito di chiamata è facoltativo perché non è necessario indicare che il valore dell'argomento può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e40f9-127">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="e40f9-128">Si aggiunge il modificatore `in` in modo esplicito presso il sito di chiamata per assicurarsi che l'argomento venga passato per riferimento, non per valore.</span><span class="sxs-lookup"><span data-stu-id="e40f9-128">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="e40f9-129">L'uso di `in` in modo esplicito ha i due effetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e40f9-129">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="e40f9-130">In primo luogo, se si specifica `in` presso il sito di chiamata si impone al compilatore di selezionare un metodo definito con un parametro `in` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e40f9-130">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="e40f9-131">In caso contrario, se due metodi si differenziano solo per la presenza di `in`, l'overload per valore rappresenta una corrispondenza migliore.</span><span class="sxs-lookup"><span data-stu-id="e40f9-131">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="e40f9-132">In secondo luogo, se si specifica `in` si dichiara l'intenzione di passare un argomento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="e40f9-132">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="e40f9-133">L'argomento usato con `in` deve rappresentare una posizione a cui sia possibile fare riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="e40f9-133">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="e40f9-134">Sono valide le stesse regole generali applicabili agli argomenti `out` e `ref`: non è possibile usare costanti, proprietà ordinarie o altre espressioni che producono valori.</span><span class="sxs-lookup"><span data-stu-id="e40f9-134">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="e40f9-135">In caso contrario, l'omissione di `in` presso il sito di chiamata informa il compilatore che è consentito creare una variabile temporanea da passare per riferimento di sola lettura al metodo.</span><span class="sxs-lookup"><span data-stu-id="e40f9-135">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="e40f9-136">Il compilatore crea una variabile temporanea per superare diverse restrizioni degli argomenti `in`:</span><span class="sxs-lookup"><span data-stu-id="e40f9-136">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="e40f9-137">Una variabile temporanea consente costanti in fase di compilazione come parametri `in`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-137">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="e40f9-138">Una variabile temporanea consente proprietà o altre espressioni per i parametri `in`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-138">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="e40f9-139">Una variabile temporanea consente argomenti che includono una conversione implicita dal tipo di argomento al tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="e40f9-139">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="e40f9-140">In tutte le istanze precedenti, il compilatore crea una variabile temporanea che archivia il valore della costante, della proprietà o di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="e40f9-140">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="e40f9-141">Il codice seguente illustra queste regole:</span><span class="sxs-lookup"><span data-stu-id="e40f9-141">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="e40f9-142">Si supponga a questo punto che sia disponibile un altro metodo che usa argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="e40f9-142">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="e40f9-143">I risultati cambiano, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e40f9-143">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="e40f9-144">L'unica chiamata a un metodo in cui l'argomento viene passato per riferimento è quella finale.</span><span class="sxs-lookup"><span data-stu-id="e40f9-144">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="e40f9-145">Per semplicità, il codice precedente usa `int` come tipo di argomento.</span><span class="sxs-lookup"><span data-stu-id="e40f9-145">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="e40f9-146">Poiché nella maggior parte dei computer moderni le dimensioni di `int` non sono maggiori di quelle di un riferimento, non si ottiene alcun vantaggio dal passaggio di un unico `int` come riferimento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e40f9-146">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="e40f9-147">Limitazioni dei parametri `in`</span><span class="sxs-lookup"><span data-stu-id="e40f9-147">Limitations on `in` parameters</span></span>

<span data-ttu-id="e40f9-148">Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="e40f9-148">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="e40f9-149">Metodi asincroni definiti usando il modificatore [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="e40f9-149">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="e40f9-150">Metodi iteratori che includono un'istruzione [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="e40f9-150">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="e40f9-151">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e40f9-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e40f9-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e40f9-152">See also</span></span>

- [<span data-ttu-id="e40f9-153">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e40f9-153">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e40f9-154">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e40f9-154">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e40f9-155">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e40f9-155">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e40f9-156">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="e40f9-156">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="e40f9-157">Scrivere codice efficiente e sicuro</span><span class="sxs-lookup"><span data-stu-id="e40f9-157">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
