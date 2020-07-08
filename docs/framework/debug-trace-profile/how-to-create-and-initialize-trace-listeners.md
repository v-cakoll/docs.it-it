---
title: 'Procedura: creare e inizializzare listener di traccia'
description: Informazioni su come creare e inizializzare listener di traccia usando classi quali System. Diagnostics. DefaultTraceListener in .NET.
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
ms.openlocfilehash: 752306124e41a7fb7458daccc8c2891631eb9616
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051207"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a>Procedura: creare e inizializzare listener di traccia

Le classi <xref:System.Diagnostics.Debug?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace?displayProperty=nameWithType> inviano messaggi a oggetti detti listener, che li ricevono e li elaborano. Uno di questi listener, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, viene creato e inizializzato automaticamente quando si abilita la traccia o il debug. Se si vuole indirizzare l'output di <xref:System.Diagnostics.Trace> o <xref:System.Diagnostics.Debug> a origini aggiuntive, è necessario creare e inizializzare listener di traccia aggiuntivi.

I listener devono essere creati in base alle esigenze dell'applicazione. Se, ad esempio, si desidera un record di testo di tutti gli output di traccia, creare un listener <xref:System.Diagnostics.TextWriterTraceListener>, che, quando è abilitato, scrive tutto l'output in un nuovo file di testo. Se invece si vuole visualizzare l'output solo durante l'esecuzione dell'applicazione, creare un listener <xref:System.Diagnostics.ConsoleTraceListener>, che indirizza tutto l'output a una finestra della console. Il listener <xref:System.Diagnostics.EventLogTraceListener> è in grado di indirizzare l'output di traccia a un registro eventi. Per altre informazioni, vedere [Listener di traccia](trace-listeners.md).

È possibile creare listener di traccia in un [file di configurazione dell'applicazione](../configure-apps/index.md) o nel codice. È consigliabile usare file di configurazione dell'applicazione, in quanto consentono di aggiungere, modificare o rimuovere listener di traccia senza dover modificare il codice.

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a>Per creare e usare un listener di traccia tramite un file di configurazione

1. Dichiarare il listener di traccia nel file di configurazione dell'applicazione. Se il listener che si sta creando richiede altri oggetti, dichiarare anche tali oggetti. L'esempio seguente mostra come creare un listener denominato `myListener` che scrive nel file di testo `TextWriterOutput.log`.

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

2. Usare la classe <xref:System.Diagnostics.Trace> nel codice per scrivere un messaggio nei listener di traccia.

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

### <a name="to-create-and-use-a-trace-listener-in-code"></a>Per creare e usare un listener di traccia nel codice

- Aggiungere il listener di traccia alla raccolta <xref:System.Diagnostics.Trace.Listeners%2A> e inviare le informazioni di traccia ai listener.

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

    \- - oppure -

- Se non si vuole che il listener riceva l'output di traccia, non aggiungerlo alla raccolta <xref:System.Diagnostics.Trace.Listeners%2A>. È possibile trasmettere l'output tramite un listener indipendentemente dalla raccolta <xref:System.Diagnostics.Trace.Listeners%2A> chiamando i metodi di output del listener stesso. L'esempio seguente mostra come scrivere una riga in un listener non incluso nella raccolta <xref:System.Diagnostics.Trace.Listeners%2A>.

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

## <a name="see-also"></a>Vedere anche

- [Listener di traccia](trace-listeners.md)
- [Opzioni di traccia](trace-switches.md)
- [Procedura: aggiungere istruzioni di traccia al codice dell'applicazione](how-to-add-trace-statements-to-application-code.md)
- [Traccia e strumentazione di applicazioni](tracing-and-instrumenting-applications.md)
