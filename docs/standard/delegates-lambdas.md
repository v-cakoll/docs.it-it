---
title: Delegati e lambda
description: Informazioni su come i delegati, che definiscono un tipo che specifica una determinata firma del metodo, possono essere chiamati direttamente o passati a un altro metodo e.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: a9ca935814d1a7f77ded5f371ccd496c3859c523
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635934"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="2d492-103">Delegati e lambda</span><span class="sxs-lookup"><span data-stu-id="2d492-103">Delegates and lambdas</span></span>

<span data-ttu-id="2d492-104">I delegati definiscono un tipo che specifica una particolare firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="2d492-104">Delegates define a type that specifies a particular method signature.</span></span> <span data-ttu-id="2d492-105">Un metodo (statico o istanza) che soddisfa questa firma può essere assegnato a una variabile del tipo, quindi chiamato direttamente (con gli argomenti appropriati) o passato come argomento a un altro metodo e quindi chiamato.</span><span class="sxs-lookup"><span data-stu-id="2d492-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="2d492-106">L'esempio seguente mostra l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="2d492-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="2d492-107">La riga `public delegate string Reverse(string s);` crea un tipo delegato di una determinata firma, in questo caso un metodo che accetta un parametro di stringa e quindi restituisce un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="2d492-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="2d492-108">Il metodo `static string ReverseString(string s)`, che ha esattamente la stessa firma del tipo delegato definito, implementa il delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="2d492-109">La riga `Reverse rev = ReverseString;` indica che si può assegnare un metodo a una variabile del tipo di delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2d492-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="2d492-110">La riga `Console.WriteLine(rev("a string"));` illustra come usare una variabile di un tipo delegato per richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="2d492-111">Per semplificare il processo di sviluppo, .NET include un set di tipi di delegato che i programmatori possono riutilizzare senza dover creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="2d492-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="2d492-112">Questi tipi `Func<>` `Action<>` sono `Predicate<>`, e , e possono essere utilizzati senza dover definire nuovi tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="2d492-112">These types are `Func<>`, `Action<>` and `Predicate<>`, and they can be used without having to define new delegate types.</span></span> <span data-ttu-id="2d492-113">Ci sono alcune differenze tra i tre tipi che hanno a che fare con il modo in cui sono stati destinati ad essere utilizzati:</span><span class="sxs-lookup"><span data-stu-id="2d492-113">There are some differences between the three types that have to do with the way they were intended to be used:</span></span>

* <span data-ttu-id="2d492-114">`Action<>` viene usato quando è necessario eseguire un'azione usando gli argomenti del delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="2d492-115">Il metodo che incapsula non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="2d492-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="2d492-116">`Func<>` viene in genere usato in presenza di una trasformazione, ovvero quando è necessario trasformare gli argomenti del delegato in un risultato diverso.</span><span class="sxs-lookup"><span data-stu-id="2d492-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="2d492-117">Le proiezioni sono un buon esempio.</span><span class="sxs-lookup"><span data-stu-id="2d492-117">Projections are a good example.</span></span> <span data-ttu-id="2d492-118">Il metodo che incapsula restituisce un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="2d492-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="2d492-119">`Predicate<>` viene usato quando è necessario determinare se l'argomento soddisfa la condizione del delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="2d492-120">Può anche essere scritto `Func<T, bool>`come un oggetto , ovvero il metodo restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="2d492-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="2d492-121">L'esempio precedente può essere ora riscritto usando il delegato `Func<>` anziché un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2d492-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="2d492-122">Il programma continuerà a essere eseguito nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="2d492-122">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="2d492-123">In questo esempio semplice la presenza di un metodo definito all'esterno del metodo `Main` non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="2d492-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="2d492-124">In .NET Framework 2.0 è stato introdotto il concetto di *delegati anonimi,* che consentono di creare delegati "inline" senza dover specificare alcun tipo o metodo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2d492-124">.NET Framework 2.0 introduced the concept of *anonymous delegates*, which let you create "inline" delegates without having to specify any additional type or method.</span></span>

<span data-ttu-id="2d492-125">Nell'esempio seguente, un delegato anonimo filtra un elenco in base ai soli numeri pari e quindi li stampa nella console.</span><span class="sxs-lookup"><span data-stu-id="2d492-125">In the following example, an anonymous delegate filters a list to just the even numbers and then prints them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="2d492-126">È possibile osservare che il corpo del delegato è costituito da un set di espressioni, come qualsiasi altro delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="2d492-127">Ma invece di essere una definizione separata, abbiamo introdotto <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> _ad hoc_ nella nostra chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="2d492-127">But instead of it being a separate definition, we've introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="2d492-128">Anche con questo approccio, tuttavia, rimane una parte considerevole di codice che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="2d492-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="2d492-129">A tale scopo, vengono usate le *espressioni lambda*.</span><span class="sxs-lookup"><span data-stu-id="2d492-129">This is where *lambda expressions* come into play.</span></span> <span data-ttu-id="2d492-130">Le espressioni lambda, o solo "lambda" in breve, sono state introdotte in C ,0 come uno dei blocchi predefiniti di base di Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="2d492-130">Lambda expressions, or just "lambdas" for short, were introduced in C# 3.0 as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="2d492-131">Si tratta semplicemente una sintassi più pratica per l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="2d492-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="2d492-132">Dichiarano una firma e un corpo del metodo, ma non hanno un'identità formale propria, a meno che non siano assegnati a un delegato.</span><span class="sxs-lookup"><span data-stu-id="2d492-132">They declare a signature and a method body, but don't have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="2d492-133">A differenza dei delegati, possono essere assegnate direttamente come parte sinistra della registrazione eventi o in diverse clausole e metodi LINQ.</span><span class="sxs-lookup"><span data-stu-id="2d492-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="2d492-134">Poiché un'espressione lambda è soltanto un modo diverso di specificare un delegato, è possibile riscrivere l'esempio precedente per usare un'espressione lambda anziché un delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="2d492-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="2d492-135">Nell'esempio precedente l'espressione lambda usata è `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="2d492-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="2d492-136">Anche in questo caso, è solo una comoda sintassi per l'utilizzo di delegati.</span><span class="sxs-lookup"><span data-stu-id="2d492-136">Again, it is just a convenient syntax for using delegates.</span></span> <span data-ttu-id="2d492-137">Ciò che accade sotto le coperte è simile a quello che accade con il delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="2d492-137">What happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="2d492-138">Le lambda sono semplicemente delegati, ovvero possono essere usate come gestori di eventi come mostra il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2d492-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

<span data-ttu-id="2d492-139">L'operatore `+=` in questo contesto viene usato per eseguire la sottoscrizione a un [evento](../../docs/csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="2d492-139">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="2d492-140">Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="2d492-140">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="2d492-141">Altre informazioni e risorse</span><span class="sxs-lookup"><span data-stu-id="2d492-141">Further reading and resources</span></span>

* [<span data-ttu-id="2d492-142">Delegati</span><span class="sxs-lookup"><span data-stu-id="2d492-142">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="2d492-143">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="2d492-143">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="2d492-144">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="2d492-144">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
