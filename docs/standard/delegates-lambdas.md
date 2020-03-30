---
title: Delegati e lambda
description: Informazioni sul modo in cui i delegati definiscono un tipo, che specifica una firma del metodo particolare, che può essere chiamato direttamente o passato a un altro metodo e chiamato.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 34bfa4c6007ec771f784e927675f4e24d52e194f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391234"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="1ecb9-103">Delegati e lambda</span><span class="sxs-lookup"><span data-stu-id="1ecb9-103">Delegates and lambdas</span></span>

<span data-ttu-id="1ecb9-104">I delegati definiscono un tipo che specifica una firma di metodo specifica.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="1ecb9-105">Un metodo (statico o istanza) che soddisfa questa firma può essere assegnato a una variabile del tipo, quindi chiamato direttamente (con gli argomenti appropriati) o passato come argomento a un altro metodo e quindi chiamato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="1ecb9-106">L'esempio seguente mostra l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-106">The following example demonstrates delegate use.</span></span>

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

* <span data-ttu-id="1ecb9-107">La riga `public delegate string Reverse(string s);` crea un tipo delegato di una determinata firma, in questo caso un metodo che accetta un parametro di stringa e quindi restituisce un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="1ecb9-108">Il metodo `static string ReverseString(string s)`, che ha esattamente la stessa firma del tipo delegato definito, implementa il delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="1ecb9-109">La riga `Reverse rev = ReverseString;` indica che si può assegnare un metodo a una variabile del tipo di delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="1ecb9-110">La riga `Console.WriteLine(rev("a string"));` illustra come usare una variabile di un tipo delegato per richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="1ecb9-111">Per semplificare il processo di sviluppo, .NET include un set di tipi di delegato che i programmatori possono riutilizzare senza dover creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="1ecb9-112">I tipi sono `Func<>`, `Action<>` e `Predicate<>` e possono essere usati in posizioni diverse all'interno delle API .NET senza dover definire nuovi tipi di delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="1ecb9-113">Le differenze tra i tre tipi sono evidenti nelle firme e riguardano principalmente la modalità di utilizzo prevista:</span><span class="sxs-lookup"><span data-stu-id="1ecb9-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

* <span data-ttu-id="1ecb9-114">`Action<>` viene usato quando è necessario eseguire un'azione usando gli argomenti del delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="1ecb9-115">Il metodo che incapsula non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="1ecb9-116">`Func<>` viene in genere usato in presenza di una trasformazione, ovvero quando è necessario trasformare gli argomenti del delegato in un risultato diverso.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="1ecb9-117">Le proiezioni sono un esempio tipico.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-117">Projections are a prime example of this.</span></span> <span data-ttu-id="1ecb9-118">Il metodo che incapsula restituisce un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="1ecb9-119">`Predicate<>` viene usato quando è necessario determinare se l'argomento soddisfa la condizione del delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="1ecb9-120">Può anche essere scritto `Func<T, bool>`come un oggetto , ovvero il metodo restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="1ecb9-121">L'esempio precedente può essere ora riscritto usando il delegato `Func<>` anziché un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="1ecb9-122">Il programma continuerà a essere eseguito nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-122">The program will continue running exactly the same.</span></span>

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

<span data-ttu-id="1ecb9-123">In questo esempio semplice la presenza di un metodo definito all'esterno del metodo `Main` non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="1ecb9-124">Per questa ragione è stato introdotto in .NET Framework 2.0 il concetto di **delegati anonimi**.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-124">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="1ecb9-125">I delegati anonimi consentono di creare delegati "inline" senza dover specificare tipi o metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-125">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="1ecb9-126">Sarà sufficiente incorporare la definizione del delegato dove necessario.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-126">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="1ecb9-127">In questo esempio il delegato anonimo viene configurato e usato per visualizzare un elenco dei soli numeri pari che vengono quindi stampati nella console.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-127">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

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

<span data-ttu-id="1ecb9-128">È possibile osservare che il corpo del delegato è costituito da un set di espressioni, come qualsiasi altro delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-128">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="1ecb9-129">Ma anziché essere una definizione separata, il delegato è stato inserito _appositamente_ nella chiamata al metodo <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-129">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1ecb9-130">Anche con questo approccio, tuttavia, rimane una parte considerevole di codice che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-130">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="1ecb9-131">A tale scopo, vengono usate le **espressioni lambda**.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-131">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="1ecb9-132">Le espressioni lambda, chiamate anche "lambda", sono state usate per la prima volta in C# 3.0 come uno dei componenti fondamentali di Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="1ecb9-132">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="1ecb9-133">Si tratta semplicemente una sintassi più pratica per l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-133">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="1ecb9-134">Dichiarano una firma e un corpo del metodo, ma non hanno un'identità formale propria, a meno che non siano assegnati a un delegato.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-134">They declare a signature and a method body, but don’t have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="1ecb9-135">A differenza dei delegati, possono essere assegnate direttamente come parte sinistra della registrazione eventi o in diverse clausole e metodi LINQ.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-135">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="1ecb9-136">Poiché un'espressione lambda è soltanto un modo diverso di specificare un delegato, è possibile riscrivere l'esempio precedente per usare un'espressione lambda anziché un delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-136">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

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

<span data-ttu-id="1ecb9-137">Nell'esempio precedente l'espressione lambda usata è `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-137">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="1ecb9-138">Anche in questo caso, si tratta soltanto di una sintassi **molto** pratica per l'uso di delegati con un funzionamento simile a quello del delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-138">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="1ecb9-139">Le lambda sono semplicemente delegati, ovvero possono essere usate come gestori di eventi come mostra il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1ecb9-139">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

<span data-ttu-id="1ecb9-140">L'operatore `+=` in questo contesto viene usato per eseguire la sottoscrizione a un [evento](../../docs/csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="1ecb9-140">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="1ecb9-141">Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="1ecb9-141">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="1ecb9-142">Altre informazioni e risorse</span><span class="sxs-lookup"><span data-stu-id="1ecb9-142">Further reading and resources</span></span>

* [<span data-ttu-id="1ecb9-143">Delegati</span><span class="sxs-lookup"><span data-stu-id="1ecb9-143">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="1ecb9-144">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="1ecb9-144">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="1ecb9-145">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="1ecb9-145">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
