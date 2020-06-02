---
title: LINQ (Language Integrated Query)
description: Informazioni su come LINQ fornisce funzionalità di query a livello di linguaggio e un'API a C# e Visual Basic come modo per scrivere codice dichiarativo espressivo.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: cd0260de3facdd37c46e9fb2f09ddc4cac08e71b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291071"
---
# <a name="linq-language-integrated-query"></a>LINQ (Language Integrated Query)

## <a name="what-is-it"></a>Che cos'è?

LINQ fornisce funzionalità di query a livello di linguaggio e un'API di [funzione di ordine superiore](https://en.wikipedia.org/wiki/Higher-order_function) a C# e Visual Basic come modo per scrivere codice dichiarativo espressivo.

Sintassi di query a livello di linguaggio:

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

Stesso esempio usando l'API `IEnumerable<T>`:

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a>LINQ è espressivo

Si supponga di avere un elenco di animali domestici e di volerlo convertire in un dizionario nel quale sia possibile accedere a un animale selezionando direttamente il valore `RFID` corrispondente.

Codice imperativo tradizionale:

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

Scopo del codice non è creare un nuovo `Dictionary<int, Pet>` e aggiungerlo tramite un ciclo. Piuttosto è convertire un elenco esistente in un dizionario. A differenza del codice imperativo, LINQ consente di rispettare tale intenzione.

Espressione LINQ equivalente:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

Il codice che usa LINQ è utile perché mette sullo stesso livello scopo e codice in fase di programmazione. Un altro vantaggio del codice è il fatto che sia conciso. È infatti possibile ridurre parti prolisse della codebase di un 1/3 come illustrato in precedenza. Interessante, vero?

## <a name="linq-providers-simplify-data-access"></a>I provider LINQ semplificano l'accesso ai dati

Per gran parte dei software in circostanze normali, tutto è basato sulla gestione dei dati da un'origine dati, ad esempio database, JSON, XML e così via. Spesso è necessario imparare a conoscere un'API nuova per ogni origine dati, operazione alquanto noiosa. LINQ semplifica tale processo estraendo gli elementi comuni di accesso ai dati in una sintassi di query simile indipendentemente dal tipo di origine dei dati raccolti.

Nell'esempio seguente vengono individuati tutti gli elementi XML con un valore dell'attributo specifico.

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

Scrivere il codice per attraversare manualmente il documento XML ed eseguire tale operazione sarebbe più complicato.

I provider LINQ non consentono solo di interagire con XML. [LINQ to SQL](../framework/data/adonet/sql/linq/index.md) è un Object-Relational Mapper (ORM) pressoché essenziale per un database del server MSSQL. La libreria [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) consente l'attraversamento di un documento JSON tramite LINQ. Se invece non esiste una libreria adatta, è anche possibile [scrivere un provider LINQ personalizzato](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).

## <a name="why-use-the-query-syntax"></a>Perché usare la sintassi di query?

È una domanda frequente. Dopo tutto, questa sintassi

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

è molto più breve rispetto alla seguente:

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

La sintassi dell'API non è un modo più conciso per una sintassi di query?

No. La sintassi di query consente l'uso della clausola **let** grazie alla quale è possibile introdurre e associare una variabile nell'ambito dell'espressione, usandola nelle parti successive dell'espressione. È possibile riprodurre lo stesso codice usando solo la sintassi dell'API, ma il codice risulterebbe di difficile lettura.

Una domanda sorge spontanea. **È consigliabile usare solo la sintassi di query?**

La risposta a questa domanda è **sì** se...

* La codebase esistente usa già la sintassi di query
* È necessario definire l'ambito delle variabili all'interno delle query per motivi di complessità
* Si preferisce la sintassi di query, che non si distaccherà dalla codebase

La risposta a questa domanda è **no** se...

* La codebase esistente usa già la sintassi dell'API
* Non è necessario definire l'ambito delle variabili all'interno delle query
* Si preferisce la sintassi dell'API, che non si distaccherà dalla codebase

## <a name="essential-samples"></a>Esempi significativi

Per un elenco completo di esempi di LINQ, vedere [101 LINQ Samples](https://docs.microsoft.com/samples/dotnet/try-samples/101-linq-samples/) (101 esempi di LINQ).

Di seguito una rapida dimostrazione di alcune delle parti essenziali di LINQ. Non è affatto una dimostrazione completa, poiché LINQ offre molte più funzionalità rispetto a quanto viene illustrato di seguito.

* Essenziali sono `Where`, `Select` e `Aggregate`:

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

* Elenco di elenchi bidimensionale:

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

* Unione tra due set, con criteri di confronto personalizzati:

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

* Intersezione tra due set:

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

* Ordinamento:

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

* Infine, un esempio più avanzato: determinare se i valori delle proprietà di due istanze dello stesso tipo sono uguali. L'esempio è stato preso in prestito e modificato da [questo articolo di StackOverflow](https://stackoverflow.com/a/844855):

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

## <a name="plinq"></a>PLINQ

PLINQ o Parallel LINQ è un motore di esecuzione parallela per le espressioni LINQ. In altre parole, un'espressione LINQ può essere facilmente parallelizzata su un numero qualsiasi di thread. Questa operazione viene eseguita chiamando `AsParallel()`, che precede l'espressione.

Considerare quanto segue:

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

Questo codice, se necessario, crea un partizione di `facebookUsers` tra i thread del sistema, somma i like totali su ogni thread in parallelo, somma i risultati calcolati da ogni thread e proietta il risultato in una stringa.

Sotto forma di diagramma:

![Diagramma PLINQ](./media/using-linq/plinq-diagram.png)

I processi basati su CPU parallelizzabili che possono essere espressi facilmente tramite LINQ, quindi funzioni pure senza effetti collateri, sono i candidati ideali di PLINQ. Per i processi _con_ effetti collaterali, è possibile usare [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).

## <a name="further-resources"></a>Altre risorse:

* [101 esempi di LINQ](https://docs.microsoft.com/samples/dotnet/try-samples/101-linq-samples/)
* [LINQPad](https://www.linqpad.net/), un ambiente Playground e un motore di query di database per C#/F #/Visual Basic
* [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un e-book per scoprire come implementare LINQ-to-objects
