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
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a>Procedura: utilizzare TraceSource e filtri con listener di traccia
Una delle nuove funzionalità di .NET Framework versione 2.0 è un sistema di traccia avanzato. Il sistema di base è invariato: i messaggi di traccia vengono inviati tramite commutatori ai listener, che inviano i dati a un supporto di output associato. Una delle differenze principali per la versione 2.0 è che le tracce possono essere avviate tramite istanze della classe <xref:System.Diagnostics.TraceSource>. La classe <xref:System.Diagnostics.TraceSource> è progettata per operare come un sistema di traccia avanzato e può essere usata al posto dei metodi statici delle versioni precedenti delle classi di traccia <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug>. Le classi note <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug> esistono ancora, ma la procedura consigliata prevede l'uso della classe <xref:System.Diagnostics.TraceSource> per la traccia.  
  
 Questo argomento descrive l'uso di <xref:System.Diagnostics.TraceSource> associata a un file di configurazione dell'applicazione.  È possibile, ma non consigliabile, gestire la traccia con <xref:System.Diagnostics.TraceSource> senza usare un file di configurazione. Per informazioni sulla traccia senza un file di configurazione, vedere [Procedura: Creare e inizializzare origini di traccia](how-to-create-and-initialize-trace-sources.md).  
  
### <a name="to-create-and-initialize-your-trace-source"></a>Per creare e inizializzare l'origine di traccia  
  
1. Il primo passaggio per la strumentazione di un'applicazione con la traccia consiste nel creare un'origine di traccia. Nei progetti di grandi dimensioni con vari componenti, è possibile creare un'origine di traccia separata per ogni componente. La procedura consigliata consiste nell'usare il nome dell'applicazione per il nome dell'origine di traccia, in modo che sia più semplice mantenere separate le diverse tracce. Il codice seguente crea una nuova origine di traccia (`mySource)`) e chiama un metodo (`Activity1`) che analizza gli eventi.  I messaggi di traccia vengono scritti dal listener di traccia predefinito.  
  
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
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a>Per creare e inizializzare listener di traccia e filtri  
  
1. Il codice nella prima procedura non identifica alcun listener di traccia o filtro a livello di codice. Con questo codice i messaggi di traccia vengono scritti semplicemente nel listener di traccia predefinito. Per configurare listener di traccia specifici e i relativi filtri associati, modificare il file di configurazione corrispondente al nome dell'applicazione. In questo file, è possibile aggiungere o rimuovere un listener, impostare le proprietà e il filtro per un listener o rimuovere i listener. L'esempio di file di configurazione seguente mostra come inizializzare un listener di traccia della console e un listener di traccia del writer di testo per l'origine di traccia creata nella procedura precedente. Oltre alla configurazione dei listener di traccia, il file di configurazione crea filtri per entrambi i listener nonché un'opzione di origine per l'origine di traccia. Per l'aggiunta dei listener di analisi sono illustrate due tecniche: aggiunta del listener direttamente nell'origine di analisi e aggiunta di un listener alla raccolta dei listener condivisi e quindi aggiunta di quest'ultimo in base al nome all'origine di analisi. I filtri identificati per i due listener vengono inizializzati con livelli di origine differenti. Di conseguenza, alcuni messaggi vengono scritti da uno solo dei due listener.  
  
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
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a>Per modificare il livello in cui un listener scrive un messaggio di traccia  
  
1. Il file di configurazione inizializza le impostazioni dell'origine di traccia nel momento in cui l'applicazione viene inizializzata. Per modificare queste impostazioni, è necessario modificare il file di configurazione e riavviare l'applicazione o aggiornare l'applicazione a livello di codice usando il metodo <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>. L'applicazione può modificare dinamicamente le proprietà impostate dal file di configurazione per eseguire l'override delle eventuali impostazioni specificate dall'utente.  È possibile, ad esempio, assicurarsi che i messaggi critici vengano sempre inviati a un file di testo, indipendentemente dalle impostazioni di configurazione correnti.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [Procedura: creare e inizializzare origini di traccia](how-to-create-and-initialize-trace-sources.md)
- [Listener di traccia](trace-listeners.md)
