---
title: Iterators
description: Informazioni su come usare gli iteratori C# predefiniti e come creare metodi iteratori personalizzati.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: efa755c2243c18fb51b653abccb2bfc702bbc055
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507377"
---
# <a name="iterators"></a><span data-ttu-id="49b94-103">Iterators</span><span class="sxs-lookup"><span data-stu-id="49b94-103">Iterators</span></span>

<span data-ttu-id="49b94-104">Quasi tutti i programmi che vengono scritti avranno la necessità di eseguire un'iterazione in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49b94-104">Almost every program you write will have some need to iterate over a collection.</span></span> <span data-ttu-id="49b94-105">Si scriverà il codice che esamina ogni elemento in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49b94-105">You'll write code that examines every item in a collection.</span></span>

<span data-ttu-id="49b94-106">Si creeranno anche metodi iteratori che sono metodi che producono un iteratore (ovvero un oggetto che attraversa un contenitore, in particolare gli elenchi) per gli elementi di tale classe.</span><span class="sxs-lookup"><span data-stu-id="49b94-106">You'll also create iterator methods which are methods that produces an iterator (which is an object that traverses a container, particularly lists) for the elements of that class.</span></span> <span data-ttu-id="49b94-107">Essi possono essere usati per le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="49b94-107">These can be used for:</span></span>

+ <span data-ttu-id="49b94-108">Esecuzione di un'azione su ogni elemento in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49b94-108">Performing an action on each item in a collection.</span></span>
+ <span data-ttu-id="49b94-109">Enumerazione di una raccolta personalizzata.</span><span class="sxs-lookup"><span data-stu-id="49b94-109">Enumerating a custom collection.</span></span>
+ <span data-ttu-id="49b94-110">Estensione in [LINQ](linq/index.md) o in altre librerie.</span><span class="sxs-lookup"><span data-stu-id="49b94-110">Extending [LINQ](linq/index.md) or other libraries.</span></span>
+ <span data-ttu-id="49b94-111">Creazione di una pipeline di dati dove i dati fluiscono in modo efficace tramite i metodi iteratori.</span><span class="sxs-lookup"><span data-stu-id="49b94-111">Creating a data pipeline where data flows efficiently through iterator methods.</span></span>

<span data-ttu-id="49b94-112">Il linguaggio C# offre funzionalità per entrambi gli scenari.</span><span class="sxs-lookup"><span data-stu-id="49b94-112">The C# language provides features for both these scenarios.</span></span> <span data-ttu-id="49b94-113">In questo articolo viene offerta una panoramica di tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="49b94-113">This article provides an overview of those features.</span></span>

<span data-ttu-id="49b94-114">Questa esercitazione prevede diversi passaggi.</span><span class="sxs-lookup"><span data-stu-id="49b94-114">This tutorial has multiple steps.</span></span> <span data-ttu-id="49b94-115">Dopo ogni passaggio, è possibile eseguire l'applicazione e verificare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="49b94-115">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="49b94-116">È anche possibile [visualizzare o scaricare l'esempio completato](https://github.com/dotnet/samples/blob/master/csharp/iterators) per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="49b94-116">You can also [view or download the completed sample](https://github.com/dotnet/samples/blob/master/csharp/iterators) for this topic.</span></span> <span data-ttu-id="49b94-117">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="49b94-117">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="iterating-with-foreach"></a><span data-ttu-id="49b94-118">Iterazione con foreach</span><span class="sxs-lookup"><span data-stu-id="49b94-118">Iterating with foreach</span></span>

<span data-ttu-id="49b94-119">L'enumerazione di una raccolta è semplice: la parola chiave `foreach` enumera una raccolta eseguendo l'istruzione incorporata una volta per ogni elemento nella raccolta:</span><span class="sxs-lookup"><span data-stu-id="49b94-119">Enumerating a collection is simple: The `foreach` keyword enumerates a collection, executing the embedded statement once for each element in the collection:</span></span>

```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="49b94-120">Questo è tutto.</span><span class="sxs-lookup"><span data-stu-id="49b94-120">That's all there is to it.</span></span> <span data-ttu-id="49b94-121">Per eseguire l'iterazione in tutto il contenuto di una raccolta, è sufficiente l'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="49b94-121">To iterate over all the contents of a collection, the `foreach` statement is all you need.</span></span> <span data-ttu-id="49b94-122">L'istruzione `foreach` non è tuttavia magica.</span><span class="sxs-lookup"><span data-stu-id="49b94-122">The `foreach` statement isn't magic, though.</span></span> <span data-ttu-id="49b94-123">Si basa su due interfacce generiche definite nella libreria di base di .NET per generare il codice necessario per eseguire l'iterazione di una raccolta: `IEnumerable<T>` e `IEnumerator<T>`.</span><span class="sxs-lookup"><span data-stu-id="49b94-123">It relies on two generic interfaces defined in the .NET core library in order to generate the code necessary to iterate a collection: `IEnumerable<T>` and `IEnumerator<T>`.</span></span> <span data-ttu-id="49b94-124">Questo meccanismo è illustrato più dettagliatamente nel seguito di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="49b94-124">This mechanism is explained in more detail below.</span></span>

<span data-ttu-id="49b94-125">Queste due interfacce dispongono anche di controparti non generiche: `IEnumerable` e `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="49b94-125">Both of these interfaces also have non-generic counterparts: `IEnumerable` and `IEnumerator`.</span></span> <span data-ttu-id="49b94-126">Le versioni [generic](programming-guide/generics/index.md) sono preferite per il codice moderno.</span><span class="sxs-lookup"><span data-stu-id="49b94-126">The [generic](programming-guide/generics/index.md) versions are preferred for modern code.</span></span>

## <a name="enumeration-sources-with-iterator-methods"></a><span data-ttu-id="49b94-127">Origini di enumerazione con metodi iteratori</span><span class="sxs-lookup"><span data-stu-id="49b94-127">Enumeration sources with iterator methods</span></span>

<span data-ttu-id="49b94-128">Un'altra eccezionale funzionalità del linguaggio C# consente di creare metodi che creano un'origine per un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="49b94-128">Another great feature of the C# language enables you to build methods that create a source for an enumeration.</span></span> <span data-ttu-id="49b94-129">Essi sono denominati *metodi iteratori*.</span><span class="sxs-lookup"><span data-stu-id="49b94-129">These are referred to as *iterator methods*.</span></span> <span data-ttu-id="49b94-130">Un metodo iteratore definisce come generare gli oggetti in una sequenza quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="49b94-130">An iterator method defines how to generate the objects in a sequence when requested.</span></span> <span data-ttu-id="49b94-131">Usare le parole chiave contestuali `yield return` per definire un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="49b94-131">You use the `yield return` contextual keywords to define an iterator method.</span></span>

<span data-ttu-id="49b94-132">È possibile scrivere questo metodo per produrre la sequenza di numeri interi da 0 a 9:</span><span class="sxs-lookup"><span data-stu-id="49b94-132">You could write this method to produce the sequence of integers from 0 through 9:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

<span data-ttu-id="49b94-133">Il codice sopra riportato indica istruzioni `yield return` distinte per evidenziare che è possibile usare più istruzioni `yield return` discrete in un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="49b94-133">The code above shows distinct `yield return` statements to highlight the fact that you can use multiple discrete `yield return` statements in an iterator method.</span></span>
<span data-ttu-id="49b94-134">È possibile (come capita spesso) usare altri costrutti di linguaggio per semplificare il codice di un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="49b94-134">You can (and often do) use other language constructs to simplify the code of an iterator method.</span></span> <span data-ttu-id="49b94-135">La definizione di metodo seguente produce la stessa identica sequenza di numeri:</span><span class="sxs-lookup"><span data-stu-id="49b94-135">The method definition below produces the exact same sequence of numbers:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;
}
```

<span data-ttu-id="49b94-136">Non è necessario scegliere l'uno o l'altro.</span><span class="sxs-lookup"><span data-stu-id="49b94-136">You don't have to decide one or the other.</span></span> <span data-ttu-id="49b94-137">È possibile specificare qualsiasi numero di istruzioni `yield return` necessarie per soddisfare le esigenze del metodo:</span><span class="sxs-lookup"><span data-stu-id="49b94-137">You can have as many `yield return` statements as necessary to meet the needs of your method:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    index = 100;
    while (index < 110)
        yield return index++;
}
```

<span data-ttu-id="49b94-138">Questa è la sintassi di base.</span><span class="sxs-lookup"><span data-stu-id="49b94-138">That's the basic syntax.</span></span> <span data-ttu-id="49b94-139">Si consideri un esempio reale in cui si vuole scrivere un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="49b94-139">Let's consider a real world example where you would write an iterator method.</span></span> <span data-ttu-id="49b94-140">Si supponga di lavorare su un progetto IoT e che i sensori dispositivo generino un flusso di dati molto grande.</span><span class="sxs-lookup"><span data-stu-id="49b94-140">Imagine you're on an IoT project and the device sensors generate a very large stream of data.</span></span> <span data-ttu-id="49b94-141">Per ottenere un'idea dei dati, è possibile scrivere un metodo che campioni ogni elemento dati n.</span><span class="sxs-lookup"><span data-stu-id="49b94-141">To get a feel for the data, you might write a method that samples every Nth data element.</span></span> <span data-ttu-id="49b94-142">Questo piccolo metodo iteratore serve allo scopo:</span><span class="sxs-lookup"><span data-stu-id="49b94-142">This small iterator method does the trick:</span></span>

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

<span data-ttu-id="49b94-143">I metodi iteratori presentano un'importante restrizione: non è possibile avere sia un'istruzione `return` che un'istruzione `yield return` nello stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="49b94-143">There is one important restriction on iterator methods: you can't have both a `return` statement and a `yield return` statement in the same method.</span></span> <span data-ttu-id="49b94-144">Il codice seguente non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="49b94-144">The following will not compile:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    // generates a compile time error:
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;
}
```

<span data-ttu-id="49b94-145">Questa restrizione non costituisce in genere un problema.</span><span class="sxs-lookup"><span data-stu-id="49b94-145">This restriction normally isn't a problem.</span></span> <span data-ttu-id="49b94-146">È possibile scegliere di usare `yield return` in tutto il metodo o di separare il metodo originale in più metodi, alcuni con l'uso di `return` e altri con l'uso di `yield return`.</span><span class="sxs-lookup"><span data-stu-id="49b94-146">You have a choice of either using `yield return` throughout the method, or separating the original method into multiple methods, some using `return`, and some using `yield return`.</span></span>

<span data-ttu-id="49b94-147">È possibile modificare leggermente l'ultimo metodo in modo da usare `yield return` ovunque:</span><span class="sxs-lookup"><span data-stu-id="49b94-147">You can modify the last method slightly to use `yield return` everywhere:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```

<span data-ttu-id="49b94-148">In alcuni casi, la risposta giusta è la suddivisione di un metodo iteratore in due metodi diversi:</span><span class="sxs-lookup"><span data-stu-id="49b94-148">Sometimes, the right answer is to split an iterator method into two different methods.</span></span> <span data-ttu-id="49b94-149">uno che usa `return` e un altro che usa `yield return`.</span><span class="sxs-lookup"><span data-stu-id="49b94-149">One that uses `return`, and a second that uses `yield return`.</span></span> <span data-ttu-id="49b94-150">Si consideri una situazione in cui si vuole restituire una raccolta vuota o i primi 5 numeri dispari, in base a un argomento booleano.</span><span class="sxs-lookup"><span data-stu-id="49b94-150">Consider a situation where you might want to return an empty collection, or the first 5 odd numbers, based on a boolean argument.</span></span> <span data-ttu-id="49b94-151">Ciò può essere scritto con i due metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="49b94-151">You could write that as these two methods:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index < 10)
    {
        if (index % 2 == 1)
            yield return index;
        index++;
    }
}
```

<span data-ttu-id="49b94-152">Esaminare i metodi descritti precedentemente.</span><span class="sxs-lookup"><span data-stu-id="49b94-152">Look at the methods above.</span></span> <span data-ttu-id="49b94-153">Il primo usa l'istruzione `return` standard per restituire una raccolta vuota o l'iteratore creato dal secondo metodo.</span><span class="sxs-lookup"><span data-stu-id="49b94-153">The first uses the standard `return` statement to return either an empty collection, or the iterator created by the second method.</span></span> <span data-ttu-id="49b94-154">Il secondo metodo usa l'istruzione `yield return` per creare la sequenza richiesta.</span><span class="sxs-lookup"><span data-stu-id="49b94-154">The second method uses the `yield return` statement to create the requested sequence.</span></span>

## <a name="deeper-dive-into-foreach"></a><span data-ttu-id="49b94-155">Approfondimento di `foreach`</span><span class="sxs-lookup"><span data-stu-id="49b94-155">Deeper Dive into `foreach`</span></span>

<span data-ttu-id="49b94-156">L'istruzione `foreach` si espande in un termine standard che usa le interfacce `IEnumerable<T>` e `IEnumerator<T>` per eseguire l'iterazione tra tutti gli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49b94-156">The `foreach` statement expands into a standard idiom that uses the `IEnumerable<T>` and `IEnumerator<T>` interfaces to iterate across all elements of a collection.</span></span> <span data-ttu-id="49b94-157">Riduce al minimo gli errori commessi dagli sviluppatori a causa di una gestione non corretta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="49b94-157">It also  minimizes errors developers make by not properly managing resources.</span></span>

<span data-ttu-id="49b94-158">Il compilatore traduce il ciclo `foreach` illustrato nel primo esempio in un risultato simile a questo costrutto:</span><span class="sxs-lookup"><span data-stu-id="49b94-158">The compiler translates the `foreach` loop shown in the first example into something similar to this construct:</span></span>

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="49b94-159">Il costrutto sopra rappresenta il codice generato dal compilatore C# a partire dalla versione 5 e successive.</span><span class="sxs-lookup"><span data-stu-id="49b94-159">The construct above represents the code generated by the C# compiler as of version 5 and above.</span></span> <span data-ttu-id="49b94-160">Prima della versione 5, la variabile `item` aveva un ambito diverso:</span><span class="sxs-lookup"><span data-stu-id="49b94-160">Prior to version 5, the `item` variable had a different scope:</span></span>

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="49b94-161">La modifica è stata apportata perché il comportamento precedente avrebbe potuto causare bug gravi e difficili da diagnosticare relativi alle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="49b94-161">This was changed because the earlier behavior could lead to subtle and hard to diagnose bugs involving lambda expressions.</span></span> <span data-ttu-id="49b94-162">Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="49b94-162">For more information about lambda expressions, see [Lambda expressions](./programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="49b94-163">Il codice esatto generato dal compilatore è leggermente più complesso e gestisce situazioni in cui l'oggetto restituito da `GetEnumerator()` implementa l'interfaccia `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="49b94-163">The exact code generated by the compiler is somewhat more complicated, and handles situations where the object returned by `GetEnumerator()` implements the `IDisposable` interface.</span></span> <span data-ttu-id="49b94-164">L'espansione completa genera codice più simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49b94-164">The full expansion generates code more like this:</span></span>

```csharp
{
    var enumerator = collection.GetEnumerator();
    try
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally
    {
        // dispose of enumerator.
    }
}
```

<span data-ttu-id="49b94-165">Il modo in cui l'enumeratore viene eliminato dipende dalle caratteristiche del tipo di `enumerator`.</span><span class="sxs-lookup"><span data-stu-id="49b94-165">The manner in which the enumerator is disposed of depends on the characteristics of the type of `enumerator`.</span></span> <span data-ttu-id="49b94-166">Nel caso generale, la clausola `finally` si espande a:</span><span class="sxs-lookup"><span data-stu-id="49b94-166">In the general case, the `finally` clause expands to:</span></span>

```csharp
finally
{
   (enumerator as IDisposable)?.Dispose();
}
```

<span data-ttu-id="49b94-167">Tuttavia, se il tipo di `enumerator` è un tipo sealed e non esiste alcuna conversione implicita dal tipo di `enumerator` a `IDisposable`, la clausola `finally` si espande in un blocco vuoto:</span><span class="sxs-lookup"><span data-stu-id="49b94-167">However, if the type of `enumerator` is a sealed type and there is no implicit conversion from the type of `enumerator` to `IDisposable`, the `finally` clause expands to an empty block:</span></span>

```csharp
finally
{
}
```

<span data-ttu-id="49b94-168">Se esiste una conversione implicita dal tipo di `enumerator` a `IDisposable` e `enumerator` è un tipo di valore non nullable, la `finally` si clausola espande a:</span><span class="sxs-lookup"><span data-stu-id="49b94-168">If there is an implicit conversion from the type of `enumerator` to `IDisposable`, and `enumerator` is a non-nullable value type, the `finally` clause expands to:</span></span>

```csharp
finally
{
   ((IDisposable)enumerator).Dispose();
}
```

<span data-ttu-id="49b94-169">Fortunatamente, non è necessario ricordare tutti questi dettagli.</span><span class="sxs-lookup"><span data-stu-id="49b94-169">Thankfully, you don't need to remember all these details.</span></span> <span data-ttu-id="49b94-170">L'istruzione `foreach` gestisce tutte queste sfumature.</span><span class="sxs-lookup"><span data-stu-id="49b94-170">The `foreach` statement handles all those nuances for you.</span></span> <span data-ttu-id="49b94-171">Il compilatore genererà il codice corretto per tutti questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="49b94-171">The compiler will generate the correct code for any of these constructs.</span></span>
