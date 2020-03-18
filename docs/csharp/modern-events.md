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
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="2e661-103">Schema di eventi .NET Core aggiornato</span><span class="sxs-lookup"><span data-stu-id="2e661-103">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="2e661-104">Indietro</span><span class="sxs-lookup"><span data-stu-id="2e661-104">Previous</span></span>](event-pattern.md)

<span data-ttu-id="2e661-105">L'articolo precedente descriveva gli schemi di eventi più comuni.</span><span class="sxs-lookup"><span data-stu-id="2e661-105">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="2e661-106">.NET Core ha uno schema più flessibile.</span><span class="sxs-lookup"><span data-stu-id="2e661-106">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="2e661-107">In questa versione la definizione `EventHandler<TEventArgs>` non ha più il vincolo che prevede che `TEventArgs` deve essere una classe derivata da `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2e661-107">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="2e661-108">Di conseguenza, la flessibilità è maggiore e viene offerta la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2e661-108">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="2e661-109">Si consideri innanzitutto la flessibilità.</span><span class="sxs-lookup"><span data-stu-id="2e661-109">Let's start with the flexibility.</span></span> <span data-ttu-id="2e661-110">La classe System.EventArgs introduce un solo metodo: `MemberwiseClone()` che crea una copia superficiale dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e661-110">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="2e661-111">Il metodo deve usare la reflection per implementare la funzionalità per tutte le classi derivate da `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2e661-111">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="2e661-112">Tale funzionalità risulta più semplice da creare in una classe derivata specifica.</span><span class="sxs-lookup"><span data-stu-id="2e661-112">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="2e661-113">Ciò significa che la derivazione da System.EventArgs è un vincolo che limita la progettazione e non offre altri vantaggi.</span><span class="sxs-lookup"><span data-stu-id="2e661-113">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="2e661-114">Infatti, è possibile modificare le definizioni di `FileFoundArgs` e `SearchDirectoryArgs` in modo che non derivino da `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2e661-114">In fact, you can change the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="2e661-115">Il programma funzionerà esattamente allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="2e661-115">The program will work exactly the same.</span></span>

<span data-ttu-id="2e661-116">È anche possibile modificare `SearchDirectoryArgs` in uno struct se si esegue una modifica aggiuntiva:</span><span class="sxs-lookup"><span data-stu-id="2e661-116">You could also change the `SearchDirectoryArgs` to a struct, if you make one more change:</span></span>

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

<span data-ttu-id="2e661-117">La modifica aggiuntiva consiste nell'effettuare una chiamata al costruttore senza parametri prima di specificare il costruttore che inizializza tutti i campi.</span><span class="sxs-lookup"><span data-stu-id="2e661-117">The additional change is to call the parameterless constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="2e661-118">Senza questa aggiunta, le regole del linguaggio C# segnalano un accesso alle proprietà precedente alla loro assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2e661-118">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="2e661-119">Non modificare `FileFoundArgs` da classe (tipo riferimento) a struct (tipo valore)</span><span class="sxs-lookup"><span data-stu-id="2e661-119">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="2e661-120">poiché il protocollo di gestione dell'annullamento richiede che gli argomenti degli eventi vengano passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="2e661-120">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="2e661-121">Se è stata apportata la stessa modifica, la classe di ricerca file non potrà mai osservare le modifiche apportate da un sottoscrittore di eventi.</span><span class="sxs-lookup"><span data-stu-id="2e661-121">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="2e661-122">Per ogni sottoscrittore verrà usata una nuova copia della struttura che sarà una copia diversa da quella vista dall'oggetto di ricerca file.</span><span class="sxs-lookup"><span data-stu-id="2e661-122">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="2e661-123">Si consideri quindi come questa modifica può essere compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2e661-123">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="2e661-124">La rimozione del vincolo non ha effetto sul codice esistente.</span><span class="sxs-lookup"><span data-stu-id="2e661-124">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="2e661-125">I tipi di argomento degli eventi esistenti derivano ancora da `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2e661-125">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="2e661-126">La compatibilità con le versioni precedenti è uno dei motivi principali per cui continueranno a derivare da `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2e661-126">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="2e661-127">Tutti i sottoscrittori di eventi esistenti saranno sottoscrittori di un evento basato sul modello classico.</span><span class="sxs-lookup"><span data-stu-id="2e661-127">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="2e661-128">In base a una logica simile, tutti i tipi di argomento degli eventi creati non avranno sottoscrittori in alcuna codebase esistente.</span><span class="sxs-lookup"><span data-stu-id="2e661-128">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="2e661-129">I nuovi tipi di evento che non derivano da `System.EventArgs` non interromperanno le codebase.</span><span class="sxs-lookup"><span data-stu-id="2e661-129">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="2e661-130">Eventi con i sottoscrittori asincroni</span><span class="sxs-lookup"><span data-stu-id="2e661-130">Events with Async subscribers</span></span>

<span data-ttu-id="2e661-131">L'ultimo modello da conoscere consiste nell'apprendere come scrivere sottoscrittori di eventi che effettuano chiamate a codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="2e661-131">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="2e661-132">Questa operazione è descritta nell'articolo relativo ad [async e await](async.md).</span><span class="sxs-lookup"><span data-stu-id="2e661-132">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="2e661-133">Sebbene i metodi asincroni possano avere un tipo restituito void, questa procedura è fortemente sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="2e661-133">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="2e661-134">Quando il codice del sottoscrittore di eventi chiama un metodo asincrono, l'unica opzione consiste nel creare un metodo `async void`.</span><span class="sxs-lookup"><span data-stu-id="2e661-134">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="2e661-135">Il metodo è necessario per la firma del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="2e661-135">The event handler signature requires it.</span></span>

<span data-ttu-id="2e661-136">Queste richieste contrastanti devono essere conciliate.</span><span class="sxs-lookup"><span data-stu-id="2e661-136">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="2e661-137">In qualche modo, è necessario creare un metodo `async void` sicuro.</span><span class="sxs-lookup"><span data-stu-id="2e661-137">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="2e661-138">I principi di base del modello da implementare sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e661-138">The basics of the pattern you need to implement are below:</span></span>

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

<span data-ttu-id="2e661-139">Si noti innanzitutto che il gestore è contrassegnato come gestore asincrono.</span><span class="sxs-lookup"><span data-stu-id="2e661-139">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="2e661-140">Poiché viene assegnato al tipo delegato di un gestore eventi, avrà un tipo restituito void.</span><span class="sxs-lookup"><span data-stu-id="2e661-140">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="2e661-141">Per questa ragione è necessario seguire il modello indicato nel gestore e non consentire la generazione di eccezioni dal contesto del gestore asincrono.</span><span class="sxs-lookup"><span data-stu-id="2e661-141">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="2e661-142">Poiché non restituisce attività, non sarà presente alcuna attività che segnala l'errore attivando lo stato di errore.</span><span class="sxs-lookup"><span data-stu-id="2e661-142">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="2e661-143">Poiché è asincrono, il metodo non può generare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e661-143">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="2e661-144">(Il metodo chiamante ha `async`continuato l'esecuzione perché è .) Il comportamento di runtime effettivo verrà definito in modo diverso per ambienti diversi.</span><span class="sxs-lookup"><span data-stu-id="2e661-144">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="2e661-145">Può terminare il thread o il processo proprietario del thread o lasciare il processo in uno stato indeterminato.</span><span class="sxs-lookup"><span data-stu-id="2e661-145">It may terminate the thread or the process that owns the thread, or leave the process in an indeterminate state.</span></span> <span data-ttu-id="2e661-146">Tutti questi potenziali risultati sono altamente indesiderabili.</span><span class="sxs-lookup"><span data-stu-id="2e661-146">All of these potential outcomes are highly undesirable.</span></span>

<span data-ttu-id="2e661-147">Per questo motivo è necessario includere l'istruzione await per l'attività asincrona nel proprio blocco try.</span><span class="sxs-lookup"><span data-stu-id="2e661-147">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="2e661-148">Se causa un'attività non riuscita, è possibile registrare l'errore.</span><span class="sxs-lookup"><span data-stu-id="2e661-148">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="2e661-149">Se si tratta di un errore dal quale non è possibile ripristinare l'applicazione, è possibile uscire rapidamente dal programma.</span><span class="sxs-lookup"><span data-stu-id="2e661-149">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="2e661-150">Questi sono gli aggiornamenti più importanti per il modello di eventi .NET.</span><span class="sxs-lookup"><span data-stu-id="2e661-150">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="2e661-151">Nelle librerie usate sono disponibili numerosi esempi delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2e661-151">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="2e661-152">È necessario tuttavia riconoscere i modelli più recenti.</span><span class="sxs-lookup"><span data-stu-id="2e661-152">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="2e661-153">L'articolo successivo descrive come distinguere l'uso di `delegates` e `events` nelle progettazioni.</span><span class="sxs-lookup"><span data-stu-id="2e661-153">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="2e661-154">Si tratta di concetti simili e l'articolo risulterà utile per effettuare la scelta più adatta ai propri programmi.</span><span class="sxs-lookup"><span data-stu-id="2e661-154">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="2e661-155">Avanti</span><span class="sxs-lookup"><span data-stu-id="2e661-155">Next</span></span>](distinguish-delegates-events.md)
