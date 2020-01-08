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
# <a name="work-with-language-integrated-query-linq"></a>Usare LINQ (Language-Integrated Query)

## <a name="introduction"></a>Introduzione

Questa esercitazione illustra le funzionalità disponibili in .NET Core e nel linguaggio C#. Scoprirai come eseguire queste operazioni:

- Generare sequenze con LINQ.
- Scrivere metodi che possono essere usati facilmente nelle query LINQ.
- Distinguere tra valutazione eager e Lazy.

Si apprenderanno queste tecniche creando un'applicazione che illustra una delle abilità di base di un prestigiatore: il [miscuglio faro](https://en.wikipedia.org/wiki/Faro_shuffle). In breve, il miscuglio faro è una tecnica che consiste nel tagliare un mazzo di carte esattamente a metà e quindi nel sovrapporre alternativamente le carte delle due metà per ricostruire il mazzo originale.

I prestigiatori adottano questa tecnica perché, dopo ogni miscuglio, ciascuna carta si trova in una posizione nota e le carte vengono ordinate in base a uno schema ripetitivo.

Ai fini dell'esercitazione, questa tecnica offre un modo scherzoso per illustrare la manipolazione di sequenze di dati. L'applicazione da compilare costruisce un mazzo di schede e quindi esegue una sequenza di shuffle, scrivendo ogni volta la sequenza. Si confronterà inoltre l'ordine aggiornato con quello originale.

Questa esercitazione prevede diversi passaggi. Dopo ogni passaggio, è possibile eseguire l'applicazione e verificare lo stato di avanzamento. È anche possibile vedere l'[esempio completo](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) disponibile nel repository dotnet/samples su GitHub. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET core. È possibile trovare le istruzioni di installazione nella pagina di [download di .NET Core](https://dotnet.microsoft.com/download) . È possibile eseguire questa applicazione in Windows, Ubuntu Linux o OS X oppure in un contenitore docker. È necessario installare l'editor di codice preferito. Le descrizioni seguenti usano [Visual Studio Code](https://code.visualstudio.com/) un editor multipiattaforma open source. ma è possibile usare gli strumenti con cui si ha maggiore familiarità.

## <a name="create-the-application"></a>Creare l'applicazione

Il primo passaggio consiste nel creare una nuova applicazione. Aprire un prompt dei comandi e creare una nuova directory per l'applicazione, impostandola come directory corrente. Digitare il comando `dotnet new console` al prompt dei comandi Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.

Se non si è mai usato C#, [questa esercitazione](console-teleprompter.md) illustra la struttura di un programma C#. È possibile leggerla e tornare qui per ottenere altre informazioni su LINQ.

## <a name="create-the-data-set"></a>Creare il set di dati

Prima di iniziare, verificare che le righe seguenti si trovino all'inizio del file `Program.cs` generato da `dotnet new console`:

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

Se queste tre righe (istruzioni `using`) non sono all'inizio del file, il programma non viene compilato.

Ora che si dispone di tutti i riferimenti necessari, considerare quali elementi costituiscono un mazzo di carte. Generalmente un mazzo di carte da gioco ha quattro semi, ognuno dei quali ha tredici valori. Normalmente si prenderebbe in considerazione l'idea di creare subito una classe `Card` e popolare una raccolta di oggetti `Card` manualmente. Ma con LINQ è possibile creare un mazzo di carte in maniera più concisa. Invece di creare una classe `Card`, è possibile creare due sequenze che rappresentino rispettivamente i semi e i valori. Si creerà una coppia molto semplice di [*metodi Iterator*](../iterators.md#enumeration-sources-with-iterator-methods) che genereranno i valori e i semi come interfacce <xref:System.Collections.Generic.IEnumerable%601> di stringhe:

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

Inserire questi metodi sotto il metodo `Main` nel file `Program.cs`. Questi due metodi usano entrambi la sintassi `yield return` per generare una sequenza durante l'esecuzione. Il compilatore crea un oggetto che implementa <xref:System.Collections.Generic.IEnumerable%601> e genera la sequenza di stringhe a mano a mano che vengono richieste.

Usare ora questi metodi Iterator per creare il mazzo di carte. Si inserirà la query LINQ nel metodo `Main`. Ecco come appare:

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

Le clausole `from` multiple generano un <xref:System.Linq.Enumerable.SelectMany%2A> che crea una singola sequenza tramite la combinazione di ogni elemento nella prima sequenza con ogni elemento nella seconda. L'ordine è importante ai fini di questa esercitazione. Il primo elemento nella prima sequenza di origine (semi) viene combinato con ogni elemento della seconda sequenza (valori). Si ottengono così le 13 carte appartenenti al primo seme. Il processo viene ripetuto con ogni elemento della prima sequenza, ovvero i semi. Il risultato finale è un mazzo di carte ordinato in base ai semi e quindi in base ai valori.

È importante tenere presente che, sia che si scelga di scrivere la query LINQ nella sintassi di query usata sopra o di usare invece la sintassi del metodo, è sempre possibile passare da un formato di sintassi all'altro. La query riportata sopra, scritta nella sintassi di query, può essere scritta nella sintassi del metodo nel modo seguente:

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

Il compilatore converte le istruzioni LINQ scritte con la sintassi di query nella sintassi del metodo equivalente. Pertanto, indipendentemente dalla sintassi scelta, le due versioni della query producono lo stesso risultato. Scegliere la sintassi più adatta per la propria situazione: ad esempio, se si lavora in un team in cui alcuni membri non hanno dimestichezza con la sintassi del metodo, preferire la sintassi di query.

Andare avanti ed eseguire l'esempio che si è creato finora. Verranno visualizzate le 52 carte del mazzo. Può essere molto utile eseguire questo esempio in un debugger per osservare come vengono eseguiti i metodi `Suits()` e `Ranks()`. È possibile vedere chiaramente che in ogni sequenza ciascuna stringa viene generata solo quando è necessario.

![Una finestra della console con l'app che scrive 52 carte.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulate-the-order"></a>Modificare l'ordine

A questo punto occorre concentrarsi sul modo in cui si mischieranno le carte nel mazzo. Il primo passaggio consiste nel tagliare il mazzo in due. I metodi <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> inclusi nelle API LINQ offrono questa funzionalità. Inserirli sotto il ciclo `foreach`:

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

Non esiste tuttavia un metodo per mischiare le carte nella libreria standard, quindi è necessario scriverne uno personalizzato. Il metodo che verrà creato illustra diverse tecniche che verranno usate con programmi basati su LINQ, quindi ogni parte di questo processo verrà spiegata in passaggi.

Per aggiungere alcune funzionalità per l'interazione con l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> che verrà restituita dalle query LINQ,è necessario scrivere dei tipi speciali di metodi detti [metodi di estensione](../programming-guide/classes-and-structs/extension-methods.md). In breve, un metodo di estensione è uno speciale *metodo statico* che aggiunge nuove funzionalità a un tipo già esistente senza bisogno di modificare il tipo originale a cui si vogliono aggiungere funzionalità.

Assegnare ai metodi di estensione una nuova posizione aggiungendo al programma un nuovo file di classe *statica* denominato `Extensions.cs`, quindi iniziare a compilare il primo metodo di estensione:

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

Osservare per un momento la firma del metodo, in particolare i parametri:

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

È possibile notare l'aggiunta del modificatore `this` nel primo argomento del metodo. Ciò significa che il metodo viene chiamato come se fosse un membro del tipo del primo argomento. Questa dichiarazione di metodo segue anche un termine standard in cui i tipi di input e output sono `IEnumerable<T>`. Ciò consente la concatenazione dei metodi LINQ per l'esecuzione di query più complesse.

Naturalmente, dato che il mazzo è stato diviso in due, occorrerà unire queste due metà. Nel codice questo significa enumerare entrambe le sequenze acquisite tramite <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> contemporaneamente, *`interleaving`* gli elementi e creare una sola sequenza, ossia il mazzo di carte ora mischiato. Per scrivere un metodo LINQ utilizzabile con le due sequenze è necessario comprendere il funzionamento di <xref:System.Collections.Generic.IEnumerable%601>.

L'interfaccia <xref:System.Collections.Generic.IEnumerable%601> ha un unico metodo: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>. L'oggetto restituito da <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> ha un metodo per passare all'elemento successivo e una proprietà che recupera l'elemento corrente nella sequenza. Si useranno questi due membri per enumerare la raccolta e restituire gli elementi. Questo metodo Interleave sarà un metodo iteratore. Di conseguenza, anziché creare una raccolta e restituirla, si userà la sintassi `yield return` mostrata in precedenza.

Questa è l'implementazione del metodo:

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

Dopo avere scritto questo metodo, tornare al metodo `Main` e mischiare una volta il mazzo:

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

## <a name="comparisons"></a>Confronti

Quante volte è necessario mischiare il mazzo per ripristinare l'ordine originale? Per scoprirlo è necessario scrivere un metodo che determina se due sequenze sono uguali. Una volta creato tale metodo, sarà necessario inserire in un ciclo il codice per mischiare il mazzo e verificare quando viene ripristinato l'ordine originale.

Scrivere un metodo per determinare se due sequenze sono uguali è un'operazione piuttosto intuitiva. La struttura è simile a quella del metodo usato per mischiare il mazzo. In questo caso, però, anziché eseguire un'istruzione `yield return` in ogni elemento, si confronteranno gli elementi corrispondenti di ogni sequenza. Al termine dell'enumerazione dell'intera sequenza, se ogni elemento corrisponde, le sequenze sono identiche:

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

Questo esempio illustra un secondo termine del linguaggio LINQ: i metodi terminali. Questi metodi accettano una sequenza come input (o, in questo caso, due sequenze) e restituiscono un singolo valore scalare. Quando si usa un metodo terminale, questo è sempre il metodo finale in una catena di metodi per una query LINQ, da qui il nome "terminale".

È possibile notare questo comportamento nella pratica quando si usa il metodo per determinare quando viene ripristinato l'ordine originale del mazzo. Inserire in un ciclo il codice per mischiare il mazzo e arrestare l'esecuzione quando viene ripristinato l'ordine originale della sequenza applicando il metodo `SequenceEquals()`. È possibile notare che questo sarebbe sempre il metodo finale in qualsiasi query poiché restituisce un singolo valore anziché una sequenza:

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

Eseguire il codice ottenuto fino a questo momento e prendere nota del modo in cui il mazzo viene riordinato ogni volta che viene mischiato. Dopo 8 volte (iterazioni del ciclo do-while), il mazzo torna alla configurazione originale che aveva quando è stato creato dalla query LINQ iniziale.

## <a name="optimizations"></a>Ottimizzazioni

L'esempio creato finora *mischia le carte esterne*, lasciando le carte in cima e in fondo al mazzo sempre nella stessa posizione, ma è possibile introdurre una variazione e *mischiare anche le carte interne*, cambiando la posizione di tutte e 52 le carte. Per mischiare il mazzo in questo modo, si alternano le carte in modo che la prima carta della metà inferiore diventi la prima carta del mazzo. Di conseguenza, l'ultima carta della metà superiore diventerà l'ultima carta del mazzo. Si tratta di una semplice modifica a una singola riga di codice. Aggiornare la query corrente scambiando le posizioni di <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A>. In questo modo si cambia l'ordine della metà superiore e di quella inferiore del mazzo:

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

Eseguire nuovamente il programma. Si noterà che il ripristino dell'ordine del mazzo richiede 52 iterazioni. Nel corso dell'esecuzione del programma si inizierà a notare anche un calo significativo delle prestazioni.

Questo problema può essere dovuto a vari motivi. Una delle cause principali di questo calo delle prestazioni consiste nell'uso inefficiente della [*valutazione lazy*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

In breve, la valutazione lazy indica che la valutazione di un'istruzione non viene eseguita finché il suo valore non è necessario. Le query LINQ sono istruzioni che vengono valutate in modalità lazy. Le sequenze vengono generate solo quando vengono richiesti gli elementi. Questo è in genere uno dei principali vantaggi di LINQ, ma in un programma di questo tipo può tradursi in una crescita esponenziale del tempo di esecuzione.

Tenere presente che il mazzo originale è stato generato con una query LINQ. e, ogni volta che si mischiano le carte, il mazzo viene generato eseguendo tre query LINQ sul mazzo precedente. Tutte queste operazioni sono eseguite in modalità lazy e quindi vengono ripetute ogni volta che è richiesta la sequenza. Quando si giunge alla cinquantaduesima iterazione, il mazzo originale è stato rigenerato un numero di volte molto elevato. Per comprendere più facilmente questo comportamento è possibile scrivere un log. Si potrà così correggere il problema.

Nel file `Extensions.cs` digitare o copiare il metodo riportato di seguito. Questo metodo di estensione crea un nuovo file denominato `debug.log` nella directory del progetto e registra la query attualmente in esecuzione nel file di log. Questo metodo di estensione può essere aggiunto a qualsiasi query per indicare che la query è stata eseguita.

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

Si noterà una sottolineatura ondulata rossa sotto `File`, per indicare che non esiste. Non viene compilato, perché il compilatore non riconosce `File`. Per risolvere questo problema, assicurarsi di aggiungere la seguente riga di codice sotto la prima riga in `Extensions.cs`:

```csharp
using System.IO;
```

Questo dovrebbe risolvere il problema e far scomparire l'indicatore di errore rosso.

Instrumentare quindi la definizione di ogni query con un messaggio di log:

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

Si noti che la registrazione non viene eseguita ogni volta che si accede a una query, ma solo quando si crea la query originale. L'esecuzione del programma richiede ancora molto tempo, ma ora si è individuato il motivo del problema. Se il tempo necessario per mischiare anche le carte interne con la registrazione attivata è eccessivo, limitarsi a mischiare quelle esterne. Gli effetti della valutazione lazy saranno ancora visibili. In un'unica esecuzione del programma verranno eseguite 2592 query, inclusa la generazione di tutti i semi e valori.

È possibile migliorare le prestazioni del codice per ridurre il numero di esecuzioni eseguite. Una semplice correzione consiste nel *memorizzare nella cache* i risultati della query LINQ originale che costruisce il mazzo di carte. Attualmente si rieseguono le query ad ogni iterazione del ciclo do-while, ricostruendo il mazzo di carte e rimescolandolo ogni volta. Per memorizzare il mazzo di carte nella cache, è possibile sfruttare i metodi LINQ <xref:System.Linq.Enumerable.ToArray%2A> e <xref:System.Linq.Enumerable.ToList%2A>. Accodandoli alle query, eseguiranno le stesse azioni per cui sono stati creati, ma ora archivieranno i risultati in una matrice o un elenco, a seconda del metodo che si è scelto di chiamare. Accodare il metodo LINQ <xref:System.Linq.Enumerable.ToArray%2A> a entrambe le query ed eseguire di nuovo il programma:

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

Ora il numero di query per mischiare le carte esterne è ridotto a 30. Eseguire nuovamente il programma per mischiare anche le carte interne e si noteranno miglioramenti analoghi: ora vengono eseguite 162 query.

Questo esempio è stato **progettato** per mettere in evidenza i casi d'uso in cui la valutazione lazy può causare problemi di prestazioni. Sebbene sia importante capire dove la valutazione lazy può influire sulle prestazioni del codice, è altrettanto importante comprendere che non tutte le query devono essere eseguite in modalità eager. La riduzione delle prestazioni che si verifica senza usare <xref:System.Linq.Enumerable.ToArray%2A> avviene perché ogni nuova configurazione del mazzo di carte è basata sulla configurazione precedente. Quando si usa la valutazione lazy, ogni nuova configurazione del mazzo è basata sul mazzo originale, anche eseguendo il codice che ha creato `startingDeck`. Questo comportamento determina una grande quantità di operazioni aggiuntive.

In pratica, per alcuni algoritmi è più efficiente la valutazione eager, mentre per altri è preferibile la valutazione lazy. Per l'uso quotidiano, quest'ultima rappresenta in genere la scelta migliore quando l'origine dati è costituita da un processo separato, ad esempio un motore di database. Per i database, la valutazione lazy consente alle query più complesse di eseguire un solo round trip al processo di database e di tornare al resto del codice. LINQ offre la stessa flessibilità sia che si scelga di usare la valutazione lazy o eager. Misurare pertanto i processi e scegliere il tipo di valutazione che offre le prestazioni migliori.

## <a name="conclusion"></a>Conclusione

In questo progetto sono stati illustrati gli argomenti seguenti:

- Uso di query LINQ per aggregare i dati in una sequenza significativa
- Scrittura di metodi di estensione per aggiungere funzionalità personalizzate alle query LINQ
- Individuazione delle aree del codice in cui le query LINQ potrebbero riscontrare problemi di prestazioni, ad esempio una riduzione della velocità
- Valutazione lazy e valutazione eager relativamente alle query LINQ e implicazioni che potrebbero avere sulle prestazioni delle query

Oltre a LINQ, è stata illustrata una tecnica usata dai prestigiatori per i trucchi con le carte. I prestigiatori usano il miscuglio Faro perché possono controllare lo spostamento di ogni carta nel mazzo. È una tecnica che, per mantenere la sua magia, dovrebbe restare nota a pochi.

Per altre informazioni su LINQ, vedere:

- [LINQ (Language-Integrated Query)](../programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ](../programming-guide/concepts/linq/index.md)
- [Operazioni di query LINQ di base (C#)](../programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Trasformazioni dati con LINQ (C#)](../programming-guide/concepts/linq/data-transformations-with-linq.md)
- [Sintassi di query e sintassi di metodi in LINQ (C#)](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
- [Funzionalità di C# che supportano LINQ](../programming-guide/concepts/linq/features-that-support-linq.md)
