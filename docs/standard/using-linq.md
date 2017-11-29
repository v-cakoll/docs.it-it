---
title: LINQ (Language Integrated Query)
description: "Informazioni sul modo in cui LINQ offre funzionalità per eseguire query a livello di linguaggio e un'API per C# e VB che consente di scrivere codice dichiarativo ed espressivo."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 1478b5dc5844cef0abfea44eba88a12801d32bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="b4981-104">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b4981-104">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="b4981-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4981-105">What is it?</span></span>

<span data-ttu-id="b4981-106">LINQ offre funzionalità per eseguire query a livello di linguaggio e un'API con [funzione di ordine superiore](https://en.wikipedia.org/wiki/Higher-order_function) per C# e VB che consente di scrivere codice dichiarativo ed espressivo.</span><span class="sxs-lookup"><span data-stu-id="b4981-106">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and VB as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="b4981-107">Sintassi di query a livello di linguaggio:</span><span class="sxs-lookup"><span data-stu-id="b4981-107">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

<span data-ttu-id="b4981-108">Stesso esempio usando l'API `IEnumerable<T>`:</span><span class="sxs-lookup"><span data-stu-id="b4981-108">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a><span data-ttu-id="b4981-109">LINQ è espressivo</span><span class="sxs-lookup"><span data-stu-id="b4981-109">LINQ is Expressive</span></span>

<span data-ttu-id="b4981-110">Si supponga di avere un elenco di animali domestici e di volerlo convertire in un dizionario nel quale sia possibile accedere a un animale selezionando direttamente il valore `RFID` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b4981-110">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="b4981-111">Codice imperativo tradizionale:</span><span class="sxs-lookup"><span data-stu-id="b4981-111">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

<span data-ttu-id="b4981-112">Scopo del codice non è creare un nuovo `Dictionary<int, Pet>` e aggiungerlo tramite un ciclo. Piuttosto è convertire un elenco esistente in un dizionario.</span><span class="sxs-lookup"><span data-stu-id="b4981-112">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="b4981-113">A differenza del codice imperativo, LINQ consente di rispettare tale intenzione.</span><span class="sxs-lookup"><span data-stu-id="b4981-113">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="b4981-114">Espressione LINQ equivalente:</span><span class="sxs-lookup"><span data-stu-id="b4981-114">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

<span data-ttu-id="b4981-115">Il codice che usa LINQ è utile perché mette sullo stesso livello scopo e codice in fase di programmazione.</span><span class="sxs-lookup"><span data-stu-id="b4981-115">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="b4981-116">Un altro vantaggio del codice è il fatto che sia conciso.</span><span class="sxs-lookup"><span data-stu-id="b4981-116">Another bonus is code brevity.</span></span> <span data-ttu-id="b4981-117">È infatti possibile ridurre parti prolisse della codebase di un 1/3 come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b4981-117">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="b4981-118">Interessante, vero?</span><span class="sxs-lookup"><span data-stu-id="b4981-118">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="b4981-119">I provider LINQ semplificano l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="b4981-119">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="b4981-120">Per gran parte dei software in circostanze normali, tutto è basato sulla gestione dei dati da un'origine dati, ad esempio database, JSON, XML e così via.</span><span class="sxs-lookup"><span data-stu-id="b4981-120">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="b4981-121">Spesso è necessario imparare a conoscere un'API nuova per ogni origine dati, operazione alquanto noiosa.</span><span class="sxs-lookup"><span data-stu-id="b4981-121">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="b4981-122">LINQ semplifica tale processo estraendo gli elementi comuni di accesso ai dati in una sintassi di query simile indipendentemente dal tipo di origine dei dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="b4981-122">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="b4981-123">Nell'esempio seguente vengono individuati tutti gli elementi XML con un valore dell'attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="b4981-123">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

<span data-ttu-id="b4981-124">Scrivere il codice per attraversare manualmente il documento XML ed eseguire tale operazione sarebbe più complicato.</span><span class="sxs-lookup"><span data-stu-id="b4981-124">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="b4981-125">I provider LINQ non consentono solo di interagire con XML.</span><span class="sxs-lookup"><span data-stu-id="b4981-125">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="b4981-126">[LINQ to SQL](https://msdn.microsoft.com/library/bb386976.aspx) è un Object-Relational Mapper (ORM) pressoché essenziale per un database del server MSSQL.</span><span class="sxs-lookup"><span data-stu-id="b4981-126">[Linq to SQL](https://msdn.microsoft.com/library/bb386976.aspx) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="b4981-127">La libreria [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) consente l'attraversamento di un documento JSON tramite LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4981-127">The [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="b4981-128">Se invece non esiste una libreria adatta, è anche possibile [scrivere un provider LINQ personalizzato](https://msdn.microsoft.com/library/Bb546158.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4981-128">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://msdn.microsoft.com/library/Bb546158.aspx)!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="b4981-129">Perché usare la sintassi di query?</span><span class="sxs-lookup"><span data-stu-id="b4981-129">Why Use the Query Syntax?</span></span>

<span data-ttu-id="b4981-130">È una domanda frequente.</span><span class="sxs-lookup"><span data-stu-id="b4981-130">This is a question which often comes up.</span></span> <span data-ttu-id="b4981-131">Dopo tutto, questa sintassi</span><span class="sxs-lookup"><span data-stu-id="b4981-131">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

<span data-ttu-id="b4981-132">è molto più breve rispetto alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b4981-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

<span data-ttu-id="b4981-133">La sintassi dell'API non è un modo più conciso per una sintassi di query?</span><span class="sxs-lookup"><span data-stu-id="b4981-133">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="b4981-134">No.</span><span class="sxs-lookup"><span data-stu-id="b4981-134">No.</span></span> <span data-ttu-id="b4981-135">La sintassi di query consente di usare la clausola **let**, che consente di introdotta e associare una variabile nell'ambito dell'espressione, usandola nelle parti successive dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="b4981-135">The query syntax allows for the use the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="b4981-136">È possibile riprodurre lo stesso codice usando solo la sintassi dell'API, ma il codice risulterebbe di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="b4981-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="b4981-137">Una domanda sorge spontanea. **È consigliabile usare solo la sintassi di query?**</span><span class="sxs-lookup"><span data-stu-id="b4981-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="b4981-138">La risposta a questa domanda è **sì** se...</span><span class="sxs-lookup"><span data-stu-id="b4981-138">The answer to this question is **yes** if...</span></span>

*   <span data-ttu-id="b4981-139">La codebase esistente usa già la sintassi di query</span><span class="sxs-lookup"><span data-stu-id="b4981-139">Your existing codebase already uses the query syntax</span></span>
*   <span data-ttu-id="b4981-140">È necessario definire l'ambito delle variabili all'interno delle query per motivi di complessità</span><span class="sxs-lookup"><span data-stu-id="b4981-140">You need to scope variables within your queries due to complexity</span></span>
*   <span data-ttu-id="b4981-141">Si preferisce la sintassi di query, che non si distaccherà dalla codebase</span><span class="sxs-lookup"><span data-stu-id="b4981-141">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="b4981-142">La risposta a questa domanda è **no** se...</span><span class="sxs-lookup"><span data-stu-id="b4981-142">The answer to this question is **no** if...</span></span>

*   <span data-ttu-id="b4981-143">La codebase esistente usa già la sintassi dell'API</span><span class="sxs-lookup"><span data-stu-id="b4981-143">Your existing codebase already uses the API syntax</span></span>
*   <span data-ttu-id="b4981-144">Non è necessario definire l'ambito delle variabili all'interno delle query</span><span class="sxs-lookup"><span data-stu-id="b4981-144">You have no need to scope variables within your queries</span></span>
*   <span data-ttu-id="b4981-145">Si preferisce la sintassi dell'API, che non si distaccherà dalla codebase</span><span class="sxs-lookup"><span data-stu-id="b4981-145">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="b4981-146">Esempi significativi</span><span class="sxs-lookup"><span data-stu-id="b4981-146">Essential Samples</span></span>

<span data-ttu-id="b4981-147">Per un elenco completo di esempi di LINQ, vedere [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 esempi di LINQ).</span><span class="sxs-lookup"><span data-stu-id="b4981-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="b4981-148">Di seguito una rapida dimostrazione di alcune delle parti essenziali di LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4981-148">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="b4981-149">Non è affatto una dimostrazione completa, poiché LINQ offre molte più funzionalità rispetto a quanto viene illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b4981-149">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

*   <span data-ttu-id="b4981-150">Essenziali sono `Where`, `Select` e `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="b4981-150">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing then lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   <span data-ttu-id="b4981-151">Elenco di elenchi bidimensionale:</span><span class="sxs-lookup"><span data-stu-id="b4981-151">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   <span data-ttu-id="b4981-152">Unione tra due set, con criteri di confronto personalizzati:</span><span class="sxs-lookup"><span data-stu-id="b4981-152">Union between two sets (with custom comparator):</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // default hashcode is enough here, as these are simple objects.
        return b.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   <span data-ttu-id="b4981-153">Intersezione tra due set:</span><span class="sxs-lookup"><span data-stu-id="b4981-153">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   <span data-ttu-id="b4981-154">Ordinamento:</span><span class="sxs-lookup"><span data-stu-id="b4981-154">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   <span data-ttu-id="b4981-155">Infine, un esempio più avanzato: determinare se i valori delle proprietà di due istanze dello stesso tipo sono uguali. L'esempio è stato preso in prestito e modificato da [questo articolo di StackOverflow](http://stackoverflow.com/a/844855):</span><span class="sxs-lookup"><span data-stu-id="b4981-155">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](http://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self != null && to != null)
    {
        var type = typeof(T);
        var ignoreList = new List<string>(ignore);

        // Selects the properties which have unequal values into a sequence of those properties.
        var unequalProperties = from pi in type.GetProperties(BindingFlags.Public | BindingFlags.Instance)
                                where !ignoreList.Contains(pi.Name)
                                let selfValue = type.GetProperty(pi.Name).GetValue(self, null)
                                let toValue = type.GetProperty(pi.Name).GetValue(to, null)
                                where selfValue != toValue && (selfValue == null || !selfValue.Equals(toValue))
                                select new { Prop = pi.Name, selfValue, toValue };
        return !unequalProperties.Any();
    }

    return self == to;
}
```

## <a name="plinq"></a><span data-ttu-id="b4981-156">PLINQ</span><span class="sxs-lookup"><span data-stu-id="b4981-156">PLINQ</span></span>

<span data-ttu-id="b4981-157">PLINQ o Parallel LINQ è un motore di esecuzione parallela per le espressioni LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4981-157">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="b4981-158">In altre parole, un'espressione LINQ può essere facilmente parallelizzata su un numero qualsiasi di thread.</span><span class="sxs-lookup"><span data-stu-id="b4981-158">In other words, a regular LINQ expressions can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="b4981-159">Questa operazione viene eseguita chiamando `AsParallel()`, che precede l'espressione.</span><span class="sxs-lookup"><span data-stu-id="b4981-159">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="b4981-160">Si consideri quanto segue.</span><span class="sxs-lookup"><span data-stu-id="b4981-160">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

<span data-ttu-id="b4981-161">Questo codice, se necessario, crea un partizione di `facebookUsers` tra i thread del sistema, somma i like totali su ogni thread in parallelo, somma i risultati calcolati da ogni thread e proietta il risultato in una stringa.</span><span class="sxs-lookup"><span data-stu-id="b4981-161">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="b4981-162">Sotto forma di diagramma:</span><span class="sxs-lookup"><span data-stu-id="b4981-162">In diagram form:</span></span>

![Diagramma PLINQ](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="b4981-164">I processi basati su CPU parallelizzabili che possono essere espressi facilmente tramite LINQ, quindi funzioni pure senza effetti collateri, sono i candidati ideali di PLINQ.</span><span class="sxs-lookup"><span data-stu-id="b4981-164">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="b4981-165">Per i processi _con_ effetti collaterali, è possibile usare [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4981-165">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx).</span></span>

## <a name="further-resources"></a><span data-ttu-id="b4981-166">Altre risorse:</span><span class="sxs-lookup"><span data-stu-id="b4981-166">Further Resources:</span></span>

*   [<span data-ttu-id="b4981-167">101 esempi di LINQ</span><span class="sxs-lookup"><span data-stu-id="b4981-167">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   <span data-ttu-id="b4981-168">[Linqpad](https://www.linqpad.net/), un ambiente di sviluppo e un motore di query sul database per C#/F#/VB</span><span class="sxs-lookup"><span data-stu-id="b4981-168">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/VB</span></span>
*   <span data-ttu-id="b4981-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un e-book per scoprire come implementare LINQ-to-objects</span><span class="sxs-lookup"><span data-stu-id="b4981-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
