---
title: 'Procedura: utilizzare TraceSource e filtri con listener di traccia'
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
ms.openlocfilehash: 53cdce767d437c47aab94e883381954f8cf70653
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215925"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="24e63-102">Procedura: utilizzare TraceSource e filtri con listener di traccia</span><span class="sxs-lookup"><span data-stu-id="24e63-102">How to: Use TraceSource and Filters with Trace Listeners</span></span>
<span data-ttu-id="24e63-103">Una delle nuove funzionalità di .NET Framework versione 2.0 è un sistema di traccia avanzato.</span><span class="sxs-lookup"><span data-stu-id="24e63-103">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="24e63-104">Il sistema di base è invariato: i messaggi di traccia vengono inviati tramite commutatori ai listener, che inviano i dati a un supporto di output associato.</span><span class="sxs-lookup"><span data-stu-id="24e63-104">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="24e63-105">Una delle differenze principali per la versione 2.0 è che le tracce possono essere avviate tramite istanze della classe <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="24e63-105">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="24e63-106">La classe <xref:System.Diagnostics.TraceSource> è progettata per operare come un sistema di traccia avanzato e può essere usata al posto dei metodi statici delle versioni precedenti delle classi di traccia <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug>.</span><span class="sxs-lookup"><span data-stu-id="24e63-106"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="24e63-107">Le classi note <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug> esistono ancora, ma la procedura consigliata prevede l'uso della classe <xref:System.Diagnostics.TraceSource> per la traccia.</span><span class="sxs-lookup"><span data-stu-id="24e63-107">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="24e63-108">Questo argomento descrive l'uso di <xref:System.Diagnostics.TraceSource> associata a un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24e63-108">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="24e63-109">È possibile, ma non consigliabile, gestire la traccia con <xref:System.Diagnostics.TraceSource> senza usare un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="24e63-109">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="24e63-110">Per informazioni sulla traccia senza un file di configurazione, vedere [Procedura: Creare e inizializzare origini di traccia](how-to-create-and-initialize-trace-sources.md).</span><span class="sxs-lookup"><span data-stu-id="24e63-110">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="24e63-111">Per creare e inizializzare l'origine di traccia</span><span class="sxs-lookup"><span data-stu-id="24e63-111">To create and initialize your trace source</span></span>  
  
1. <span data-ttu-id="24e63-112">Il primo passaggio per la strumentazione di un'applicazione con la traccia consiste nel creare un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="24e63-112">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="24e63-113">Nei progetti di grandi dimensioni con vari componenti, è possibile creare un'origine di traccia separata per ogni componente.</span><span class="sxs-lookup"><span data-stu-id="24e63-113">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="24e63-114">La procedura consigliata consiste nell'usare il nome dell'applicazione per il nome dell'origine di traccia,</span><span class="sxs-lookup"><span data-stu-id="24e63-114">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="24e63-115">in modo che sia più semplice mantenere separate le diverse tracce.</span><span class="sxs-lookup"><span data-stu-id="24e63-115">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="24e63-116">Il codice seguente crea una nuova origine di traccia (`mySource)`) e chiama un metodo (`Activity1`) che analizza gli eventi.</span><span class="sxs-lookup"><span data-stu-id="24e63-116">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="24e63-117">I messaggi di traccia vengono scritti dal listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="24e63-117">The trace messages are written by the default trace listener.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="24e63-118">Per creare e inizializzare listener di traccia e filtri</span><span class="sxs-lookup"><span data-stu-id="24e63-118">To create and initialize trace listeners and filters</span></span>  
  
1. <span data-ttu-id="24e63-119">Il codice nella prima procedura non identifica alcun listener di traccia o filtro a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="24e63-119">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="24e63-120">Con questo codice i messaggi di traccia vengono scritti semplicemente nel listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="24e63-120">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="24e63-121">Per configurare listener di traccia specifici e i relativi filtri associati, modificare il file di configurazione corrispondente al nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24e63-121">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="24e63-122">In questo file, è possibile aggiungere o rimuovere un listener, impostare le proprietà e il filtro per un listener o rimuovere i listener.</span><span class="sxs-lookup"><span data-stu-id="24e63-122">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="24e63-123">L'esempio di file di configurazione seguente mostra come inizializzare un listener di traccia della console e un listener di traccia del writer di testo per l'origine di traccia creata nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="24e63-123">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="24e63-124">Oltre alla configurazione dei listener di traccia, il file di configurazione crea filtri per entrambi i listener nonché un'opzione di origine per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="24e63-124">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="24e63-125">Per l'aggiunta dei listener di analisi sono illustrate due tecniche: aggiunta del listener direttamente nell'origine di analisi e aggiunta di un listener alla raccolta dei listener condivisi e quindi aggiunta di quest'ultimo in base al nome all'origine di analisi.</span><span class="sxs-lookup"><span data-stu-id="24e63-125">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="24e63-126">I filtri identificati per i due listener vengono inizializzati con livelli di origine differenti.</span><span class="sxs-lookup"><span data-stu-id="24e63-126">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="24e63-127">Di conseguenza, alcuni messaggi vengono scritti da uno solo dei due listener.</span><span class="sxs-lookup"><span data-stu-id="24e63-127">This results in some messages being written by only one of the two listeners.</span></span>  
  
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
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
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
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="24e63-128">Per modificare il livello in cui un listener scrive un messaggio di traccia</span><span class="sxs-lookup"><span data-stu-id="24e63-128">To change the level at which a listener writes a trace message</span></span>  
  
1. <span data-ttu-id="24e63-129">Il file di configurazione inizializza le impostazioni dell'origine di traccia nel momento in cui l'applicazione viene inizializzata.</span><span class="sxs-lookup"><span data-stu-id="24e63-129">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="24e63-130">Per modificare queste impostazioni, è necessario modificare il file di configurazione e riavviare l'applicazione o aggiornare l'applicazione a livello di codice usando il metodo <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24e63-130">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24e63-131">L'applicazione può modificare dinamicamente le proprietà impostate dal file di configurazione per eseguire l'override delle eventuali impostazioni specificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="24e63-131">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="24e63-132">È possibile, ad esempio, assicurarsi che i messaggi critici vengano sempre inviati a un file di testo, indipendentemente dalle impostazioni di configurazione correnti.</span><span class="sxs-lookup"><span data-stu-id="24e63-132">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="24e63-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24e63-133">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="24e63-134">Procedura: creare e inizializzare origini di traccia</span><span class="sxs-lookup"><span data-stu-id="24e63-134">How to: Create and Initialize Trace Sources</span></span>](how-to-create-and-initialize-trace-sources.md)
- [<span data-ttu-id="24e63-135">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="24e63-135">Trace Listeners</span></span>](trace-listeners.md)
