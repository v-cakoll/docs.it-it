---
title: Uso di LINQ
description: "Questa esercitazione illustra come generare sequenze con LINQ, come scrivere i metodi da usare nelle query LINQ e come distinguere le modalità di valutazione eager e lazy."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/28/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: ec86c558b9aa9c6269fcf9890978f61a934c081f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-linq"></a><span data-ttu-id="acd85-104">Uso di LINQ</span><span class="sxs-lookup"><span data-stu-id="acd85-104">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="acd85-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="acd85-105">Introduction</span></span>

<span data-ttu-id="acd85-106">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="acd85-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="acd85-107">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="acd85-107">You’ll learn:</span></span>

*   <span data-ttu-id="acd85-108">Come generare sequenze con LINQ</span><span class="sxs-lookup"><span data-stu-id="acd85-108">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="acd85-109">Come scrivere i metodi da usare facilmente nelle query LINQ</span><span class="sxs-lookup"><span data-stu-id="acd85-109">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="acd85-110">Come distinguere le modalità di valutazione eager e lazy</span><span class="sxs-lookup"><span data-stu-id="acd85-110">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="acd85-111">Si apprenderanno queste tecniche creando un'applicazione che illustra una delle abilità di base di un prestigiatore: il [miscuglio faro](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="acd85-111">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="acd85-112">In breve, il miscuglio faro è una tecnica che consiste nel tagliare un mazzo di carte esattamente a metà e quindi nel sovrapporre alternativamente le carte delle due metà per ricostruire il mazzo originale.</span><span class="sxs-lookup"><span data-stu-id="acd85-112">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="acd85-113">I prestigiatori adottano questa tecnica perché, dopo ogni miscuglio, ciascuna carta si trova in una posizione nota e le carte vengono ordinate in base a uno schema ripetitivo.</span><span class="sxs-lookup"><span data-stu-id="acd85-113">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="acd85-114">Ai fini dell'esercitazione, questa tecnica offre un modo scherzoso per illustrare la manipolazione di sequenze di dati.</span><span class="sxs-lookup"><span data-stu-id="acd85-114">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="acd85-115">Si creerà un'applicazione che costruisce un mazzo di carte ed esegue una serie di miscugli scrivendo ogni volta la sequenza ottenuta.</span><span class="sxs-lookup"><span data-stu-id="acd85-115">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="acd85-116">Si confronterà inoltre l'ordine aggiornato con quello originale.</span><span class="sxs-lookup"><span data-stu-id="acd85-116">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="acd85-117">Questa esercitazione prevede diversi passaggi.</span><span class="sxs-lookup"><span data-stu-id="acd85-117">This tutorial has multiple steps.</span></span> <span data-ttu-id="acd85-118">Dopo ogni passaggio, è possibile eseguire l'applicazione e verificare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="acd85-118">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="acd85-119">È anche possibile vedere l'[esempio completo](https://github.com/dotnet/docs/blob/master/samples/csharp/getting-started/console-linq) disponibile nel repository dotnet/docs su GitHub.</span><span class="sxs-lookup"><span data-stu-id="acd85-119">You can also see the [completed sample](https://github.com/dotnet/docs/blob/master/samples/csharp/getting-started/console-linq) in the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="acd85-120">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="acd85-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acd85-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="acd85-121">Prerequisites</span></span>

<span data-ttu-id="acd85-122">È necessario configurare il computer per l'esecuzione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="acd85-122">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="acd85-123">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="acd85-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="acd85-124">Questa applicazione può essere eseguita in Windows, Ubuntu Linux, OS X o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="acd85-124">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="acd85-125">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="acd85-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="acd85-126">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="acd85-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="acd85-127">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="acd85-127">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="acd85-128">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="acd85-128">Create the Application</span></span>

<span data-ttu-id="acd85-129">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-129">The first step is to create a new application.</span></span> <span data-ttu-id="acd85-130">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="acd85-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="acd85-131">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="acd85-131">Make that the current directory.</span></span> <span data-ttu-id="acd85-132">Digitare il comando `dotnet new console` al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="acd85-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="acd85-133">per creare i file di avvio per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="acd85-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="acd85-134">Se non si è mai usato C#, [questa esercitazione](console-teleprompter.md) illustra la struttura di un programma C#.</span><span class="sxs-lookup"><span data-stu-id="acd85-134">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="acd85-135">È possibile leggerla e tornare qui per ottenere altre informazioni su LINQ.</span><span class="sxs-lookup"><span data-stu-id="acd85-135">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="acd85-136">Creazione del set di dati</span><span class="sxs-lookup"><span data-stu-id="acd85-136">Creating the Data Set</span></span>

<span data-ttu-id="acd85-137">Si creerà innanzitutto un mazzo di carte.</span><span class="sxs-lookup"><span data-stu-id="acd85-137">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="acd85-138">Eseguire questa operazione usando una query LINQ con due origini, una per i quattro semi e l'altra per i 13 valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-138">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="acd85-139">Le due origini verranno combinate in un mazzo da 52 carte.</span><span class="sxs-lookup"><span data-stu-id="acd85-139">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="acd85-140">Un'istruzione `Console.WriteLine` all'interno di un ciclo `foreach` visualizza le carte.</span><span class="sxs-lookup"><span data-stu-id="acd85-140">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="acd85-141">Questa è la query da eseguire:</span><span class="sxs-lookup"><span data-stu-id="acd85-141">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="acd85-142">Le clausole `from` multiple generano un `SelectMany` che crea una singola sequenza tramite la combinazione di ogni elemento nella prima sequenza con ogni elemento nella seconda.</span><span class="sxs-lookup"><span data-stu-id="acd85-142">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="acd85-143">L'ordine è importante ai fini di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-143">The order is important for our purposes.</span></span> <span data-ttu-id="acd85-144">Il primo elemento nella prima sequenza di origine (semi) viene combinato con ogni elemento della seconda sequenza (valori).</span><span class="sxs-lookup"><span data-stu-id="acd85-144">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="acd85-145">Si ottengono così le 13 carte appartenenti al primo seme.</span><span class="sxs-lookup"><span data-stu-id="acd85-145">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="acd85-146">Il processo viene ripetuto con ogni elemento della prima sequenza, ovvero i semi.</span><span class="sxs-lookup"><span data-stu-id="acd85-146">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="acd85-147">Il risultato finale è un mazzo di carte ordinato in base ai semi e quindi in base ai valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-147">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="acd85-148">Dopo questa operazione, è necessario creare i metodi Suits() e Ranks(), rispettivamente per i semi e valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-148">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="acd85-149">Si inizierà con un set molto semplice di *metodi iteratore* che generano la sequenza come un oggetto enumerabile di stringhe:</span><span class="sxs-lookup"><span data-stu-id="acd85-149">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
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

<span data-ttu-id="acd85-150">Questi due metodi usano entrambi la sintassi `yield return` per generare una sequenza durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acd85-150">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="acd85-151">Il compilatore crea un oggetto che implementa `IEnumerable<T>` e genera la sequenza di stringhe a mano a mano che vengono richieste.</span><span class="sxs-lookup"><span data-stu-id="acd85-151">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="acd85-152">Andare avanti ed eseguire l'esempio che si è creato finora.</span><span class="sxs-lookup"><span data-stu-id="acd85-152">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="acd85-153">Verranno visualizzate le 52 carte del mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-153">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="acd85-154">Può essere molto utile eseguire questo esempio in un debugger per osservare come vengono eseguiti i metodi `Suits()` e `Values()`.</span><span class="sxs-lookup"><span data-stu-id="acd85-154">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="acd85-155">È possibile vedere chiaramente che in ogni sequenza ciascuna stringa viene generata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="acd85-155">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Finestra della console con l'applicazione che scrive 52 carte](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="acd85-157">Modifica dell'ordine</span><span class="sxs-lookup"><span data-stu-id="acd85-157">Manipulating the Order</span></span>

<span data-ttu-id="acd85-158">A questo punto, si creerà un metodo di utilità che può eseguire il miscuglio.</span><span class="sxs-lookup"><span data-stu-id="acd85-158">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="acd85-159">Il primo passaggio consiste nel tagliare il mazzo in due.</span><span class="sxs-lookup"><span data-stu-id="acd85-159">The first step is to split the deck in two.</span></span> <span data-ttu-id="acd85-160">I metodi `Take()` e `Skip()` inclusi nelle API LINQ offrono questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="acd85-160">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="acd85-161">Il metodo shuffle, per eseguire il miscuglio, non esiste nella libreria standard ed è pertanto necessario scriverne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="acd85-161">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="acd85-162">Questo nuovo metodo illustra varie tecniche che è possibile usare con programmi basati su LINQ. Ogni parte del metodo verrà quindi descritta in passaggi distinti.</span><span class="sxs-lookup"><span data-stu-id="acd85-162">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="acd85-163">La firma per il metodo crea un *metodo di estensione*:</span><span class="sxs-lookup"><span data-stu-id="acd85-163">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="acd85-164">Un metodo di estensione è un *metodo statico* con finalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="acd85-164">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="acd85-165">È possibile notare l'aggiunta del modificatore `this` nel primo argomento del metodo.</span><span class="sxs-lookup"><span data-stu-id="acd85-165">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="acd85-166">Ciò significa che il metodo viene chiamato come se fosse un membro del tipo del primo argomento.</span><span class="sxs-lookup"><span data-stu-id="acd85-166">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="acd85-167">I metodi di estensione possono essere dichiarati solo all'interno di classi `static`. Si creerà pertanto una nuova classe statica denominata `extensions` per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="acd85-167">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="acd85-168">Proseguendo con l'esercitazione si aggiungeranno altri metodi di estensione che verranno inseriti nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="acd85-168">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="acd85-169">Questa dichiarazione di metodo segue anche un termine standard in cui i tipi di input e output sono `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="acd85-169">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="acd85-170">Ciò consente la concatenazione dei metodi LINQ per l'esecuzione di query più complesse.</span><span class="sxs-lookup"><span data-stu-id="acd85-170">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="acd85-171">Si eseguirà contemporaneamente l'enumerazione di entrambe le sequenze, alternando gli elementi e creando un unico oggetto.</span><span class="sxs-lookup"><span data-stu-id="acd85-171">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="acd85-172">Per scrivere un metodo LINQ utilizzabile con le due sequenze è necessario comprendere il funzionamento di `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="acd85-172">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="acd85-173">L'interfaccia `IEnumerable` ha un unico metodo: `GetEnumerator()`.</span><span class="sxs-lookup"><span data-stu-id="acd85-173">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="acd85-174">L'oggetto restituito da `GetEnumerator()` ha un metodo per passare all'elemento successivo e una proprietà che recupera l'elemento corrente nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="acd85-174">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="acd85-175">Si useranno questi due membri per enumerare la raccolta e restituire gli elementi.</span><span class="sxs-lookup"><span data-stu-id="acd85-175">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="acd85-176">Questo metodo Interleave sarà un metodo iteratore. Di conseguenza, anziché creare una raccolta e restituirla, si userà la sintassi `yield return` mostrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="acd85-176">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="acd85-177">Questa è l'implementazione del metodo:</span><span class="sxs-lookup"><span data-stu-id="acd85-177">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="acd85-178">Dopo avere scritto questo metodo, tornare al metodo `Main` e mischiare una volta il mazzo:</span><span class="sxs-lookup"><span data-stu-id="acd85-178">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
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

## <a name="comparisons"></a><span data-ttu-id="acd85-179">Confronti</span><span class="sxs-lookup"><span data-stu-id="acd85-179">Comparisons</span></span>

<span data-ttu-id="acd85-180">Per vedere quante volte è necessario mischiare il mazzo per ripristinare l'ordine originale</span><span class="sxs-lookup"><span data-stu-id="acd85-180">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="acd85-181">è necessario scrivere un metodo che determina se due sequenze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="acd85-181">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="acd85-182">Una volta creato tale metodo, sarà necessario inserire in un ciclo il codice per mischiare il mazzo e verificare quando viene ripristinato l'ordine originale.</span><span class="sxs-lookup"><span data-stu-id="acd85-182">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="acd85-183">Scrivere un metodo per determinare se due sequenze sono uguali è un'operazione piuttosto intuitiva.</span><span class="sxs-lookup"><span data-stu-id="acd85-183">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="acd85-184">La struttura è simile a quella del metodo usato per mischiare il mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-184">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="acd85-185">In questo caso, però, anziché restituire ogni elemento, si confronteranno gli elementi corrispondenti di ogni sequenza.</span><span class="sxs-lookup"><span data-stu-id="acd85-185">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="acd85-186">Al termine dell'enumerazione dell'intera sequenza, se ogni elemento corrisponde, le sequenze sono identiche:</span><span class="sxs-lookup"><span data-stu-id="acd85-186">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="acd85-187">Questo esempio illustra un secondo termine del linguaggio LINQ: i metodi terminali.</span><span class="sxs-lookup"><span data-stu-id="acd85-187">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="acd85-188">Questi metodi accettano una sequenza come input (o, in questo caso, due sequenze) e restituiscono un singolo valore scalare.</span><span class="sxs-lookup"><span data-stu-id="acd85-188">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="acd85-189">Quando viene usato, questo tipo di metodo è sempre il metodo finale di una query,</span><span class="sxs-lookup"><span data-stu-id="acd85-189">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="acd85-190">come indicato dal nome.</span><span class="sxs-lookup"><span data-stu-id="acd85-190">(Hence the name).</span></span> 

<span data-ttu-id="acd85-191">È possibile notare questo comportamento nella pratica quando si usa il metodo per determinare quando viene ripristinato l'ordine originale del mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-191">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="acd85-192">Inserire in un ciclo il codice per mischiare il mazzo e arrestare l'esecuzione quando viene ripristinato l'ordine originale della sequenza applicando il metodo `SequenceEquals()`.</span><span class="sxs-lookup"><span data-stu-id="acd85-192">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="acd85-193">È possibile notare che questo sarebbe sempre il metodo finale in qualsiasi query poiché restituisce un singolo valore anziché una sequenza:</span><span class="sxs-lookup"><span data-stu-id="acd85-193">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="acd85-194">Eseguire l'esempio e vedere come viene riordinato il mazzo a ogni iterazione, finché non viene ripristinata la configurazione originale dopo 8 iterazioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-194">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="acd85-195">Ottimizzazioni</span><span class="sxs-lookup"><span data-stu-id="acd85-195">Optimizations</span></span>

<span data-ttu-id="acd85-196">L'esempio creato finora *mischia solo le carte interne*, lasciando le carte in cima e in fondo al mazzo sempre nella stessa posizione,</span><span class="sxs-lookup"><span data-stu-id="acd85-196">The sample you've built so far executes an *in shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="acd85-197">ma è possibile introdurre una variazione e *mischiare anche le carte esterne*, cambiando la posizione di tutte e 52 le schede.</span><span class="sxs-lookup"><span data-stu-id="acd85-197">Let's make one change, and run an *out shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="acd85-198">Per mischiare il mazzo in questo modo, si alternano le carte in modo che la prima carta della metà inferiore diventi la prima carta del mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-198">For an out shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="acd85-199">Di conseguenza, l'ultima carta della metà superiore diventerà l'ultima carta del mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-199">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="acd85-200">Si tratta semplicemente di una modifica di riga.</span><span class="sxs-lookup"><span data-stu-id="acd85-200">That's just a one line change.</span></span> <span data-ttu-id="acd85-201">Aggiornare la chiamata al metodo shuffle per modificare l'ordine della metà superiore e di quella inferiore del mazzo:</span><span class="sxs-lookup"><span data-stu-id="acd85-201">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="acd85-202">Eseguire nuovamente il programma. Si noterà che il ripristino dell'ordine del mazzo richiede 52 iterazioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-202">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="acd85-203">Nel corso dell'esecuzione del programma si inizierà a notare anche un calo significativo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-203">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="acd85-204">Questo problema può essere dovuto a vari motivi.</span><span class="sxs-lookup"><span data-stu-id="acd85-204">There are a number of reasons for this.</span></span> <span data-ttu-id="acd85-205">Una delle cause principali consiste nell'uso inefficiente della *valutazione lazy*.</span><span class="sxs-lookup"><span data-stu-id="acd85-205">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="acd85-206">Le query LINQ vengono valutate in modalità lazy.</span><span class="sxs-lookup"><span data-stu-id="acd85-206">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="acd85-207">Le sequenze vengono generate solo quando vengono richiesti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="acd85-207">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="acd85-208">Questo è in genere uno dei principali vantaggi di LINQ,</span><span class="sxs-lookup"><span data-stu-id="acd85-208">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="acd85-209">ma in un programma di questo tipo può tradursi in una crescita esponenziale del tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acd85-209">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="acd85-210">Il mazzo originale è stato generato tramite una query LINQ</span><span class="sxs-lookup"><span data-stu-id="acd85-210">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="acd85-211">e, ogni volta che si mischiano le carte, il mazzo viene generato eseguendo tre query LINQ sul mazzo precedente.</span><span class="sxs-lookup"><span data-stu-id="acd85-211">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="acd85-212">Tutte queste operazioni sono eseguite in modalità lazy</span><span class="sxs-lookup"><span data-stu-id="acd85-212">All these are performed lazily.</span></span> <span data-ttu-id="acd85-213">e quindi vengono ripetute ogni volta che è richiesta la sequenza.</span><span class="sxs-lookup"><span data-stu-id="acd85-213">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="acd85-214">Quando si giunge alla cinquantaduesima iterazione, il mazzo originale è stato rigenerato un numero di volte molto elevato.</span><span class="sxs-lookup"><span data-stu-id="acd85-214">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="acd85-215">Per comprendere più facilmente questo comportamento è possibile scrivere un log.</span><span class="sxs-lookup"><span data-stu-id="acd85-215">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="acd85-216">Si potrà così correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="acd85-216">Then, you'll fix it.</span></span>

<span data-ttu-id="acd85-217">Di seguito è riportato un metodo log che è possibile aggiungere a qualsiasi query per indicare che la query è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="acd85-217">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="acd85-218">Instrumentare quindi la definizione di ogni query con un messaggio di log:</span><span class="sxs-lookup"><span data-stu-id="acd85-218">Next, instrument the definition of each query with a log message:</span></span>

```csharp
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
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
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

<span data-ttu-id="acd85-219">Si noti che la registrazione non viene eseguita ogni volta che si accede a una query,</span><span class="sxs-lookup"><span data-stu-id="acd85-219">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="acd85-220">ma solo quando si crea la query originale.</span><span class="sxs-lookup"><span data-stu-id="acd85-220">You log only when you create the original query.</span></span> <span data-ttu-id="acd85-221">L'esecuzione del programma richiede ancora molto tempo, ma ora si è individuato il motivo del problema.</span><span class="sxs-lookup"><span data-stu-id="acd85-221">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="acd85-222">Se il tempo necessario per mischiare anche le carte esterne è eccessivo, limitarsi a mischiare quelle interne.</span><span class="sxs-lookup"><span data-stu-id="acd85-222">If you run out of patience running the outer shuffle with logging turned on, switch back to the inner shuffle.</span></span> <span data-ttu-id="acd85-223">Gli effetti della valutazione lazy saranno ancora visibili.</span><span class="sxs-lookup"><span data-stu-id="acd85-223">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="acd85-224">In un'unica esecuzione del programma verranno eseguite 2592 query, inclusa la generazione di tutti i semi e valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-224">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="acd85-225">Esiste un modo semplice per aggiornare il programma ed evitare tutte queste esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-225">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="acd85-226">I metodi LINQ `ToArray()` e `ToList()` consentono di eseguire la query e di memorizzare i risultati rispettivamente in una matrice e in un elenco.</span><span class="sxs-lookup"><span data-stu-id="acd85-226">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="acd85-227">Sono quindi utili per memorizzare nella cache i risultati di una query evitando così di ripetere la query di origine.</span><span class="sxs-lookup"><span data-stu-id="acd85-227">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="acd85-228">Aggiungere una chiamata a `ToArray()` alle query che generano i mazzi di carte ed eseguire nuovamente la query:</span><span class="sxs-lookup"><span data-stu-id="acd85-228">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="acd85-229">In questo modo, il numero di query si ridurrà a 30.</span><span class="sxs-lookup"><span data-stu-id="acd85-229">Run again, and the inner shuffle is down to 30 queries.</span></span> <span data-ttu-id="acd85-230">Eseguire nuovamente il programma per mischiare anche le carte esterne e si noteranno miglioramenti analoghi.</span><span class="sxs-lookup"><span data-stu-id="acd85-230">Run again with the outer shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="acd85-231">Il totale delle query sarà infatti 162.</span><span class="sxs-lookup"><span data-stu-id="acd85-231">(It now executes 162 queries).</span></span>

<span data-ttu-id="acd85-232">Non interpretare erroneamente questo esempio pensando che tutte le query devono essere eseguite in modalità eager.</span><span class="sxs-lookup"><span data-stu-id="acd85-232">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="acd85-233">Questo esempio è stato pensato per mettere in evidenza i casi d'uso in cui la valutazione lazy può causare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-233">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="acd85-234">Questo avviene perché ogni nuova configurazione del mazzo di carte è basata sulla configurazione precedente.</span><span class="sxs-lookup"><span data-stu-id="acd85-234">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="acd85-235">Quando si usa la valutazione lazy, ogni nuova configurazione del mazzo è basata sul mazzo originale, anche eseguendo il codice che ha creato `startingDeck`.</span><span class="sxs-lookup"><span data-stu-id="acd85-235">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="acd85-236">Questo comportamento determina una grande quantità di operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="acd85-236">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="acd85-237">In pratica, per alcuni algoritmi è più efficiente la valutazione eager, mentre per altri è preferibile la valutazione lazy.</span><span class="sxs-lookup"><span data-stu-id="acd85-237">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="acd85-238">Quest'ultima rappresenta in genere la scelta migliore quando l'origine dati è costituita da un processo separato, ad esempio un motore di database.</span><span class="sxs-lookup"><span data-stu-id="acd85-238">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="acd85-239">In questi casi, la valutazione lazy consente alle query più complesse di eseguire un solo round trip al processo di database. LINQ supporta entrambi i tipi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-239">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="acd85-240">Scegliere l'opzione migliore per il proprio caso.</span><span class="sxs-lookup"><span data-stu-id="acd85-240">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="acd85-241">Preparazione per le nuove funzionalità</span><span class="sxs-lookup"><span data-stu-id="acd85-241">Preparing for New Features</span></span>

<span data-ttu-id="acd85-242">Il codice scritto in questa esercitazione offre un esempio di come creare un prototipo semplice per eseguire un'operazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-242">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="acd85-243">Questo è un ottimo modo per esaminare un problema e, per molte funzionalità, può rappresentare la migliore soluzione definitiva.</span><span class="sxs-lookup"><span data-stu-id="acd85-243">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="acd85-244">Sono stati usati *tipi anonimi* per le carte e ogni carta è rappresentata da stringhe.</span><span class="sxs-lookup"><span data-stu-id="acd85-244">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="acd85-245">I *tipi anonimi* offrono molti vantaggi in termini di produttività.</span><span class="sxs-lookup"><span data-stu-id="acd85-245">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="acd85-246">Non è necessario definire una classe per rappresentare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-246">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="acd85-247">Il tipo viene generato automaticamente dal compilatore</span><span class="sxs-lookup"><span data-stu-id="acd85-247">The compiler generates the type for you.</span></span> <span data-ttu-id="acd85-248">e sfrutta molte delle procedure consigliate per gli oggetti dati semplici.</span><span class="sxs-lookup"><span data-stu-id="acd85-248">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="acd85-249">È *non modificabile*, ossia nessuna delle proprietà del tipo può essere modificata dopo che è stata costruita.</span><span class="sxs-lookup"><span data-stu-id="acd85-249">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="acd85-250">I tipi anonimi sono interni a un assembly e quindi non sono considerati parte integrante dell'API pubblica per tale assembly.</span><span class="sxs-lookup"><span data-stu-id="acd85-250">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="acd85-251">Contengono inoltre un override del metodo `ToString()` che restituisce una stringa formattata con ciascuno dei valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-251">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="acd85-252">I tipi anonimi presentano anche degli svantaggi.</span><span class="sxs-lookup"><span data-stu-id="acd85-252">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="acd85-253">Non hanno nomi accessibili e non possono quindi essere usati come argomenti o valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="acd85-253">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="acd85-254">Si noterà che i metodi precedenti in cui sono stati usati questi tipi anonimi sono metodi generici.</span><span class="sxs-lookup"><span data-stu-id="acd85-254">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="acd85-255">L'override di `ToString()` potrebbe non risultare adeguato a mano a mano che si aggiungono altre funzionalità all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="acd85-255">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="acd85-256">Nell'esempio vengono inoltre usate stringhe per il seme e il valore di ogni carta.</span><span class="sxs-lookup"><span data-stu-id="acd85-256">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="acd85-257">Questa è una soluzione abbastanza aperta.</span><span class="sxs-lookup"><span data-stu-id="acd85-257">That's quite open ended.</span></span> <span data-ttu-id="acd85-258">Il sistema dei tipi C# può essere utile per migliorare il codice, sfruttando i tipi `enum` per tali valori.</span><span class="sxs-lookup"><span data-stu-id="acd85-258">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="acd85-259">Iniziando dai semi,</span><span class="sxs-lookup"><span data-stu-id="acd85-259">Start with the suits.</span></span> <span data-ttu-id="acd85-260">l'uso di un tipo `enum` può offrire una soluzione ideale:</span><span class="sxs-lookup"><span data-stu-id="acd85-260">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="acd85-261">Il metodo `Suits()` cambia anche il tipo e l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="acd85-261">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="acd85-262">Eseguire quindi la stessa modifica anche per i valori delle carte:</span><span class="sxs-lookup"><span data-stu-id="acd85-262">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="acd85-263">E per il metodo da cui sono generati:</span><span class="sxs-lookup"><span data-stu-id="acd85-263">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="acd85-264">Come intervento finale, si può decidere di creare un tipo che rappresenta la carta anziché basarsi su un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="acd85-264">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="acd85-265">I tipi anonimi sono ideali per i tipi semplici e locali, ma in questo esempio la carta da gioco è uno dei concetti principali.</span><span class="sxs-lookup"><span data-stu-id="acd85-265">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="acd85-266">Dovrebbe quindi essere un tipo concreto.</span><span class="sxs-lookup"><span data-stu-id="acd85-266">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="acd85-267">Questo tipo usa *proprietà di sola lettura implementate automaticamente* che sono impostate nel costruttore e non sono quindi modificabili.</span><span class="sxs-lookup"><span data-stu-id="acd85-267">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="acd85-268">Si avvale inoltre della nuova funzionalità di *interpolazione delle stringhe* che facilita la formattazione dell'output di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="acd85-268">It also makes use of the new *string interpolation* feature that makes it easier to format string output.</span></span>

<span data-ttu-id="acd85-269">Aggiornare la query che genera il mazzo di carte iniziale in modo da usare il nuovo tipo:</span><span class="sxs-lookup"><span data-stu-id="acd85-269">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="acd85-270">Compilare e ripetere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acd85-270">Compile and run again.</span></span> <span data-ttu-id="acd85-271">L'output è un po' più pulito e il codice è leggermente più chiaro e può essere esteso con più facilità.</span><span class="sxs-lookup"><span data-stu-id="acd85-271">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="acd85-272">Conclusione</span><span class="sxs-lookup"><span data-stu-id="acd85-272">Conclusion</span></span>

<span data-ttu-id="acd85-273">Questo esempio ha illustrato alcuni dei metodi usati in LINQ e come creare metodi personalizzati da usare facilmente con il codice abilitato per LINQ.</span><span class="sxs-lookup"><span data-stu-id="acd85-273">This sample should you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="acd85-274">Ha inoltre mostrato le differenze tra le modalità di valutazione lazy e eager e l'effetto che può avere tale decisione sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="acd85-274">It also showed you the differences between lazy and eager evaluation, and the affect that decision can have on performance.</span></span>

<span data-ttu-id="acd85-275">Ha spiegato anche alcuni aspetti di una delle tecniche di cartomagia.</span><span class="sxs-lookup"><span data-stu-id="acd85-275">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="acd85-276">I prestigiatori usano il miscuglio faro perché possono controllare lo spostamento di ogni carta nel mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-276">Magician's use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="acd85-277">In alcuni trucchi, il prestigiatore chiede a una persona del pubblico di mettere una carta all'inizio del mazzo e mischia il mazzo più volte senza mai perdere di vista la posizione della carta.</span><span class="sxs-lookup"><span data-stu-id="acd85-277">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="acd85-278">Per altri trucchi di illusionismo il mazzo di carte deve essere impostato in un certo modo.</span><span class="sxs-lookup"><span data-stu-id="acd85-278">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="acd85-279">Il prestigiatore ordina il mazzo prima di eseguire il trucco</span><span class="sxs-lookup"><span data-stu-id="acd85-279">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="acd85-280">e quindi mischia cinque volte le carte interne al mazzo.</span><span class="sxs-lookup"><span data-stu-id="acd85-280">Then she will shuffle the deck 5 times using an inner shuffle.</span></span> <span data-ttu-id="acd85-281">In uno spettacolo, può mostrare un mazzo apparentemente ordinato in maniera casuale, mischiare le carte tre volte e infine ottenere un mazzo con le carte disposte esattamente nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="acd85-281">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>
