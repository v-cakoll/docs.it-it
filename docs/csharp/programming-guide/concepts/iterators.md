---
title: Eseguire un'iterazione sulle raccolte in C#
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: aceedd11466c75cedad3c67224c3a5595b4cabfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626270"
---
# <a name="iterators-c"></a><span data-ttu-id="c27e0-102">Iteratori (C#)</span><span class="sxs-lookup"><span data-stu-id="c27e0-102">Iterators (C#)</span></span>

<span data-ttu-id="c27e0-103">Un *iteratore* può essere usato per scorrere le raccolte come gli elenchi e le matrici.</span><span class="sxs-lookup"><span data-stu-id="c27e0-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="c27e0-104">Un metodo iteratore o funzione di accesso `get` esegue un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c27e0-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="c27e0-105">Un iteratore usa l'istruzione [yield return](../../language-reference/keywords/yield.md) per restituire un elemento per volta.</span><span class="sxs-lookup"><span data-stu-id="c27e0-105">An iterator method uses the [yield return](../../language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="c27e0-106">Quando viene raggiunta un'istruzione `yield return`, la posizione corrente nel codice viene memorizzata.</span><span class="sxs-lookup"><span data-stu-id="c27e0-106">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="c27e0-107">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-107">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="c27e0-108">Si usa un metodo iteratore dal codice client tramite un'istruzione [foreach](../../language-reference/keywords/foreach-in.md) o una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="c27e0-108">You consume an iterator from client code by using a [foreach](../../language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>

<span data-ttu-id="c27e0-109">Nell'esempio seguente, la prima iterazione del ciclo `foreach` fa procedere l'esecuzione nel metodo iteratore `SomeNumbers` fino al raggiungimento della prima istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-109">In the following example, the first iteration of the `foreach` loop causes execution to proceed in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="c27e0-110">Questa iterazione restituisce un valore pari a 3 e viene mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="c27e0-111">All'iterazione successiva del ciclo, l'esecuzione nel metodo iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="c27e0-112">Questa iterazione restituisce un valore pari a 5 e viene ancora mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="c27e0-113">Il ciclo termina quando si raggiunge la fine del metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-113">The loop completes when the end of the iterator method is reached.</span></span>

```csharp
static void Main()
{
    foreach (int number in SomeNumbers())
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 3 5 8
    Console.ReadKey();
}

public static System.Collections.IEnumerable SomeNumbers()
{
    yield return 3;
    yield return 5;
    yield return 8;
}
```

<span data-ttu-id="c27e0-114">Il tipo restituito di un metodo iteratore o di una funzione di accesso `get` può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="c27e0-115">È possibile utilizzare un'istruzione `yield break` per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="c27e0-115">You can use a `yield break` statement to end the iteration.</span></span>

> [!NOTE]
> <span data-ttu-id="c27e0-116">Per tutti gli esempi in questo argomento, ad eccezione dell'esempio di iteratore semplice, includere le istruzioni [using](../../language-reference/keywords/using-directive.md) per gli spazi dei nomi `System.Collections` e `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-116">For all examples in this topic except the Simple Iterator example, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="simple-iterator"></a><span data-ttu-id="c27e0-117">Iteratore semplice</span><span class="sxs-lookup"><span data-stu-id="c27e0-117">Simple Iterator</span></span>

<span data-ttu-id="c27e0-118">L'esempio seguente contiene un'istruzione `yield return` singola all'interno di un ciclo [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="c27e0-118">The following example has a single `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="c27e0-119">In `Main` ogni iterazione del corpo dell'istruzione `foreach` crea una chiamata alla funzione iteratore, che procede all'istruzione `yield return` successiva.</span><span class="sxs-lookup"><span data-stu-id="c27e0-119">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>

```csharp
static void Main()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 6 8 10 12 14 16 18
    Console.ReadKey();
}

public static System.Collections.Generic.IEnumerable<int>
    EvenSequence(int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (int number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="creating-a-collection-class"></a><span data-ttu-id="c27e0-120">Creazione di una classe Collection</span><span class="sxs-lookup"><span data-stu-id="c27e0-120">Creating a Collection Class</span></span>

<span data-ttu-id="c27e0-121">Nell'esempio seguente la classe `DaysOfTheWeek` implementa l'interfaccia <xref:System.Collections.IEnumerable>, che richiede un metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-121">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="c27e0-122">Il compilatore chiama implicitamente il metodo `GetEnumerator`, che restituisce un <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-122">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="c27e0-123">Il metodo `GetEnumerator` restituisce una stringa alla volta usando l'istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-123">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>

```csharp
static void Main()
{
    DaysOfTheWeek days = new DaysOfTheWeek();

    foreach (string day in days)
    {
        Console.Write(day + " ");
    }
    // Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey();
}

public class DaysOfTheWeek : IEnumerable
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public IEnumerator GetEnumerator()
    {
        for (int index = 0; index < days.Length; index++)
        {
            // Yield each day of the week.
            yield return days[index];
        }
    }
}
```

<span data-ttu-id="c27e0-124">Nell'esempio seguente viene creata una classe `Zoo` che contiene una raccolta di animali.</span><span class="sxs-lookup"><span data-stu-id="c27e0-124">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="c27e0-125">L'istruzione `foreach` che fa riferimento all'istanza della classe (`theZoo`) chiama implicitamente il metodo `GetEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-125">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="c27e0-126">Le istruzioni `foreach` che fanno riferimento alle proprietà `Birds` e `Mammals` usano il metodo iteratore denominato `AnimalsForType`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-126">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

```csharp
static void Main()
{
    Zoo theZoo = new Zoo();

    theZoo.AddMammal("Whale");
    theZoo.AddMammal("Rhinoceros");
    theZoo.AddBird("Penguin");
    theZoo.AddBird("Warbler");

    foreach (string name in theZoo)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros Penguin Warbler

    foreach (string name in theZoo.Birds)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Penguin Warbler

    foreach (string name in theZoo.Mammals)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros

    Console.ReadKey();
}

public class Zoo : IEnumerable
{
    // Private members.
    private List<Animal> animals = new List<Animal>();

    // Public methods.
    public void AddMammal(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });
    }

    public void AddBird(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });
    }

    public IEnumerator GetEnumerator()
    {
        foreach (Animal theAnimal in animals)
        {
            yield return theAnimal.Name;
        }
    }

    // Public members.
    public IEnumerable Mammals
    {
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }
    }

    public IEnumerable Birds
    {
        get { return AnimalsForType(Animal.TypeEnum.Bird); }
    }

    // Private methods.
    private IEnumerable AnimalsForType(Animal.TypeEnum type)
    {
        foreach (Animal theAnimal in animals)
        {
            if (theAnimal.Type == type)
            {
                yield return theAnimal.Name;
            }
        }
    }

    // Private class.
    private class Animal
    {
        public enum TypeEnum { Bird, Mammal }

        public string Name { get; set; }
        public TypeEnum Type { get; set; }
    }
}
```

## <a name="using-iterators-with-a-generic-list"></a><span data-ttu-id="c27e0-127">Uso di iteratori con un elenco generico</span><span class="sxs-lookup"><span data-stu-id="c27e0-127">Using Iterators with a Generic List</span></span>

<span data-ttu-id="c27e0-128">Nell'esempio seguente la classe generica <xref:System.Collections.Generic.Stack%601> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-128">In the following example, the <xref:System.Collections.Generic.Stack%601> generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="c27e0-129">Il metodo <xref:System.Collections.Generic.Stack%601.Push%2A> assegna valori a una matrice di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-129">The <xref:System.Collections.Generic.Stack%601.Push%2A> method assigns values to an array of type `T`.</span></span> <span data-ttu-id="c27e0-130">Il metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> restituisce i valori della matrice tramite l'istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-130">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>

<span data-ttu-id="c27e0-131">Oltre al metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> generico, è necessario implementare anche il metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A> non generico,</span><span class="sxs-lookup"><span data-stu-id="c27e0-131">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="c27e0-132">poiché <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-132">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="c27e0-133">L'implementazione non generica rinvia all'implementazione generica.</span><span class="sxs-lookup"><span data-stu-id="c27e0-133">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="c27e0-134">L'esempio usa iteratori denominati per supportare diversi modi di iterazione nella stessa raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="c27e0-134">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="c27e0-135">Questi iteratori denominati sono le proprietà `TopToBottom` e `BottomToTop` e il metodo `TopN`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-135">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="c27e0-136">La proprietà `BottomToTop` usa un iteratore in una funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-136">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>

```csharp
static void Main()
{
    Stack<int> theStack = new Stack<int>();

    //  Add items to the stack.
    for (int number = 0; number <= 9; number++)
    {
        theStack.Push(number);
    }

    // Retrieve items from the stack.
    // foreach is allowed because theStack implements IEnumerable<int>.
    foreach (int number in theStack)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    // foreach is allowed, because theStack.TopToBottom returns IEnumerable(Of Integer).
    foreach (int number in theStack.TopToBottom)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    foreach (int number in theStack.BottomToTop)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 0 1 2 3 4 5 6 7 8 9

    foreach (int number in theStack.TopN(7))
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3

    Console.ReadKey();
}

public class Stack<T> : IEnumerable<T>
{
    private T[] values = new T[100];
    private int top = 0;

    public void Push(T t)
    {
        values[top] = t;
        top++;
    }
    public T Pop()
    {
        top--;
        return values[top];
    }

    // This method implements the GetEnumerator method. It allows
    // an instance of the class to be used in a foreach statement.
    public IEnumerator<T> GetEnumerator()
    {
        for (int index = top - 1; index >= 0; index--)
        {
            yield return values[index];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }

    public IEnumerable<T> TopToBottom
    {
        get { return this; }
    }

    public IEnumerable<T> BottomToTop
    {
        get
        {
            for (int index = 0; index <= top - 1; index++)
            {
                yield return values[index];
            }
        }
    }

    public IEnumerable<T> TopN(int itemsFromTop)
    {
        // Return less than itemsFromTop if necessary.
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;

        for (int index = top - 1; index >= startIndex; index--)
        {
            yield return values[index];
        }
    }

}
```

## <a name="syntax-information"></a><span data-ttu-id="c27e0-137">Informazioni sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="c27e0-137">Syntax Information</span></span>

<span data-ttu-id="c27e0-138">Un iteratore può verificarsi come metodo o funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-138">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="c27e0-139">Un iteratore non può verificarsi in un evento, in un costruttore di istanze, in un costruttore statico o in un finalizzatore statico.</span><span class="sxs-lookup"><span data-stu-id="c27e0-139">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>

<span data-ttu-id="c27e0-140">Deve esistere una conversione implicita `yield return` dal tipo di `IEnumerable<T>` espressione nell'istruzione all'argomento di tipo per l'oggetto restituito dall'iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-140">An implicit conversion must exist from the expression type in the `yield return` statement to the type argument for the `IEnumerable<T>` returned by the iterator.</span></span>

<span data-ttu-id="c27e0-141">In C# un metodo iteratore non può avere parametri `in`, `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-141">In C#, an iterator method cannot have any `in`, `ref`, or `out` parameters.</span></span>

<span data-ttu-id="c27e0-142">Nel linguaggio `yield` C, non è una parola riservata e `return` `break` ha un significato speciale solo quando viene usata prima di una parola chiave o .</span><span class="sxs-lookup"><span data-stu-id="c27e0-142">In C#, `yield` is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="c27e0-143">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="c27e0-143">Technical Implementation</span></span>

<span data-ttu-id="c27e0-144">Anche se si scrive un iteratore come metodo, il compilatore lo traduce in una classe annidata che, in pratica, è una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="c27e0-144">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="c27e0-145">Questa classe tiene traccia della posizione dell'iteratore purché il ciclo `foreach` nel codice client sia continuo.</span><span class="sxs-lookup"><span data-stu-id="c27e0-145">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>

<span data-ttu-id="c27e0-146">Per verificare le operazioni eseguite dal compilatore, è possibile usare lo strumento Ildsam.exe per visualizzare il codice Microsoft Intermediate Language generato per un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-146">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that's generated for an iterator method.</span></span>

<span data-ttu-id="c27e0-147">Quando si crea un iteratore per una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md), non è necessario implementare l'intera interfaccia <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-147">When you create an iterator for a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="c27e0-148">Quando il compilatore rileva l'iteratore, genera automaticamente i metodi `Current`, `MoveNext` e `Dispose` dell'interfaccia <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-148">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="c27e0-149">In ogni iterazione successiva del ciclo `foreach` (o alla chiamata diretta a `IEnumerator.MoveNext`), il corpo di codice iteratore successivo riprende dopo la precedente istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-149">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="c27e0-150">Prosegue quindi fino alla successiva istruzione `yield return` fino a quando non viene raggiunta la fine del corpo dell'iteratore, o fino a quando non viene rilevata un'istruzione `yield break`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-150">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>

<span data-ttu-id="c27e0-151">Gli iteratori non supportano il metodo <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-151">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c27e0-152">Per eseguire di nuovo l'iterazione dall'inizio, è necessario ottenere un nuovo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-152">To reiterate from the start, you must obtain a new iterator.</span></span> <span data-ttu-id="c27e0-153">La chiamata <xref:System.Collections.IEnumerator.Reset%2A> sull'iteratore restituito da un metodo iteratore genera <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="c27e0-153">Calling <xref:System.Collections.IEnumerator.Reset%2A> on the iterator returned by an iterator method throws a <xref:System.NotSupportedException>.</span></span>

<span data-ttu-id="c27e0-154">Per altre informazioni, vedere [Specifiche del linguaggio C#](~/_csharplang/spec/classes.md#iterators).</span><span class="sxs-lookup"><span data-stu-id="c27e0-154">For additional information, see the [C# Language Specification](~/_csharplang/spec/classes.md#iterators).</span></span>

## <a name="use-of-iterators"></a><span data-ttu-id="c27e0-155">Uso degli iteratori</span><span class="sxs-lookup"><span data-stu-id="c27e0-155">Use of Iterators</span></span>

<span data-ttu-id="c27e0-156">Gli iteratori consentono di mantenere la semplicità di un ciclo `foreach` quando è necessario usare codice complesso per popolare una sequenza di elenco.</span><span class="sxs-lookup"><span data-stu-id="c27e0-156">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="c27e0-157">Ciò può risultare utile per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c27e0-157">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="c27e0-158">Modificare la sequenza di elenco dopo la prima iterazione del ciclo `foreach`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-158">Modify the list sequence after the first `foreach` loop iteration.</span></span>

- <span data-ttu-id="c27e0-159">Evitare il caricamento completo di un elenco di grandi dimensioni prima della prima iterazione di un ciclo `foreach`.</span><span class="sxs-lookup"><span data-stu-id="c27e0-159">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="c27e0-160">Un esempio è un'operazione di recupero di paging per caricare un batch di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="c27e0-160">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="c27e0-161">Un altro esempio è il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, che implementa gli iteratori all'interno di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c27e0-161">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>

- <span data-ttu-id="c27e0-162">Incapsulare la generazione dell'elenco nell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="c27e0-162">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="c27e0-163">Nel metodo iteratore è possibile compilare l'elenco e restituire quindi ogni risultato in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="c27e0-163">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="c27e0-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c27e0-164">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="c27e0-165">foreach, in</span><span class="sxs-lookup"><span data-stu-id="c27e0-165">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="c27e0-166">yield</span><span class="sxs-lookup"><span data-stu-id="c27e0-166">yield</span></span>](../../language-reference/keywords/yield.md)
- [<span data-ttu-id="c27e0-167">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="c27e0-167">Using foreach with Arrays</span></span>](../arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="c27e0-168">Generics</span><span class="sxs-lookup"><span data-stu-id="c27e0-168">Generics</span></span>](../generics/index.md)
