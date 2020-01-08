---
title: Applicazione console
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 03/06/2017
ms.technology: csharp-fundamentals
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 0eb9883373484b72f771e0033936f56d00f9186d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346804"
---
# <a name="console-application"></a>Applicazione console

Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#. Verranno affrontati gli argomenti seguenti:

- Nozioni di base sull'interfaccia della riga di comando di .NET Core
- Struttura di un'applicazione console in C#
- Input/output della console
- Nozioni di base sulle API di I/O dei file in .NET
- Nozioni di base sul modello di programmazione asincrona delle attività in .NET

Verrà creata un'applicazione in grado di leggere un file di testo e restituire il contenuto del file alla console. La velocità di riproduzione dell'output della console verrà quindi configurata in modo da consentirne la lettura ad alta voce. È possibile aumentare o diminuire la velocità premendo il tasto < (minore di) o > (maggiore di).

In questa esercitazione verranno create anche numerose funzionalità.

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core. È possibile trovare le istruzioni di installazione nella pagina di [download di .NET Core](https://dotnet.microsoft.com/download) . Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.
È necessario installare l'editor di codice preferito.

## <a name="create-the-application"></a>Creare l'applicazione

Il primo passaggio consiste nel creare una nuova applicazione. Aprire un prompt dei comandi e creare una nuova directory per l'applicazione, impostandola come directory corrente. Digitare il comando `dotnet new console` al prompt dei comandi Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.

Prima di iniziare ad apportare modifiche, è opportuno ripercorrere i passaggi necessari per eseguire l'applicazione Hello World semplice. Dopo aver creato l'applicazione, digitare `dotnet restore` al prompt dei comandi. Questo comando esegue il processo di ripristino dei pacchetti NuGet. Lo strumento NuGet consente di gestire pacchetti .NET. Questo comando scarica eventuali dipendenze mancanti per il progetto. Poiché si tratta di un nuovo progetto, non è ancora presente alcuna dipendenza e con la prima esecuzione verrà quindi scaricato .NET Core Framework. Dopo questo passaggio iniziale, sarà sufficiente eseguire `dotnet restore` quando si aggiungono nuovi pacchetti dipendenti o si aggiorna la versione di una delle dipendenze.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Dopo aver ripristinato i pacchetti, eseguire `dotnet build` per avviare il motore di compilazione e creare il file eseguibile dell'applicazione. Eseguire infine `dotnet run` per avviare l'applicazione.

Il codice dell'applicazione Hello World semplice è tutto contenuto in Program.cs. Aprire il file con un editor di testo per effettuare subito le prime modifiche.
Nella parte iniziale del file è presente un'istruzione using:

```csharp
using System;
```

Questa istruzione indica al compilatore che qualsiasi tipo dello spazio dei nomi `System` rientra nell'ambito. Come altri linguaggi orientati agli oggetti, anche C# ricorre agli spazi dei nomi per organizzare i tipi. Il programma Hello World non è diverso. È possibile vedere che il programma è incluso nello spazio dei nomi con il nome basato sul nome della directory corrente. Per questa esercitazione, è necessario modificare il nome dello spazio dei nomi per `TeleprompterConsole`:

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a>Lettura e restituzione del file

La prima funzionalità da aggiungere è la capacità di leggere un file di testo e visualizzare tutto il testo nella console. Si aggiungerà innanzitutto un file di testo. Copiare il file [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) dal repository GitHub di questo [esempio](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) alla directory del progetto. Questo file verrà usato come script per l'applicazione. Per informazioni su come scaricare l'app di esempio per questo argomento, vedere le istruzioni nell'argomento [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Aggiungere quindi il metodo seguente alla classe `Program` (immediatamente sotto il metodo `Main`):

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

Questo metodo usa tipi provenienti da due nuovi spazi dei nomi. Per eseguirne la compilazione è necessario aggiungere le due righe seguenti all'inizio del file:

```csharp
using System.Collections.Generic;
using System.IO;
```

L'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è definita nello spazio dei nomi <xref:System.Collections.Generic>. La classe <xref:System.IO.File> è definita nello spazio dei nomi <xref:System.IO>.

Questo metodo è un tipo speciale di metodo C# denominato *metodo iteratore*.
I metodi enumeratore restituiscono sequenze che vengono valutate in modo differito. In altre parole, ogni elemento della sequenza viene generato nel momento in cui viene richiesto dal codice che utilizza la sequenza. I metodi enumeratore contengono una o più istruzioni [`yield return`](../language-reference/keywords/yield.md). L'oggetto restituito dal metodo `ReadFrom` contiene il codice per generare ogni elemento della sequenza. In questo esempio, ciò consiste nella lettura della riga di testo successiva dal file di origine e nella restituzione della stringa. Ogni volta che il codice chiamante richiede l'elemento successivo della sequenza, il codice legge la riga di testo successiva dal file e la restituisce. Quando il file è stato letto completamente, la sequenza indica che non sono presenti altri elementi.

Altri due elementi della sintassi C# possono risultare nuovi all'utente. L'istruzione [`using`](../language-reference/keywords/using-statement.md) gestisce la pulizia delle risorse in questo metodo. La variabile inizializzata nell'istruzione `using` (`reader`, in questo esempio) deve implementare l'interfaccia <xref:System.IDisposable>. Tale interfaccia definisce un singolo metodo, `Dispose`, che deve essere chiamato quando deve essere rilasciata la risorsa. Il compilatore genera la chiamata quando l'esecuzione raggiunge la parentesi graffa di chiusura dell'istruzione `using`. Il codice generato dal compilatore assicura che la risorsa venga rilasciata anche se viene generata un'eccezione dal codice nel blocco definito tramite l'istruzione using.

La variabile `reader` viene definita tramite la parola chiave `var`. [`var`](../language-reference/keywords/var.md) definisce una *variabile locale tipizzata in modo implicito*, ovvero il tipo della variabile è determinato dal tipo in fase di compilazione dell'oggetto assegnato alla variabile. In questo caso corrisponde al valore restituito dal metodo <xref:System.IO.File.OpenText(System.String)>, ovvero a un oggetto <xref:System.IO.StreamReader>.

Si compilerà ora il codice per leggere il file nel metodo `Main`:

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

Eseguire il programma, usando `dotnet run` in modo da poter visualizzare ogni riga visualizzata nella console.

## <a name="adding-delays-and-formatting-output"></a>Aggiunta di ritardi e formattazione dell'output

Il testo restituito viene visualizzato troppo velocemente per potere essere letto a voce alta. È quindi necessario aggiungere ritardi nell'output. Si inizierà creando codice di base che consenta l'elaborazione asincrona. Questi primi passaggi dovranno tuttavia seguire alcuni anti-pattern, evidenziati nei commenti mentre si aggiunge il codice, e il codice verrà aggiornato nei passaggi successivi.

Questa sezione è articolata in due fasi. Nella prima fase si aggiornerà il metodo iteratore in modo che restituisca singole parole anziché righe intere. A questo scopo è necessario apportare le modifiche seguenti. Sostituire la funzione `yield return line;` con il codice seguente:

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

Sarà quindi necessario modificare il modo in cui vengono usate le righe del file e aggiungere un ritardo dopo la scrittura di ogni parola. Sostituire l'istruzione `Console.WriteLine(line)` nel metodo `Main` con il blocco seguente:

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

La classe <xref:System.Threading.Tasks.Task> si trova nello spazio dei nomi <xref:System.Threading.Tasks> ed è quindi necessario aggiungere l'istruzione `using` all'inizio del file:

```csharp
using System.Threading.Tasks;
```

Eseguire l'esempio e verificare l'output. Ogni singola parola viene ora visualizzata, seguita da un ritardo di 200 ms. L'output visualizzato mostra tuttavia alcuni problemi perché il file di testo di origine presenta più righe con oltre 80 caratteri senza interruzione di riga, che possono risultare difficili da leggere durante lo scorrimento. Questo problema è facile da risolvere. Basta tenere traccia della durata di ogni riga e generare una nuova riga ogni volta che la lunghezza raggiunge una determinata soglia. Dichiarare una variabile locale dopo la dichiarazione di `words` nel metodo `ReadFrom` che contiene la lunghezza di riga:

```csharp
var lineLength = 0;
```

Aggiungere quindi il codice seguente dopo l'istruzione `yield return word + " ";` (prima della parentesi graffa di chiusura):

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

Eseguire l'esempio. Sarà possibile ora leggere ad alta voce alla velocità prestabilita.

## <a name="async-tasks"></a>Attività asincrone

In questa fase finale si aggiungerà il codice per scrivere l'output in modo asincrono in un'attività e si eseguirà anche un'altra attività per leggere l'input dell'utente, nel caso in cui si voglia accelerare o rallentare la visualizzazione del testo o arrestarla del tutto.
Sarà necessario eseguire alcuni passaggi ma, al termine, saranno implementati tutti gli aggiornamenti necessari.
Il primo passaggio consiste nel creare un metodo di restituzione asincrono <xref:System.Threading.Tasks.Task> che rappresenta il codice creato finora per leggere e visualizzare il file.

Aggiungere questo metodo alla classe `Program` (tratto dal corpo del metodo `Main`):

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

Si noteranno due modifiche. Nel corpo del metodo, anziché chiamare <xref:System.Threading.Tasks.Task.Wait> per attendere in modo sincrono il completamento di un'attività, questa versione usa la parola chiave `await`. A questo scopo, è necessario aggiungere il modificatore `async` alla firma del metodo. Il metodo restituisce `Task`. Osservare inoltre come non siano presenti istruzioni return che restituiscono un oggetto `Task`. L'oggetto `Task`, infatti, viene creato dal codice che il compilatore genera quando si usa l'operatore `await`. È possibile immaginare quindi che il metodo restituisca l'oggetto quando raggiunge la parola chiave `await`. L'oggetto `Task` restituito indica che il lavoro non è stato completato.
Il metodo riprende l'esecuzione quando viene completata l'attività attesa. Al termine dell'esecuzione, l'oggetto `Task` restituito indica che il lavoro è stato completato.
Il codice chiamante può monitorare l'oggetto `Task` restituito per determinare quando è stato completato.

È possibile chiamare questo nuovo metodo nel metodo `Main`:

```csharp
ShowTeleprompter().Wait();
```

Di seguito, nel metodo `Main`, il codice attende in modo sincrono. Quando possibile, è consigliabile usare l'operatore `await` anziché attendere in modo sincrono. Nel metodo `Main` di un'applicazione console, tuttavia, non è possibile usare l'operatore `await`. Questo comporterebbe infatti la chiusura dell'applicazione prima che siano state completate tutte le attività.

> [!NOTE]
> Se si usa C# 7,1 o versione successiva, è possibile creare applicazioni console con [`async` `Main` metodo](../whats-new/csharp-7-1.md#async-main).

È ora necessario scrivere il secondo metodo asincrono per leggere dalla console e verificare la presenza del tasto "<" (minore di), ">" (maggiore di), "X" o "x". Di seguito è illustrato il metodo da aggiungere per questa attività.

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
            {
                break;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

Si crea in questo modo un'espressione lambda per rappresentare un delegato <xref:System.Action> che legge un carattere dalla console e modifica una variabile locale che rappresenta il ritardo quando l'utente preme il tasto < (minore di) o > (maggiore di). Il metodo delegato termina quando l'utente preme il tasto "X" o "x", che permette all'utente di arrestare la visualizzazione del testo in qualsiasi momento.
Questo metodo usa <xref:System.Console.ReadKey> per bloccare l'operazione e attendere che l'utente prema un tasto.

Per completare questa funzionalità, è necessario creare un nuovo metodo di restituzione `async Task` in grado di avviare entrambe le attività (`GetInput` e `ShowTeleprompter`) e gestire i dati condivisi tra di esse.

A questo punto, occorre creare una classe in grado di gestire i dati condivisi tra le due attività. Questa classe contiene due proprietà pubbliche: il ritardo e un flag `Done` per indicare che il file è stato letto interamente:

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            DelayInMilliseconds = newDelay;
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

Inserire la classe in un nuovo file e includerla nello spazio dei nomi `TeleprompterConsole`, come illustrato in precedenza. Sarà inoltre necessario aggiungere un'istruzione `using static` in modo da poter fare riferimento ai metodi `Min` e `Max` anche senza conoscere il nome dello spazio dei nomi o della classe di inclusione. Un'istruzione [`using static`](../language-reference/keywords/using-static.md) importa i metodi da una classe. Questo comportamento è in contrasto con le istruzioni `using` usate finora che hanno importato tutte le classi da uno spazio dei nomi.

```csharp
using static System.Math;
```

Sarà quindi necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino il nuovo oggetto `config`. Scrivere un ultimo metodo `Task` di restituzione dell'oggetto `async`, in grado di avviare entrambe le attività e chiudere la prima attività nel momento in cui viene completata:

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

Il nuovo metodo qui è la chiamata <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>. In questo modo si crea un oggetto `Task` che termina non appena viene completata un'attività inclusa nel relativo elenco di argomenti.

È ora necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino l'oggetto `config` per il ritardo:

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
                config.SetDone();
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

Questa nuova versione di `ShowTeleprompter` chiama un nuovo metodo nella classe `TeleprompterConfig`. A questo punto, è necessario aggiornare `Main` affinché chiami `RunTeleprompter` anziché `ShowTeleprompter`:

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a>Conclusione

In questa esercitazione sono state illustrate diverse funzionalità del linguaggio C# e presentate le librerie .NET Core correlate all'uso di applicazioni console.
A partire da queste informazioni è possibile approfondire la conoscenza del linguaggio e delle classi presentate nell'esercitazione. Sono state inoltre fornite nozioni di base sulle operazioni di input/output del file e della console e sull'uso bloccante e non bloccante della programmazione asincrona basata sulle attività, è stata offerta una panoramica del linguaggio C# ed è stata descritta l'organizzazione dei programmi C# e degli strumenti e dell'interfaccia della riga di comando di .NET Core.

Per altre informazioni su I/O di file, consultare l'argomento [I/O di file e di flussi](../../standard/io/index.md). Per altre informazioni sul modello di programmazione asincrono usato in questa esercitazione, consultare l'argomento [Programmazione asincrona basata su attività](../..//standard/parallel-programming/task-based-asynchronous-programming.md) e l'argomento [Programmazione asincrona](../async.md).
