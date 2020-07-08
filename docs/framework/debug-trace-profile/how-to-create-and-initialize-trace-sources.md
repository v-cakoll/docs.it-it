---
title: 'Procedura: creare e inizializzare origini di traccia'
description: Creare e inizializzare origini di traccia usando la classe TraceSource in .NET. Questa classe fornisce metodi per tracciare gli eventi e i dati ed emettere tracce informative.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: 55d7854bff991ba185d3f5d6e4c6e7222c9e3039
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051272"
---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="23fb0-104">Procedura: creare e inizializzare origini di traccia</span><span class="sxs-lookup"><span data-stu-id="23fb0-104">How to: Create and Initialize Trace Sources</span></span>
<span data-ttu-id="23fb0-105">La classe <xref:System.Diagnostics.TraceSource> viene utilizzata dalle applicazioni per produrre tracce associabili all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-105">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="23fb0-106"><xref:System.Diagnostics.TraceSource> fornisce metodi di traccia che consentono di tracciare con facilità eventi e dati e di generare tracce informative.</span><span class="sxs-lookup"><span data-stu-id="23fb0-106"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="23fb0-107">L'output di traccia da <xref:System.Diagnostics.TraceSource> può essere creato e inizializzato con o senza l'utilizzo di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-107">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="23fb0-108">In questo argomento vengono fornite istruzioni per entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="23fb0-108">This topic provides instructions for both options.</span></span> <span data-ttu-id="23fb0-109">È tuttavia consigliabile utilizzare file di configurazione per semplificare la riconfigurazione delle tracce prodotte dalle origini di traccia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-109">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="23fb0-110">Per creare e inizializzare un'origine di traccia utilizzando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="23fb0-110">To create and initialize a trace source using a configuration file</span></span>  
  
1. <span data-ttu-id="23fb0-111">Creare un progetto di applicazione console di Visual Studio (.NET Framework) e sostituire il codice fornito con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="23fb0-111">Create a Visual Studio console application project (.NET Framework) and replace the supplied code with the following code.</span></span> <span data-ttu-id="23fb0-112">Il codice registra errori e avvisi e ne restituisce alcuni sulla console e alcuni nel file myListener creato dalle voci del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-112">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. <span data-ttu-id="23fb0-113">Aggiungere un file di configurazione dell'applicazione al progetto per inizializzare l'origine della traccia denominata `TraceSourceApp` nell'esempio di codice riportato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="23fb0-113">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3. <span data-ttu-id="23fb0-114">Sostituire il contenuto del file di configurazione predefinito con le impostazioni seguenti per inizializzare un listener di traccia della console e un listener di traccia del writer di testo per l'origine di traccia creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="23fb0-114">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"
            switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"
            type="System.Diagnostics.TextWriterTraceListener"
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     <span data-ttu-id="23fb0-115">Oltre alla configurazione dei listener di traccia, il file di configurazione crea filtri per entrambi i listener nonché un'opzione di origine per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="23fb0-115">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="23fb0-116">Per l'aggiunta dei listener di analisi sono illustrate due tecniche: aggiunta del listener direttamente nell'origine di analisi e aggiunta di un listener alla raccolta dei listener condivisi e quindi aggiunta di quest'ultimo in base al nome all'origine di analisi.</span><span class="sxs-lookup"><span data-stu-id="23fb0-116">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="23fb0-117">I filtri identificati per i due listener vengono inizializzati con livelli di origine differenti.</span><span class="sxs-lookup"><span data-stu-id="23fb0-117">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="23fb0-118">Di conseguenza, alcuni messaggi vengono scritti da uno solo dei due listener.</span><span class="sxs-lookup"><span data-stu-id="23fb0-118">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="23fb0-119">Il file di configurazione inizializza le impostazioni dell'origine di traccia nel momento in cui l'applicazione viene inizializzata.</span><span class="sxs-lookup"><span data-stu-id="23fb0-119">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="23fb0-120">L'applicazione può modificare dinamicamente le proprietà impostate dal file di configurazione per eseguire l'override delle eventuali impostazioni specificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="23fb0-120">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="23fb0-121">È possibile, ad esempio, assicurare che i messaggi critici vengano sempre inviati a un file di testo, indipendentemente dalle impostazioni di configurazione correnti.</span><span class="sxs-lookup"><span data-stu-id="23fb0-121">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="23fb0-122">Nell'esempio di codice viene illustrato come eseguire l'override delle impostazioni del file di configurazione per garantire l'invio dei messaggi critici ai listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="23fb0-122">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="23fb0-123">Le eventuali modifiche apportate alle impostazioni del file di configurazione durante l'esecuzione dell'applicazione non vengono applicate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="23fb0-123">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="23fb0-124">Per modificare le impostazioni, è necessario riavviare l'applicazione o aggiornare l'applicazione a livello di codice utilizzando il metodo <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="23fb0-124">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="23fb0-125">Per inizializzare le origini di analisi, i listener e i filtri senza un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="23fb0-125">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
- <span data-ttu-id="23fb0-126">Utilizzare l'esempio di codice seguente per abilitare la traccia in un'origine di traccia senza utilizzare un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-126">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="23fb0-127">Si consiglia, tuttavia, di utilizzare questa tecnica soltanto quando si desidera eseguire la traccia senza dipendere dai file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23fb0-127">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="23fb0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23fb0-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="23fb0-129">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="23fb0-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
