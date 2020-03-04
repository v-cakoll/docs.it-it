---
title: LINQ (Language Integrated Query)
description: Informazioni su come LINQ fornisce funzionalità di query a livello di linguaggio e un' C# API a e Visual Basic come modo per scrivere codice dichiarativo espressivo.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: eafd8f78c3d8de1ba064021111f869571d5a570f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160326"
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="0f9b4-103">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="0f9b4-103">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="0f9b4-104">Che cos'è?</span><span class="sxs-lookup"><span data-stu-id="0f9b4-104">What is it?</span></span>

<span data-ttu-id="0f9b4-105">LINQ fornisce funzionalità di query a livello di linguaggio e un'API di [funzione di ordine superiore](https://en.wikipedia.org/wiki/Higher-order_function) a C# e Visual Basic come modo per scrivere codice dichiarativo espressivo.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-105">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="0f9b4-106">Sintassi di query a livello di linguaggio:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-106">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

```vb
Dim linqExperts = From p in programmers
                  Where p.IsNewToLINQ
                  Select New LINQExpert(p)
```

<span data-ttu-id="0f9b4-107">Stesso esempio usando l'API `IEnumerable<T>`:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-107">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="0f9b4-108">LINQ è espressivo</span><span class="sxs-lookup"><span data-stu-id="0f9b4-108">LINQ is Expressive</span></span>

<span data-ttu-id="0f9b4-109">Si supponga di avere un elenco di animali domestici e di volerlo convertire in un dizionario nel quale sia possibile accedere a un animale selezionando direttamente il valore `RFID` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="0f9b4-110">Codice imperativo tradizionale:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-110">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

<span data-ttu-id="0f9b4-111">Scopo del codice non è creare un nuovo `Dictionary<int, Pet>` e aggiungerlo tramite un ciclo. Piuttosto è convertire un elenco esistente in un dizionario.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-111">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="0f9b4-112">A differenza del codice imperativo, LINQ consente di rispettare tale intenzione.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-112">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="0f9b4-113">Espressione LINQ equivalente:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-113">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="0f9b4-114">Il codice che usa LINQ è utile perché mette sullo stesso livello scopo e codice in fase di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="0f9b4-115">Un altro vantaggio del codice è il fatto che sia conciso.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-115">Another bonus is code brevity.</span></span> <span data-ttu-id="0f9b4-116">È infatti possibile ridurre parti prolisse della codebase di un 1/3 come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="0f9b4-117">Interessante, vero?</span><span class="sxs-lookup"><span data-stu-id="0f9b4-117">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="0f9b4-118">I provider LINQ semplificano l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="0f9b4-118">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="0f9b4-119">Per gran parte dei software in circostanze normali, tutto è basato sulla gestione dei dati da un'origine dati, ad esempio database, JSON, XML e così via.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="0f9b4-120">Spesso è necessario imparare a conoscere un'API nuova per ogni origine dati, operazione alquanto noiosa.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="0f9b4-121">LINQ semplifica tale processo estraendo gli elementi comuni di accesso ai dati in una sintassi di query simile indipendentemente dal tipo di origine dei dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-121">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="0f9b4-122">Nell'esempio seguente vengono individuati tutti gli elementi XML con un valore dell'attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-122">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function

```

<span data-ttu-id="0f9b4-123">Scrivere il codice per attraversare manualmente il documento XML ed eseguire tale operazione sarebbe più complicato.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-123">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="0f9b4-124">I provider LINQ non consentono solo di interagire con XML.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-124">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="0f9b4-125">[LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) è un Object-Relational Mapper (ORM) pressoché essenziale per un database del server MSSQL.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-125">[Linq to SQL](../../docs/framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="0f9b4-126">La libreria [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) consente l'attraversamento di un documento JSON tramite LINQ.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="0f9b4-127">Se invece non esiste una libreria adatta, è anche possibile [scrivere un provider LINQ personalizzato](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="0f9b4-127">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="0f9b4-128">Perché usare la sintassi di query?</span><span class="sxs-lookup"><span data-stu-id="0f9b4-128">Why Use the Query Syntax?</span></span>

<span data-ttu-id="0f9b4-129">È una domanda frequente.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-129">This is a question which often comes up.</span></span> <span data-ttu-id="0f9b4-130">Dopo tutto, questa sintassi</span><span class="sxs-lookup"><span data-stu-id="0f9b4-130">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="0f9b4-131">è molto più breve rispetto alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-131">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

```vb
Dim filteredItems = From item In myItems
                    Where item.Foo
                    Select item
```

<span data-ttu-id="0f9b4-132">La sintassi dell'API non è un modo più conciso per una sintassi di query?</span><span class="sxs-lookup"><span data-stu-id="0f9b4-132">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="0f9b4-133">No.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-133">No.</span></span> <span data-ttu-id="0f9b4-134">La sintassi di query consente l'uso della clausola **let** grazie alla quale è possibile introdurre e associare una variabile nell'ambito dell'espressione, usandola nelle parti successive dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-134">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="0f9b4-135">È possibile riprodurre lo stesso codice usando solo la sintassi dell'API, ma il codice risulterebbe di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-135">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="0f9b4-136">Una domanda sorge spontanea. **È consigliabile usare solo la sintassi di query?**</span><span class="sxs-lookup"><span data-stu-id="0f9b4-136">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="0f9b4-137">La risposta a questa domanda è **sì** se...</span><span class="sxs-lookup"><span data-stu-id="0f9b4-137">The answer to this question is **yes** if...</span></span>

* <span data-ttu-id="0f9b4-138">La codebase esistente usa già la sintassi di query</span><span class="sxs-lookup"><span data-stu-id="0f9b4-138">Your existing codebase already uses the query syntax</span></span>
* <span data-ttu-id="0f9b4-139">È necessario definire l'ambito delle variabili all'interno delle query per motivi di complessità</span><span class="sxs-lookup"><span data-stu-id="0f9b4-139">You need to scope variables within your queries due to complexity</span></span>
* <span data-ttu-id="0f9b4-140">Si preferisce la sintassi di query, che non si distaccherà dalla codebase</span><span class="sxs-lookup"><span data-stu-id="0f9b4-140">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="0f9b4-141">La risposta a questa domanda è **no** se...</span><span class="sxs-lookup"><span data-stu-id="0f9b4-141">The answer to this question is **no** if...</span></span>

* <span data-ttu-id="0f9b4-142">La codebase esistente usa già la sintassi dell'API</span><span class="sxs-lookup"><span data-stu-id="0f9b4-142">Your existing codebase already uses the API syntax</span></span>
* <span data-ttu-id="0f9b4-143">Non è necessario definire l'ambito delle variabili all'interno delle query</span><span class="sxs-lookup"><span data-stu-id="0f9b4-143">You have no need to scope variables within your queries</span></span>
* <span data-ttu-id="0f9b4-144">Si preferisce la sintassi dell'API, che non si distaccherà dalla codebase</span><span class="sxs-lookup"><span data-stu-id="0f9b4-144">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="0f9b4-145">Esempi significativi</span><span class="sxs-lookup"><span data-stu-id="0f9b4-145">Essential Samples</span></span>

<span data-ttu-id="0f9b4-146">Per un elenco completo di esempi di LINQ, vedere [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 esempi di LINQ).</span><span class="sxs-lookup"><span data-stu-id="0f9b4-146">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="0f9b4-147">Di seguito una rapida dimostrazione di alcune delle parti essenziali di LINQ.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-147">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="0f9b4-148">Non è affatto una dimostrazione completa, poiché LINQ offre molte più funzionalità rispetto a quanto viene illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-148">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

* <span data-ttu-id="0f9b4-149">Essenziali sono `Where`, `Select` e `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-149">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list.
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax.
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B.
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax.
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings.
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

```vb
' Filtering a list.
Dim germanShepards = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepard)

' Using the query syntax.
Dim queryGermanShepards = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepard
                          Select dog

' Mapping a list from type A to type B.
Dim cats = dogs.Select(Function(dog) dog.TurnIntoACat())

' Using the query syntax.
Dim queryCats = From dog In dogs
                Select dog.TurnIntoACat()

' Summing the lengths of a set of strings.
Dim seed As Integer = 0
Dim sumOfStrings As Integer = strings.Aggregate(seed, Function(s1, s2) s1.Length + s2.Length)
```

* <span data-ttu-id="0f9b4-150">Elenco di elenchi bidimensionale:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-150">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

* <span data-ttu-id="0f9b4-151">Unione tra due set, con criteri di confronto personalizzati:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-151">Union between two sets (with custom comparator):</span></span>

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
        // Default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels.
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

```vb
Public Class DogHairLengthComparer
  Inherits IEqualityComparer(Of Dog)

  Public Function Equals(a As Dog,b As Dog) As Boolean
      If a Is Nothing AndAlso b Is Nothing Then
          Return True
      ElseIf (a Is Nothing AndAlso b IsNot Nothing) OrElse (a IsNot Nothing AndAlso b Is Nothing) Then
          Return False
      Else
          Return a.HairLengthType = b.HairLengthType
      End If
  End Function

  Public Function GetHashCode(d As Dog) As Integer
      ' Default hashcode is enough here, as these are simple objects.
      Return d.GetHashCode()
  End Function
End Class

...

' Gets all the short-haired dogs between two different kennels.
Dim allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, New DogHairLengthComparer())
```

* <span data-ttu-id="0f9b4-152">Intersezione tra due set:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-152">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

```vb
' Gets the volunteers who spend share time with two humane societies.
Dim volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     New VolunteerTimeComparer())
```

* <span data-ttu-id="0f9b4-153">Ordinamento:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-153">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

```vb
' Get driving directions, ordering by if it's toll-free before estimated driving time.
Dim results = DirectionsProcessor.GetDirections(start, end).
                OrderBy(Function(direction) direction.HasNoTolls).
                ThenBy(Function(direction) direction.EstimatedTime)
```

* <span data-ttu-id="0f9b4-154">Infine, un esempio più avanzato: determinare se i valori delle proprietà di due istanze dello stesso tipo sono uguali. L'esempio è stato preso in prestito e modificato da [questo articolo di StackOverflow](https://stackoverflow.com/a/844855):</span><span class="sxs-lookup"><span data-stu-id="0f9b4-154">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self == null || to == null)
    {
        return self == to;
    }

    // Selects the properties which have unequal values into a sequence of those properties.
    var unequalProperties = from property in typeof(T).GetProperties(BindingFlags.Public | BindingFlags.Instance)
                            where !ignore.Contains(property.Name)
                            let selfValue = property.GetValue(self, null)
                            let toValue = property.GetValue(to, null)
                            where !Equals(selfValue, toValue)
                            select property;
    return !unequalProperties.Any();
}
```

```vb
<System.Runtime.CompilerServices.Extension()>
Public Function PublicInstancePropertiesEqual(Of T As Class)(self As T, [to] As T, ParamArray ignore As String()) As Boolean
    If self Is Nothing OrElse [to] Is Nothing Then
        Return self Is [to]
    End If

    ' Selects the properties which have unequal values into a sequence of those properties.
    Dim unequalProperties = From [property] In GetType(T).GetProperties(BindingFlags.Public Or BindingFlags.Instance)
                            Where Not ignore.Contains([property].Name)
                            Let selfValue = [property].GetValue(self, Nothing)
                            Let toValue = [property].GetValue([to], Nothing)
                            Where Not Equals(selfValue, toValue) Select [property]
    Return Not unequalProperties.Any()
End Function
```

## <a name="plinq"></a><span data-ttu-id="0f9b4-155">PLINQ</span><span class="sxs-lookup"><span data-stu-id="0f9b4-155">PLINQ</span></span>

<span data-ttu-id="0f9b4-156">PLINQ o Parallel LINQ è un motore di esecuzione parallela per le espressioni LINQ.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-156">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="0f9b4-157">In altre parole, un'espressione LINQ può essere facilmente parallelizzata su un numero qualsiasi di thread.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-157">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="0f9b4-158">Questa operazione viene eseguita chiamando `AsParallel()`, che precede l'espressione.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-158">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="0f9b4-159">Valutare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-159">Consider the following:</span></span>

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

```vb
Public Shared GetAllFacebookUserLikesMessage(facebookUsers As IEnumerable(Of FacebookUser)) As String
{
    Dim seed As UInt64 = 0

    Dim threadAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim threadResultAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim resultSelector As Func(Of Uint64, string) = Function(total) $"Facebook has {total} likes!"

    Return facebookUsers.AsParallel().
                        Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector)
}
```

<span data-ttu-id="0f9b4-160">Questo codice, se necessario, crea un partizione di `facebookUsers` tra i thread del sistema, somma i like totali su ogni thread in parallelo, somma i risultati calcolati da ogni thread e proietta il risultato in una stringa.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-160">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="0f9b4-161">Sotto forma di diagramma:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-161">In diagram form:</span></span>

![Diagramma PLINQ](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="0f9b4-163">I processi basati su CPU parallelizzabili che possono essere espressi facilmente tramite LINQ, quindi funzioni pure senza effetti collateri, sono i candidati ideali di PLINQ.</span><span class="sxs-lookup"><span data-stu-id="0f9b4-163">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="0f9b4-164">Per i processi _con_ effetti collaterali, è possibile usare [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="0f9b4-164">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="further-resources"></a><span data-ttu-id="0f9b4-165">Altre risorse:</span><span class="sxs-lookup"><span data-stu-id="0f9b4-165">Further Resources:</span></span>

* [<span data-ttu-id="0f9b4-166">101 esempi di LINQ</span><span class="sxs-lookup"><span data-stu-id="0f9b4-166">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
* <span data-ttu-id="0f9b4-167">[LINQPad](https://www.linqpad.net/), un ambiente Playground e un motore di query di C#databaseF#per//Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f9b4-167">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="0f9b4-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un e-book per scoprire come implementare LINQ-to-objects</span><span class="sxs-lookup"><span data-stu-id="0f9b4-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
