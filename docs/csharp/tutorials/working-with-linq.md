---
title: Uso di LINQ
description: Questa esercitazione illustra come generare sequenze con LINQ, come scrivere i metodi da usare nelle query LINQ e come distinguere le modalità di valutazione eager e lazy.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: 8984fdf0ff26726b6d05e8bee8a9e8ae1c350ea7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345617"
---
# <a name="work-with-language-integrated-query-linq"></a><span data-ttu-id="844be-103">Usare LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="844be-103">Work with Language-Integrated Query (LINQ)</span></span>

## <a name="introduction"></a><span data-ttu-id="844be-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="844be-104">Introduction</span></span>

<span data-ttu-id="844be-105">Questa esercitazione illustra le funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="844be-105">This tutorial teaches you features in .NET Core and the C# language.</span></span> <span data-ttu-id="844be-106">Scoprirai come eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="844be-106">You’ll learn how to:</span></span>

- <span data-ttu-id="844be-107">Generare sequenze con LINQ.</span><span class="sxs-lookup"><span data-stu-id="844be-107">Generate sequences with LINQ.</span></span>
- <span data-ttu-id="844be-108">Scrivere metodi che possono essere usati facilmente nelle query LINQ.</span><span class="sxs-lookup"><span data-stu-id="844be-108">Write methods that can be easily used in LINQ queries.</span></span>
- <span data-ttu-id="844be-109">Distinguere tra valutazione eager e Lazy.</span><span class="sxs-lookup"><span data-stu-id="844be-109">Distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="844be-110">Si apprenderanno queste tecniche creando un'applicazione che illustra una delle abilità di base di un prestigiatore: il [miscuglio faro](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="844be-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="844be-111">In breve, il miscuglio faro è una tecnica che consiste nel tagliare un mazzo di carte esattamente a metà e quindi nel sovrapporre alternativamente le carte delle due metà per ricostruire il mazzo originale.</span><span class="sxs-lookup"><span data-stu-id="844be-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="844be-112">I prestigiatori adottano questa tecnica perché, dopo ogni miscuglio, ciascuna carta si trova in una posizione nota e le carte vengono ordinate in base a uno schema ripetitivo.</span><span class="sxs-lookup"><span data-stu-id="844be-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span>

<span data-ttu-id="844be-113">Ai fini dell'esercitazione, questa tecnica offre un modo scherzoso per illustrare la manipolazione di sequenze di dati.</span><span class="sxs-lookup"><span data-stu-id="844be-113">For your purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="844be-114">L'applicazione da compilare costruisce un mazzo di schede e quindi esegue una sequenza di shuffle, scrivendo ogni volta la sequenza.</span><span class="sxs-lookup"><span data-stu-id="844be-114">The application you'll build constructs a card deck and then performs a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="844be-115">Si confronterà inoltre l'ordine aggiornato con quello originale.</span><span class="sxs-lookup"><span data-stu-id="844be-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="844be-116">Questa esercitazione prevede diversi passaggi.</span><span class="sxs-lookup"><span data-stu-id="844be-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="844be-117">Dopo ogni passaggio, è possibile eseguire l'applicazione e verificare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="844be-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="844be-118">È anche possibile vedere l'[esempio completo](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) disponibile nel repository dotnet/samples su GitHub.</span><span class="sxs-lookup"><span data-stu-id="844be-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="844be-119">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="844be-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="844be-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="844be-120">Prerequisites</span></span>

<span data-ttu-id="844be-121">È necessario configurare il computer per l'esecuzione di .NET core.</span><span class="sxs-lookup"><span data-stu-id="844be-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="844be-122">È possibile trovare le istruzioni di installazione nella pagina di [download di .NET Core](https://dotnet.microsoft.com/download) .</span><span class="sxs-lookup"><span data-stu-id="844be-122">You can find the installation instructions on the [.NET Core Download](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="844be-123">È possibile eseguire questa applicazione in Windows, Ubuntu Linux o OS X oppure in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="844be-123">You can run this application on Windows, Ubuntu Linux, or OS X, or in a Docker container.</span></span> <span data-ttu-id="844be-124">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="844be-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="844be-125">Le descrizioni seguenti usano [Visual Studio Code](https://code.visualstudio.com/) un editor multipiattaforma open source.</span><span class="sxs-lookup"><span data-stu-id="844be-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross-platform editor.</span></span> <span data-ttu-id="844be-126">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="844be-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="844be-127">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="844be-127">Create the Application</span></span>

<span data-ttu-id="844be-128">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="844be-128">The first step is to create a new application.</span></span> <span data-ttu-id="844be-129">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="844be-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="844be-130">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="844be-130">Make that the current directory.</span></span> <span data-ttu-id="844be-131">Digitare il comando `dotnet new console` al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="844be-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="844be-132">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="844be-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="844be-133">Se non si è mai usato C#, [questa esercitazione](console-teleprompter.md) illustra la struttura di un programma C#.</span><span class="sxs-lookup"><span data-stu-id="844be-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="844be-134">È possibile leggerla e tornare qui per ottenere altre informazioni su LINQ.</span><span class="sxs-lookup"><span data-stu-id="844be-134">You can read that and then return here to learn more about LINQ.</span></span>

## <a name="create-the-data-set"></a><span data-ttu-id="844be-135">Creare il set di dati</span><span class="sxs-lookup"><span data-stu-id="844be-135">Create the Data Set</span></span>

<span data-ttu-id="844be-136">Prima di iniziare, verificare che le righe seguenti si trovino all'inizio del file `Program.cs` generato da `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="844be-136">Before you begin, make sure that the following lines are at the top of the `Program.cs` file generated by `dotnet new console`:</span></span>

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="844be-137">Se queste tre righe (istruzioni `using`) non sono all'inizio del file, il programma non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="844be-137">If these three lines (`using` statements) aren't at the top of the file, our program will not compile.</span></span>

<span data-ttu-id="844be-138">Ora che si dispone di tutti i riferimenti necessari, considerare quali elementi costituiscono un mazzo di carte.</span><span class="sxs-lookup"><span data-stu-id="844be-138">Now that you have all of the references that you'll need, consider what constitutes a deck of cards.</span></span> <span data-ttu-id="844be-139">Generalmente un mazzo di carte da gioco ha quattro semi, ognuno dei quali ha tredici valori.</span><span class="sxs-lookup"><span data-stu-id="844be-139">Commonly, a deck of playing cards has four suits, and each suit has thirteen values.</span></span> <span data-ttu-id="844be-140">Normalmente si prenderebbe in considerazione l'idea di creare subito una classe `Card` e popolare una raccolta di oggetti `Card` manualmente.</span><span class="sxs-lookup"><span data-stu-id="844be-140">Normally, you might consider creating a `Card` class right off the bat and populating a collection of `Card` objects by hand.</span></span> <span data-ttu-id="844be-141">Ma con LINQ è possibile creare un mazzo di carte in maniera più concisa.</span><span class="sxs-lookup"><span data-stu-id="844be-141">With LINQ, you can be more concise than the usual way of dealing with creating a deck of cards.</span></span> <span data-ttu-id="844be-142">Invece di creare una classe `Card`, è possibile creare due sequenze che rappresentino rispettivamente i semi e i valori.</span><span class="sxs-lookup"><span data-stu-id="844be-142">Instead of creating a `Card` class, you can create two sequences to represent suits and ranks, respectively.</span></span> <span data-ttu-id="844be-143">Si creerà una coppia molto semplice di [*metodi Iterator*](../iterators.md#enumeration-sources-with-iterator-methods) che genereranno i valori e i semi come interfacce <xref:System.Collections.Generic.IEnumerable%601> di stringhe:</span><span class="sxs-lookup"><span data-stu-id="844be-143">You'll create a really simple pair of [*iterator methods*](../iterators.md#enumeration-sources-with-iterator-methods) that will generate the ranks and suits as <xref:System.Collections.Generic.IEnumerable%601>s of strings:</span></span>

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="844be-144">Inserire questi metodi sotto il metodo `Main` nel file `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="844be-144">Place these underneath the `Main` method in your `Program.cs` file.</span></span> <span data-ttu-id="844be-145">Questi due metodi usano entrambi la sintassi `yield return` per generare una sequenza durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="844be-145">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="844be-146">Il compilatore crea un oggetto che implementa <xref:System.Collections.Generic.IEnumerable%601> e genera la sequenza di stringhe a mano a mano che vengono richieste.</span><span class="sxs-lookup"><span data-stu-id="844be-146">The compiler builds an object that implements <xref:System.Collections.Generic.IEnumerable%601> and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="844be-147">Usare ora questi metodi Iterator per creare il mazzo di carte.</span><span class="sxs-lookup"><span data-stu-id="844be-147">Now, use these iterator methods to create the deck of cards.</span></span> <span data-ttu-id="844be-148">Si inserirà la query LINQ nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="844be-148">You'll place the LINQ query in our `Main` method.</span></span> <span data-ttu-id="844be-149">Ecco come appare:</span><span class="sxs-lookup"><span data-stu-id="844be-149">Here's a look at it:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

<span data-ttu-id="844be-150">Le clausole `from` multiple generano un <xref:System.Linq.Enumerable.SelectMany%2A> che crea una singola sequenza tramite la combinazione di ogni elemento nella prima sequenza con ogni elemento nella seconda.</span><span class="sxs-lookup"><span data-stu-id="844be-150">The multiple `from` clauses produce a <xref:System.Linq.Enumerable.SelectMany%2A>, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="844be-151">L'ordine è importante ai fini di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="844be-151">The order is important for our purposes.</span></span> <span data-ttu-id="844be-152">Il primo elemento nella prima sequenza di origine (semi) viene combinato con ogni elemento della seconda sequenza (valori).</span><span class="sxs-lookup"><span data-stu-id="844be-152">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Ranks).</span></span> <span data-ttu-id="844be-153">Si ottengono così le 13 carte appartenenti al primo seme.</span><span class="sxs-lookup"><span data-stu-id="844be-153">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="844be-154">Il processo viene ripetuto con ogni elemento della prima sequenza, ovvero i semi.</span><span class="sxs-lookup"><span data-stu-id="844be-154">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="844be-155">Il risultato finale è un mazzo di carte ordinato in base ai semi e quindi in base ai valori.</span><span class="sxs-lookup"><span data-stu-id="844be-155">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="844be-156">È importante tenere presente che, sia che si scelga di scrivere la query LINQ nella sintassi di query usata sopra o di usare invece la sintassi del metodo, è sempre possibile passare da un formato di sintassi all'altro.</span><span class="sxs-lookup"><span data-stu-id="844be-156">It's important to keep in mind that whether you choose to write your LINQ in the query syntax used above or use method syntax instead, it's always possible to go from one form of syntax to the other.</span></span> <span data-ttu-id="844be-157">La query riportata sopra, scritta nella sintassi di query, può essere scritta nella sintassi del metodo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="844be-157">The above query written in query syntax can be written in method syntax as:</span></span>

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

<span data-ttu-id="844be-158">Il compilatore converte le istruzioni LINQ scritte con la sintassi di query nella sintassi del metodo equivalente.</span><span class="sxs-lookup"><span data-stu-id="844be-158">The compiler translates LINQ statements written with query syntax into the equivalent method call syntax.</span></span> <span data-ttu-id="844be-159">Pertanto, indipendentemente dalla sintassi scelta, le due versioni della query producono lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="844be-159">Therefore, regardless of your syntax choice, the two versions of the query produce the same result.</span></span> <span data-ttu-id="844be-160">Scegliere la sintassi più adatta per la propria situazione: ad esempio, se si lavora in un team in cui alcuni membri non hanno dimestichezza con la sintassi del metodo, preferire la sintassi di query.</span><span class="sxs-lookup"><span data-stu-id="844be-160">Choose which syntax works best for your situation: for instance, if you're working in a team where some of the members have difficulty with method syntax, try to prefer using query syntax.</span></span>

<span data-ttu-id="844be-161">Andare avanti ed eseguire l'esempio che si è creato finora.</span><span class="sxs-lookup"><span data-stu-id="844be-161">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="844be-162">Verranno visualizzate le 52 carte del mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-162">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="844be-163">Può essere molto utile eseguire questo esempio in un debugger per osservare come vengono eseguiti i metodi `Suits()` e `Ranks()`.</span><span class="sxs-lookup"><span data-stu-id="844be-163">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Ranks()` methods execute.</span></span> <span data-ttu-id="844be-164">È possibile vedere chiaramente che in ogni sequenza ciascuna stringa viene generata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="844be-164">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Una finestra della console con l'app che scrive 52 carte.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulate-the-order"></a><span data-ttu-id="844be-166">Modificare l'ordine</span><span class="sxs-lookup"><span data-stu-id="844be-166">Manipulate the Order</span></span>

<span data-ttu-id="844be-167">A questo punto occorre concentrarsi sul modo in cui si mischieranno le carte nel mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-167">Next, focus on how you're going to shuffle the cards in the deck.</span></span> <span data-ttu-id="844be-168">Il primo passaggio consiste nel tagliare il mazzo in due.</span><span class="sxs-lookup"><span data-stu-id="844be-168">The first step in any good shuffle is to split the deck in two.</span></span> <span data-ttu-id="844be-169">I metodi <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> inclusi nelle API LINQ offrono questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="844be-169">The <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods that are part of the LINQ APIs provide that feature for you.</span></span> <span data-ttu-id="844be-170">Inserirli sotto il ciclo `foreach`:</span><span class="sxs-lookup"><span data-stu-id="844be-170">Place them underneath the `foreach` loop:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

<span data-ttu-id="844be-171">Non esiste tuttavia un metodo per mischiare le carte nella libreria standard, quindi è necessario scriverne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="844be-171">However, there's no shuffle method to take advantage of in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="844be-172">Il metodo che verrà creato illustra diverse tecniche che verranno usate con programmi basati su LINQ, quindi ogni parte di questo processo verrà spiegata in passaggi.</span><span class="sxs-lookup"><span data-stu-id="844be-172">The shuffle method you'll be creating illustrates several techniques that you'll use with LINQ-based programs, so each part of this process will be explained in steps.</span></span>

<span data-ttu-id="844be-173">Per aggiungere alcune funzionalità per l'interazione con l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> che verrà restituita dalle query LINQ,è necessario scrivere dei tipi speciali di metodi detti [metodi di estensione](../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="844be-173">In order to add some functionality to how you interact with the <xref:System.Collections.Generic.IEnumerable%601> you'll get back from LINQ queries, you'll need to write some special kinds of methods called [extension methods](../programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="844be-174">In breve, un metodo di estensione è uno speciale *metodo statico* che aggiunge nuove funzionalità a un tipo già esistente senza bisogno di modificare il tipo originale a cui si vogliono aggiungere funzionalità.</span><span class="sxs-lookup"><span data-stu-id="844be-174">Briefly, an extension method is a special purpose *static method* that adds new functionality to an already-existing type without having to modify the original type you want to add functionality to.</span></span>

<span data-ttu-id="844be-175">Assegnare ai metodi di estensione una nuova posizione aggiungendo al programma un nuovo file di classe *statica* denominato `Extensions.cs`, quindi iniziare a compilare il primo metodo di estensione:</span><span class="sxs-lookup"><span data-stu-id="844be-175">Give your extension methods a new home by adding a new *static* class file to your program called `Extensions.cs`, and then start building out the first extension method:</span></span>

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

<span data-ttu-id="844be-176">Osservare per un momento la firma del metodo, in particolare i parametri:</span><span class="sxs-lookup"><span data-stu-id="844be-176">Look at the method signature for a moment, specifically the parameters:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="844be-177">È possibile notare l'aggiunta del modificatore `this` nel primo argomento del metodo.</span><span class="sxs-lookup"><span data-stu-id="844be-177">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="844be-178">Ciò significa che il metodo viene chiamato come se fosse un membro del tipo del primo argomento.</span><span class="sxs-lookup"><span data-stu-id="844be-178">That means you call the method as though it were a member method of the type of the first argument.</span></span> <span data-ttu-id="844be-179">Questa dichiarazione di metodo segue anche un termine standard in cui i tipi di input e output sono `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="844be-179">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="844be-180">Ciò consente la concatenazione dei metodi LINQ per l'esecuzione di query più complesse.</span><span class="sxs-lookup"><span data-stu-id="844be-180">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

<span data-ttu-id="844be-181">Naturalmente, dato che il mazzo è stato diviso in due, occorrerà unire queste due metà.</span><span class="sxs-lookup"><span data-stu-id="844be-181">Naturally, since you split the deck into halves, you'll need to join those halves together.</span></span> <span data-ttu-id="844be-182">Nel codice questo significa enumerare entrambe le sequenze acquisite tramite <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> contemporaneamente, *`interleaving`* gli elementi e creare una sola sequenza, ossia il mazzo di carte ora mischiato.</span><span class="sxs-lookup"><span data-stu-id="844be-182">In code, this means you'll be enumerating both of the sequences you acquired through <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> at once, *`interleaving`* the elements, and creating one sequence: your now-shuffled deck of cards.</span></span> <span data-ttu-id="844be-183">Per scrivere un metodo LINQ utilizzabile con le due sequenze è necessario comprendere il funzionamento di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="844be-183">Writing a LINQ method that works with two sequences requires that you understand how <xref:System.Collections.Generic.IEnumerable%601> works.</span></span>

<span data-ttu-id="844be-184">L'interfaccia <xref:System.Collections.Generic.IEnumerable%601> ha un unico metodo: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="844be-184">The <xref:System.Collections.Generic.IEnumerable%601> interface has one method: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span></span> <span data-ttu-id="844be-185">L'oggetto restituito da <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> ha un metodo per passare all'elemento successivo e una proprietà che recupera l'elemento corrente nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="844be-185">The object returned by <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="844be-186">Si useranno questi due membri per enumerare la raccolta e restituire gli elementi.</span><span class="sxs-lookup"><span data-stu-id="844be-186">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="844be-187">Questo metodo Interleave sarà un metodo iteratore. Di conseguenza, anziché creare una raccolta e restituirla, si userà la sintassi `yield return` mostrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="844be-187">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span>

<span data-ttu-id="844be-188">Questa è l'implementazione del metodo:</span><span class="sxs-lookup"><span data-stu-id="844be-188">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="844be-189">Dopo avere scritto questo metodo, tornare al metodo `Main` e mischiare una volta il mazzo:</span><span class="sxs-lookup"><span data-stu-id="844be-189">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="844be-190">Confronti</span><span class="sxs-lookup"><span data-stu-id="844be-190">Comparisons</span></span>

<span data-ttu-id="844be-191">Quante volte è necessario mischiare il mazzo per ripristinare l'ordine originale?</span><span class="sxs-lookup"><span data-stu-id="844be-191">How many shuffles it takes to set the deck back to its original order?</span></span> <span data-ttu-id="844be-192">Per scoprirlo è necessario scrivere un metodo che determina se due sequenze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="844be-192">To find out, you'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="844be-193">Una volta creato tale metodo, sarà necessario inserire in un ciclo il codice per mischiare il mazzo e verificare quando viene ripristinato l'ordine originale.</span><span class="sxs-lookup"><span data-stu-id="844be-193">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="844be-194">Scrivere un metodo per determinare se due sequenze sono uguali è un'operazione piuttosto intuitiva.</span><span class="sxs-lookup"><span data-stu-id="844be-194">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="844be-195">La struttura è simile a quella del metodo usato per mischiare il mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-195">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="844be-196">In questo caso, però, anziché eseguire un'istruzione `yield return` in ogni elemento, si confronteranno gli elementi corrispondenti di ogni sequenza.</span><span class="sxs-lookup"><span data-stu-id="844be-196">Only this time, instead of `yield return`ing each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="844be-197">Al termine dell'enumerazione dell'intera sequenza, se ogni elemento corrisponde, le sequenze sono identiche:</span><span class="sxs-lookup"><span data-stu-id="844be-197">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="844be-198">Questo esempio illustra un secondo termine del linguaggio LINQ: i metodi terminali.</span><span class="sxs-lookup"><span data-stu-id="844be-198">This shows a second LINQ idiom: terminal methods.</span></span> <span data-ttu-id="844be-199">Questi metodi accettano una sequenza come input (o, in questo caso, due sequenze) e restituiscono un singolo valore scalare.</span><span class="sxs-lookup"><span data-stu-id="844be-199">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="844be-200">Quando si usa un metodo terminale, questo è sempre il metodo finale in una catena di metodi per una query LINQ, da qui il nome "terminale".</span><span class="sxs-lookup"><span data-stu-id="844be-200">When using terminal methods, they are always the final method in a chain of methods for a LINQ query, hence the name "terminal".</span></span>

<span data-ttu-id="844be-201">È possibile notare questo comportamento nella pratica quando si usa il metodo per determinare quando viene ripristinato l'ordine originale del mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-201">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="844be-202">Inserire in un ciclo il codice per mischiare il mazzo e arrestare l'esecuzione quando viene ripristinato l'ordine originale della sequenza applicando il metodo `SequenceEquals()`.</span><span class="sxs-lookup"><span data-stu-id="844be-202">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="844be-203">È possibile notare che questo sarebbe sempre il metodo finale in qualsiasi query poiché restituisce un singolo valore anziché una sequenza:</span><span class="sxs-lookup"><span data-stu-id="844be-203">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="844be-204">Eseguire il codice ottenuto fino a questo momento e prendere nota del modo in cui il mazzo viene riordinato ogni volta che viene mischiato.</span><span class="sxs-lookup"><span data-stu-id="844be-204">Run the code you've got so far and take note of how the deck rearranges on each shuffle.</span></span> <span data-ttu-id="844be-205">Dopo 8 volte (iterazioni del ciclo do-while), il mazzo torna alla configurazione originale che aveva quando è stato creato dalla query LINQ iniziale.</span><span class="sxs-lookup"><span data-stu-id="844be-205">After 8 shuffles (iterations of the do-while loop), the deck returns to the original configuration it was in when you first created it from the starting LINQ query.</span></span>

## <a name="optimizations"></a><span data-ttu-id="844be-206">Ottimizzazioni</span><span class="sxs-lookup"><span data-stu-id="844be-206">Optimizations</span></span>

<span data-ttu-id="844be-207">L'esempio creato finora *mischia le carte esterne*, lasciando le carte in cima e in fondo al mazzo sempre nella stessa posizione,</span><span class="sxs-lookup"><span data-stu-id="844be-207">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="844be-208">ma è possibile introdurre una variazione e *mischiare anche le carte interne*, cambiando la posizione di tutte e 52 le carte.</span><span class="sxs-lookup"><span data-stu-id="844be-208">Let's make one change: we'll use an *in shuffle* instead, where all 52 cards change position.</span></span> <span data-ttu-id="844be-209">Per mischiare il mazzo in questo modo, si alternano le carte in modo che la prima carta della metà inferiore diventi la prima carta del mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-209">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="844be-210">Di conseguenza, l'ultima carta della metà superiore diventerà l'ultima carta del mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-210">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="844be-211">Si tratta di una semplice modifica a una singola riga di codice.</span><span class="sxs-lookup"><span data-stu-id="844be-211">This is a simple change to a singular line of code.</span></span> <span data-ttu-id="844be-212">Aggiornare la query corrente scambiando le posizioni di <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="844be-212">Update the current shuffle query by switching the positions of <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span> <span data-ttu-id="844be-213">In questo modo si cambia l'ordine della metà superiore e di quella inferiore del mazzo:</span><span class="sxs-lookup"><span data-stu-id="844be-213">This will change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="844be-214">Eseguire nuovamente il programma. Si noterà che il ripristino dell'ordine del mazzo richiede 52 iterazioni.</span><span class="sxs-lookup"><span data-stu-id="844be-214">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="844be-215">Nel corso dell'esecuzione del programma si inizierà a notare anche un calo significativo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="844be-215">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="844be-216">Questo problema può essere dovuto a vari motivi.</span><span class="sxs-lookup"><span data-stu-id="844be-216">There are a number of reasons for this.</span></span> <span data-ttu-id="844be-217">Una delle cause principali di questo calo delle prestazioni consiste nell'uso inefficiente della [*valutazione lazy*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="844be-217">You can tackle one of the major causes of this performance drop: inefficient use of [*lazy evaluation*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

<span data-ttu-id="844be-218">In breve, la valutazione lazy indica che la valutazione di un'istruzione non viene eseguita finché il suo valore non è necessario.</span><span class="sxs-lookup"><span data-stu-id="844be-218">Briefly, lazy evaluation states that the evaluation of a statement is not performed until its value is needed.</span></span> <span data-ttu-id="844be-219">Le query LINQ sono istruzioni che vengono valutate in modalità lazy.</span><span class="sxs-lookup"><span data-stu-id="844be-219">LINQ queries are statements that are evaluated lazily.</span></span> <span data-ttu-id="844be-220">Le sequenze vengono generate solo quando vengono richiesti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="844be-220">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="844be-221">Questo è in genere uno dei principali vantaggi di LINQ,</span><span class="sxs-lookup"><span data-stu-id="844be-221">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="844be-222">ma in un programma di questo tipo può tradursi in una crescita esponenziale del tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="844be-222">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="844be-223">Tenere presente che il mazzo originale è stato generato con una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="844be-223">Remember that we generated the original deck using a LINQ query.</span></span> <span data-ttu-id="844be-224">e, ogni volta che si mischiano le carte, il mazzo viene generato eseguendo tre query LINQ sul mazzo precedente.</span><span class="sxs-lookup"><span data-stu-id="844be-224">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="844be-225">Tutte queste operazioni sono eseguite in modalità lazy</span><span class="sxs-lookup"><span data-stu-id="844be-225">All these are performed lazily.</span></span> <span data-ttu-id="844be-226">e quindi vengono ripetute ogni volta che è richiesta la sequenza.</span><span class="sxs-lookup"><span data-stu-id="844be-226">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="844be-227">Quando si giunge alla cinquantaduesima iterazione, il mazzo originale è stato rigenerato un numero di volte molto elevato.</span><span class="sxs-lookup"><span data-stu-id="844be-227">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="844be-228">Per comprendere più facilmente questo comportamento è possibile scrivere un log.</span><span class="sxs-lookup"><span data-stu-id="844be-228">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="844be-229">Si potrà così correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="844be-229">Then, you'll fix it.</span></span>

<span data-ttu-id="844be-230">Nel file `Extensions.cs` digitare o copiare il metodo riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="844be-230">In your `Extensions.cs` file, type in or copy the method below.</span></span> <span data-ttu-id="844be-231">Questo metodo di estensione crea un nuovo file denominato `debug.log` nella directory del progetto e registra la query attualmente in esecuzione nel file di log.</span><span class="sxs-lookup"><span data-stu-id="844be-231">This extension method creates a new file called `debug.log` within your project directory and records what query is currently being executed to the log file.</span></span> <span data-ttu-id="844be-232">Questo metodo di estensione può essere aggiunto a qualsiasi query per indicare che la query è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="844be-232">This extension method can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="844be-233">Si noterà una sottolineatura ondulata rossa sotto `File`, per indicare che non esiste.</span><span class="sxs-lookup"><span data-stu-id="844be-233">You will see a red squiggle under `File`, meaning it doesn't exist.</span></span> <span data-ttu-id="844be-234">Non viene compilato, perché il compilatore non riconosce `File`.</span><span class="sxs-lookup"><span data-stu-id="844be-234">It won't compile, since the compiler doesn't know what `File` is.</span></span> <span data-ttu-id="844be-235">Per risolvere questo problema, assicurarsi di aggiungere la seguente riga di codice sotto la prima riga in `Extensions.cs`:</span><span class="sxs-lookup"><span data-stu-id="844be-235">To solve this problem, make sure to add the following line of code under the very first line in `Extensions.cs`:</span></span>

```csharp
using System.IO;
```

<span data-ttu-id="844be-236">Questo dovrebbe risolvere il problema e far scomparire l'indicatore di errore rosso.</span><span class="sxs-lookup"><span data-stu-id="844be-236">This should solve the issue and the red error disappears.</span></span>

<span data-ttu-id="844be-237">Instrumentare quindi la definizione di ogni query con un messaggio di log:</span><span class="sxs-lookup"><span data-stu-id="844be-237">Next, instrument the definition of each query with a log message:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="844be-238">Si noti che la registrazione non viene eseguita ogni volta che si accede a una query,</span><span class="sxs-lookup"><span data-stu-id="844be-238">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="844be-239">ma solo quando si crea la query originale.</span><span class="sxs-lookup"><span data-stu-id="844be-239">You log only when you create the original query.</span></span> <span data-ttu-id="844be-240">L'esecuzione del programma richiede ancora molto tempo, ma ora si è individuato il motivo del problema.</span><span class="sxs-lookup"><span data-stu-id="844be-240">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="844be-241">Se il tempo necessario per mischiare anche le carte interne con la registrazione attivata è eccessivo, limitarsi a mischiare quelle esterne.</span><span class="sxs-lookup"><span data-stu-id="844be-241">If you run out of patience running the in shuffle with logging turned on, switch back to the out shuffle.</span></span> <span data-ttu-id="844be-242">Gli effetti della valutazione lazy saranno ancora visibili.</span><span class="sxs-lookup"><span data-stu-id="844be-242">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="844be-243">In un'unica esecuzione del programma verranno eseguite 2592 query, inclusa la generazione di tutti i semi e valori.</span><span class="sxs-lookup"><span data-stu-id="844be-243">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="844be-244">È possibile migliorare le prestazioni del codice per ridurre il numero di esecuzioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="844be-244">You can improve the performance of the code here to reduce the number of executions you make.</span></span> <span data-ttu-id="844be-245">Una semplice correzione consiste nel *memorizzare nella cache* i risultati della query LINQ originale che costruisce il mazzo di carte.</span><span class="sxs-lookup"><span data-stu-id="844be-245">A simple fix you can make is to *cache* the results of the original LINQ query that constructs the deck of cards.</span></span> <span data-ttu-id="844be-246">Attualmente si rieseguono le query ad ogni iterazione del ciclo do-while, ricostruendo il mazzo di carte e rimescolandolo ogni volta.</span><span class="sxs-lookup"><span data-stu-id="844be-246">Currently, you're executing the queries again and again every time the do-while loop goes through an iteration, re-constructing the deck of cards and reshuffling it every time.</span></span> <span data-ttu-id="844be-247">Per memorizzare il mazzo di carte nella cache, è possibile sfruttare i metodi LINQ <xref:System.Linq.Enumerable.ToArray%2A> e <xref:System.Linq.Enumerable.ToList%2A>. Accodandoli alle query, eseguiranno le stesse azioni per cui sono stati creati, ma ora archivieranno i risultati in una matrice o un elenco, a seconda del metodo che si è scelto di chiamare.</span><span class="sxs-lookup"><span data-stu-id="844be-247">To cache the deck of cards, you can leverage the LINQ methods <xref:System.Linq.Enumerable.ToArray%2A> and <xref:System.Linq.Enumerable.ToList%2A>; when you append them to the queries, they'll perform the same actions you've told them to, but now they'll store the results in an array or a list, depending on which method you choose to call.</span></span> <span data-ttu-id="844be-248">Accodare il metodo LINQ <xref:System.Linq.Enumerable.ToArray%2A> a entrambe le query ed eseguire di nuovo il programma:</span><span class="sxs-lookup"><span data-stu-id="844be-248">Append the LINQ method <xref:System.Linq.Enumerable.ToArray%2A> to both queries and run the program again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="844be-249">Ora il numero di query per mischiare le carte esterne è ridotto a 30.</span><span class="sxs-lookup"><span data-stu-id="844be-249">Now the out shuffle is down to 30 queries.</span></span> <span data-ttu-id="844be-250">Eseguire nuovamente il programma per mischiare anche le carte interne e si noteranno miglioramenti analoghi: ora vengono eseguite 162 query.</span><span class="sxs-lookup"><span data-stu-id="844be-250">Run again with the in shuffle and you'll see similar improvements: it now executes 162 queries.</span></span>

<span data-ttu-id="844be-251">Questo esempio è stato **progettato** per mettere in evidenza i casi d'uso in cui la valutazione lazy può causare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="844be-251">Please note that this example is **designed** to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="844be-252">Sebbene sia importante capire dove la valutazione lazy può influire sulle prestazioni del codice, è altrettanto importante comprendere che non tutte le query devono essere eseguite in modalità eager.</span><span class="sxs-lookup"><span data-stu-id="844be-252">While it's important to see where lazy evaluation can impact code performance, it's equally important to understand that not all queries should run eagerly.</span></span> <span data-ttu-id="844be-253">La riduzione delle prestazioni che si verifica senza usare <xref:System.Linq.Enumerable.ToArray%2A> avviene perché ogni nuova configurazione del mazzo di carte è basata sulla configurazione precedente.</span><span class="sxs-lookup"><span data-stu-id="844be-253">The performance hit you incur without using <xref:System.Linq.Enumerable.ToArray%2A> is because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="844be-254">Quando si usa la valutazione lazy, ogni nuova configurazione del mazzo è basata sul mazzo originale, anche eseguendo il codice che ha creato `startingDeck`.</span><span class="sxs-lookup"><span data-stu-id="844be-254">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="844be-255">Questo comportamento determina una grande quantità di operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="844be-255">That causes a large amount of extra work.</span></span>

<span data-ttu-id="844be-256">In pratica, per alcuni algoritmi è più efficiente la valutazione eager, mentre per altri è preferibile la valutazione lazy.</span><span class="sxs-lookup"><span data-stu-id="844be-256">In practice, some algorithms run well using eager evaluation, and others run well using lazy evaluation.</span></span> <span data-ttu-id="844be-257">Per l'uso quotidiano, quest'ultima rappresenta in genere la scelta migliore quando l'origine dati è costituita da un processo separato, ad esempio un motore di database.</span><span class="sxs-lookup"><span data-stu-id="844be-257">For daily usage, lazy evaluation is usually a better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="844be-258">Per i database, la valutazione lazy consente alle query più complesse di eseguire un solo round trip al processo di database e di tornare al resto del codice.</span><span class="sxs-lookup"><span data-stu-id="844be-258">For databases, lazy evaluation allows more complex queries to execute only one round trip to the database process and back to the rest of your code.</span></span> <span data-ttu-id="844be-259">LINQ offre la stessa flessibilità sia che si scelga di usare la valutazione lazy o eager. Misurare pertanto i processi e scegliere il tipo di valutazione che offre le prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="844be-259">LINQ is flexible whether you choose to utilize lazy or eager evaluation, so measure your processes and pick whichever kind of evaluation gives you the best performance.</span></span>

## <a name="conclusion"></a><span data-ttu-id="844be-260">Conclusione</span><span class="sxs-lookup"><span data-stu-id="844be-260">Conclusion</span></span>

<span data-ttu-id="844be-261">In questo progetto sono stati illustrati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="844be-261">In this project, you covered:</span></span>

- <span data-ttu-id="844be-262">Uso di query LINQ per aggregare i dati in una sequenza significativa</span><span class="sxs-lookup"><span data-stu-id="844be-262">using LINQ queries to aggregate data into a meaningful sequence</span></span>
- <span data-ttu-id="844be-263">Scrittura di metodi di estensione per aggiungere funzionalità personalizzate alle query LINQ</span><span class="sxs-lookup"><span data-stu-id="844be-263">writing Extension methods to add our own custom functionality to LINQ queries</span></span>
- <span data-ttu-id="844be-264">Individuazione delle aree del codice in cui le query LINQ potrebbero riscontrare problemi di prestazioni, ad esempio una riduzione della velocità</span><span class="sxs-lookup"><span data-stu-id="844be-264">locating areas in our code where our LINQ queries might run into performance issues like degraded speed</span></span>
- <span data-ttu-id="844be-265">Valutazione lazy e valutazione eager relativamente alle query LINQ e implicazioni che potrebbero avere sulle prestazioni delle query</span><span class="sxs-lookup"><span data-stu-id="844be-265">lazy and eager evaluation in regards to LINQ queries and the implications they might have on query performance</span></span>

<span data-ttu-id="844be-266">Oltre a LINQ, è stata illustrata una tecnica usata dai prestigiatori per i trucchi con le carte.</span><span class="sxs-lookup"><span data-stu-id="844be-266">Aside from LINQ, you learned a bit about a technique magicians use for card tricks.</span></span> <span data-ttu-id="844be-267">I prestigiatori usano il miscuglio Faro perché possono controllare lo spostamento di ogni carta nel mazzo.</span><span class="sxs-lookup"><span data-stu-id="844be-267">Magicians use the Faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="844be-268">È una tecnica che, per mantenere la sua magia, dovrebbe restare nota a pochi.</span><span class="sxs-lookup"><span data-stu-id="844be-268">Now that you know, don't spoil it for everyone else!</span></span>

<span data-ttu-id="844be-269">Per altre informazioni su LINQ, vedere:</span><span class="sxs-lookup"><span data-stu-id="844be-269">For more information on LINQ, see:</span></span>

- [<span data-ttu-id="844be-270">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="844be-270">Language Integrated Query (LINQ)</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="844be-271">Introduzione a LINQ</span><span class="sxs-lookup"><span data-stu-id="844be-271">Introduction to LINQ</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="844be-272">Operazioni di query LINQ di base (C#)</span><span class="sxs-lookup"><span data-stu-id="844be-272">Basic LINQ Query Operations (C#)</span></span>](../programming-guide/concepts/linq/basic-linq-query-operations.md)
- [<span data-ttu-id="844be-273">Trasformazioni dati con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="844be-273">Data Transformations With LINQ (C#)</span></span>](../programming-guide/concepts/linq/data-transformations-with-linq.md)
- [<span data-ttu-id="844be-274">Sintassi di query e sintassi di metodi in LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="844be-274">Query Syntax and Method Syntax in LINQ (C#)</span></span>](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
- [<span data-ttu-id="844be-275">Funzionalità di C# che supportano LINQ</span><span class="sxs-lookup"><span data-stu-id="844be-275">C# Features That Support LINQ</span></span>](../programming-guide/concepts/linq/features-that-support-linq.md)
