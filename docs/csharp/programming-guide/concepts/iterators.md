---
title: Eseguire un'iterazione sulle raccolte in C#
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: 15b77fd11c0ff606119425ec7aae8e7127315e82
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240694"
---
# <a name="iterators-c"></a>Iteratori (C#)

Un *iteratore* può essere usato per scorrere le raccolte come gli elenchi e le matrici.

Un metodo iteratore o funzione di accesso `get` esegue un'iterazione personalizzata su una raccolta. Un iteratore usa l'istruzione [yield return](../../language-reference/keywords/yield.md) per restituire un elemento per volta. Quando viene raggiunta un'istruzione `yield return`, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.

Si usa un metodo iteratore dal codice client tramite un'istruzione [foreach](../../language-reference/keywords/foreach-in.md) o una query LINQ.

Nell'esempio seguente, la prima iterazione del ciclo `foreach` fa procedere l'esecuzione nel metodo iteratore `SomeNumbers` fino al raggiungimento della prima istruzione `yield return`. Questa iterazione restituisce un valore pari a 3 e viene mantenuta la posizione corrente nel metodo iteratore. All'iterazione successiva del ciclo, l'esecuzione nel metodo iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `yield return`. Questa iterazione restituisce un valore pari a 5 e viene ancora mantenuta la posizione corrente nel metodo iteratore. Il ciclo termina quando si raggiunge la fine del metodo iteratore.

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

Il tipo restituito di un metodo iteratore o di una funzione di accesso `get` può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

È possibile utilizzare un'istruzione `yield break` per terminare l'iterazione.

> [!NOTE]
> Per tutti gli esempi in questo argomento, ad eccezione dell'esempio di iteratore semplice, includere le istruzioni [using](../../language-reference/keywords/using-directive.md) per gli spazi dei nomi `System.Collections` e `System.Collections.Generic`.

## <a name="simple-iterator"></a>Iteratore semplice

L'esempio seguente contiene un'istruzione `yield return` singola all'interno di un ciclo [for](../../language-reference/keywords/for.md). In `Main` ogni iterazione del corpo dell'istruzione `foreach` crea una chiamata alla funzione iteratore, che procede all'istruzione `yield return` successiva.

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

## <a name="creating-a-collection-class"></a>Creazione di una classe Collection

Nell'esempio seguente la classe `DaysOfTheWeek` implementa l'interfaccia <xref:System.Collections.IEnumerable>, che richiede un metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Il compilatore chiama implicitamente il metodo `GetEnumerator`, che restituisce un <xref:System.Collections.IEnumerator>.

Il metodo `GetEnumerator` restituisce una stringa alla volta usando l'istruzione `yield return`.

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

Nell'esempio seguente viene creata una classe `Zoo` che contiene una raccolta di animali.

L'istruzione `foreach` che fa riferimento all'istanza della classe (`theZoo`) chiama implicitamente il metodo `GetEnumerator`. Le istruzioni `foreach` che fanno riferimento alle proprietà `Birds` e `Mammals` usano il metodo iteratore denominato `AnimalsForType`.

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

## <a name="using-iterators-with-a-generic-list"></a>Uso di iteratori con un elenco generico

Nell'esempio seguente la classe generica <xref:System.Collections.Generic.Stack%601> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>. Il metodo <xref:System.Collections.Generic.Stack%601.Push%2A> assegna valori a una matrice di tipo `T`. Il metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> restituisce i valori della matrice tramite l'istruzione `yield return`.

Oltre al metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> generico, è necessario implementare anche il metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A> non generico, poiché <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable>. L'implementazione non generica rinvia all'implementazione generica.

L'esempio usa iteratori denominati per supportare diversi modi di iterazione nella stessa raccolta dati. Questi iteratori denominati sono le proprietà `TopToBottom` e `BottomToTop` e il metodo `TopN`.

La proprietà `BottomToTop` usa un iteratore in una funzione di accesso `get`.

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

## <a name="syntax-information"></a>Informazioni sulla sintassi

Un iteratore può verificarsi come metodo o funzione di accesso `get`. Un iteratore non può verificarsi in un evento, in un costruttore di istanze, in un costruttore statico o in un finalizzatore statico.

Una conversione implicita deve esistere dal tipo di espressione nell' `yield return` istruzione all'argomento tipo per l'oggetto `IEnumerable<T>` restituito dall'iteratore.

In C# un metodo iteratore non può avere parametri `in`, `ref` o `out`.

In C#, `yield` non è una parola riservata e ha un significato speciale solo quando viene usata prima di `return` una `break` parola chiave o.

## <a name="technical-implementation"></a>Implementazione tecnica

Anche se si scrive un iteratore come metodo, il compilatore lo traduce in una classe annidata che, in pratica, è una macchina a stati. Questa classe tiene traccia della posizione dell'iteratore purché il ciclo `foreach` nel codice client sia continuo.

Per verificare le operazioni eseguite dal compilatore, è possibile usare lo strumento Ildsam.exe per visualizzare il codice Microsoft Intermediate Language generato per un metodo iteratore.

Quando si crea un iteratore per una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md), non è necessario implementare l'intera interfaccia <xref:System.Collections.IEnumerator>. Quando il compilatore rileva l'iteratore, genera automaticamente i metodi `Current`, `MoveNext` e `Dispose` dell'interfaccia <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

In ogni iterazione successiva del ciclo `foreach` (o alla chiamata diretta a `IEnumerator.MoveNext`), il corpo di codice iteratore successivo riprende dopo la precedente istruzione `yield return`. Prosegue quindi fino alla successiva istruzione `yield return` fino a quando non viene raggiunta la fine del corpo dell'iteratore, o fino a quando non viene rilevata un'istruzione `yield break`.

Gli iteratori non supportano il metodo <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>. Per eseguire di nuovo l'iterazione dall'inizio, è necessario ottenere un nuovo iteratore. La chiamata <xref:System.Collections.IEnumerator.Reset%2A> sull'iteratore restituito da un metodo iteratore genera <xref:System.NotSupportedException>.

Per altre informazioni, vedere [Specifiche del linguaggio C#](~/_csharplang/spec/classes.md#iterators).

## <a name="use-of-iterators"></a>Uso degli iteratori

Gli iteratori consentono di mantenere la semplicità di un ciclo `foreach` quando è necessario usare codice complesso per popolare una sequenza di elenco. Ciò può risultare utile per eseguire le operazioni seguenti:

- Modificare la sequenza di elenco dopo la prima iterazione del ciclo `foreach`.

- Evitare il caricamento completo di un elenco di grandi dimensioni prima della prima iterazione di un ciclo `foreach`. Un esempio è un'operazione di recupero di paging per caricare un batch di righe della tabella. Un altro esempio è il <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> metodo, che implementa gli iteratori in .NET.

- Incapsulare la generazione dell'elenco nell'iteratore. Nel metodo iteratore è possibile compilare l'elenco e restituire quindi ogni risultato in un ciclo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [foreach, in](../../language-reference/keywords/foreach-in.md)
- [yield](../../language-reference/keywords/yield.md)
- [Uso di foreach con matrici](../arrays/using-foreach-with-arrays.md)
- [Generics](../generics/index.md)
