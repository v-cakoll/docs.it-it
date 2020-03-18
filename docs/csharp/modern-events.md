---
title: Schema di eventi .NET Core aggiornato
description: Informazioni su come lo schema di eventi .NET Core favorisca la flessibilità grazie alla compatibilità con le versioni precedenti e come implementare l'elaborazione sicura di eventi con sottoscrittori asincroni.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: c8858158ede761db8a3002beb26e521880f77feb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170436"
---
# <a name="the-updated-net-core-event-pattern"></a>Schema di eventi .NET Core aggiornato

[Indietro](event-pattern.md)

L'articolo precedente descriveva gli schemi di eventi più comuni. .NET Core ha uno schema più flessibile. In questa versione la definizione `EventHandler<TEventArgs>` non ha più il vincolo che prevede che `TEventArgs` deve essere una classe derivata da `System.EventArgs`.

Di conseguenza, la flessibilità è maggiore e viene offerta la compatibilità con le versioni precedenti. Si consideri innanzitutto la flessibilità. La classe System.EventArgs introduce un solo metodo: `MemberwiseClone()` che crea una copia superficiale dell'oggetto.
Il metodo deve usare la reflection per implementare la funzionalità per tutte le classi derivate da `EventArgs`. Tale funzionalità risulta più semplice da creare in una classe derivata specifica. Ciò significa che la derivazione da System.EventArgs è un vincolo che limita la progettazione e non offre altri vantaggi.
Infatti, è possibile modificare le definizioni di `FileFoundArgs` e `SearchDirectoryArgs` in modo che non derivino da `EventArgs`.
Il programma funzionerà esattamente allo stesso modo.

È anche possibile modificare `SearchDirectoryArgs` in uno struct se si esegue una modifica aggiuntiva:

```csharp
internal struct SearchDirectoryArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs) : this()
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
```

La modifica aggiuntiva consiste nell'effettuare una chiamata al costruttore senza parametri prima di specificare il costruttore che inizializza tutti i campi. Senza questa aggiunta, le regole del linguaggio C# segnalano un accesso alle proprietà precedente alla loro assegnazione.

Non modificare `FileFoundArgs` da classe (tipo riferimento) a struct (tipo valore) poiché il protocollo di gestione dell'annullamento richiede che gli argomenti degli eventi vengano passati per riferimento. Se è stata apportata la stessa modifica, la classe di ricerca file non potrà mai osservare le modifiche apportate da un sottoscrittore di eventi. Per ogni sottoscrittore verrà usata una nuova copia della struttura che sarà una copia diversa da quella vista dall'oggetto di ricerca file.

Si consideri quindi come questa modifica può essere compatibile con le versioni precedenti.
La rimozione del vincolo non ha effetto sul codice esistente. I tipi di argomento degli eventi esistenti derivano ancora da `System.EventArgs`.
La compatibilità con le versioni precedenti è uno dei motivi principali per cui continueranno a derivare da `System.EventArgs`. Tutti i sottoscrittori di eventi esistenti saranno sottoscrittori di un evento basato sul modello classico.

In base a una logica simile, tutti i tipi di argomento degli eventi creati non avranno sottoscrittori in alcuna codebase esistente. I nuovi tipi di evento che non derivano da `System.EventArgs` non interromperanno le codebase.

## <a name="events-with-async-subscribers"></a>Eventi con i sottoscrittori asincroni

L'ultimo modello da conoscere consiste nell'apprendere come scrivere sottoscrittori di eventi che effettuano chiamate a codice asincrono. Questa operazione è descritta nell'articolo relativo ad [async e await](async.md). Sebbene i metodi asincroni possano avere un tipo restituito void, questa procedura è fortemente sconsigliata. Quando il codice del sottoscrittore di eventi chiama un metodo asincrono, l'unica opzione consiste nel creare un metodo `async void`. Il metodo è necessario per la firma del gestore eventi.

Queste richieste contrastanti devono essere conciliate. In qualche modo, è necessario creare un metodo `async void` sicuro. I principi di base del modello da implementare sono i seguenti:

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

Si noti innanzitutto che il gestore è contrassegnato come gestore asincrono. Poiché viene assegnato al tipo delegato di un gestore eventi, avrà un tipo restituito void. Per questa ragione è necessario seguire il modello indicato nel gestore e non consentire la generazione di eccezioni dal contesto del gestore asincrono. Poiché non restituisce attività, non sarà presente alcuna attività che segnala l'errore attivando lo stato di errore. Poiché è asincrono, il metodo non può generare l'eccezione. (Il metodo chiamante ha `async`continuato l'esecuzione perché è .) Il comportamento di runtime effettivo verrà definito in modo diverso per ambienti diversi. Può terminare il thread o il processo proprietario del thread o lasciare il processo in uno stato indeterminato. Tutti questi potenziali risultati sono altamente indesiderabili.

Per questo motivo è necessario includere l'istruzione await per l'attività asincrona nel proprio blocco try. Se causa un'attività non riuscita, è possibile registrare l'errore. Se si tratta di un errore dal quale non è possibile ripristinare l'applicazione, è possibile uscire rapidamente dal programma.

Questi sono gli aggiornamenti più importanti per il modello di eventi .NET. Nelle librerie usate sono disponibili numerosi esempi delle versioni precedenti. È necessario tuttavia riconoscere i modelli più recenti.

L'articolo successivo descrive come distinguere l'uso di `delegates` e `events` nelle progettazioni. Si tratta di concetti simili e l'articolo risulterà utile per effettuare la scelta più adatta ai propri programmi.

[Avanti](distinguish-delegates-events.md)
