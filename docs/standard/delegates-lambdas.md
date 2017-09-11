---
title: Delegati e lambda
description: "Informazioni sul modo in cui i delegati definiscono un tipo, che specifica una firma del metodo particolare, che può essere chiamato direttamente o passato a un altro metodo e chiamato."
keywords: .NET, .NET Core
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.translationtype: HT
ms.sourcegitcommit: ef6d1bf9a7153f7adf635d13b4dcfb7647ed2e33
ms.openlocfilehash: d04a158db4f97a0e37f8a92149a3f237ee2e5434
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---

# <a name="delegates-and-lambdas"></a><span data-ttu-id="5f031-104">Delegati e lambda</span><span class="sxs-lookup"><span data-stu-id="5f031-104">Delegates and lambdas</span></span>

<span data-ttu-id="5f031-105">I delegati definiscono un tipo che specifica una firma di metodo specifica.</span><span class="sxs-lookup"><span data-stu-id="5f031-105">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="5f031-106">Un metodo (statico o istanza) che soddisfa questa firma può essere assegnato a una variabile del tipo, quindi chiamato direttamente (con gli argomenti appropriati) o passato come argomento a un altro metodo e quindi chiamato.</span><span class="sxs-lookup"><span data-stu-id="5f031-106">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="5f031-107">L'esempio seguente mostra l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="5f031-107">The following example demonstrates delegate use.</span></span>

```csharp
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

*   <span data-ttu-id="5f031-108">Nella riga 4 viene creato un tipo delegato di una determinata firma, in questo caso un metodo che accetta un parametro di stringa e quindi restituisce un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="5f031-108">On line 4 we create a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
*   <span data-ttu-id="5f031-109">Nella riga 6 viene definita l'implementazione del delegato specificando un metodo con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="5f031-109">On line 6, we define the implementation of the delegate by providing a method that has the exact same signature.</span></span>
*   <span data-ttu-id="5f031-110">Nella riga 13 il metodo viene assegnato a un tipo conforme al delegato `Reverse`.</span><span class="sxs-lookup"><span data-stu-id="5f031-110">On line 13, the method is assigned to a type that conforms to the `Reverse` delegate.</span></span>
*   <span data-ttu-id="5f031-111">Infine, nella riga 15 viene chiamato il delegato passando una stringa da invertire.</span><span class="sxs-lookup"><span data-stu-id="5f031-111">Finally, on line 15 we invoke the delegate passing a string to be reversed.</span></span>

<span data-ttu-id="5f031-112">Per semplificare il processo di sviluppo, .NET include un set di tipi di delegato che i programmatori possono riutilizzare senza dover creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="5f031-112">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="5f031-113">I tipi sono `Func<>`, `Action<>` e `Predicate<>` e possono essere usati in posizioni diverse all'interno delle API .NET senza dover definire nuovi tipi di delegato.</span><span class="sxs-lookup"><span data-stu-id="5f031-113">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="5f031-114">Le differenze tra i tre tipi sono evidenti nelle firme e riguardano principalmente la modalità di utilizzo prevista:</span><span class="sxs-lookup"><span data-stu-id="5f031-114">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

*   <span data-ttu-id="5f031-115">`Action<>` viene usato quando è necessario eseguire un'azione usando gli argomenti del delegato.</span><span class="sxs-lookup"><span data-stu-id="5f031-115">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
*   <span data-ttu-id="5f031-116">`Func<>` viene in genere usato in presenza di una trasformazione, ovvero quando è necessario trasformare gli argomenti del delegato in un risultato diverso.</span><span class="sxs-lookup"><span data-stu-id="5f031-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="5f031-117">Le proiezioni sono un esempio tipico.</span><span class="sxs-lookup"><span data-stu-id="5f031-117">Projections are a prime example of this.</span></span>
*   <span data-ttu-id="5f031-118">`Predicate<>` viene usato quando è necessario determinare se l'argomento soddisfa la condizione del delegato.</span><span class="sxs-lookup"><span data-stu-id="5f031-118">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="5f031-119">Può essere scritto anche come `Func<T, bool>`.</span><span class="sxs-lookup"><span data-stu-id="5f031-119">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="5f031-120">L'esempio precedente può essere ora riscritto usando il delegato `Func<>` anziché un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f031-120">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="5f031-121">Il programma continuerà a essere eseguito nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="5f031-121">The program will continue running exactly the same.</span></span>

```csharp
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

<span data-ttu-id="5f031-122">In questo esempio semplice, la presenza di un metodo definito all'esterno del metodo Main() non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="5f031-122">For this simple example, having a method defined outside of the Main() method seems a bit superfluous.</span></span> <span data-ttu-id="5f031-123">Per questa ragione è stato introdotto in .NET Framework 2.0 il concetto di **delegati anonimi**.</span><span class="sxs-lookup"><span data-stu-id="5f031-123">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="5f031-124">I delegati anonimi consentono di creare delegati "inline" senza dover specificare tipi o metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5f031-124">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="5f031-125">Sarà sufficiente incorporare la definizione del delegato dove necessario.</span><span class="sxs-lookup"><span data-stu-id="5f031-125">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="5f031-126">In questo esempio il delegato anonimo viene configurato e usato per visualizzare un elenco dei soli numeri pari che vengono quindi stampati nella console.</span><span class="sxs-lookup"><span data-stu-id="5f031-126">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

```csharp
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
      delegate(int no)
      {
          return (no%2 == 0);
      }
    );

    foreach (var item in result)
    {
        Console.WriteLine(item);
    }
  }
}
```

<span data-ttu-id="5f031-127">Si notino le righe evidenziate.</span><span class="sxs-lookup"><span data-stu-id="5f031-127">Notice the highlighted lines.</span></span> <span data-ttu-id="5f031-128">È possibile osservare che il corpo del delegato è costituito da un set di espressioni, come qualsiasi altro delegato.</span><span class="sxs-lookup"><span data-stu-id="5f031-128">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="5f031-129">Ma anziché essere una definizione separata, il delegato è stato inserito _appositamente_ nella chiamata al metodo `FindAll()` del tipo `List<T>`.</span><span class="sxs-lookup"><span data-stu-id="5f031-129">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the `FindAll()` method of the `List<T>` type.</span></span>

<span data-ttu-id="5f031-130">Anche con questo approccio, tuttavia, rimane una parte considerevole di codice che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="5f031-130">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="5f031-131">A tale scopo, vengono usate le **espressioni lambda**.</span><span class="sxs-lookup"><span data-stu-id="5f031-131">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="5f031-132">Le espressioni lambda, chiamate anche "lambda", sono state usate per la prima volta in C# 3.0 come uno dei componenti fondamentali di Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="5f031-132">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="5f031-133">Si tratta semplicemente una sintassi più pratica per l'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="5f031-133">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="5f031-134">Dichiarano una firma e il corpo di un metodo senza avere una propria identità formale, a meno che non vengano assegnate a un delegato.</span><span class="sxs-lookup"><span data-stu-id="5f031-134">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="5f031-135">A differenza dei delegati, possono essere assegnate direttamente come parte sinistra della registrazione eventi o in diverse clausole e metodi Linq.</span><span class="sxs-lookup"><span data-stu-id="5f031-135">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various Linq clauses and methods.</span></span>

<span data-ttu-id="5f031-136">Poiché un'espressione lambda è soltanto un modo diverso di specificare un delegato, è possibile riscrivere l'esempio precedente per usare un'espressione lambda anziché un delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="5f031-136">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
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

<span data-ttu-id="5f031-137">Nelle righe evidenziate è possibile osservare l'aspetto di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="5f031-137">If you take a look at the highlighted lines, you can see how a lambda expression looks like.</span></span> <span data-ttu-id="5f031-138">Anche in questo caso, si tratta soltanto di una sintassi **molto** pratica per l'uso di delegati con un funzionamento simile a quello del delegato anonimo.</span><span class="sxs-lookup"><span data-stu-id="5f031-138">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="5f031-139">Le lambda sono semplicemente delegati, ovvero possono essere usate come gestori di eventi come mostra il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5f031-139">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

## <a name="further-reading-and-resources"></a><span data-ttu-id="5f031-140">Altre informazioni e risorse</span><span class="sxs-lookup"><span data-stu-id="5f031-140">Further reading and resources</span></span>

*   [<span data-ttu-id="5f031-141">Delegati</span><span class="sxs-lookup"><span data-stu-id="5f031-141">Delegates</span></span>](https://msdn.microsoft.com/library/ms173171.aspx)
*   [<span data-ttu-id="5f031-142">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="5f031-142">Anonymous Functions</span></span>](https://msdn.microsoft.com/library/bb882516.aspx)
*   [<span data-ttu-id="5f031-143">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="5f031-143">Lambda expressions</span></span>](https://msdn.microsoft.com/library/bb397687.aspx)

