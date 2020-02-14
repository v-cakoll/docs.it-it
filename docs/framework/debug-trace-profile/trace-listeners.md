---
title: Listener di traccia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
ms.openlocfilehash: a51c046a296fbb62d21c7784cf7c1e78b700f3e9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216146"
---
# <a name="trace-listeners"></a><span data-ttu-id="8eb93-102">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="8eb93-102">Trace Listeners</span></span>
<span data-ttu-id="8eb93-103">Quando si usa **Trace**, **Debug** e <xref:System.Diagnostics.TraceSource>, è necessario disporre di un meccanismo per la raccolta e la registrazione dei messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="8eb93-103">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="8eb93-104">I messaggi di traccia vengono ricevuti dai *listener*.</span><span class="sxs-lookup"><span data-stu-id="8eb93-104">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="8eb93-105">La funzione di un listener è quella di raccogliere, archiviare e indirizzare i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="8eb93-105">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="8eb93-106">I listener dirigono l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="8eb93-106">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="8eb93-107">I listener sono disponibili per le classi **Debug**, **Trace** e <xref:System.Diagnostics.TraceSource>, ognuna delle quali può inviare il proprio output a un'ampia gamma di oggetti listener.</span><span class="sxs-lookup"><span data-stu-id="8eb93-107">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="8eb93-108">Di seguito sono riportati i listener predefiniti comunemente usati:</span><span class="sxs-lookup"><span data-stu-id="8eb93-108">The following are the commonly used predefined listeners:</span></span>  
  
- <span data-ttu-id="8eb93-109"><xref:System.Diagnostics.TextWriterTraceListener> reindirizza l'output a un'istanza della classe <xref:System.IO.TextWriter> o a qualsiasi oggetto che sia una classe <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="8eb93-109">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="8eb93-110">Può anche scrivere nella console o in un file, perché si tratta di classi <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="8eb93-110">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
- <span data-ttu-id="8eb93-111"><xref:System.Diagnostics.EventLogTraceListener> reindirizza l'output a un log eventi.</span><span class="sxs-lookup"><span data-stu-id="8eb93-111">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
- <span data-ttu-id="8eb93-112"><xref:System.Diagnostics.DefaultTraceListener> genera messaggi **Write** e **WriteLine** in **OutputDebugString** e nel metodo **Debugger.Log**.</span><span class="sxs-lookup"><span data-stu-id="8eb93-112">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="8eb93-113">In Visual Studio questo comportamento fa sì che i messaggi di debug vengano visualizzati nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="8eb93-113">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="8eb93-114">I messaggi **Assert** non riusciti e **Fail** vengono generati anche nell'API Windows **OutputDebugString** e nel metodo **Debugger.Log** e provocano anche la visualizzazione di una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8eb93-114">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="8eb93-115">Questo comportamento è quello predefinito per i messaggi di **Debug** e **Trace**, perché **DefaultTraceListener** viene automaticamente incluso in ogni raccolta `Listeners` ed è l'unico listener incluso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8eb93-115">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
- <span data-ttu-id="8eb93-116"><xref:System.Diagnostics.ConsoleTraceListener> reindirizza l'output di traccia o di debug all'output standard o al flusso di errori standard.</span><span class="sxs-lookup"><span data-stu-id="8eb93-116">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
- <span data-ttu-id="8eb93-117">Tramite l'oggetto <xref:System.Diagnostics.DelimitedListTraceListener> l'output di traccia o di debug viene indirizzato a un writer di testo, ad esempio un writer di flusso oppure a un flusso, ad esempio un flusso di file.</span><span class="sxs-lookup"><span data-stu-id="8eb93-117">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="8eb93-118">L'output di traccia è in un formato di testo delimitato che usa il delimitatore specificato dalla proprietà <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.</span><span class="sxs-lookup"><span data-stu-id="8eb93-118">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
- <span data-ttu-id="8eb93-119"><xref:System.Diagnostics.XmlWriterTraceListener> reindirizza l'output di traccia o di debug come dati con codifica XML a un oggetto <xref:System.IO.TextWriter> o <xref:System.IO.Stream>, come <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="8eb93-119">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="8eb93-120">Se si vuole che altri listener oltre a <xref:System.Diagnostics.DefaultTraceListener> ricevano l'output di **Debug**, **Trace** e <xref:System.Diagnostics.TraceSource>, è necessario aggiungerli alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="8eb93-120">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="8eb93-121">Per altre informazioni, vedere [Procedura: Creare e inizializzare listener di traccia](how-to-create-and-initialize-trace-listeners.md) e [Procedura: Usare TraceSource e filtri con listener di traccia](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="8eb93-121">For more information, see [How to: Create and Initialize Trace Listeners](how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="8eb93-122">Tutti i listener inclusi nella raccolta **Listeners** ricevono gli stessi messaggi dai metodi di output di traccia.</span><span class="sxs-lookup"><span data-stu-id="8eb93-122">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="8eb93-123">Si supponga, ad esempio, di configurare due listener, **TextWriterTraceListener** ed **EventLogTraceListener**.</span><span class="sxs-lookup"><span data-stu-id="8eb93-123">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="8eb93-124">Ogni listener riceve lo stesso messaggio.</span><span class="sxs-lookup"><span data-stu-id="8eb93-124">Each listener receives the same message.</span></span> <span data-ttu-id="8eb93-125">**TextWriterTraceListener** reindirizzerà l'output a un flusso, mentre **EventLogTraceListener** reindirizzerà l'output a un log eventi.</span><span class="sxs-lookup"><span data-stu-id="8eb93-125">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="8eb93-126">L'esempio seguente mostra come inviare l'output alla raccolta **Listeners**.</span><span class="sxs-lookup"><span data-stu-id="8eb93-126">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 <span data-ttu-id="8eb93-127">Poiché Debug e Trace condividono la stessa raccolta **Listeners**, se si aggiunge un oggetto listener a una raccolta **Debug.Listeners** nell'applicazione, l'oggetto viene aggiunto anche alla raccolta **Trace.Listeners**.</span><span class="sxs-lookup"><span data-stu-id="8eb93-127">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="8eb93-128">L'esempio seguente mostra come usare un listener per inviare informazioni di traccia a una console:</span><span class="sxs-lookup"><span data-stu-id="8eb93-128">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="8eb93-129">Listener definiti dallo sviluppatore</span><span class="sxs-lookup"><span data-stu-id="8eb93-129">Developer-Defined Listeners</span></span>  
 <span data-ttu-id="8eb93-130">È possibile definire listener personalizzati ereditando dalla classe di base **TraceListener** ed eseguendo l'override dei metodi della classe con metodi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8eb93-130">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="8eb93-131">Per altre informazioni sulla creazione di listener definiti dallo sviluppatore, vedere <xref:System.Diagnostics.TraceListener> negli argomenti di riferimento su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8eb93-131">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb93-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eb93-132">See also</span></span>

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="8eb93-133">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="8eb93-133">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="8eb93-134">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="8eb93-134">Trace Switches</span></span>](trace-switches.md)
