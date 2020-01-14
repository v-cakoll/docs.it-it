---
title: Scrittura di app grandi e reattive in .NET Framework
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c320d004b05e58fc7c239cd8c1f3bcec84ad8f78
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937914"
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="78c78-102">Scrittura di app grandi e reattive in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78c78-102">Writing Large, Responsive .NET Framework Apps</span></span>

<span data-ttu-id="78c78-103">Questo articolo include suggerimenti per il miglioramento delle prestazioni delle app .NET Framework di grandi dimensioni o di app che elaborano una quantità elevata di dati, ad esempio file o database.</span><span class="sxs-lookup"><span data-stu-id="78c78-103">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="78c78-104">Questi suggerimenti derivano dalla riscrittura di compilatori C# e Visual Basic nel codice gestito e l'articolo include diversi esempi concreti tratti dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="78c78-104">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span> 
  
<span data-ttu-id="78c78-105">Grazie a .NET Framework è possibile ottenere una produttività elevata per la creazione di app.</span><span class="sxs-lookup"><span data-stu-id="78c78-105">The .NET Framework is highly productive for building apps.</span></span> <span data-ttu-id="78c78-106">Linguaggi avanzati e sicuri e una vasta raccolta di librerie rendono molto efficace la creazione delle app.</span><span class="sxs-lookup"><span data-stu-id="78c78-106">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span> <span data-ttu-id="78c78-107">La produttività elevata comporta tuttavia alcune conseguenze.</span><span class="sxs-lookup"><span data-stu-id="78c78-107">However, with great productivity comes responsibility.</span></span> <span data-ttu-id="78c78-108">È consigliabile usare tutte le funzionalità di .NET Framework, ma occorre ottimizzare le prestazioni del codice in caso di necessità.</span><span class="sxs-lookup"><span data-stu-id="78c78-108">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span> 
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="78c78-109">Applicabilità delle prestazioni del nuovo compilatore all'app</span><span class="sxs-lookup"><span data-stu-id="78c78-109">Why the new compiler performance applies to your app</span></span>  
 <span data-ttu-id="78c78-110">Il team responsabile del progetto .NET Compiler Platform ("Roslyn") ha riscritto i compilatori C# e Visual Basic nel codice gestito, per offrire nuove API per la modellazione e l'analisi di codice, la creazione di strumenti e l'abilitazione di esperienze più avanzate e sensibili al codice in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="78c78-110">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span> <span data-ttu-id="78c78-111">La riscrittura dei compilatori e la creazione di esperienze di Visual Studio nei nuovi compilatori hanno permesso di ottenere approfondimenti utili sulle prestazioni, applicabili a qualsiasi app .NET Framework di grandi dimensioni o a qualsiasi app che elabora quantità elevate di dati.</span><span class="sxs-lookup"><span data-stu-id="78c78-111">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span> <span data-ttu-id="78c78-112">Per avvalersi degli approfondimenti e degli esempi tratti dal compilatore C#, non sono necessarie conoscenze specifiche sui compilatori.</span><span class="sxs-lookup"><span data-stu-id="78c78-112">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span> 
  
 <span data-ttu-id="78c78-113">Visual Studio usa le API dei compilatori per creare tutte le funzionalità IntelliSense amate dagli utenti, ad esempio la colorazione di identificatori e parole chiave, elenchi di completamento della sintassi, zigzag per gli errori, suggerimenti relativi ai parametri, problemi relativi al codice e azioni per il codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-113">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span> <span data-ttu-id="78c78-114">Visual Studio offre questo supporto mentre gli sviluppatori digitano e modificano il codice e Visual Studio deve essere sempre in grado di rispondere mentre il compilatore modella in modo continuativo il codice modificato dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="78c78-114">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span> 
  
 <span data-ttu-id="78c78-115">Quando gli utenti finali interagiscono con l'app, si aspettano che sia reattiva.</span><span class="sxs-lookup"><span data-stu-id="78c78-115">When your end users interact with your app, they expect it to be responsive.</span></span> <span data-ttu-id="78c78-116">La digitazione o la gestione dei comandi non devono essere mai bloccate.</span><span class="sxs-lookup"><span data-stu-id="78c78-116">Typing or command handling should never be blocked.</span></span> <span data-ttu-id="78c78-117">Le informazioni di supporto devono essere visualizzate rapidamente o scomparire se l'utente continua a digitare.</span><span class="sxs-lookup"><span data-stu-id="78c78-117">Help should pop up quickly or give up if the user continues typing.</span></span> <span data-ttu-id="78c78-118">L'app deve evitare di bloccare il thread dell'interfaccia utente con calcoli di lunga durata, che potrebbero dare l'impressione di lentezza dell'app.</span><span class="sxs-lookup"><span data-stu-id="78c78-118">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span> 
  
 <span data-ttu-id="78c78-119">Per ulteriori informazioni sui compilatori Roslyn, vedere [il .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span><span class="sxs-lookup"><span data-stu-id="78c78-119">For more information about Roslyn compilers, see [The .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span></span>
  
## <a name="just-the-facts"></a><span data-ttu-id="78c78-120">Considerazioni essenziali</span><span class="sxs-lookup"><span data-stu-id="78c78-120">Just the Facts</span></span>  
 <span data-ttu-id="78c78-121">Quando si ottimizzano le prestazioni e si creano app .NET Framework reattive, occorre prestare attenzione alle considerazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="78c78-121">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span> 
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="78c78-122">Considerazione 1: Non eseguire prematuramente l'ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="78c78-122">Fact 1: Don’t prematurely optimize</span></span>  
 <span data-ttu-id="78c78-123">La scrittura di codice più complesso del necessario comporta costi di gestione, debug e ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-123">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span> <span data-ttu-id="78c78-124">I programmatori esperti sono in grado di risolvere problemi di codifica e di scrivere codice più efficiente in modo intuitivo.</span><span class="sxs-lookup"><span data-stu-id="78c78-124">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span> <span data-ttu-id="78c78-125">A volte, però, ottimizzano il codice con troppo anticipo.</span><span class="sxs-lookup"><span data-stu-id="78c78-125">However, they sometimes prematurely optimize their code.</span></span> <span data-ttu-id="78c78-126">Ad esempio, usano una tabella hash quando sarebbe sufficiente una semplice matrice o usano una procedura complessa per la memorizzazione nella cache, che può provocare la perdita di memoria, invece di ricalcolare semplicemente i valori.</span><span class="sxs-lookup"><span data-stu-id="78c78-126">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span> <span data-ttu-id="78c78-127">Anche se si è programmatori esperti, è consigliabile eseguire test relativi alle prestazioni e analizzare il codice in caso di problemi.</span><span class="sxs-lookup"><span data-stu-id="78c78-127">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span> 
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="78c78-128">Considerazione 2: Solo le misurazioni assicurano la precisione</span><span class="sxs-lookup"><span data-stu-id="78c78-128">Fact 2: If you’re not measuring, you’re guessing</span></span>  
 <span data-ttu-id="78c78-129">I profili e le misurazioni sono attendibili.</span><span class="sxs-lookup"><span data-stu-id="78c78-129">Profiles and measurements don’t lie.</span></span> <span data-ttu-id="78c78-130">I profili indicano se la CPU è caricata completamente o se si è verificato un blocco di I/O del disco.</span><span class="sxs-lookup"><span data-stu-id="78c78-130">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span> <span data-ttu-id="78c78-131">Specificano inoltre il tipo e la quantità di memoria allocata e se la CPU dedica molto tempo a operazioni di [Garbage Collection](../../standard/garbage-collection/index.md) (GC).</span><span class="sxs-lookup"><span data-stu-id="78c78-131">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../standard/garbage-collection/index.md) (GC).</span></span> 
  
 <span data-ttu-id="78c78-132">È consigliabile definire obiettivi per le prestazioni relative a esperienze utente o scenari chiave dell'app e scrivere test per la misurazione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-132">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span> <span data-ttu-id="78c78-133">Esaminare i test che rilevano errori applicando un metodo scientifico: usare i profili come indicazione, definire ipotesi sulla natura del problema e testare le ipotesi tramite un esperimento o una modifica del codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-133">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span> <span data-ttu-id="78c78-134">Stabilire misure iniziali per le prestazioni nel tempo grazie a testing regolare, in modo da potere isolare le modifiche che provocano una regressione nelle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-134">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span> <span data-ttu-id="78c78-135">Un approccio rigoroso alle operazioni relative alle prestazioni permette di evitare di perdere tempo con aggiornamenti di codice superflui.</span><span class="sxs-lookup"><span data-stu-id="78c78-135">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span> 
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="78c78-136">Considerazione 3: La qualità degli strumenti è essenziale</span><span class="sxs-lookup"><span data-stu-id="78c78-136">Fact 3: Good tools make all the difference</span></span>  
 <span data-ttu-id="78c78-137">Gli strumenti efficaci permettono di individuare rapidamente i problemi principali a livello di prestazioni (CPU, memoria o disco) e semplificano l'individuazione del codice che provoca tali colli di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="78c78-137">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span> <span data-ttu-id="78c78-138">Microsoft fornisce un'ampia gamma di strumenti per le prestazioni, ad esempio [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) e [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span><span class="sxs-lookup"><span data-stu-id="78c78-138">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) and [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span></span> 
  
 <span data-ttu-id="78c78-139">PerfView è uno strumento gratuito e straordinariamente efficace che permette di concentrarsi sui problemi essenziali, ad esempio I/O del disco, eventi GC e memoria.</span><span class="sxs-lookup"><span data-stu-id="78c78-139">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span> <span data-ttu-id="78c78-140">È possibile acquisire eventi ETW ([Event Tracing for Windows](../wcf/samples/etw-tracing.md)) relativi alle prestazioni e visualizzare con facilità le informazioni specifiche per app, processi, stack e thread.</span><span class="sxs-lookup"><span data-stu-id="78c78-140">You can capture performance-related [Event Tracing for Windows](../wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span> <span data-ttu-id="78c78-141">PerfView mostra la quantità e il tipo di memoria allocata dall'app e le quantità di memoria allocate da quali funzioni o stack di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78c78-141">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="78c78-142">Per informazioni dettagliate, vedere gli esaurienti argomenti, demo e video inclusi con lo strumento (ad esempio le [esercitazioni relative a PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial) su Channel 9).</span><span class="sxs-lookup"><span data-stu-id="78c78-142">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span> 
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="78c78-143">Considerazione 4: Le allocazioni sono importantissime</span><span class="sxs-lookup"><span data-stu-id="78c78-143">Fact 4: It’s all about allocations</span></span>  
 <span data-ttu-id="78c78-144">Si potrebbe pensare che la creazione di un'app .NET Framework reattiva dipenda completamente dagli algoritmi, ad esempio dall'uso dell'ordinamento rapido invece dell'ordinamento a bolle, ma non è così.</span><span class="sxs-lookup"><span data-stu-id="78c78-144">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span> <span data-ttu-id="78c78-145">Il fattore principale nella creazione di un'app reattiva è costituito dall'allocazione della memoria, in particolare se le dimensioni dell'app sono molto elevate o se l'app elabora quantità elevate di dati.</span><span class="sxs-lookup"><span data-stu-id="78c78-145">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span> 
  
 <span data-ttu-id="78c78-146">Quasi tutte le operazioni relative alla creazione di esperienze IDE reattive con le API del nuovo compilatore comportano il tentativo di evitare allocazioni e la gestione delle strategie per la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-146">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span> <span data-ttu-id="78c78-147">Le tracce di PerfView mostrano che le prestazioni dei nuovi compilatori C# e Visual Basic è associato raramente alla CPU.</span><span class="sxs-lookup"><span data-stu-id="78c78-147">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span> <span data-ttu-id="78c78-148">I compilatori possono essere associati a I/O durante la lettura di centinaia di migliaia o di milioni di righe di codice, la lettura di metadati o l'emissione di codice generato.</span><span class="sxs-lookup"><span data-stu-id="78c78-148">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span> <span data-ttu-id="78c78-149">I ritardi dei thread dell'interfaccia utente sono quasi sempre dovuti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="78c78-149">The UI thread delays are nearly all due to garbage collection.</span></span> <span data-ttu-id="78c78-150">Le operazioni di Garbage Collection di .NET Framework sono ottimizzate al massimo per le prestazioni e sono eseguite nella maggior parte dei casi simultaneamente all'esecuzione del codice dell'app.</span><span class="sxs-lookup"><span data-stu-id="78c78-150">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span> <span data-ttu-id="78c78-151">Una singola allocazione può tuttavia attivare una raccolta [gen2](../../standard/garbage-collection/fundamentals.md) dispendiosa, arrestando tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="78c78-151">However, a single allocation can trigger an expensive [gen2](../../standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span> 
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="78c78-152">Allocazioni comuni ed esempi</span><span class="sxs-lookup"><span data-stu-id="78c78-152">Common allocations and examples</span></span>  
 <span data-ttu-id="78c78-153">Le espressioni di esempio in questa sezione includono allocazioni nascoste apparentemente di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-153">The example expressions in this section have hidden allocations that appear small.</span></span> <span data-ttu-id="78c78-154">Se tuttavia un'app di grandi dimensioni esegue le espressioni per un numero sufficiente di volte, è possibile che ciò generi centinaia di megabyte o addirittura gigabyte di allocazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-154">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span> <span data-ttu-id="78c78-155">Ad esempio, test di un minuto che simulano la digitazione nell'editor da parte di uno sviluppatore hanno provocato l'allocazione di gigabyte di memoria e hanno portato il team responsabile delle prestazioni a esaminare a fondo gli scenari relativi alla digitazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-155">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span> 
  
### <a name="boxing"></a><span data-ttu-id="78c78-156">Boxing</span><span class="sxs-lookup"><span data-stu-id="78c78-156">Boxing</span></span>  
 <span data-ttu-id="78c78-157">La [conversione boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) si verifica quando si esegue il wrapping in un oggetto di tipi di valori che normalmente si trovano nello stack o in strutture di dati,</span><span class="sxs-lookup"><span data-stu-id="78c78-157">[Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span> <span data-ttu-id="78c78-158">ovvero quando si alloca un oggetto per l'inclusione dei dati e quindi si restituisce un puntatore a quell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="78c78-158">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span> <span data-ttu-id="78c78-159">La conversione boxing dei valori è a volte eseguita in .NET Framework a causa della firma di un metodo o del tipo di posizione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-159">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span> <span data-ttu-id="78c78-160">Il wrapping di un tipo di valore in un oggetto provoca l'allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="78c78-160">Wrapping a value type in an object causes memory allocation.</span></span> <span data-ttu-id="78c78-161">Molte operazioni di conversione boxing possono comportare megabyte o gigabyte di allocazioni nell'app e quindi l'app provocherà più operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="78c78-161">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="78c78-162">I compilatori di linguaggi e .NET Framework evitano la conversione boxing quando possibile, ma a volte questa conversione si verifica in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="78c78-162">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span> 
  
 <span data-ttu-id="78c78-163">Per verificare la conversione boxing in PerfView, aprire una traccia ed esaminare gli stack di allocazione heap corrispondenti al nome di processo dell'app. Occorre ricordare che PerfView crea report relativi a tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="78c78-163">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span> <span data-ttu-id="78c78-164">Se alle allocazioni sono associati tipi quali <xref:System.Int32?displayProperty=nameWithType> e <xref:System.Char?displayProperty=nameWithType>, si sta eseguendo la conversione boxing dei tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="78c78-164">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span> <span data-ttu-id="78c78-165">Se si sceglie uno di questi tipi, saranno visualizzati gli stack e le funzioni in cui ne è eseguita la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="78c78-165">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span> 
  
 <span data-ttu-id="78c78-166">**Esempio 1: Metodi di stringa e argomenti di tipo valore**</span><span class="sxs-lookup"><span data-stu-id="78c78-166">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="78c78-167">Questo codice di esempio illustra la conversione boxing potenzialmente superflua ed eccessiva:</span><span class="sxs-lookup"><span data-stu-id="78c78-167">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="78c78-168">Il codice fornisce funzionalità di registrazione, in modo che un'app possa chiamare spesso la funzione `Log`, anche milioni di volte.</span><span class="sxs-lookup"><span data-stu-id="78c78-168">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span> <span data-ttu-id="78c78-169">Il problema consiste nel fatto che la chiamata a `string.Format` provoca l'overload di <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="78c78-169">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span> 
  
 <span data-ttu-id="78c78-170">L'overload richiede a .NET Framework di eseguire la conversione boxing dei valori `int` in oggetti per passarli alla chiamata del metodo.</span><span class="sxs-lookup"><span data-stu-id="78c78-170">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span> <span data-ttu-id="78c78-171">Una soluzione parziale consiste nel chiamare `id.ToString()` e `size.ToString()` e passare tutte le stringe (ovvero gli oggetti) alla chiamata `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="78c78-171">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span> <span data-ttu-id="78c78-172">La chiamata a `ToString()` permette di allocare una stringa, ma l'allocazione sarà comunque eseguita in `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="78c78-172">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span> 
  
 <span data-ttu-id="78c78-173">È possibile che si pensi che questa chiamata di base a `string.Format` sia solo una concatenazione di stringhe e che quindi si scriva invece il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="78c78-173">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="78c78-174">Questa riga di codice, tuttavia, introduce un'allocazione di tipo boxing, poiché si ottiene <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29> come risultato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-174">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span> <span data-ttu-id="78c78-175">È necessario che .NET Framework esegua la conversione boxing del valore letterale di carattere per richiamare `Concat`</span><span class="sxs-lookup"><span data-stu-id="78c78-175">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="78c78-176">**Correzione per l'esempio 1**</span><span class="sxs-lookup"><span data-stu-id="78c78-176">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="78c78-177">La correzione completa è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="78c78-177">The complete fix is simple.</span></span> <span data-ttu-id="78c78-178">È sufficiente sostituire il valore letterale di carattere con il valore letterale di stringa, che non provoca conversione boxing poiché le stringhe sono già oggetti:</span><span class="sxs-lookup"><span data-stu-id="78c78-178">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="78c78-179">**Esempio 2: Conversione boxing delle enumerazioni**</span><span class="sxs-lookup"><span data-stu-id="78c78-179">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="78c78-180">Questo esempio è responsabile di una quantità elevata di allocazioni nei nuovi compilatori C# e Visual Basic a causa dell'uso frequente di tipi di enumerazione, in particolare nelle operazioni di ricerca nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="78c78-180">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span> 
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="78c78-181">Questo problema è molto complesso.</span><span class="sxs-lookup"><span data-stu-id="78c78-181">This problem is very subtle.</span></span> <span data-ttu-id="78c78-182">PerfView lo segnalerebbe come conversione boxing di <xref:System.Enum.GetHashCode>, poiché il metodo esegue la conversione boxing della rappresentazione sottostante del tipo di enumerazione, per fini di implementazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-182">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span> <span data-ttu-id="78c78-183">Se si esamina attentamente in PerfView, è possibile notare due allocazioni di tipo boxing per ogni chiamata a <xref:System.Enum.GetHashCode>.</span><span class="sxs-lookup"><span data-stu-id="78c78-183">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span> <span data-ttu-id="78c78-184">Il compilatore ne inserisce una e .NET Framework inserisce l'altra.</span><span class="sxs-lookup"><span data-stu-id="78c78-184">The compiler inserts one, and the .NET Framework inserts the other.</span></span> 
  
 <span data-ttu-id="78c78-185">**Correzione per l'esempio 2**</span><span class="sxs-lookup"><span data-stu-id="78c78-185">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="78c78-186">È possibile evitare con facilità entrambe le allocazioni tramite esecuzione di cast sulla rappresentazione sottostante prima di chiamare <xref:System.Enum.GetHashCode>:</span><span class="sxs-lookup"><span data-stu-id="78c78-186">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="78c78-187">Un'altra causa comune della conversione boxing sui tipi di enumerazione è costituita dal metodo <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78c78-187">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="78c78-188">È necessario eseguire la conversione boxing dell'argomento passato a <xref:System.Enum.HasFlag%28System.Enum%29>.</span><span class="sxs-lookup"><span data-stu-id="78c78-188">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span> <span data-ttu-id="78c78-189">Nella maggior parte dei casi, la sostituzione di chiamate a <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> con un test bit per bit risulta più semplice e non comporta la creazione di allocazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-189">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span> 
  
 <span data-ttu-id="78c78-190">Occorre ricordare la prima considerazione sulle prestazioni, ovvero non ottimizzare con troppo anticipo, e non iniziare a riscrivere in questo modo tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-190">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span> <span data-ttu-id="78c78-191">È necessario essere consapevoli dei costi relativi alla conversione boxing, ma cambiare il codice solo dopo la profilatura dell'app e l'individuazione delle aree sensibili.</span><span class="sxs-lookup"><span data-stu-id="78c78-191">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span> 
  
### <a name="strings"></a><span data-ttu-id="78c78-192">Stringhe</span><span class="sxs-lookup"><span data-stu-id="78c78-192">Strings</span></span>  
 <span data-ttu-id="78c78-193">Le modifiche alle stringhe sono una delle cause principali delle allocazioni e spesso sono visualizzate nelle prime cinque allocazioni in PerfView.</span><span class="sxs-lookup"><span data-stu-id="78c78-193">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span> <span data-ttu-id="78c78-194">I programmi usano le stringhe per serializzazione, JSON e API REST.</span><span class="sxs-lookup"><span data-stu-id="78c78-194">Programs use strings for serialization, JSON, and REST APIs.</span></span> <span data-ttu-id="78c78-195">È possibile usare le stringhe come costanti a livello di codice per l'ineroperabilità con i sistemi quando non è possibile usare i tipi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-195">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span> <span data-ttu-id="78c78-196">Quando la profilatura mostra che le stringhe influiscono notevolmente sulle prestazioni, cercare chiamate a metodi <xref:System.String> quali <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A> e così via.</span><span class="sxs-lookup"><span data-stu-id="78c78-196">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span> <span data-ttu-id="78c78-197">L'uso di <xref:System.Text.StringBuilder> per evitare i costi di creazione di una stringa da molti pezzi è utile, ma anche l'allocazione dell'oggetto <xref:System.Text.StringBuilder> potrebbe trasformarsi in un collo di bottiglia da gestire.</span><span class="sxs-lookup"><span data-stu-id="78c78-197">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span> 
  
 <span data-ttu-id="78c78-198">**Esempio 3: Operazioni su stringhe**</span><span class="sxs-lookup"><span data-stu-id="78c78-198">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="78c78-199">Il compilatore C# include il codice seguente per la scrittura del testo di un commento di un documento XML formattato:</span><span class="sxs-lookup"><span data-stu-id="78c78-199">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="78c78-200">Come si può notare, nel codice sono eseguite molte modifiche sulle stringhe.</span><span class="sxs-lookup"><span data-stu-id="78c78-200">You can see that this code does a lot of string manipulation.</span></span> <span data-ttu-id="78c78-201">Il codice usa i metodi della libreria per suddividere le righe in stringhe separate, ritagliare lo spazio vuoto, verificare se l'argomento `text` è un commento di documentazione XML ed estrarre sottostringhe dalle righe.</span><span class="sxs-lookup"><span data-stu-id="78c78-201">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span> 
  
 <span data-ttu-id="78c78-202">Nella prima riga in `WriteFormattedDocComment` la chiamata `text.Split` esegue l'allocazione di una nuova matrice di tre elementi come argomento a ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="78c78-202">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span> <span data-ttu-id="78c78-203">Il compilatore deve emettere ogni volta codice per allocare questa matrice.</span><span class="sxs-lookup"><span data-stu-id="78c78-203">The compiler has to emit code to allocate this array each time.</span></span> <span data-ttu-id="78c78-204">Il compilatore infatti non è in grado di sapere se <xref:System.String.Split%2A> archivia la matrice in una posizione in cui potrebbe essere modificata da altro codice, influendo così su chiamate successive a `WriteFormattedDocComment`.</span><span class="sxs-lookup"><span data-stu-id="78c78-204">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span> <span data-ttu-id="78c78-205">La chiamata a <xref:System.String.Split%2A> esegue anche l'allocazione di una stringa per ogni riga in `text` ed esegue l'allocazione di memoria aggiuntiva per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-205">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span> 
  
 <span data-ttu-id="78c78-206">`WriteFormattedDocComment` include tre chiamate al metodo <xref:System.String.TrimStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c78-206">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span> <span data-ttu-id="78c78-207">Due cicli interni duplicano le operazioni e le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-207">Two are in inner loops that duplicate work and allocations.</span></span> <span data-ttu-id="78c78-208">Per complicare ulteriormente la situazione, la chiamata al metodo <xref:System.String.TrimStart%2A> senza argomenti comporta l'allocazione di una matrice vuota (per il parametro `params`), oltre al risultato della stringa.</span><span class="sxs-lookup"><span data-stu-id="78c78-208">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span> 
  
 <span data-ttu-id="78c78-209">È infine presente una chiamata al metodo <xref:System.String.Substring%2A>, che in genere esegue l'allocazione di una nuova stringa.</span><span class="sxs-lookup"><span data-stu-id="78c78-209">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span> 
  
 <span data-ttu-id="78c78-210">**Correzione per l'esempio 3**</span><span class="sxs-lookup"><span data-stu-id="78c78-210">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="78c78-211">A differenza degli esempi precedenti, queste allocazioni non possono essere corrette da piccole modifiche.</span><span class="sxs-lookup"><span data-stu-id="78c78-211">Unlike the earlier examples, small edits cannot fix these allocations.</span></span> <span data-ttu-id="78c78-212">È necessario esaminare il problema nel suo complesso e scegliere un approccio diverso.</span><span class="sxs-lookup"><span data-stu-id="78c78-212">You need to step back, look at the problem, and approach it differently.</span></span> <span data-ttu-id="78c78-213">Come si può notare, ad esempio, l'argomento per `WriteFormattedDocComment()` è una stringa che include tutte le informazioni necessarie per il metodo. Il codice può quindi eseguire più indicizzazioni invece di allocare molte stringhe parziali.</span><span class="sxs-lookup"><span data-stu-id="78c78-213">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span> 
  
 <span data-ttu-id="78c78-214">Il team responsabile delle prestazioni del compilatore ha affrontato tutte queste allocazioni con codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="78c78-214">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc... 
```  
  
 <span data-ttu-id="78c78-215">La prima versione di `WriteFormattedDocComment()` esegue l'allocazione di una matrice, alcune sottostringhe e una sottostringa ritagliata, insieme a una matrice di `params` vuota.</span><span class="sxs-lookup"><span data-stu-id="78c78-215">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span> <span data-ttu-id="78c78-216">È stata verificata anche la presenza di "///".</span><span class="sxs-lookup"><span data-stu-id="78c78-216">It also checked for "///".</span></span> <span data-ttu-id="78c78-217">Il codice rivisto usa solo l'indicizzazione e non esegue alcuna allocazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-217">The revised code uses only indexing and allocates nothing.</span></span> <span data-ttu-id="78c78-218">Trova il primo carattere che non è uno spazio vuoto, quindi controlla il carattere per carattere per verificare se la stringa inizia con "///".</span><span class="sxs-lookup"><span data-stu-id="78c78-218">It finds the first character that is not white space, and then checks character by character to see if the string starts with "///".</span></span> <span data-ttu-id="78c78-219">Il nuovo codice USA `IndexOfFirstNonWhiteSpaceChar` anziché <xref:System.String.TrimStart%2A> per restituire il primo indice (dopo un indice iniziale specificato) in cui si verifica un carattere diverso da uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="78c78-219">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-white-space character occurs.</span></span> <span data-ttu-id="78c78-220">La correzione non è completa, ma è semplice intuire come applicare correzioni simili per ottenere una soluzione completa.</span><span class="sxs-lookup"><span data-stu-id="78c78-220">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span> <span data-ttu-id="78c78-221">Applicando questo approccio a tutto il codice sarà possibile rimuovere tutte le allocazioni in `WriteFormattedDocComment()`.</span><span class="sxs-lookup"><span data-stu-id="78c78-221">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span> 
  
 <span data-ttu-id="78c78-222">**Esempio 4: StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="78c78-222">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="78c78-223">Questo esempio usa un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="78c78-223">This example uses a <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="78c78-224">La funzione seguente genera un nome completo del tipo per tipi generici:</span><span class="sxs-lookup"><span data-stu-id="78c78-224">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="78c78-225">Occorre esaminare attentamente la riga che crea una nuova istanza di <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="78c78-225">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span> <span data-ttu-id="78c78-226">Il codice provoca allocazioni per `sb.ToString()` e allocazioni interne nell'implementazione di <xref:System.Text.StringBuilder>, ma non è possibile controllare queste allocazioni se si vuole ottenere il risultato della stringa.</span><span class="sxs-lookup"><span data-stu-id="78c78-226">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span> 
  
 <span data-ttu-id="78c78-227">**Correzione per l'esempio 4**</span><span class="sxs-lookup"><span data-stu-id="78c78-227">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="78c78-228">Per correggere l'allocazione dell'oggetto `StringBuilder`, memorizzare l'oggetto nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-228">To fix the `StringBuilder` object allocation, cache the  object.</span></span> <span data-ttu-id="78c78-229">La memorizzazione nella cache anche di una singola istanza che potrebbe essere eliminata può migliorare in modo significativo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-229">Even caching a single instance that might get thrown away can improve performance significantly.</span></span> <span data-ttu-id="78c78-230">Questa è la nuova implementazione della funzione, in cui si omette tutto il codice tranne le prime e le ultime righe:</span><span class="sxs-lookup"><span data-stu-id="78c78-230">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="78c78-231">Gli elementi essenziali sono le nuove funzioni `AcquireBuilder()` e `GetStringAndReleaseBuilder()`:</span><span class="sxs-lookup"><span data-stu-id="78c78-231">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="78c78-232">Poiché i nuovi compilatori usano il threading, queste implementazioni usano un campo statico a livello di thread (attributo <xref:System.ThreadStaticAttribute>) per la memorizzazione nella cache di <xref:System.Text.StringBuilder> ed è probabilmente possibile evitare la dichiarazione di `ThreadStatic`.</span><span class="sxs-lookup"><span data-stu-id="78c78-232">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span> <span data-ttu-id="78c78-233">Il campo statico a livello di thread include un valore univoco per ogni thread che esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-233">The thread-static field holds a unique value for each thread that executes this code.</span></span> 
  
 <span data-ttu-id="78c78-234">`AcquireBuilder()` restituisce l'istanza di <xref:System.Text.StringBuilder> memorizzata nella cache, se presente, dopo averla pulita e dopo avere impostato il campo o la cache su Null.</span><span class="sxs-lookup"><span data-stu-id="78c78-234">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span> <span data-ttu-id="78c78-235">In caso contrario, `AcquireBuilder()` crea una nuova istanza e la restituisce, lasciando il campo o la cache impostati su Null.</span><span class="sxs-lookup"><span data-stu-id="78c78-235">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span> 
  
 <span data-ttu-id="78c78-236">Al termine delle operazioni con <xref:System.Text.StringBuilder> , è possibile chiamare `GetStringAndReleaseBuilder()` per ottenere il risultato della stringa, ad eccezione dell'istanza di <xref:System.Text.StringBuilder> nel campo o nella cache, e quindi restituire il risultato.</span><span class="sxs-lookup"><span data-stu-id="78c78-236">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span> <span data-ttu-id="78c78-237">È possibile che il codice sia immesso di nuovo per l'esecuzione e che siano creati più oggetti <xref:System.Text.StringBuilder>, anche se ciò si verifica raramente.</span><span class="sxs-lookup"><span data-stu-id="78c78-237">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span> <span data-ttu-id="78c78-238">Il codice salva solo l'ultima istanza rilasciata di <xref:System.Text.StringBuilder> per un uso successivo.</span><span class="sxs-lookup"><span data-stu-id="78c78-238">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span> <span data-ttu-id="78c78-239">Questa semplice strategia per la memorizzazione nella cache riduce in modo significativo le allocazioni nei nuovi compilatori.</span><span class="sxs-lookup"><span data-stu-id="78c78-239">This simple caching strategy significantly reduced allocations in the new compilers.</span></span> <span data-ttu-id="78c78-240">Parti di .NET Framework e MSBuild ("MSBuild") usano una tecnica simile per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-240">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span> 
  
 <span data-ttu-id="78c78-241">Questa semplice strategia per la memorizzazione nella cache rispetta le indicazioni per una progettazione ottimale della cache, poiché prevede un limite per le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-241">This simple caching strategy adheres to good cache design because it has a size cap.</span></span> <span data-ttu-id="78c78-242">La quantità di codice, tuttavia, è superiore rispetto all'originale e ciò comporta maggiori costi di gestione.</span><span class="sxs-lookup"><span data-stu-id="78c78-242">However, there is more code now than in the original, which means more maintenance costs.</span></span> <span data-ttu-id="78c78-243">È consigliabile adottare la strategia per la memorizzazione nella cache solo se si sono verificati problemi di prestazioni e se PerfView ha mostrato che le allocazioni di <xref:System.Text.StringBuilder> contribuiscono in modo significativo a questi problemi.</span><span class="sxs-lookup"><span data-stu-id="78c78-243">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span> 
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="78c78-244">LINQ ed espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="78c78-244">LINQ and lambdas</span></span>  
<span data-ttu-id="78c78-245">LINQ (Language-Integrated Query), insieme alle espressioni lambda, è un esempio di funzionalità di produttività.</span><span class="sxs-lookup"><span data-stu-id="78c78-245">Language-Integrated Query (LINQ), in conjunction with lambda expressions, is an example of a productivity feature.</span></span> <span data-ttu-id="78c78-246">Tuttavia, il suo utilizzo potrebbe avere un impatto significativo sulle prestazioni nel tempo e potrebbe essere necessario riscrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-246">However, its use may have a significant impact on performance over time, and you might find you need to rewrite your code.</span></span>
  
 <span data-ttu-id="78c78-247">**Esempio 5: Espressioni lambda, List\<T> e IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="78c78-247">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="78c78-248">Questo esempio usa [LINQ e il codice di stile funzionale](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) per individuare un simbolo nel modello del compilatore, a partire da una stringa di nome:</span><span class="sxs-lookup"><span data-stu-id="78c78-248">This example uses [LINQ and functional style code](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="78c78-249">Il nuovo compilatore e le esperienze IDE basate sul compilatore chiamano molto spesso `FindMatchingSymbol()` e questa singola riga di codice della funzione include alcune allocazioni nascoste.</span><span class="sxs-lookup"><span data-stu-id="78c78-249">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span> <span data-ttu-id="78c78-250">Per esaminare queste allocazioni, suddividere prima di tutto la singola riga di codice della funzione in due righe:</span><span class="sxs-lookup"><span data-stu-id="78c78-250">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="78c78-251">Nella prima riga l' [espressione lambda](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) `s => s.Name == name` si [chiude sulla](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) variabile locale `name`.</span><span class="sxs-lookup"><span data-stu-id="78c78-251">In the first line, the [lambda expression](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) `s => s.Name == name` [closes over](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) the local variable `name`.</span></span> <span data-ttu-id="78c78-252">Ciò significa che, oltre ad allocare un oggetto per il [delegato](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) incluso in `predicate`, il codice esegue l'allocazione di una classe statica in cui includere l'ambiente che acquisisce il valore di `name`.</span><span class="sxs-lookup"><span data-stu-id="78c78-252">This means that in addition to allocating an object for the [delegate](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span> <span data-ttu-id="78c78-253">Il compilatore genera codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="78c78-253">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="78c78-254">Le due allocazioni di `new`, una per la classe di ambiente e una per il delegato, sono ora esplicite.</span><span class="sxs-lookup"><span data-stu-id="78c78-254">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span> 
  
 <span data-ttu-id="78c78-255">Esaminare ora la chiamata a `FirstOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="78c78-255">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="78c78-256">Anche questo metodo di estensione nel tipo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> comporta un'allocazione.</span><span class="sxs-lookup"><span data-stu-id="78c78-256">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span> <span data-ttu-id="78c78-257">Poiché `FirstOrDefault` accetta un oggetto <xref:System.Collections.Generic.IEnumerable%601> come primo argomento, è possibile espandere la chiamata al codice seguente (semplificato leggermente per questo esempio):</span><span class="sxs-lookup"><span data-stu-id="78c78-257">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ... 
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="78c78-258">Il tipo della variabile `symbols` è <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="78c78-258">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="78c78-259">Il tipo della raccolta <xref:System.Collections.Generic.List%601> implementa <xref:System.Collections.Generic.IEnumerable%601> e definisce in modo intelligente un enumeratore (interfaccia <xref:System.Collections.Generic.IEnumerator%601>) implementato da <xref:System.Collections.Generic.List%601> con un `struct`.</span><span class="sxs-lookup"><span data-stu-id="78c78-259">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span> <span data-ttu-id="78c78-260">L'uso di una struttura invece di una classe significa che in genere si evitano allocazioni heap e ciò può influire sulle prestazioni delle operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="78c78-260">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span> <span data-ttu-id="78c78-261">Gli enumeratori sono in genere usati con il ciclo `foreach` del linguaggio, che usa la struttura dell'enumeratore restituita allo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="78c78-261">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span> <span data-ttu-id="78c78-262">L'incremento del puntatore dello stack di chiamate per un oggetto non influisce sulle operazioni di Garbage Collection in modo analogo all'allocazione heap.</span><span class="sxs-lookup"><span data-stu-id="78c78-262">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span> 
  
 <span data-ttu-id="78c78-263">Nel caso della chiamata `FirstOrDefault` espansa, il codice deve chiamare `GetEnumerator()` su un oggetto <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="78c78-263">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="78c78-264">L'assegnazione di `symbols` alla variabile `enumerable` di tipo `IEnumerable<Symbol>` comporta la perdita dell'informazione che indica che l'oggetto effettivo è un <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="78c78-264">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="78c78-265">Ciò significa che quando il codice recupera l'enumeratore con `enumerable.GetEnumerator()`, .NET Framework deve eseguire la conversione boxing della struttura restituita per assegnarla alla variabile `enumerator`.</span><span class="sxs-lookup"><span data-stu-id="78c78-265">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span> 
  
 <span data-ttu-id="78c78-266">**Correzione per l'esempio 5**</span><span class="sxs-lookup"><span data-stu-id="78c78-266">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="78c78-267">La correzione consiste nel riscrivere `FindMatchingSymbol` come indicato di seguito, sostituendo la singola riga di codice corrispondente con sei righe di codice che risultano comunque concise, facili da leggere, comprendere e gestire:</span><span class="sxs-lookup"><span data-stu-id="78c78-267">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="78c78-268">Il codice non usa metodi di estensione LINQ, espressioni lambda o enumeratori e non comporta allocazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-268">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span> <span data-ttu-id="78c78-269">L'assenza di allocazioni è dovuta al fatto che il compilatore è in grado di verificare che la raccolta `symbols` e un <xref:System.Collections.Generic.List%601> e può associare l'enumeratore esistente (una struttura) a una variabile locale con il tipo corretto per evitare la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="78c78-269">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span> <span data-ttu-id="78c78-270">La versione originale di questa funzione è un esempio ottimale delle capacità espressive di C# e della produttività di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78c78-270">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span> <span data-ttu-id="78c78-271">La nuova versione, più efficiente, mantiene queste qualità senza aggiungere codice complesso da gestire.</span><span class="sxs-lookup"><span data-stu-id="78c78-271">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span> 
  
### <a name="async-method-caching"></a><span data-ttu-id="78c78-272">Memorizzazione del metodo async nella cache</span><span class="sxs-lookup"><span data-stu-id="78c78-272">Async method caching</span></span>  

<span data-ttu-id="78c78-273">L'esempio seguente mostra un problema comune che si verifica quando si cerca di usare i risultati memorizzati nella cache in un metodo [async](../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="78c78-273">The next example shows a common problem when you try to use cached results in an [async](../../csharp/programming-guide/concepts/async/index.md) method.</span></span>
  
 <span data-ttu-id="78c78-274">**Esempio 6: Memorizzazione nella cache nei metodi async**</span><span class="sxs-lookup"><span data-stu-id="78c78-274">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="78c78-275">Le funzionalità IDE di Visual Studio basate sui nuovi compilatori C# e Visual Basic recuperano spesso alberi della sintassi e i compilatori usano il metodo async durante il recupero per mantenere la reattività di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="78c78-275">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span> <span data-ttu-id="78c78-276">Ecco la prima versione del codice che si potrebbe scrivere per ottenere un albero della sintassi:</span><span class="sxs-lookup"><span data-stu-id="78c78-276">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="78c78-277">Come si può notare, la chiamata a `GetSyntaxTreeAsync()` crea un'istanza di `Parser`, analizza il codice e quindi restituisce un oggetto <xref:System.Threading.Tasks.Task>, `Task<SyntaxTree>`.</span><span class="sxs-lookup"><span data-stu-id="78c78-277">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span> <span data-ttu-id="78c78-278">La parte dispendiosa consiste nell'allocazione dell'istanza di `Parser` e nell'analisi del codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-278">The expensive part is allocating the `Parser` instance and parsing the code.</span></span> <span data-ttu-id="78c78-279">Questa funzione restituisce un <xref:System.Threading.Tasks.Task>, in modo che i chiamanti possano attendere il completamento del processo di analisi e liberare il thread dell'interfaccia utente in modo che possa rispondere all'input utente.</span><span class="sxs-lookup"><span data-stu-id="78c78-279">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span> 
  
 <span data-ttu-id="78c78-280">È possibile che alcune funzionalità di Visual Studio tentino di ottenere lo stesso albero della sintassi. La scrittura del codice seguente permette quindi di memorizzare nella cache il risultato dell'analisi, per risparmiare tempo e allocazioni.</span><span class="sxs-lookup"><span data-stu-id="78c78-280">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span> <span data-ttu-id="78c78-281">Questo codice comporta tuttavia un'allocazione:</span><span class="sxs-lookup"><span data-stu-id="78c78-281">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="78c78-282">Il nuovo codice con memorizzazione nella cache include un campo `SyntaxTree` con nome `cachedResult`.</span><span class="sxs-lookup"><span data-stu-id="78c78-282">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span> <span data-ttu-id="78c78-283">Quando questo campo è Null, `GetSyntaxTreeAsync()` esegue le operazioni e salva il risultato nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-283">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span> <span data-ttu-id="78c78-284">`GetSyntaxTreeAsync()` restituisce l'oggetto `SyntaxTree`.</span><span class="sxs-lookup"><span data-stu-id="78c78-284">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span> <span data-ttu-id="78c78-285">Se però è disponibile una funzione di tipo `async``Task<SyntaxTree>` e si restituisce un valore di tipo `SyntaxTree`, il compilatore emette codice per allocare un oggetto Task in cui includere il risultato, usando `Task<SyntaxTree>.FromResult()`.</span><span class="sxs-lookup"><span data-stu-id="78c78-285">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span> <span data-ttu-id="78c78-286">L'oggetto Task è contrassegnato come completato e il risultato è immediatamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="78c78-286">The Task is marked as completed, and the result is immediately available.</span></span> <span data-ttu-id="78c78-287">Nel codice per i nuovi compilatori gli oggetti <xref:System.Threading.Tasks.Task> già completati erano così frequenti che la correzione di queste allocazioni ha permesso un notevole miglioramento della reattività.</span><span class="sxs-lookup"><span data-stu-id="78c78-287">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span> 
  
 <span data-ttu-id="78c78-288">**Correzione per l'esempio 6**</span><span class="sxs-lookup"><span data-stu-id="78c78-288">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="78c78-289">Per rimuovere l'allocazione <xref:System.Threading.Tasks.Task> completata, è possibile memorizzare nella cache l'oggetto attività con il risultato completato:</span><span class="sxs-lookup"><span data-stu-id="78c78-289">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??   
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="78c78-290">Questo codice modifica il tipo di `cachedResult` in `Task<SyntaxTree>` e usa una funzione `async` dell'helper che include il codice originale da `GetSyntaxTreeAsync()`.</span><span class="sxs-lookup"><span data-stu-id="78c78-290">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span> <span data-ttu-id="78c78-291">`GetSyntaxTreeAsync()` usa ora l'[operatore Null-coalescing](../../csharp/language-reference/operators/null-coalescing-operator.md) per restituire `cachedResult` nel caso in cui non sia Null.</span><span class="sxs-lookup"><span data-stu-id="78c78-291">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span> <span data-ttu-id="78c78-292">Se `cachedResult` è Null, `GetSyntaxTreeAsync()` chiama `GetSyntaxTreeUncachedAsync()` e memorizza il risultato nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-292">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span> <span data-ttu-id="78c78-293">Si noti che `GetSyntaxTreeAsync()` non attende la chiamata a `GetSyntaxTreeUncachedAsync()`, come farebbe normalmente il codice.</span><span class="sxs-lookup"><span data-stu-id="78c78-293">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span> <span data-ttu-id="78c78-294">Se non si attende, quando `GetSyntaxTreeUncachedAsync()` restituisce l'oggetto <xref:System.Threading.Tasks.Task> corrispondente, `GetSyntaxTreeAsync()` restituisce immediatamente l'oggetto <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="78c78-294">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="78c78-295">Il risultato memorizzato nella cache è ora un oggetto <xref:System.Threading.Tasks.Task> e non sono quindi presenti allocazioni per la restituzione del risultato memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-295">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span> 
  
### <a name="additional-considerations"></a><span data-ttu-id="78c78-296">Ulteriori considerazioni</span><span class="sxs-lookup"><span data-stu-id="78c78-296">Additional considerations</span></span>  
 <span data-ttu-id="78c78-297">Di seguito sono riportate altre considerazioni sui potenziali problemi relativi ad app di grandi dimensioni o app che elaborano quantità elevate di dati.</span><span class="sxs-lookup"><span data-stu-id="78c78-297">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span> 
  
 <span data-ttu-id="78c78-298">**Dizionari**</span><span class="sxs-lookup"><span data-stu-id="78c78-298">**Dictionaries**</span></span>  
  
 <span data-ttu-id="78c78-299">I dizionari sono usati ampliamente in molti programmi e, benché siano molto comodi e intrinsecamente efficienti,</span><span class="sxs-lookup"><span data-stu-id="78c78-299">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span> <span data-ttu-id="78c78-300">sono tuttavia usati spesso in modo non appropriato.</span><span class="sxs-lookup"><span data-stu-id="78c78-300">However, they’re often used inappropriately.</span></span> <span data-ttu-id="78c78-301">L'analisi eseguita in Visual Studio e nei nuovi compilatori mostra che molti dizionari includono un solo elemento o sono vuoti.</span><span class="sxs-lookup"><span data-stu-id="78c78-301">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span> <span data-ttu-id="78c78-302">Un <xref:System.Collections.Generic.Dictionary%602> vuoto include dieci campi e occupa 48 byte sull'heap in una macchina x86.</span><span class="sxs-lookup"><span data-stu-id="78c78-302">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span> <span data-ttu-id="78c78-303">I dizionari sono molto utili se si necessita di una struttura di dati di mapping o associativa con ricerca continua.</span><span class="sxs-lookup"><span data-stu-id="78c78-303">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span> <span data-ttu-id="78c78-304">Se sono presenti solo pochi elementi, tuttavia, l'uso del dizionario comporta lo spreco di una grande quantità di spazio.</span><span class="sxs-lookup"><span data-stu-id="78c78-304">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span> <span data-ttu-id="78c78-305">In alternativa, è ad esempio possibile eseguire in modo iterativo una ricerca in un oggetto `List<KeyValuePair\<K,V>>`, con velocità analoga.</span><span class="sxs-lookup"><span data-stu-id="78c78-305">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span> <span data-ttu-id="78c78-306">Se si usa un dizionario solo per il caricamento di dati e la lettura dei dati, uno schema molto comune, l'uso di una matrice ordinata con una ricerca di tipo N(log(N)) potrebbe offrire velocità analoghe, in base al numero di elementi usati.</span><span class="sxs-lookup"><span data-stu-id="78c78-306">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span> 
  
 <span data-ttu-id="78c78-307">**Classi e strutture**</span><span class="sxs-lookup"><span data-stu-id="78c78-307">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="78c78-308">In un certo senso, le classi e le strutture comportano un compromesso classico tra spazio e tempo per l'ottimizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="78c78-308">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span> <span data-ttu-id="78c78-309">Le classi comportano 12 byte di sovraccarico in una macchina x86, anche se non includono campi, ma il passaggio di classi è poco dispendioso, poiché per fare riferimento a un'istanza di classe è necessario solo un puntatore.</span><span class="sxs-lookup"><span data-stu-id="78c78-309">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span> <span data-ttu-id="78c78-310">Le strutture non comportano allocazioni heap se non sono sottoposte a conversione boxing, ma quando si passano strutture di grandi dimensioni come argomenti di funzione o valori restituiti, la copia atomica di tutti i membri di dati delle strutture richiede tempo della CPU.</span><span class="sxs-lookup"><span data-stu-id="78c78-310">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span> <span data-ttu-id="78c78-311">Occorre prestare attenzione alle chiamate ripetute alle proprietà che restituiscono strutture e memorizzare nella cache il valore della proprietà in una variabile locale per evitare la copia eccessiva di dati.</span><span class="sxs-lookup"><span data-stu-id="78c78-311">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span> 
  
 <span data-ttu-id="78c78-312">**Cache**</span><span class="sxs-lookup"><span data-stu-id="78c78-312">**Caches**</span></span>  
  
 <span data-ttu-id="78c78-313">Una soluzione comune per ottimizzare le prestazioni consiste nel memorizzare i risultati nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-313">A common performance trick is to cache results.</span></span> <span data-ttu-id="78c78-314">Una cache senza limiti di dimensione o senza criteri di eliminazione può tuttavia provocare perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="78c78-314">However, a cache without a size cap or disposal policy can be a memory leak.</span></span> <span data-ttu-id="78c78-315">Quando si elaborano quantità elevate di dati, se le cache trattengono una quantità elevata di memoria, è possibile che le operazioni di Garbage Collection annullino i vantaggi delle ricerche memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="78c78-315">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span> 
  
 <span data-ttu-id="78c78-316">In questo articolo è stato illustrato come individuare i sintomi relativi a colli di bottiglia delle prestazioni che possono influire sulla reattività dell'app, in particolare per sistemi di grandi dimensioni o sistemi che elaborano quantità elevate di dati.</span><span class="sxs-lookup"><span data-stu-id="78c78-316">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="78c78-317">Le cause più comuni includono la conversione boxing, le modifiche alle stringhe, le espressioni LINQ e lambda, la memorizzazione di metodi async nella cache, la memorizzazione nella cache senza limiti di dimensione o criteri di eliminazione, l'uso non appropriato di dizionari e il passaggio di strutture.</span><span class="sxs-lookup"><span data-stu-id="78c78-317">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span> <span data-ttu-id="78c78-318">Occorre tenere presenti le quattro considerazioni per l'ottimizzazione delle app:</span><span class="sxs-lookup"><span data-stu-id="78c78-318">Keep in mind the four facts for tuning your apps:</span></span>  
  
- <span data-ttu-id="78c78-319">Non eseguire prematuramente l'ottimizzazione: è consigliabile essere produttivi e ottimizzare l'app quando si individuano problemi.</span><span class="sxs-lookup"><span data-stu-id="78c78-319">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span> 
  
- <span data-ttu-id="78c78-320">I profili sono attendibili: solo le misurazioni assicurano la precisione.</span><span class="sxs-lookup"><span data-stu-id="78c78-320">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span> 
  
- <span data-ttu-id="78c78-321">La qualità degli strumenti è essenziale: scaricare PerfView e provare a usarlo.</span><span class="sxs-lookup"><span data-stu-id="78c78-321">Good tools make all the difference – download PerfView and try it out.</span></span> 
  
- <span data-ttu-id="78c78-322">Le allocazioni sono importantissime: il team responsabile della piattaforma del compilatore si è impegnato principalmente nel migliorare le prestazioni dei nuovi compilatori da questo punto di vista.</span><span class="sxs-lookup"><span data-stu-id="78c78-322">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="78c78-323">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78c78-323">See also</span></span>

- [<span data-ttu-id="78c78-324">Video di presentazione di questo argomento</span><span class="sxs-lookup"><span data-stu-id="78c78-324">Video of presentation of this topic</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [<span data-ttu-id="78c78-325">Guida per principianti alla profilatura delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="78c78-325">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [<span data-ttu-id="78c78-326">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="78c78-326">Performance</span></span>](index.md)
- <span data-ttu-id="78c78-327">[Suggerimenti sulle prestazioni .NET](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="78c78-327">[.NET Performance Tips](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span></span>
- [<span data-ttu-id="78c78-328">Esercitazioni su Channel 9 PerfView</span><span class="sxs-lookup"><span data-stu-id="78c78-328">Channel 9 PerfView tutorials</span></span>](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [<span data-ttu-id="78c78-329">SDK .NET Compiler Platform</span><span class="sxs-lookup"><span data-stu-id="78c78-329">The .NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="78c78-330">repository DotNet/Roslyn su GitHub</span><span class="sxs-lookup"><span data-stu-id="78c78-330">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)
