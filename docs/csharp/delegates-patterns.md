---
title: Modelli comuni per i delegati
description: Informazioni sui modelli comuni per l'uso dei delegati nel codice per evitare l'accoppiamento forte tra i componenti.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83214800fb997e9274cacfd1bae85ab07c4515a2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="common-patterns-for-delegates"></a><span data-ttu-id="ad6c0-104">Modelli comuni per i delegati</span><span class="sxs-lookup"><span data-stu-id="ad6c0-104">Common Patterns for Delegates</span></span>

[<span data-ttu-id="ad6c0-105">Precedente</span><span class="sxs-lookup"><span data-stu-id="ad6c0-105">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="ad6c0-106">I delegati offrono un meccanismo che consente progettazioni software che comportano un accoppiamento minimo tra i componenti.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-106">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="ad6c0-107">Un esempio eccellente di questo tipo di progettazione è LINQ.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-107">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="ad6c0-108">Tutte le funzionalità del modello di espressione di query LINQ sono basate sui delegati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-108">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="ad6c0-109">Considerare il semplice esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-109">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="ad6c0-110">La sequenza di numeri viene filtrata mantenendo solo i numeri inferiori al valore 10.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-110">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="ad6c0-111">Il metodo `Where` usa un delegato che determina quali elementi di un filtro passano il filtro.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-111">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="ad6c0-112">Quando si crea una query LINQ, si specifica l'implementazione del delegato per questo scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-112">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="ad6c0-113">Il prototipo del metodo Where è:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-113">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<in TSource> (IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="ad6c0-114">Questo esempio viene ripetuto con tutti i metodi che fanno parte di LINQ.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-114">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="ad6c0-115">Tutti i metodi si basano su delegati per il codice che gestisce la query specifica.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-115">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="ad6c0-116">Lo schema progettuale di questa API è molto utile per apprendere e comprendere.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-116">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="ad6c0-117">Questo semplice esempio illustrato come i delegati richiedono pochissimo accoppiamento tra i componenti.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-117">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="ad6c0-118">Non è necessario creare una classe che deriva da una determinata classe base.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-118">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="ad6c0-119">Non è necessario implementare un'interfaccia specifica.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-119">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="ad6c0-120">L'unico requisito è fornire l'implementazione di un metodo che è fondamentale per l'attività in questione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-120">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="ad6c0-121">Creazione di componenti personalizzati con i delegati</span><span class="sxs-lookup"><span data-stu-id="ad6c0-121">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="ad6c0-122">Continuando con lo stesso esempio si crea un componente usando una progettazione basata sui delegati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-122">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="ad6c0-123">Definire un componente che può essere usato per i messaggi di registro in un sistema di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-123">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="ad6c0-124">I componenti di libreria possono essere usati in molti ambienti diversi, su più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-124">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="ad6c0-125">Sono disponibili molte funzionalità comuni nel componente che gestisce i registri.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-125">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="ad6c0-126">È necessario che vengano accettati i messaggi da qualsiasi componente nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-126">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="ad6c0-127">I messaggi avranno priorità diverse che possono essere gestite dal componente principale.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-127">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="ad6c0-128">I messaggi devono avere timestamp nel formato archiviato finale.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-128">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="ad6c0-129">Per gli scenari più avanzati, è possibile filtrare i messaggi in base al componente di origine.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-129">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="ad6c0-130">La posizione in cui vengono scritti i messaggi è uno degli aspetti della funzionalità che verrà modificato spesso.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-130">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="ad6c0-131">In alcuni ambienti possono essere scritti nella console degli errori.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-131">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="ad6c0-132">In altri casi, in un file.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-132">In others, a file.</span></span> <span data-ttu-id="ad6c0-133">Le altre possibilità includono l'archiviazione database, i log eventi del sistema operativo o un'altra archiviazione di documenti.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-133">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="ad6c0-134">Esistono anche combinazioni di output che possono essere usate in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-134">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="ad6c0-135">È possibile scrivere i messaggi nella console e in un file.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-135">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="ad6c0-136">Una progettazione basata sui delegati offre molta flessibilità e semplifica il supporto di meccanismi di archiviazione che possono essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-136">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="ad6c0-137">In questa progettazione, il componente del log primario può essere una classe non virtuale e persino sealed.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-137">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="ad6c0-138">È possibile collegare qualsiasi set di delegati per scrivere i messaggi in diversi supporti di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-138">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="ad6c0-139">Il supporto incorporato per i delegati multicast semplifica il supporto di scenari in cui i messaggi devono essere scritti in più posizioni (un file e una console).</span><span class="sxs-lookup"><span data-stu-id="ad6c0-139">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="ad6c0-140">Prima implementazione</span><span class="sxs-lookup"><span data-stu-id="ad6c0-140">A First Implementation</span></span>

<span data-ttu-id="ad6c0-141">Per iniziare in modo semplice, l'implementazione iniziale accetterà i nuovi messaggi e li scriverà usando qualsiasi delegato associato.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-141">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="ad6c0-142">È possibile iniziare con un solo delegato che scrive i messaggi nella console.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-142">You can start with one delegate that writes messages to the console.</span></span>

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(string msg)
    {
        WriteMessage(msg);
    }
}
```

<span data-ttu-id="ad6c0-143">La classe statica precedente è l'elemento più semplice in grado di funzionare.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-143">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="ad6c0-144">È necessario scrivere la singola implementazione per il metodo che scrive i messaggi nella console:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-144">We need to write the single implementation for the method that writes messages to the console:</span></span> 

```csharp
public static void LogToConsole(string message)
{
    Console.Error.WriteLine(message);
}
```

<span data-ttu-id="ad6c0-145">Infine, è necessario collegare il delegato associandolo al delegato WriteMessage dichiarato nel logger:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-145">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

```csharp
Logger.WriteMessage += LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="ad6c0-146">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ad6c0-146">Practices</span></span>

<span data-ttu-id="ad6c0-147">L'esempio è abbastanza semplice ma illustra alcune importanti linee guida per le progettazioni che usano i delegati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-147">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="ad6c0-148">L'uso dei tipi delegati definiti nel framework principale semplifica l'uso dei delegati da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-148">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="ad6c0-149">Non è necessario definire nuovi tipi e gli sviluppatori che usano la libreria non devono conoscere tipi delegati nuovi e specializzati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-149">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="ad6c0-150">Le interfacce usate sono essenziali e offrono la massima flessibilità: per creare un nuovo logger di output è necessario creare un solo metodo.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-150">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="ad6c0-151">Il metodo creato può essere statico o di istanza</span><span class="sxs-lookup"><span data-stu-id="ad6c0-151">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="ad6c0-152">e avere qualsiasi accesso.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-152">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="ad6c0-153">Formattazione dell'output</span><span class="sxs-lookup"><span data-stu-id="ad6c0-153">Formatting Output</span></span>

<span data-ttu-id="ad6c0-154">Creare una prima versione più affidabile e altri meccanismi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-154">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="ad6c0-155">Successivamente, aggiungere alcuni argomenti al metodo `LogMessage()` in modo che la classe del log crei messaggi più strutturati:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-155">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

```csharp
// Logger implementation two
public enum Severity
{
    Verbose,
    Trace,
    Information,
    Warning,
    Error,
    Critical
}

public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```

<span data-ttu-id="ad6c0-156">Usare quindi l'argomento `Severity` per filtrare i messaggi inviati all'output del log.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-156">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static Severity LogLevel {get;set;} = Severity.Warning;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        if (s < LogLevel)
            return;
            
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```
## <a name="practices"></a><span data-ttu-id="ad6c0-157">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ad6c0-157">Practices</span></span>

<span data-ttu-id="ad6c0-158">Sono state aggiunte nuove funzionalità all'infrastruttura di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-158">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="ad6c0-159">Poiché il componente di logger è accoppiato molto genericamente a qualsiasi meccanismo di output, è possibile aggiungere queste nuove funzionalità senza alcun impatto sul codice che implementa il delegato del logger.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-159">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="ad6c0-160">Durante la compilazione, si noteranno ulteriori esempi di come questo accoppiamento generico offra una maggiore flessibilità per l'aggiornamento di parti del sito senza modifiche in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-160">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="ad6c0-161">In un'applicazione di dimensioni maggiori, infatti, le classi di output del logger potrebbero trovarsi in un assembly diverso e non richiedere alcuna ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-161">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="ad6c0-162">Creazione di un secondo modulo di output</span><span class="sxs-lookup"><span data-stu-id="ad6c0-162">Building a Second Output Engine</span></span>

<span data-ttu-id="ad6c0-163">Il componente di log è stato migliorato.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-163">The Log component is coming along well.</span></span> <span data-ttu-id="ad6c0-164">Aggiungere un modulo di output che registra i messaggi in un file.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-164">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="ad6c0-165">Questo modulo di output sarà leggermente più complesso.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-165">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="ad6c0-166">Sarà costituito da una classe che incapsula le operazioni di file e garantisce che il file venga sempre chiuso dopo ogni scrittura.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-166">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="ad6c0-167">Questo garantisce che tutti i dati vengano scaricati su disco dopo la generazione di ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-167">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="ad6c0-168">Il logger basato su file è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-168">Here is that file based logger:</span></span>

```csharp
public class FileLogger
{
    private readonly string logPath;
    public FileLogger(string path)
    {
        logPath = path;
        Logger.WriteMessage += LogMessage;
    }
    
    public void DetachLog() => Logger.WriteMessage -= LogMessage;

    // make sure this can't throw.
    private void LogMessage(string msg)
    {
        try {
            using (var log = File.AppendText(logPath))
            {
                log.WriteLine(msg);
                log.Flush();
            }
        } catch (Exception e)
        {
            // Hmm. Not sure what to do.
            // Logging is failing...
        }
    }
}
```

<span data-ttu-id="ad6c0-169">Dopo aver creato questa classe, è possibile crearne un'istanza che associa il relativo metodo LogMessage al componente Logger:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-169">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

```csharp
var file = new FileLogger("log.txt");
```

<span data-ttu-id="ad6c0-170">Le due operazioni non si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-170">These two are not mutually exclusive.</span></span> <span data-ttu-id="ad6c0-171">È possibile associare entrambi i metodi di log e generare messaggi nella console e in un file:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-171">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="ad6c0-172">Successivamente, anche nella stessa applicazione, è possibile rimuovere uno dei delegati senza causare problemi nel sistema:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-172">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="ad6c0-173">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ad6c0-173">Practices</span></span>

<span data-ttu-id="ad6c0-174">A questo punto, è stato aggiunto un secondo gestore di output per il sottosistema di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-174">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="ad6c0-175">Questo gestore richiede maggiore infrastruttura per supportare correttamente il file system.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-175">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="ad6c0-176">Il delegato è un metodo di istanza</span><span class="sxs-lookup"><span data-stu-id="ad6c0-176">The delegate is an instance method.</span></span> <span data-ttu-id="ad6c0-177">ed è anche un metodo privato.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-177">It's also a private method.</span></span>
<span data-ttu-id="ad6c0-178">Non è necessaria una maggiore accessibilità poiché l'infrastruttura dei delegato è in grado di connettere i delegati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-178">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="ad6c0-179">Inoltre, la progettazione basata sui delegati offre più metodi di output senza codice aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-179">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="ad6c0-180">Non è necessario compilare un'infrastruttura aggiuntiva per supportare più metodi di output.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-180">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="ad6c0-181">I metodo vanno semplicemente ad aggiungersi all'elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-181">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="ad6c0-182">Prestare particolare attenzione al codice nel metodo di output di registrazione file.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-182">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="ad6c0-183">Viene codificato per assicurarsi che non venga generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-183">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="ad6c0-184">Sebbene questa operazione non sia sempre strettamente necessaria, è spesso consigliabile.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-184">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="ad6c0-185">Se uno dei metodi delegati genera un'eccezione, i delegati rimanenti non verranno chiamati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-185">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="ad6c0-186">Infine tenere presente che il logger di file deve gestire le risorse aprendo e chiudendo il file per ogni messaggio di log.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-186">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="ad6c0-187">È possibile scegliere di mantenere aperto il file e implementare IDisposable per chiudere il file al termine.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-187">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="ad6c0-188">Entrambe le opzioni presentano vantaggi e svantaggi.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-188">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="ad6c0-189">Entrambe creano maggiore accoppiamento tra le classi.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-189">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="ad6c0-190">Nessun codice nella classe Logger dovrà essere aggiornato per supportare gli scenari.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-190">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="ad6c0-191">Gestione dei delegati Null</span><span class="sxs-lookup"><span data-stu-id="ad6c0-191">Handling Null Delegates</span></span>

<span data-ttu-id="ad6c0-192">Aggiornare infine il metodo LogMessage in modo che risulti affidabile per i casi in cui non viene selezionato alcun meccanismo di output.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-192">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="ad6c0-193">L'implementazione corrente genererà `NullReferenceException` se non è stato associato alcun elenco chiamate al delegato `WriteMessage`.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-193">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="ad6c0-194">È possibile che si preferisca una progettazione che continua automaticamente quando non sono stati associati metodi.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-194">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="ad6c0-195">Questa operazione risulta semplice usando l'operatore condizionale Null insieme al metodo `Delegate.Invoke()`:</span><span class="sxs-lookup"><span data-stu-id="ad6c0-195">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="ad6c0-196">L'operatore condizionale Null (`?.`) provoca un corto circuito quando l'operando sinistro (in questo caso `WriteMessage`) è Null, ovvero non viene eseguito alcun tentativo di registrare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-196">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="ad6c0-197">Il metodo `Invoke()` non apparirà nella documentazione per `System.Delegate` o `System.MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-197">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="ad6c0-198">Il compilatore genera un metodo `Invoke` indipendente dai tipi per tutti i tipi delegati dichiarati.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-198">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="ad6c0-199">In questo esempio ciò significa che `Invoke` accetta un singolo argomento `string` e ha un tipo restituito void.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-199">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="ad6c0-200">Riepilogo delle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ad6c0-200">Summary of Practices</span></span>

<span data-ttu-id="ad6c0-201">Sono state descritte le prime fasi di un componente di log che può essere espanso con altri writer e altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-201">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="ad6c0-202">Se vengono usati i delegati nella progettazione, questi componenti diversi risultano accoppiati molto genericamente.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-202">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="ad6c0-203">Quest'aspetto offre numerosi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-203">This provides several advantages.</span></span> <span data-ttu-id="ad6c0-204">È molto semplice creare nuovi meccanismi di output e associarli al sistema.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-204">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="ad6c0-205">Questi meccanismi richiedono un solo metodo, ovvero il metodo che scrive il messaggio di log.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-205">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="ad6c0-206">Si tratta di una progettazione che risulta molto flessibile quando vengono aggiunte nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-206">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="ad6c0-207">Al writer viene richiesto di implementare un solo metodo.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-207">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="ad6c0-208">Il metodo può essere statico o di istanza.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-208">That method could be a static or instance method.</span></span> <span data-ttu-id="ad6c0-209">Può avere un accesso pubblico, privato o un altro tipo di accesso valido.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-209">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="ad6c0-210">La classe Logger può apportare qualsiasi numero di miglioramenti o modifiche senza causare modifiche sostanziali.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-210">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="ad6c0-211">Come qualsiasi altra classe, non è possibile modificare l'API pubblica senza il rischio di modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-211">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="ad6c0-212">Tuttavia, poiché l'accoppiamento tra il logger e i moduli di output avviene solo tramite il delegato, non vengono usati altri tipi, ad esempio interfacce o classi base.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-212">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="ad6c0-213">L'accoppiamento è ridotto al minimo.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-213">The coupling is as small as possible.</span></span>

[<span data-ttu-id="ad6c0-214">Successivo</span><span class="sxs-lookup"><span data-stu-id="ad6c0-214">Next</span></span>](events-overview.md)

