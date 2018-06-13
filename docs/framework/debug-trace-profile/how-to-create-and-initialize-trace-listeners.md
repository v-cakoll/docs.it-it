---
title: 'Procedura: creare e inizializzare listener di traccia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 943621b953fbe158b3be6ae0695ba7692b7c517f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389200"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="dbc03-102">Procedura: creare e inizializzare listener di traccia</span><span class="sxs-lookup"><span data-stu-id="dbc03-102">How to: Create and Initialize Trace Listeners</span></span>
<span data-ttu-id="dbc03-103">Le classi <xref:System.Diagnostics.Debug?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace?displayProperty=nameWithType> inviano messaggi a oggetti detti listener, che li ricevono e li elaborano.</span><span class="sxs-lookup"><span data-stu-id="dbc03-103">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="dbc03-104">Uno di questi listener, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, viene creato e inizializzato automaticamente quando si abilita la traccia o il debug.</span><span class="sxs-lookup"><span data-stu-id="dbc03-104">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="dbc03-105">Se si vuole indirizzare l'output di <xref:System.Diagnostics.Trace> o <xref:System.Diagnostics.Debug> a origini aggiuntive, è necessario creare e inizializzare listener di traccia aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="dbc03-105">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>  
  
 <span data-ttu-id="dbc03-106">I listener devono essere creati in base alle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dbc03-106">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="dbc03-107">Se, ad esempio, si desidera un record di testo di tutti gli output di traccia, creare un listener <xref:System.Diagnostics.TextWriterTraceListener>, che, quando è abilitato, scrive tutto l'output in un nuovo file di testo.</span><span class="sxs-lookup"><span data-stu-id="dbc03-107">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="dbc03-108">Se invece si vuole visualizzare l'output solo durante l'esecuzione dell'applicazione, creare un listener <xref:System.Diagnostics.ConsoleTraceListener>, che indirizza tutto l'output a una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="dbc03-108">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="dbc03-109">Il listener <xref:System.Diagnostics.EventLogTraceListener> è in grado di indirizzare l'output di traccia a un registro eventi.</span><span class="sxs-lookup"><span data-stu-id="dbc03-109">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="dbc03-110">Per altre informazioni, vedere [Listener di traccia](../../../docs/framework/debug-trace-profile/trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="dbc03-110">For more information, see [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md).</span></span>  
  
 <span data-ttu-id="dbc03-111">È possibile creare listener di traccia in un [file di configurazione dell'applicazione](../../../docs/framework/configure-apps/index.md) o nel codice.</span><span class="sxs-lookup"><span data-stu-id="dbc03-111">You can create trace listeners in an [application configuration file](../../../docs/framework/configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="dbc03-112">È consigliabile usare file di configurazione dell'applicazione, in quanto consentono di aggiungere, modificare o rimuovere listener di traccia senza dover modificare il codice.</span><span class="sxs-lookup"><span data-stu-id="dbc03-112">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>  
  
### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="dbc03-113">Per creare e usare un listener di traccia tramite un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="dbc03-113">To create and use a trace listener by using a configuration file</span></span>  
  
1.  <span data-ttu-id="dbc03-114">Dichiarare il listener di traccia nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dbc03-114">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="dbc03-115">Se il listener che si sta creando richiede altri oggetti, dichiarare anche tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="dbc03-115">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="dbc03-116">L'esempio seguente mostra come creare un listener denominato `myListener` che scrive nel file di testo `TextWriterOutput.log`.</span><span class="sxs-lookup"><span data-stu-id="dbc03-116">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <trace autoflush="false" indentsize="4">  
          <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />  
            <remove name="Default" />  
          </listeners>  
        </trace>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
2.  <span data-ttu-id="dbc03-117">Usare la classe <xref:System.Diagnostics.Trace> nel codice per scrivere un messaggio nei listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="dbc03-117">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>  
  
    ```vb  
    Trace.TraceInformation("Test message.")  
    ' You must close or flush the trace to empty the output buffer.  
    Trace.Flush()  
    ```  
  
    ```csharp  
    Trace.TraceInformation("Test message.");  
    // You must close or flush the trace to empty the output buffer.  
    Trace.Flush();  
    ```  
  
### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="dbc03-118">Per creare e usare un listener di traccia nel codice</span><span class="sxs-lookup"><span data-stu-id="dbc03-118">To create and use a trace listener in code</span></span>  
  
-   <span data-ttu-id="dbc03-119">Aggiungere il listener di traccia alla raccolta <xref:System.Diagnostics.Trace.Listeners%2A> e inviare le informazioni di traccia ai listener.</span><span class="sxs-lookup"><span data-stu-id="dbc03-119">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>  
  
    ```vb  
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))  
    Trace.TraceInformation("Test message.")  
    ' You must close or flush the trace to empty the output buffer.  
    Trace.Flush()  
    ```  
  
    ```csharp  
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));  
    Trace.TraceInformation("Test message.");  
    // You must close or flush the trace to empty the output buffer.  
    Trace.Flush();  
    ```  
  
     - <span data-ttu-id="dbc03-120">oppure -</span><span class="sxs-lookup"><span data-stu-id="dbc03-120">or -</span></span>  
  
-   <span data-ttu-id="dbc03-121">Se non si vuole che il listener riceva l'output di traccia, non aggiungerlo alla raccolta <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbc03-121">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="dbc03-122">È possibile trasmettere l'output tramite un listener indipendentemente dalla raccolta <xref:System.Diagnostics.Trace.Listeners%2A> chiamando i metodi di output del listener stesso.</span><span class="sxs-lookup"><span data-stu-id="dbc03-122">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="dbc03-123">L'esempio seguente mostra come scrivere una riga in un listener non incluso nella raccolta <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbc03-123">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>  
  
    ```vb  
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")  
    myListener.WriteLine("Test message.")  
    ' You must close or flush the trace listener to empty the output buffer.  
    myListener.Flush()  
    ```  
  
    ```csharp  
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");  
    myListener.WriteLine("Test message.");  
    // You must close or flush the trace listener to empty the output buffer.  
    myListener.Flush();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dbc03-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbc03-124">See Also</span></span>  
 [<span data-ttu-id="dbc03-125">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="dbc03-125">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="dbc03-126">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="dbc03-126">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="dbc03-127">Procedura: aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="dbc03-127">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="dbc03-128">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="dbc03-128">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
