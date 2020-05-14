---
title: Indicizzatori
description: Informazioni sugli indicizzatori C# e su come implementano proprietà indicizzate, ovvero proprietà a cui si fa riferimento usando uno o più argomenti.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: e9b1cb18157982f068f1c1e4546e637f2bd707cb
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394691"
---
# <a name="indexers"></a><span data-ttu-id="d2482-103">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="d2482-103">Indexers</span></span>

<span data-ttu-id="d2482-104">Gli *indicizzatori* sono simili alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d2482-104">*Indexers* are similar to properties.</span></span> <span data-ttu-id="d2482-105">e per molti aspetti si basano sulle stesse funzionalità del linguaggio delle [proprietà](properties.md).</span><span class="sxs-lookup"><span data-stu-id="d2482-105">In many ways indexers build on the same language features as [properties](properties.md).</span></span> <span data-ttu-id="d2482-106">Gli indicizzatori consentono proprietà *indicizzate*, ovvero proprietà a cui si fa riferimento tramite uno o più argomenti,</span><span class="sxs-lookup"><span data-stu-id="d2482-106">Indexers enable *indexed* properties: properties referenced using one or more arguments.</span></span> <span data-ttu-id="d2482-107">che forniscono un indice per una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="d2482-107">Those arguments provide an index into some collection of values.</span></span>

## <a name="indexer-syntax"></a><span data-ttu-id="d2482-108">Sintassi degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="d2482-108">Indexer Syntax</span></span>

<span data-ttu-id="d2482-109">È possibile accedere a un indicizzatore tramite un nome di variabile e parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="d2482-109">You access an indexer through a variable name and square brackets.</span></span> <span data-ttu-id="d2482-110">Gli argomenti dell'indicizzatore devono trovarsi all'interno delle parentesi:</span><span class="sxs-lookup"><span data-stu-id="d2482-110">You place the indexer arguments inside the brackets:</span></span>

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

<span data-ttu-id="d2482-111">Per dichiarare un indicizzatore si usa la parola chiave `this` come nome di proprietà e si racchiudono gli argomenti tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="d2482-111">You declare indexers using the `this` keyword as the property name, and declaring the arguments within square brackets.</span></span> <span data-ttu-id="d2482-112">Questa dichiarazione corrisponde all'utilizzo illustrato nel paragrafo precedente:</span><span class="sxs-lookup"><span data-stu-id="d2482-112">This declaration would match the usage shown in the previous paragraph:</span></span>

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

<span data-ttu-id="d2482-113">Da questo esempio iniziale è possibile rendersi conto della relazione tra la sintassi relativa alle proprietà e a quella relativa agli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="d2482-113">From this initial example, you can see the relationship between the syntax for properties and for indexers.</span></span> <span data-ttu-id="d2482-114">Questa analogia si estende alla maggior parte delle regole della sintassi degli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="d2482-114">This analogy carries through most of the syntax rules for indexers.</span></span> <span data-ttu-id="d2482-115">Agli indicizzatori si possono applicare tutti i modificatori di accesso validi (public, protected internal, protected, internal, private o private protected).</span><span class="sxs-lookup"><span data-stu-id="d2482-115">Indexers can have any valid access modifiers (public, protected internal, protected, internal, private or private protected).</span></span> <span data-ttu-id="d2482-116">Possono essere sealed, virtual o abstract.</span><span class="sxs-lookup"><span data-stu-id="d2482-116">They may be sealed, virtual, or abstract.</span></span> <span data-ttu-id="d2482-117">Come per le proprietà, in un indicizzatore è possibile specificare modificatori di accesso diversi per le funzioni di accesso get e set.</span><span class="sxs-lookup"><span data-stu-id="d2482-117">As with properties, you can specify different access modifiers for the get and set accessors in an indexer.</span></span>
<span data-ttu-id="d2482-118">È anche possibile specificare indicizzatori di sola lettura (omettendo la funzione di accesso set) o indicizzatori di sola scrittura (omettendo la funzione di accesso get).</span><span class="sxs-lookup"><span data-stu-id="d2482-118">You may also specify read-only indexers (by omitting the set accessor), or write-only indexers (by omitting the get accessor).</span></span>

<span data-ttu-id="d2482-119">È possibile applicare agli indicizzatori quasi tutto ciò che si apprende dall'uso delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="d2482-119">You can apply almost everything you learn from working with properties to indexers.</span></span> <span data-ttu-id="d2482-120">L'unica eccezione a tale regola è costituita dalle *proprietà implementate automaticamente*.</span><span class="sxs-lookup"><span data-stu-id="d2482-120">The only exception to that rule is *auto implemented properties*.</span></span> <span data-ttu-id="d2482-121">Il compilatore non è sempre in grado di generare l'archiviazione corretta per un indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="d2482-121">The compiler cannot always generate the correct storage for an indexer.</span></span>

<span data-ttu-id="d2482-122">La differenza tra indicizzatori e proprietà è costituita dalla presenza negli indicizzatori di argomenti che consentono di fare riferimento a un elemento all'interno di un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="d2482-122">The presence of arguments to reference an item in a set of items distinguishes indexers from properties.</span></span> <span data-ttu-id="d2482-123">È possibile definire più indicizzatori in un tipo, a condizione che gli elenchi di argomenti per ogni indicizzatore siano univoci.</span><span class="sxs-lookup"><span data-stu-id="d2482-123">You may define multiple indexers on a type, as long as the argument lists for each indexer is unique.</span></span> <span data-ttu-id="d2482-124">Verranno ora esaminati diversi scenari in cui è possibile usare uno o più indicizzatori in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="d2482-124">Let's explore different scenarios where you might use one or more indexers in a class definition.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d2482-125">Scenari</span><span class="sxs-lookup"><span data-stu-id="d2482-125">Scenarios</span></span>

<span data-ttu-id="d2482-126">Si definiscono *indicizzatori* in un tipo se l'API corrispondente modella una raccolta per cui si definiscono gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d2482-126">You would define *indexers* in your type when its API models some collection where you define the arguments to that collection.</span></span> <span data-ttu-id="d2482-127">Gli indicizzatori possono essere mappati direttamente o meno ai tipi di raccolta che fanno parte di .NET Framework Core.</span><span class="sxs-lookup"><span data-stu-id="d2482-127">Your indexers may or may not map directly to the collection types that are part of the .NET core framework.</span></span> <span data-ttu-id="d2482-128">Oltre alla modellazione di una raccolta, il tipo può avere altre responsabilità.</span><span class="sxs-lookup"><span data-stu-id="d2482-128">Your type may have other responsibilities in addition to modeling a collection.</span></span>
<span data-ttu-id="d2482-129">Gli indicizzatori consentono di fornire l'API corrispondente all'astrazione del tipo senza esporre nei minimi dettagli la modalità di archiviazione o di calcolo dei valori per tale astrazione.</span><span class="sxs-lookup"><span data-stu-id="d2482-129">Indexers enable you to provide the API that matches your type's abstraction without exposing the inner details of how the values for that abstraction are stored or computed.</span></span>

<span data-ttu-id="d2482-130">Di seguito è riportata la descrizione dettagliata di alcuni scenari comuni per l'uso di *indicizzatori*.</span><span class="sxs-lookup"><span data-stu-id="d2482-130">Let's walk through some of the common scenarios for using *indexers*.</span></span> <span data-ttu-id="d2482-131">È possibile accedere alla [cartella degli esempi per gli indicizzatori](https://github.com/dotnet/samples/tree/master/csharp/indexers).</span><span class="sxs-lookup"><span data-stu-id="d2482-131">You can access the [sample folder for indexers](https://github.com/dotnet/samples/tree/master/csharp/indexers).</span></span> <span data-ttu-id="d2482-132">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="d2482-132">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="arrays-and-vectors"></a><span data-ttu-id="d2482-133">Matrici e vettori</span><span class="sxs-lookup"><span data-stu-id="d2482-133">Arrays and Vectors</span></span>

<span data-ttu-id="d2482-134">Uno degli scenari più comuni per la creazione di indicizzatori si presenta quando il tipo modella una matrice o un vettore.</span><span class="sxs-lookup"><span data-stu-id="d2482-134">One of the most common scenarios for creating indexers is when your type models an array, or a vector.</span></span> <span data-ttu-id="d2482-135">È possibile creare un indicizzatore per modellare un elenco ordinato di dati.</span><span class="sxs-lookup"><span data-stu-id="d2482-135">You can create an indexer to model an ordered list of data.</span></span>

<span data-ttu-id="d2482-136">Il vantaggio di creare un indicizzatore personalizzato è la possibilità di definire la modalità di archiviazione della raccolta più adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d2482-136">The advantage of creating your own indexer is that you can define the storage for that collection to suit your needs.</span></span> <span data-ttu-id="d2482-137">Si immagini uno scenario in cui il tipo debba modellare una quantità di dati cronologici troppo grande perché sia possibile caricarla in memoria in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d2482-137">Imagine a scenario where your type models historical data that is too large to load into memory at once.</span></span> <span data-ttu-id="d2482-138">È quindi necessario caricare e scaricare sezioni della raccolta in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d2482-138">You need to load and unload sections of the collection based on usage.</span></span> <span data-ttu-id="d2482-139">L'esempio seguente riproduce questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="d2482-139">The example following models this behavior.</span></span> <span data-ttu-id="d2482-140">L'esempio indica il numero di punti dati esistenti,</span><span class="sxs-lookup"><span data-stu-id="d2482-140">It reports on how many data points exist.</span></span> <span data-ttu-id="d2482-141">crea pagine in cui inserire sezioni di dati su richiesta</span><span class="sxs-lookup"><span data-stu-id="d2482-141">It creates pages to hold sections of the data on demand.</span></span> <span data-ttu-id="d2482-142">e rimuove le pagine dalla memoria per liberare spazio per le pagine relative alle richieste più recenti.</span><span class="sxs-lookup"><span data-stu-id="d2482-142">It removes pages from memory to make room for pages needed by more recent requests.</span></span>

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

<span data-ttu-id="d2482-143">È possibile seguire questo schema di progettazione per modellare qualsiasi funzione di ordinamento di una raccolta nei casi in cui per validi motivi non è possibile caricare l'intero set di dati in una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="d2482-143">You can follow this design idiom to model any sort of collection where there are good reasons not to load the entire set of data into an in- memory collection.</span></span> <span data-ttu-id="d2482-144">Si noti che la classe `Page` è una classe annidata private che non fa parte dell'interfaccia public.</span><span class="sxs-lookup"><span data-stu-id="d2482-144">Notice that the `Page` class is a private nested class that is not part of the public interface.</span></span> <span data-ttu-id="d2482-145">Questi dettagli sono nascosti agli utenti di questa classe.</span><span class="sxs-lookup"><span data-stu-id="d2482-145">Those details are hidden from any users of this class.</span></span>

### <a name="dictionaries"></a><span data-ttu-id="d2482-146">Dizionari</span><span class="sxs-lookup"><span data-stu-id="d2482-146">Dictionaries</span></span>

<span data-ttu-id="d2482-147">Un altro scenario comune riguarda la necessità di modellare un dizionario o una mappa</span><span class="sxs-lookup"><span data-stu-id="d2482-147">Another common scenario is when you need to model a dictionary or a map.</span></span> <span data-ttu-id="d2482-148">e si presenta quando il tipo archivia i valori in base alla chiave, in genere chiavi di testo.</span><span class="sxs-lookup"><span data-stu-id="d2482-148">This scenario is when your type stores values based on key, typically text keys.</span></span> <span data-ttu-id="d2482-149">Questo esempio crea un dizionario che esegue il mapping di argomenti della riga di comando a [espressioni lambda](delegates-overview.md) che gestiscono tali opzioni.</span><span class="sxs-lookup"><span data-stu-id="d2482-149">This example creates a dictionary that maps command line arguments to [lambda expressions](delegates-overview.md) that manage those options.</span></span> <span data-ttu-id="d2482-150">Nell'esempio seguente sono presenti due classi: una classe `ArgsActions` che esegue il mapping di un'opzione della riga di comando a un delegato `Action` e una classe `ArgsProcessor` che usa `ArgsActions` per eseguire ogni `Action` quando incontra tale opzione.</span><span class="sxs-lookup"><span data-stu-id="d2482-150">The following example shows two classes: an `ArgsActions` class that maps a command line option to an `Action` delegate, and an `ArgsProcessor` that uses the `ArgsActions` to execute each `Action` when it encounters that option.</span></span>

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

<span data-ttu-id="d2482-151">In questo esempio la raccolta `ArgsAction` è strettamente mappata alla raccolta sottostante.</span><span class="sxs-lookup"><span data-stu-id="d2482-151">In this example, the `ArgsAction` collection maps closely to the underlying collection.</span></span>
<span data-ttu-id="d2482-152">La funzione `get` determina se un'opzione specifica è stata configurata.</span><span class="sxs-lookup"><span data-stu-id="d2482-152">The `get` determines if a given option has been configured.</span></span> <span data-ttu-id="d2482-153">In caso affermativo, viene restituito l'oggetto `Action` associato a tale opzione.</span><span class="sxs-lookup"><span data-stu-id="d2482-153">If so, it returns the `Action` associated with that option.</span></span> <span data-ttu-id="d2482-154">In caso contrario, restituisce un oggetto `Action` che non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d2482-154">If not, it returns an `Action` that does nothing.</span></span> <span data-ttu-id="d2482-155">La funzione di accesso public non include una funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="d2482-155">The public accessor does not include a `set` accessor.</span></span> <span data-ttu-id="d2482-156">Per l'impostazione di opzioni la progettazione usa invece un metodo public.</span><span class="sxs-lookup"><span data-stu-id="d2482-156">Rather, the design using a public method for setting options.</span></span>

### <a name="multi-dimensional-maps"></a><span data-ttu-id="d2482-157">Mappe multidimensionali</span><span class="sxs-lookup"><span data-stu-id="d2482-157">Multi-Dimensional Maps</span></span>

<span data-ttu-id="d2482-158">È possibile creare indicizzatori che usano più argomenti,</span><span class="sxs-lookup"><span data-stu-id="d2482-158">You can create indexers that use multiple arguments.</span></span> <span data-ttu-id="d2482-159">che, in più, non devono necessariamente essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="d2482-159">In addition, those arguments are not constrained to be the same type.</span></span> <span data-ttu-id="d2482-160">Di seguito sono riportati due esempi.</span><span class="sxs-lookup"><span data-stu-id="d2482-160">Let's look at two examples.</span></span>

<span data-ttu-id="d2482-161">Il primo esempio illustra una classe che genera valori per un set di Mandelbrot.</span><span class="sxs-lookup"><span data-stu-id="d2482-161">The first example shows a class that generates values for a Mandelbrot set.</span></span> <span data-ttu-id="d2482-162">Per altre informazioni sulle regole matematiche alla base di questo, leggere [questo articolo](https://en.wikipedia.org/wiki/Mandelbrot_set).</span><span class="sxs-lookup"><span data-stu-id="d2482-162">For more information on the mathematics behind the set, read [this article](https://en.wikipedia.org/wiki/Mandelbrot_set).</span></span>
<span data-ttu-id="d2482-163">L'indicizzatore usa due valori double per definire un punto del piano X, Y.</span><span class="sxs-lookup"><span data-stu-id="d2482-163">The indexer uses two doubles to define a point in the X, Y plane.</span></span>
<span data-ttu-id="d2482-164">La funzione di accesso get calcola il numero di iterazioni necessarie a stabilire che un punto non appartiene al set.</span><span class="sxs-lookup"><span data-stu-id="d2482-164">The get accessor computes the number of iterations until a point is determined to be not in the set.</span></span> <span data-ttu-id="d2482-165">Se viene raggiunto il numero massimo di iterazioni, il punto si trova nel set e viene restituito il valore maxIterations della classe.</span><span class="sxs-lookup"><span data-stu-id="d2482-165">If the maximum iterations is reached, the point is in the set, and the class's maxIterations value is returned.</span></span> <span data-ttu-id="d2482-166">Nelle immagini generate tramite computer comunemente note per il set di Mandelbrot sono definiti colori per il numero di iterazioni necessarie a determinare se un punto è esterno al set.</span><span class="sxs-lookup"><span data-stu-id="d2482-166">(The computer generated images popularized for the Mandelbrot set define colors for the number of iterations necessary to determine that a point is outside the set.</span></span>

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

<span data-ttu-id="d2482-167">Il set di Mandelbrot definisce valori in corrispondenza di ogni coordinata (x, y) per valori di numeri reali.</span><span class="sxs-lookup"><span data-stu-id="d2482-167">The Mandelbrot Set defines values at every (x,y) coordinate for real number values.</span></span>
<span data-ttu-id="d2482-168">Ciò consente di definire un dizionario che può contenere un numero infinito di valori.</span><span class="sxs-lookup"><span data-stu-id="d2482-168">That defines a dictionary that could contain an infinite number of values.</span></span> <span data-ttu-id="d2482-169">Pertanto, il set non prevede alcuna archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d2482-169">Therefore, there is no storage behind the set.</span></span> <span data-ttu-id="d2482-170">Questa classe calcola invece un valore per ogni punto in cui il codice chiama la funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="d2482-170">Instead, this class computes the value for each point when code calls the `get` accessor.</span></span> <span data-ttu-id="d2482-171">Non viene usata alcuna archiviazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="d2482-171">There's no underlying storage used.</span></span>

<span data-ttu-id="d2482-172">Verrà ora illustrato l'ultimo caso di uso degli indicizzatori, in cui l'indicizzatore riceve più argomenti di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="d2482-172">Let's examine one last use of indexers, where the indexer takes multiple arguments of different types.</span></span> <span data-ttu-id="d2482-173">Si consideri un programma per la gestione dei dati cronologici relativi alle temperature.</span><span class="sxs-lookup"><span data-stu-id="d2482-173">Consider a program that manages historical temperature data.</span></span> <span data-ttu-id="d2482-174">Questo indicizzatore imposta o riceve la temperatura massima e la temperatura minima di una determinata posizione in base alla città corrispondente e alla data:</span><span class="sxs-lookup"><span data-stu-id="d2482-174">This indexer uses a city and a date to set or get the high and low temperatures for that location:</span></span>

```csharp
using DateMeasurements =
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements =
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

<span data-ttu-id="d2482-175">Questo esempio crea un indicizzatore che esegue il mapping di dati meteo a due diversi argomenti: una città (rappresentata da un valore `string`) e una data (rappresentata da un valore `DateTime`).</span><span class="sxs-lookup"><span data-stu-id="d2482-175">This example creates an indexer that maps weather data on two different arguments: a city (represented by a `string`) and a date (represented by a `DateTime`).</span></span> <span data-ttu-id="d2482-176">Per l'archiviazione interna vengono usate due classi `Dictionary` che rappresentano il dizionario bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="d2482-176">The internal storage uses two `Dictionary` classes to represent the two-dimensional dictionary.</span></span> <span data-ttu-id="d2482-177">L'API public non rappresenta più l'archiviazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="d2482-177">The public API no longer represents the underlying storage.</span></span> <span data-ttu-id="d2482-178">Le funzionalità del linguaggio relative agli indicizzatori consentono di creare un'interfaccia public che rappresenta l'astrazione, anche se l'archiviazione sottostante deve usare tipi di raccolta principale diversi.</span><span class="sxs-lookup"><span data-stu-id="d2482-178">Rather, the language features of indexers enables you to create a public interface that represents your abstraction, even though the underlying storage must use different core collection types.</span></span>

<span data-ttu-id="d2482-179">Due parti del codice potrebbero risultare poco chiare per alcuni sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="d2482-179">There are two parts of this code that may be unfamiliar to some developers.</span></span> <span data-ttu-id="d2482-180">Queste due `using` direttive:</span><span class="sxs-lookup"><span data-stu-id="d2482-180">These two `using` directives:</span></span>

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

<span data-ttu-id="d2482-181">creano un *alias* per un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="d2482-181">create an *alias* for a constructed generic type.</span></span> <span data-ttu-id="d2482-182">Queste istruzioni consentono al codice successivo di usare i nomi `DateMeasurements` e `CityDateMeasurements`, più descrittivi, anziché la costruzione generica di `Dictionary<DateTime, Measurements>` e `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span><span class="sxs-lookup"><span data-stu-id="d2482-182">Those statements enable the code later to use the more descriptive `DateMeasurements` and `CityDateMeasurements` names instead of the generic construction of `Dictionary<DateTime, Measurements>` and `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span></span>
<span data-ttu-id="d2482-183">Questo costrutto richiede però l'uso di nomi completi di tipo sul lato destro del segno `=`.</span><span class="sxs-lookup"><span data-stu-id="d2482-183">This construct does require using the fully qualified type names on the right side of the `=` sign.</span></span>

<span data-ttu-id="d2482-184">La seconda tecnica consiste nel rimuovere le parti relative all'ora di qualsiasi oggetto `DateTime` usato per effettuare l'indicizzazione all'interno delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="d2482-184">The second technique is to strip off the time portions of any `DateTime` object used to index into the collections.</span></span> <span data-ttu-id="d2482-185">.NET non include un tipo di solo data.</span><span class="sxs-lookup"><span data-stu-id="d2482-185">.NET doesn't include a date-only type.</span></span>
<span data-ttu-id="d2482-186">Gli sviluppatori usano il tipo `DateTime`, ma usano la proprietà `Date` per assicurarsi che tutti gli oggetti `DateTime` di quel giorno siano uguali.</span><span class="sxs-lookup"><span data-stu-id="d2482-186">Developers use the `DateTime` type, but use the `Date` property to ensure that any `DateTime` object from that day are equal.</span></span>

## <a name="summing-up"></a><span data-ttu-id="d2482-187">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="d2482-187">Summing Up</span></span>

<span data-ttu-id="d2482-188">È necessario creare indicizzatori ogni volta che all'interno di una classe è presente un elemento analogo a una proprietà e tale proprietà rappresenta non un singolo valore, ma una raccolta di valori in cui ogni singolo elemento è identificato da un set di argomenti.</span><span class="sxs-lookup"><span data-stu-id="d2482-188">You should create indexers anytime you have a property-like element in your class where that property represents not a single value, but rather a collection of values where each individual item is identified by a set of arguments.</span></span> <span data-ttu-id="d2482-189">Tali argomenti consentono di identificare in modo univoco un elemento della raccolta a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="d2482-189">Those arguments can uniquely identify which item in the collection should be referenced.</span></span>
<span data-ttu-id="d2482-190">Gli indicizzatori estendono il concetto di [Proprietà](properties.md), in cui un membro viene considerato come un elemento dati dall'esterno della classe, ma come un metodo all'interno.</span><span class="sxs-lookup"><span data-stu-id="d2482-190">Indexers extend the concept of [properties](properties.md), where a member is treated like a data item from outside the class, but like a method on the inside.</span></span> <span data-ttu-id="d2482-191">Gli indicizzatori consentono agli argomenti di individuare un singolo elemento all'interno di una proprietà che rappresenta un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="d2482-191">Indexers allow arguments to find a single item in a property that represents a set of items.</span></span>
