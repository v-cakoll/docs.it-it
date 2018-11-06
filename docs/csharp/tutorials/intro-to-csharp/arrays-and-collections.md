---
title: Usare raccolte - Esercitazione introduttiva su C#
description: Imparare a usare C# esplorando la raccolta List in questa esercitazione.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: eaf921be2bd50b6e346f57f42e17f151ff336821
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205282"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="2ec21-103">Informazioni su come gestire le raccolte dati tramite il tipo di elenco generico</span><span class="sxs-lookup"><span data-stu-id="2ec21-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="2ec21-104">Questa esercitazione introduttiva offre un'introduzione al linguaggio C# e i concetti di base relativi alla classe <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="2ec21-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="2ec21-105">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="2ec21-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="2ec21-106">L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="2ec21-106">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="2ec21-107">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="2ec21-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="2ec21-108">Esempio di elenco di base</span><span class="sxs-lookup"><span data-stu-id="2ec21-108">A basic list example</span></span>

<span data-ttu-id="2ec21-109">Creare una directory denominata **list-tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2ec21-109">Create a directory named **list-tutorial**.</span></span> <span data-ttu-id="2ec21-110">Impostarla come directory corrente ed eseguire `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="2ec21-110">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="2ec21-111">Se si è già completato [Get started with .NET in 10 minutes](https://www.microsoft.com/net) (Iniziare a usare .NET in 10 minuti), è possibile continuare a usare l'applicazione myApp appena creata.</span><span class="sxs-lookup"><span data-stu-id="2ec21-111">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>

<span data-ttu-id="2ec21-112">Aprire **Program.cs** nell'editor preferito e sostituire il codice esistente con il seguente:</span><span class="sxs-lookup"><span data-stu-id="2ec21-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="2ec21-113">Sostituire `<name>` con il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="2ec21-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="2ec21-114">Salvare **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="2ec21-114">Save **Program.cs**.</span></span> <span data-ttu-id="2ec21-115">Digitare `dotnet run` nella finestra della console per provare il codice.</span><span class="sxs-lookup"><span data-stu-id="2ec21-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="2ec21-116">Questo codice consente di creare un elenco di stringhe, aggiungere tre nomi all'elenco e stampare i nomi in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="2ec21-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="2ec21-117">Vengono usati i concetti appresi nelle esercitazioni precedenti per eseguire il ciclo dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-117">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="2ec21-118">Il codice per visualizzare i nomi usa la funzionalità di [interpolazione di stringhe](../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2ec21-118">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="2ec21-119">Anteponendo il carattere `$` a `string`, è possibile incorporare il codice C# nella dichiarazione della stringa.</span><span class="sxs-lookup"><span data-stu-id="2ec21-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="2ec21-120">La stringa effettiva sostituisce il codice C# con il valore generato.</span><span class="sxs-lookup"><span data-stu-id="2ec21-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="2ec21-121">In questo esempio, `{name.ToUpper()}` viene sostituito con ogni nome, convertito in lettere maiuscole, perché è stato chiamato il metodo <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ec21-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="2ec21-122">L'esplorazione continua nelle prossime lezioni.</span><span class="sxs-lookup"><span data-stu-id="2ec21-122">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="2ec21-123">Modificare il contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="2ec21-123">Modify list contents</span></span>

<span data-ttu-id="2ec21-124">La raccolta creata usa il tipo <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="2ec21-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="2ec21-125">Questo tipo archivia sequenze di elementi.</span><span class="sxs-lookup"><span data-stu-id="2ec21-125">This type stores sequences of elements.</span></span> <span data-ttu-id="2ec21-126">Il tipo degli elementi viene specificato tra parentesi uncinate.</span><span class="sxs-lookup"><span data-stu-id="2ec21-126">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="2ec21-127">Un aspetto importante di questo tipo di <xref:System.Collections.Generic.List%601> è che supporta estensioni o riduzioni, consentendo l'aggiunta o la rimozione di elementi.</span><span class="sxs-lookup"><span data-stu-id="2ec21-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="2ec21-128">Aggiungere questo codice prima della parentesi `}` di chiusura nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ec21-128">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="2ec21-129">Sono stati aggiunti altri due nomi alla fine dell'elenco</span><span class="sxs-lookup"><span data-stu-id="2ec21-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="2ec21-130">e ne è stato anche rimosso uno.</span><span class="sxs-lookup"><span data-stu-id="2ec21-130">You've also removed one as well.</span></span> <span data-ttu-id="2ec21-131">Salvare il file e digitare `dotnet run` per provare il codice.</span><span class="sxs-lookup"><span data-stu-id="2ec21-131">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="2ec21-132"><xref:System.Collections.Generic.List%601> consente di fare riferimento a singoli elementi anche in base all'**indice**.</span><span class="sxs-lookup"><span data-stu-id="2ec21-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="2ec21-133">Inserire l'indice tra i token `[` e `]` dopo il nome dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="2ec21-134">C# usa il valore 0 per il primo indice.</span><span class="sxs-lookup"><span data-stu-id="2ec21-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="2ec21-135">Aggiungere questo codice direttamente sotto il codice appena aggiunto e provarlo:</span><span class="sxs-lookup"><span data-stu-id="2ec21-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="2ec21-136">Non è possibile accedere a un indice oltre la fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="2ec21-137">Tenere presente che gli indici iniziano da 0, pertanto l'indice massimo valido è minore di un'unità rispetto al numero di elementi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="2ec21-138">È possibile controllare la lunghezza dell'elenco tramite la proprietà <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ec21-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="2ec21-139">Aggiungere il codice seguente alla fine del metodo Main:</span><span class="sxs-lookup"><span data-stu-id="2ec21-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="2ec21-140">Salvare il file e digitare di nuovo `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="2ec21-140">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="2ec21-141">Eseguire ricerche negli elenchi e ordinarli</span><span class="sxs-lookup"><span data-stu-id="2ec21-141">Search and sort lists</span></span>

<span data-ttu-id="2ec21-142">In questi esempi vengono usati elenchi relativamente piccoli, ma le applicazioni reali creano spesso elenchi con molti più elementi, a volte anche migliaia.</span><span class="sxs-lookup"><span data-stu-id="2ec21-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="2ec21-143">Per trovare elementi in raccolte di tali dimensioni, è necessario avere la possibilità di eseguire ricerche nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="2ec21-144">Il metodo <xref:System.Collections.Generic.List%601.IndexOf%2A> cerca un elemento e ne restituisce l'indice.</span><span class="sxs-lookup"><span data-stu-id="2ec21-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="2ec21-145">Aggiungere questo codice in fondo al metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ec21-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="2ec21-146">Gli elementi in un elenco possono anche essere ordinati.</span><span class="sxs-lookup"><span data-stu-id="2ec21-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="2ec21-147">Il metodo <xref:System.Collections.Generic.List%601.Sort%2A> ordina tutti gli elementi nell'elenco in base all'ordine normale (alfabetico nel caso delle stringhe).</span><span class="sxs-lookup"><span data-stu-id="2ec21-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="2ec21-148">Aggiungere questo codice in fondo al metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ec21-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="2ec21-149">Salvare il file e digitare `dotnet run` per provare quest'ultima versione.</span><span class="sxs-lookup"><span data-stu-id="2ec21-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="2ec21-150">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="2ec21-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="2ec21-151">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="2ec21-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="2ec21-152">Rinominare il metodo `Main` in `WorkingWithStrings` e scrivere un nuovo metodo `Main` che chiama `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="2ec21-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="2ec21-153">Al termine, il codice dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2ec21-153">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="2ec21-154">Elenchi di altri tipi</span><span class="sxs-lookup"><span data-stu-id="2ec21-154">Lists of other types</span></span>

<span data-ttu-id="2ec21-155">Finora è stato usato il tipo `string` negli elenchi.</span><span class="sxs-lookup"><span data-stu-id="2ec21-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="2ec21-156">Di seguito verrà creato un <xref:System.Collections.Generic.List%601> con un tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="2ec21-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="2ec21-157">Per iniziare, creare un set di numeri.</span><span class="sxs-lookup"><span data-stu-id="2ec21-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="2ec21-158">Aggiungere il codice seguente alla fine del nuovo metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ec21-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="2ec21-159">Questo codice crea un elenco di interi e imposta i primi due interi sul valore 1.</span><span class="sxs-lookup"><span data-stu-id="2ec21-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="2ec21-160">Questi sono i primi due valori di una *successione di Fibonacci*, ovvero una sequenza di numeri.</span><span class="sxs-lookup"><span data-stu-id="2ec21-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="2ec21-161">Ogni numero della successione di Fibonacci viene ottenuto dalla somma dei due numeri precedenti.</span><span class="sxs-lookup"><span data-stu-id="2ec21-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="2ec21-162">Aggiungere questo codice:</span><span class="sxs-lookup"><span data-stu-id="2ec21-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="2ec21-163">Salvare il file e digitare `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="2ec21-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="2ec21-164">Per concentrarsi solo su questa sezione, è possibile impostare come commento il codice che chiama `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="2ec21-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="2ec21-165">Inserire due caratteri `/` prima della chiamata come di seguito: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="2ec21-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="2ec21-166">Esercizio</span><span class="sxs-lookup"><span data-stu-id="2ec21-166">Challenge</span></span>

<span data-ttu-id="2ec21-167">È il momento di scoprire se è possibile mettere in pratica alcuni dei concetti appresi in questa lezione e in quelle precedenti.</span><span class="sxs-lookup"><span data-stu-id="2ec21-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="2ec21-168">Applicare i concetti appresi finora in relazione ai numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="2ec21-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="2ec21-169">Provare a scrivere il codice per generare i primi 20 numeri nella successione.</span><span class="sxs-lookup"><span data-stu-id="2ec21-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="2ec21-170">Tenere presente che il 20° numero di Fibonacci è 6765.</span><span class="sxs-lookup"><span data-stu-id="2ec21-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="2ec21-171">Completare l'esercizio</span><span class="sxs-lookup"><span data-stu-id="2ec21-171">Complete challenge</span></span>

<span data-ttu-id="2ec21-172">È possibile visualizzare una soluzione di esempio [esaminando il codice di esempio completato su GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)</span><span class="sxs-lookup"><span data-stu-id="2ec21-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="2ec21-173">A ogni iterazione del ciclo, gli ultimi due interi nell'elenco vengono sommati e il valore risultante viene aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="2ec21-174">Il ciclo viene ripetuto fino ad aggiungere 20 elementi all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ec21-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="2ec21-175">Complimenti, è stata completata questa esercitazione dedicata agli elenchi.</span><span class="sxs-lookup"><span data-stu-id="2ec21-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="2ec21-176">È possibile continuare con l'esercitazione [Introduzione alle classi](introduction-to-classes.md) nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="2ec21-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="2ec21-177">Altre informazioni sull'uso del tipo `List` sono disponibili nell'argomento della [Guida di .NET](../../../standard/index.md) dedicato alle [raccolte](../../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ec21-177">You can learn more about working with the `List` type in the [.NET Guide](../../../standard/index.md) topic on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="2ec21-178">Questo argomento include anche informazioni su molti altri tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="2ec21-178">You'll also learn about many other collection types.</span></span>