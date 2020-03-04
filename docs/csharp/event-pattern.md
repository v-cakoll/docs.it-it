---
title: Schemi di eventi .NET standard
description: Informazioni sugli schemi di eventi .NET standard e su come creare origini eventi standard e sottoscrivere ed elaborare gli eventi standard nel codice.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: 517e46ffec163a9bd49baa58fc0b37b54b2b2809
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239859"
---
# <a name="standard-net-event-patterns"></a>Schemi di eventi .NET standard

[Indietro](events-overview.md)

Gli eventi .NET seguono in genere alcuni schemi noti. Questi schemi standard facilitano il lavoro agli sviluppatori in quanto possono essere applicati a qualsiasi programma che usa eventi .NET.

Esamineremo questi schemi standard presentando tutte le informazioni necessarie per creare origini evento standard e per sottoscrivere ed elaborare gli eventi standard nel codice.

## <a name="event-delegate-signatures"></a>Firme di delegati di eventi

La firma standard per un delegato di evento .NET è:

```csharp
void OnEventRaised(object sender, EventArgs args);
```

Il tipo restituito è void. Gli eventi sono basati su delegati e sono delegati multicast. Sono supportati più sottoscrittori per ogni origine evento. Il singolo valore restituito da un metodo non viene ridimensionato per più sottoscrittori di eventi. Qual è il valore restituito che l'origine evento vede dopo avere generato un evento? Più avanti in questo articolo si vedrà come creare protocolli di evento che supportano sottoscrittori di eventi che segnalano informazioni all'origine evento.

Gli argomenti sono due: mittente e argomenti evento. Il tipo di `sender` della fase di compilazione è `System.Object`, anche se si conosce probabilmente un tipo più derivato che va sempre bene. Per convenzione si usa `object`.

Il secondo argomento era in genere un tipo derivato da `System.EventArgs`. Nella [sezione successiva](modern-events.md) si vedrà che questa convenzione non viene più applicata. Se il tipo di evento non necessita di argomenti aggiuntivi, saranno comunque disponibili entrambi gli argomenti.
È previsto un valore speciale, `EventArgs.Empty`, che si deve usare per indicare che l'evento non contiene informazioni aggiuntive.

Creare ora una classe in cui sono elencati i file di una directory o di una delle sue sottodirectory che seguono uno schema. Questo componente genera un evento per ogni file individuato che corrisponde allo schema.

L'uso di un modello di eventi offre alcuni vantaggi di progettazione. È possibile creare più listener di evento che eseguono azioni diverse quando viene trovato uno dei file cercati. Combinando i diversi listener è possibile creare algoritmi più affidabili.

Ecco la dichiarazione iniziale di argomenti evento per trovare un file: 

[!code-csharp[EventArgs](../../samples/snippets/csharp/events/Program.cs#EventArgsV1 "Define event arguments")]

Anche se questo sembra un tipo di piccole dimensioni e di soli dati, si deve seguire la convenzione e renderlo un tipo riferimento (`class`). Questo significa che l'oggetto argomento sarà passato per riferimento e gli eventuali aggiornamenti ai dati saranno visti da tutti i sottoscrittori. La prima versione è un oggetto non modificabile. È preferibile rendere non modificabili le proprietà nel tipo argomenti evento. In questo modo un sottoscrittore non può modificare i valori prima che un altro sottoscrittore li veda. Esistono però alcune eccezioni, come si vedrà di seguito.  

Ora è necessario creare la dichiarazione di evento nella classe FileSearcher. Sfruttare il tipo `EventHandler<T>` significa non dover creare un'altra definizione di tipo. Si usa semplicemente una specializzazione generica.

Si compila la classe FileSearcher per cercare i file che corrispondono a uno schema e si genera l'evento corretto quando viene individuata una corrispondenza.

[!code-csharp[FileSearcher](../../samples/snippets/csharp/events/Program.cs#FileSearcherV1 "Create the initial file searcher")]

## <a name="defining-and-raising-field-like-events"></a>Definizione e generazione di eventi campo

Il modo più semplice per aggiungere un evento alla classe consiste nel dichiarare l'evento come campo pubblico, come illustrato nell'esempio precedente:

[!code-csharp[DeclareEvent](../../samples/snippets/csharp/events/Program.cs#DeclareEvent "Declare the file found event")]

In questo esempio sembra che venga dichiarato un campo pubblico, una prassi di programmazione orientata a oggetti non corretta. Si desidera proteggere l'accesso ai dati tramite le proprietà o i metodi. Nonostante questa possa sembrare una prassi non corretta, il codice generato dal compilatore crea wrapper che rendono gli oggetti evento accessibili solo in modalità provvisoria. Le uniche operazioni disponibili in un evento simile a un campo sono aggiungere gestori:

[!code-csharp[DeclareEventHandler](../../samples/snippets/csharp/events/Program.cs#DeclareEventHandler "Declare the file found event handler")]

e rimuovere gestori:

[!code-csharp[RemoveEventHandler](../../samples/snippets/csharp/events/Program.cs#RemoveHandler "Remove the event handler")]

Si noti che esiste una variabile locale per il gestore. Se si usasse il corpo della funzione lambda, il metodo remove non funzionerebbe correttamente. Sarebbe un'altra istanza del delegato e tacitamente non farebbe nulla.

Il codice all'esterno della classe non può generare l'evento né eseguire altre operazioni.

## <a name="returning-values-from-event-subscribers"></a>Restituzione di valori da sottoscrittori di evento

La versione semplice funziona correttamente. Si aggiungerà un'altra funzionalità: l'annullamento.

Quando si genera l'evento found, i listener devono essere in grado di arrestare l'ulteriore elaborazione se questo file è l'ultimo che è stato cercato.

I gestori di eventi non restituiscono un valore, pertanto è necessario comunicarlo in un altro modo. Lo schema di evento standard usa l'oggetto EventArgs per includere i campi che i sottoscrittori di evento possono usare per comunicare l'annullamento.

Esistono due schemi diversi che potrebbero essere usati, in base alla semantica del contratto di annullamento. In entrambi i casi si aggiungerà un campo booleano a EventArguments per l'evento found file. 

Uno degli schemi consente a qualsiasi sottoscrittore di annullare l'operazione.
Per questo schema il nuovo campo viene inizializzato su `false`. Qualsiasi sottoscrittore può cambiarlo in `true`. Dopo che tutti i sottoscrittori hanno visto l'evento generato, il componente FileSearcher esamina il valore booleano e interviene.

Il secondo schema annullerebbe l'operazione solo se tutti i sottoscrittori volessero annullare l'operazione. In questo schema viene inizializzato il nuovo campo per indicare che l'operazione deve essere annullata e qualsiasi sottoscrittore può cambiarlo per indicare che l'operazione deve continuare.
Dopo che tutti i sottoscrittori hanno visto l'evento che è stato generato, il componente FileSearcher esamina il valore booleano e interviene. Questo schema comporta un passaggio aggiuntivo: il componente deve sapere se i sottoscrittori hanno visto l'evento. Se non sono presenti sottoscrittori, il campo indicherà erroneamente un annullamento.

Ora si implementerà la prima versione per questo esempio. È necessario aggiungere un campo booleano denominato `CancelRequested` al tipo `FileFoundArgs`:

[!code-csharp[EventArgs](../../samples/snippets/csharp/events/Program.cs#EventArgs "Update event arguments")]

Il nuovo campo viene automaticamente inizializzato su `false`, il valore predefinito per un campo booleano, in modo che l'utente non lo annulli accidentalmente. L'unica modifica ulteriore apportata al componente è controllare il flag dopo la generazione dell'evento per vedere se qualcuno dei sottoscrittori ha richiesto un annullamento:

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

Un vantaggio di questo schema è che non si tratta di una modifica sostanziale.
Nessuno dei sottoscrittori ha richiesto un annullamento in precedenza e non lo stanno richiedendo neanche adesso. Il codice dei sottoscrittori non richiede alcun aggiornamento, a meno che non si voglia supportare il nuovo protocollo di annullamento. L'accoppiamento è molto debole.

Aggiorniamo il server di sottoscrizione in modo che richieda un annullamento dopo aver trovato il primo eseguibile:

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a>Aggiunta di un'altra dichiarazione di evento

Aggiungeremo ora un'altra funzionalità e dimostreremo altri idiomi del linguaggio per gli eventi. Aggiungiamo un overload del metodo `Search` che attraversa tutte le sottodirectory alla ricerca dei file.

L'operazione potrebbe rivelarsi piuttosto lunga in una directory con molte sottodirectory. Aggiungiamo un evento che viene generato quando inizia la ricerca in una nuova directory. Questo consente ai sottoscrittori di tenere traccia dell'avanzamento e di aggiornare l'utente sullo stato dell'avanzamento. Tutti gli esempi creati finora sono pubblici. Rendiamo questo evento interno. Ciò significa che è possibile rendere interni anche i tipi utilizzati per gli argomenti.

Si inizierà creando la nuova classe EventArgs derivata per la segnalazione della nuova directory e dell'avanzamento. 

[!code-csharp[DirEventArgs](../../samples/snippets/csharp/events/Program.cs#SearchDirEventArgs "Define search directory event arguments")]

Anche in questo caso è possibile seguire le indicazioni per creare un tipo di riferimento non modificabile per argomenti evento.

Ora definire l'evento. Questa volta si userà una sintassi diversa. Oltre a usare la sintassi di campo, è possibile creare la proprietà in modo esplicito con gestori di aggiunta e rimozione. Questo esempio non richiede codice aggiuntivo in tali gestori ma illustra come crearli.

[!code-csharp[Declare event with add and remove handlers](../../samples/snippets/csharp/events/Program.cs#DeclareSearchEvent "Declare the event with add and remove handlers")]

Il codice che si scrive qui rispecchia per molti aspetti quello generato dal compilatore per le definizioni di evento di campo viste in precedenza. Si crea l'evento usando una sintassi molto simile a quella impiegata per le [proprietà](properties.md). Si noti che i gestori hanno nomi diversi: `add` e `remove`. Questi vengono chiamati per attivare la sottoscrizione all'evento o annullarla. Si noti che è necessario anche dichiarare un campo di backup privato per archiviare la variabile di evento. Viene inizializzata su null.

Quindi, si aggiunge l'overload del metodo `Search` che attraversa le sottodirectory e genera entrambi gli eventi. Il modo più semplice per eseguire questa operazione è usare un argomento predefinito per specificare che si desidera cercare in tutte le directory:

[!code-csharp[SearchImplementation](../../samples/snippets/csharp/events/Program.cs#FinalImplementation "Implementation to search directories")]

A questo punto è possibile eseguire l'applicazione chiamando l'overload per cercare in tutte le sottodirectory. Non sono presenti sottoscrittori per il nuovo evento `ChangeDirectory`, ma l'uso dell'idioma `?.Invoke()` garantisce il funzionamento corretto.

 Aggiungiamo un gestore per scrivere una riga che mostra l'avanzamento nella finestra della console. 

[!code-csharp[Search](../../samples/snippets/csharp/events/Program.cs#Search "Declare event handler")]

Sono stati esaminati schemi che vengono seguiti in tutto l'ecosistema .NET.
Conoscendo questi schemi e convenzioni è possibile scrivere velocemente codice C# e .NET idiomatico.

Ora si vedranno alcune modifiche di questi schemi nella versione più recente di .NET.

[Avanti](modern-events.md)
