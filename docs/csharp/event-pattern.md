---
title: Schemi di eventi .NET standard
description: Informazioni sugli schemi di eventi .NET standard e su come creare origini eventi standard e sottoscrivere ed elaborare gli eventi standard nel codice.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 703b7b13a2175fb9c40ff707f333a1bf1530df8c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="standard-net-event-patterns"></a><span data-ttu-id="ee932-104">Schemi di eventi .NET standard</span><span class="sxs-lookup"><span data-stu-id="ee932-104">Standard .NET event patterns</span></span>

[<span data-ttu-id="ee932-105">Precedente</span><span class="sxs-lookup"><span data-stu-id="ee932-105">Previous</span></span>](events-overview.md)

<span data-ttu-id="ee932-106">Gli eventi .NET seguono in genere alcuni schemi noti.</span><span class="sxs-lookup"><span data-stu-id="ee932-106">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="ee932-107">Questi schemi standard facilitano il lavoro agli sviluppatori in quanto possono essere applicati a qualsiasi programma che usa eventi .NET.</span><span class="sxs-lookup"><span data-stu-id="ee932-107">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="ee932-108">Esamineremo questi schemi standard presentando tutte le informazioni necessarie per creare origini evento standard e per sottoscrivere ed elaborare gli eventi standard nel codice.</span><span class="sxs-lookup"><span data-stu-id="ee932-108">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="ee932-109">Firme di delegati di eventi</span><span class="sxs-lookup"><span data-stu-id="ee932-109">Event Delegate Signatures</span></span>

<span data-ttu-id="ee932-110">La firma standard per un delegato di evento .NET è:</span><span class="sxs-lookup"><span data-stu-id="ee932-110">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="ee932-111">Il tipo restituito è void.</span><span class="sxs-lookup"><span data-stu-id="ee932-111">The return type is void.</span></span> <span data-ttu-id="ee932-112">Gli eventi sono basati su delegati e sono delegati multicast.</span><span class="sxs-lookup"><span data-stu-id="ee932-112">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="ee932-113">Sono supportati più sottoscrittori per ogni origine evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-113">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="ee932-114">Il singolo valore restituito da un metodo non viene ridimensionato per più sottoscrittori di eventi.</span><span class="sxs-lookup"><span data-stu-id="ee932-114">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="ee932-115">Qual è il valore restituito che l'origine evento vede dopo avere generato un evento?</span><span class="sxs-lookup"><span data-stu-id="ee932-115">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="ee932-116">Più avanti in questo articolo si vedrà come creare protocolli di evento che supportano sottoscrittori di eventi che segnalano informazioni all'origine evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-116">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="ee932-117">Gli argomenti sono due: mittente e argomenti evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-117">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="ee932-118">Il tipo di `sender` della fase di compilazione è `System.Object`, anche se si conosce probabilmente un tipo più derivato che va sempre bene.</span><span class="sxs-lookup"><span data-stu-id="ee932-118">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="ee932-119">Per convenzione si usa `object`.</span><span class="sxs-lookup"><span data-stu-id="ee932-119">By convention, use `object`.</span></span>

<span data-ttu-id="ee932-120">Il secondo argomento era in genere un tipo derivato da `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="ee932-120">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="ee932-121">Si vedrà nella [sezione successiva](modern-events.md) che questa convenzione non è più applicata. Se il tipo di evento non richiede argomenti aggiuntivi, è necessario comunque fornire entrambi gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ee932-121">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="ee932-122">È previsto un valore speciale, `EventArgs.Empty`, che si deve usare per indicare che l'evento non contiene informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ee932-122">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="ee932-123">Creare ora una classe in cui sono elencati i file di una directory o di una delle sue sottodirectory che seguono uno schema.</span><span class="sxs-lookup"><span data-stu-id="ee932-123">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="ee932-124">Questo componente genera un evento per ogni file individuato che corrisponde allo schema.</span><span class="sxs-lookup"><span data-stu-id="ee932-124">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="ee932-125">L'uso di un modello di eventi offre alcuni vantaggi di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ee932-125">Using an event model provides some design advantages.</span></span> <span data-ttu-id="ee932-126">È possibile creare più listener di evento che eseguono azioni diverse quando viene trovato uno dei file cercati.</span><span class="sxs-lookup"><span data-stu-id="ee932-126">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="ee932-127">Combinando i diversi listener è possibile creare algoritmi più affidabili.</span><span class="sxs-lookup"><span data-stu-id="ee932-127">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="ee932-128">Ecco la dichiarazione iniziale di argomenti evento per trovare un file:</span><span class="sxs-lookup"><span data-stu-id="ee932-128">Here is the initial event argument declaration for finding a sought file:</span></span> 

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="ee932-129">Anche se questo sembra un tipo di piccole dimensioni e di soli dati, si deve seguire la convenzione e renderlo un tipo riferimento (`class`).</span><span class="sxs-lookup"><span data-stu-id="ee932-129">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="ee932-130">Questo significa che l'oggetto argomento sarà passato per riferimento e gli eventuali aggiornamenti ai dati saranno visti da tutti i sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="ee932-130">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="ee932-131">La prima versione è un oggetto non modificabile.</span><span class="sxs-lookup"><span data-stu-id="ee932-131">The first version is an immutable object.</span></span> <span data-ttu-id="ee932-132">È preferibile rendere non modificabili le proprietà nel tipo argomenti evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-132">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="ee932-133">In questo modo un sottoscrittore non può modificare i valori prima che un altro sottoscrittore li veda.</span><span class="sxs-lookup"><span data-stu-id="ee932-133">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="ee932-134">Esistono però alcune eccezioni, come si vedrà di seguito.</span><span class="sxs-lookup"><span data-stu-id="ee932-134">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="ee932-135">Ora è necessario creare la dichiarazione di evento nella classe FileSearcher.</span><span class="sxs-lookup"><span data-stu-id="ee932-135">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="ee932-136">Sfruttare il tipo `EventHandler<T>` significa non dover creare un'altra definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="ee932-136">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="ee932-137">Si usa semplicemente una specializzazione generica.</span><span class="sxs-lookup"><span data-stu-id="ee932-137">You simply use a generic specialization.</span></span>

<span data-ttu-id="ee932-138">Si compila la classe FileSearcher per cercare i file che corrispondono a uno schema e si genera l'evento corretto quando viene individuata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ee932-138">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

```csharp
public class FileSearcher
{
    public event EventHandler<FileFoundArgs> FileFound;

    public void Search(string directory, string searchPattern)
    {
        foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
        {
            FileFound?.Invoke(this, new FileFoundArgs(file));
        }
    }
}
```

## <a name="definining-and-raising-field-like-events"></a><span data-ttu-id="ee932-139">Definizione e generazione di eventi campo</span><span class="sxs-lookup"><span data-stu-id="ee932-139">Definining and Raising Field-Like Events</span></span>

<span data-ttu-id="ee932-140">Il modo più semplice per aggiungere un evento alla classe consiste nel dichiarare l'evento come campo pubblico, come illustrato nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="ee932-140">The simplest way to add an event to your class is to declare that event as a public field, as in the above example:</span></span>

```csharp
public event EventHandler<FileFoundArgs> FileFound;
```

<span data-ttu-id="ee932-141">In questo esempio sembra che venga dichiarato un campo pubblico, una prassi di programmazione a oggetti non corretta.</span><span class="sxs-lookup"><span data-stu-id="ee932-141">This looks like it's declaring a public field, which would appear to be bad object oriented practice.</span></span> <span data-ttu-id="ee932-142">Si desidera proteggere l'accesso ai dati tramite le proprietà o i metodi.</span><span class="sxs-lookup"><span data-stu-id="ee932-142">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="ee932-143">Nonostante questa possa sembrare una prassi non corretta, il codice generato dal compilatore crea wrapper che rendono gli oggetti evento accessibili solo in modalità provvisoria.</span><span class="sxs-lookup"><span data-stu-id="ee932-143">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="ee932-144">Le uniche operazioni disponibili in un evento simile a un campo sono aggiungere gestori:</span><span class="sxs-lookup"><span data-stu-id="ee932-144">The only operations available on a field-like event are add handler:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);
lister.FileFound += onFIleFound;
```

<span data-ttu-id="ee932-145">e rimuovere gestori:</span><span class="sxs-lookup"><span data-stu-id="ee932-145">and remove handler:</span></span>

```csharp
lister.FileFound -= onFileFound;
```

<span data-ttu-id="ee932-146">Si noti che esiste una variabile locale per il gestore.</span><span class="sxs-lookup"><span data-stu-id="ee932-146">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="ee932-147">Se si usasse il corpo della funzione lambda, il metodo remove non funzionerebbe correttamente.</span><span class="sxs-lookup"><span data-stu-id="ee932-147">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="ee932-148">Sarebbe un'altra istanza del delegato e tacitamente non farebbe nulla.</span><span class="sxs-lookup"><span data-stu-id="ee932-148">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="ee932-149">Il codice all'esterno della classe non può generare l'evento né eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="ee932-149">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="ee932-150">Restituzione di valori da sottoscrittori di evento</span><span class="sxs-lookup"><span data-stu-id="ee932-150">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="ee932-151">La versione semplice funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="ee932-151">Your simple version is working fine.</span></span> <span data-ttu-id="ee932-152">Si aggiungerà un'altra funzionalità: l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-152">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="ee932-153">Quando si genera l'evento found, i listener devono essere in grado di arrestare l'ulteriore elaborazione se questo file è l'ultimo che è stato cercato.</span><span class="sxs-lookup"><span data-stu-id="ee932-153">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="ee932-154">I gestori di eventi non restituiscono un valore, pertanto è necessario comunicarlo in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="ee932-154">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="ee932-155">Lo schema di evento standard usa l'oggetto EventArgs per includere i campi che i sottoscrittori di evento possono usare per comunicare l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-155">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="ee932-156">Esistono due schemi diversi che potrebbero essere usati, in base alla semantica del contratto di annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-156">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="ee932-157">In entrambi i casi si aggiungerà un campo booleano a EventArguments per l'evento found file.</span><span class="sxs-lookup"><span data-stu-id="ee932-157">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="ee932-158">Uno degli schemi consente a qualsiasi sottoscrittore di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ee932-158">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="ee932-159">Per questo schema il nuovo campo viene inizializzato su `false`.</span><span class="sxs-lookup"><span data-stu-id="ee932-159">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="ee932-160">Qualsiasi sottoscrittore può cambiarlo in `true`.</span><span class="sxs-lookup"><span data-stu-id="ee932-160">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="ee932-161">Dopo che tutti i sottoscrittori hanno visto l'evento generato, il componente FileSearcher esamina il valore booleano e interviene.</span><span class="sxs-lookup"><span data-stu-id="ee932-161">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="ee932-162">Il secondo schema annullerebbe l'operazione solo se tutti i sottoscrittori volessero annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ee932-162">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="ee932-163">In questo schema viene inizializzato il nuovo campo per indicare che l'operazione deve essere annullata e qualsiasi sottoscrittore può cambiarlo per indicare che l'operazione deve continuare.</span><span class="sxs-lookup"><span data-stu-id="ee932-163">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="ee932-164">Dopo che tutti i sottoscrittori hanno visto l'evento che è stato generato, il componente FileSearcher esamina il valore booleano e interviene.</span><span class="sxs-lookup"><span data-stu-id="ee932-164">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="ee932-165">Questo schema comporta un passaggio aggiuntivo: il componente deve sapere se i sottoscrittori hanno visto l'evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-165">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="ee932-166">Se non sono presenti sottoscrittori, il campo indicherà erroneamente un annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-166">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="ee932-167">Ora si implementerà la prima versione per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ee932-167">Let's implement the first version for this sample.</span></span> <span data-ttu-id="ee932-168">È necessario aggiungere un campo booleano al tipo FileFoundEventArgs:</span><span class="sxs-lookup"><span data-stu-id="ee932-168">You need to add a boolean field to the FileFoundEventArgs type:</span></span>

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }
    public bool CancelRequested { get; set; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="ee932-169">Il nuovo campo deve essere inizializzato su false, in modo che non sia annullato senza ragione.</span><span class="sxs-lookup"><span data-stu-id="ee932-169">This new Field should be initialized to false, so you don't cancel for no reason.</span></span> <span data-ttu-id="ee932-170">Questo è il valore predefinito per un campo booleano, perciò è impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ee932-170">That is the default value for a boolean field, so that happens automatically.</span></span> <span data-ttu-id="ee932-171">L'unica modifica ulteriore apportata al componente è controllare il flag dopo la generazione dell'evento per vedere se qualcuno dei sottoscrittori ha richiesto un annullamento:</span><span class="sxs-lookup"><span data-stu-id="ee932-171">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

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

<span data-ttu-id="ee932-172">Un vantaggio di questo schema è che non si tratta di una modifica sostanziale.</span><span class="sxs-lookup"><span data-stu-id="ee932-172">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="ee932-173">Nessuno dei sottoscrittori ha richiesto un annullamento prima e neppure ora.</span><span class="sxs-lookup"><span data-stu-id="ee932-173">None of the subscribers requested a cancel before, and they still are not.</span></span> <span data-ttu-id="ee932-174">Il codice dei sottoscrittori non richiede alcun aggiornamento, a meno che non si voglia supportare il nuovo protocollo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-174">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="ee932-175">L'accoppiamento è molto debole.</span><span class="sxs-lookup"><span data-stu-id="ee932-175">It's very loosely coupled.</span></span>

<span data-ttu-id="ee932-176">Aggiorniamo il server di sottoscrizione in modo che richieda un annullamento dopo aver trovato il primo eseguibile:</span><span class="sxs-lookup"><span data-stu-id="ee932-176">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="ee932-177">Aggiunta di un'altra dichiarazione di evento</span><span class="sxs-lookup"><span data-stu-id="ee932-177">Adding Another Event Declaration</span></span>

<span data-ttu-id="ee932-178">Aggiungeremo ora un'altra funzionalità e dimostreremo altri idiomi del linguaggio per gli eventi.</span><span class="sxs-lookup"><span data-stu-id="ee932-178">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="ee932-179">Aggiungiamo un overload del metodo `Search()` che attraversa tutte le sottodirectory alla ricerca dei file.</span><span class="sxs-lookup"><span data-stu-id="ee932-179">Let's add an overload of the `Search()` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="ee932-180">L'operazione potrebbe rivelarsi piuttosto lunga in una directory con molte sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="ee932-180">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="ee932-181">Aggiungiamo un evento che viene generato quando inizia la ricerca in una nuova directory.</span><span class="sxs-lookup"><span data-stu-id="ee932-181">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="ee932-182">Questo consente ai sottoscrittori di tenere traccia dell'avanzamento e di aggiornare l'utente sullo stato dell'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-182">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="ee932-183">Tutti gli esempi creati finora sono pubblici.</span><span class="sxs-lookup"><span data-stu-id="ee932-183">All the samples you've created so far are public.</span></span> <span data-ttu-id="ee932-184">Rendiamo questo evento interno.</span><span class="sxs-lookup"><span data-stu-id="ee932-184">Let's make this one an internal event.</span></span> <span data-ttu-id="ee932-185">Ciò significa che è possibile rendere interni anche i tipi utilizzati per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ee932-185">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="ee932-186">Si inizierà creando la nuova classe EventArgs derivata per la segnalazione della nuova directory e dell'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="ee932-186">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

```csharp
internal class SearchDirectoryArgs : EventArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs)
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
``` 

<span data-ttu-id="ee932-187">Anche in questo caso è possibile seguire le indicazioni per creare un tipo di riferimento non modificabile per argomenti evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-187">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="ee932-188">Ora definire l'evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-188">Next, define the event.</span></span> <span data-ttu-id="ee932-189">Questa volta si userà una sintassi diversa.</span><span class="sxs-lookup"><span data-stu-id="ee932-189">This time, you'll use a different syntax.</span></span> <span data-ttu-id="ee932-190">Oltre a usare la sintassi di campo, è possibile creare la proprietà in modo esplicito con gestori di aggiunta e rimozione.</span><span class="sxs-lookup"><span data-stu-id="ee932-190">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="ee932-191">In questo esempio il progetto non richiede codice aggiuntivo in tali gestori ma illustra come crearli.</span><span class="sxs-lookup"><span data-stu-id="ee932-191">In this sample, you won't need extra code in those handlers in this project, but this shows how you would create them.</span></span>

```csharp
internal event EventHandler<SearchDirectoryArgs> DirectoryChanged
{
    add { directoryChanged += value; }
    remove { directoryChanged -= value; }
}
private EventHandler<SearchDirectoryArgs> directoryChanged;
```

<span data-ttu-id="ee932-192">Il codice che si scrive qui rispecchia per molti aspetti quello generato dal compilatore per le definizioni di evento di campo, visto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ee932-192">In may ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="ee932-193">Si crea l'evento usando una sintassi molto simile a quella impiegata per le [proprietà](properties.md).</span><span class="sxs-lookup"><span data-stu-id="ee932-193">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="ee932-194">Si noti che i gestori hanno nomi diversi: `add` e `remove`.</span><span class="sxs-lookup"><span data-stu-id="ee932-194">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="ee932-195">Questi vengono chiamati per attivare la sottoscrizione all'evento o annullarla.</span><span class="sxs-lookup"><span data-stu-id="ee932-195">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="ee932-196">Si noti che è necessario anche dichiarare un campo di backup privato per archiviare la variabile di evento.</span><span class="sxs-lookup"><span data-stu-id="ee932-196">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="ee932-197">Viene inizializzata su null.</span><span class="sxs-lookup"><span data-stu-id="ee932-197">It is initialized to null.</span></span>

<span data-ttu-id="ee932-198">Quindi aggiungiamo l'overload del metodo Search() che attraversa le sottodirectory e genera entrambi gli eventi.</span><span class="sxs-lookup"><span data-stu-id="ee932-198">Next, let's add the overload of the Search() method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="ee932-199">Il modo più semplice per eseguire questa operazione è usare un argomento predefinito per specificare che si desidera cercare in tutte le directory:</span><span class="sxs-lookup"><span data-stu-id="ee932-199">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

```csharp
public void Search(string directory, string searchPattern, bool searchSubDirs = false)
{
    if (searchSubDirs)
    {
        var allDirectories = Directory.GetDirectories(directory, "*.*", SearchOption.AllDirectories);
        var completedDirs = 0;
        var totalDirs = allDirectories.Length + 1;
        foreach (var dir in allDirectories)
        {
            directoryChanged?.Invoke(this,
                new SearchDirectoryArgs(dir, totalDirs, completedDirs++));
            // Recursively search this child directory:
            SearchDirectory(dir, searchPattern);
        }
        // Include the Current Directory:
        directoryChanged?.Invoke(this,
            new SearchDirectoryArgs(directory, totalDirs, completedDirs++));
        SearchDirectory(directory, searchPattern);
    }
    else
    {
        SearchDirectory(directory, searchPattern);
    }
}

private void SearchDirectory(string directory, string searchPattern)
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

<span data-ttu-id="ee932-200">A questo punto è possibile eseguire l'applicazione chiamando l'overload per cercare in tutte le sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="ee932-200">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="ee932-201">Non sono presenti sottoscrittori per il nuovo evento `ChangeDirectory`, ma l'uso dell'idioma `?.Invoke()` garantisce il funzionamento corretto.</span><span class="sxs-lookup"><span data-stu-id="ee932-201">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="ee932-202">Aggiungiamo un gestore per scrivere una riga che mostra l'avanzamento nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ee932-202">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

```csharp
lister.DirectoryChanged += (sender, eventArgs) =>
{
    Console.Write($"Entering '{eventArgs.CurrentSearchDirectory}'.");
    Console.WriteLine($" {eventArgs.CompletedDirs} of {eventArgs.TotalDirs} completed...");
};
```

<span data-ttu-id="ee932-203">Sono stati esaminati schemi che vengono seguiti in tutto l'ecosistema .NET.</span><span class="sxs-lookup"><span data-stu-id="ee932-203">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="ee932-204">Conoscendo questi schemi e convenzioni è possibile scrivere velocemente codice C# e .NET idiomatico.</span><span class="sxs-lookup"><span data-stu-id="ee932-204">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="ee932-205">Ora si vedranno alcune modifiche di questi schemi nella versione più recente di .NET.</span><span class="sxs-lookup"><span data-stu-id="ee932-205">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="ee932-206">Successivo</span><span class="sxs-lookup"><span data-stu-id="ee932-206">Next</span></span>](modern-events.md)

