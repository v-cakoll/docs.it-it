---
title: Delegati e lambda
description: Informazioni sul modo in cui i delegati, che definiscono un tipo che specifica una firma del metodo particolare, possono essere chiamati direttamente o passati a un altro metodo e chiamati.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 184c9f61fd8456b22e8ecb262c131793160b49b0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244010"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="5ee21-103">Delegati e lambda</span><span class="sxs-lookup"><span data-stu-id="5ee21-103">Delegates and lambdas</span></span>

<span data-ttu-id="5ee21-104">I delegati definiscono un tipo che specifica una firma del metodo particolare.</span><span class="sxs-lookup"><span data-stu-id="5ee21-104">Delegates define a type that specifies a particular method signature.</span></span> <span data-ttu-id="5ee21-105">Un metodo (statico o istanza) che soddisfa questa firma può essere assegnato a una variabile del tipo, quindi chiamato direttamente (con gli argomenti appropriati) o passato come argomento a un altro metodo e quindi chiamato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="5ee21-106">L'esempio seguente mostra l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="5ee21-106">The following example demonstrates delegate use.</span></span>

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

* <span data-ttu-id="5ee21-107">La riga `public delegate string Reverse(string s);` crea un tipo delegato di una determinata firma, in questo caso un metodo che accetta un parametro di stringa e quindi restituisce un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="5ee21-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="5ee21-108">Il metodo `static string ReverseString(string s)`, che ha esattamente la stessa firma del tipo delegato definito, implementa il delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="5ee21-109">La riga `Reverse rev = ReverseString;` indica che si può assegnare un metodo a una variabile del tipo di delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5ee21-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="5ee21-110">La riga `Console.WriteLine(rev("a string"));` illustra come usare una variabile di un tipo delegato per richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="5ee21-111">Per semplificare il processo di sviluppo, .NET include un set di tipi di delegato che i programmatori possono riutilizzare senza dover creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="5ee21-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="5ee21-112">Questi tipi sono `Func<>` , `Action<>` e `Predicate<>` e possono essere usati senza dover definire nuovi tipi di delegati.</span><span class="sxs-lookup"><span data-stu-id="5ee21-112">These types are `Func<>`, `Action<>` and `Predicate<>`, and they can be used without having to define new delegate types.</span></span> <span data-ttu-id="5ee21-113">Esistono alcune differenze tra i tre tipi che hanno a che fare con il modo in cui sono stati progettati per l'uso:</span><span class="sxs-lookup"><span data-stu-id="5ee21-113">There are some differences between the three types that have to do with the way they were intended to be used:</span></span>

* <span data-ttu-id="5ee21-114">`Action<>` viene usato quando è necessario eseguire un'azione usando gli argomenti del delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="5ee21-115">Il metodo incapsulato non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="5ee21-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="5ee21-116">`Func<>` viene in genere usato in presenza di una trasformazione, ovvero quando è necessario trasformare gli argomenti del delegato in un risultato diverso.</span><span class="sxs-lookup"><span data-stu-id="5ee21-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="5ee21-117">Le proiezioni sono un esempio valido.</span><span class="sxs-lookup"><span data-stu-id="5ee21-117">Projections are a good example.</span></span> <span data-ttu-id="5ee21-118">Il metodo incapsulato restituisce un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="5ee21-119">`Predicate<>` viene usato quando è necessario determinare se l'argomento soddisfa la condizione del delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="5ee21-120">Può anche essere scritto come `Func<T, bool>` , il che significa che il metodo restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="5ee21-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="5ee21-121">L'esempio precedente può essere ora riscritto usando il delegato `Func<>` anziché un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="5ee21-122">Il programma continuerà a essere eseguito nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="5ee21-122">The program will continue running exactly the same.</span></span>

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

<span data-ttu-id="5ee21-123">In questo esempio semplice la presenza di un metodo definito all'esterno del metodo `Main` non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="5ee21-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="5ee21-124">.NET Framework 2,0 ha introdotto il concetto di *delegati anonimi*, che consentono di creare delegati "inline" senza dover specificare alcun tipo o metodo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5ee21-124">.NET Framework 2.0 introduced the concept of *anonymous delegates*, which let you create "inline" delegates without having to specify any additional type or method.</span></span>

<span data-ttu-id="5ee21-125">Nell'esempio seguente un delegato anonimo filtra un elenco solo per i numeri pari e li stampa nella console.</span><span class="sxs-lookup"><span data-stu-id="5ee21-125">In the following example, an anonymous delegate filters a list to just the even numbers and then prints them to the console.</span></span>

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

<span data-ttu-id="5ee21-126">È possibile osservare che il corpo del delegato è costituito da un set di espressioni, come qualsiasi altro delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="5ee21-127">Anziché essere una definizione separata, è stata introdotta _ad hoc_ nella chiamata al <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="5ee21-127">But instead of it being a separate definition, we've introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="5ee21-128">Anche con questo approccio, tuttavia, rimane una parte considerevole di codice che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="5ee21-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="5ee21-129">A tale scopo, vengono usate le *espressioni lambda*.</span><span class="sxs-lookup"><span data-stu-id="5ee21-129">This is where *lambda expressions* come into play.</span></span> <span data-ttu-id="5ee21-130">Le espressioni lambda, o solo "lambda", sono state introdotte in C# 3,0 come uno dei componenti fondamentali di Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="5ee21-130">Lambda expressions, or just "lambdas" for short, were introduced in C# 3.0 as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="5ee21-131">Si tratta semplicemente una sintassi più pratica per l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="5ee21-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="5ee21-132">Dichiarano una firma e il corpo di un metodo, ma non hanno un'identità formale, a meno che non siano assegnati a un delegato.</span><span class="sxs-lookup"><span data-stu-id="5ee21-132">They declare a signature and a method body, but don't have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="5ee21-133">A differenza dei delegati, possono essere assegnati direttamente come lato destro della registrazione degli eventi o in diversi metodi e clausole LINQ.</span><span class="sxs-lookup"><span data-stu-id="5ee21-133">Unlike delegates, they can be directly assigned as the right-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="5ee21-134">Poiché un'espressione lambda è soltanto un modo diverso di specificare un delegato, è possibile riscrivere l'esempio precedente per usare un'espressione lambda anziché un delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="5ee21-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

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

<span data-ttu-id="5ee21-135">Nell'esempio precedente l'espressione lambda usata è `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="5ee21-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="5ee21-136">Anche in questo caso si tratta semplicemente di una semplice sintassi per l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="5ee21-136">Again, it is just a convenient syntax for using delegates.</span></span> <span data-ttu-id="5ee21-137">Ciò che accade sotto le quinte è simile a quello che accade con il delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="5ee21-137">What happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="5ee21-138">Le lambda sono semplicemente delegati, ovvero possono essere usate come gestori di eventi come mostra il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5ee21-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

<span data-ttu-id="5ee21-139">L'operatore `+=` in questo contesto viene usato per eseguire la sottoscrizione a un [evento](../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="5ee21-139">The `+=` operator in this context is used to subscribe to an [event](../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="5ee21-140">Per ulteriori informazioni, vedere [come sottoscrivere e annullare la sottoscrizione di eventi](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="5ee21-140">For more information, see [How to subscribe to and unsubscribe from events](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="5ee21-141">Altre informazioni e risorse</span><span class="sxs-lookup"><span data-stu-id="5ee21-141">Further reading and resources</span></span>

* [<span data-ttu-id="5ee21-142">Delegati</span><span class="sxs-lookup"><span data-stu-id="5ee21-142">Delegates</span></span>](../csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="5ee21-143">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="5ee21-143">Anonymous Functions</span></span>](../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="5ee21-144">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="5ee21-144">Lambda expressions</span></span>](../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
