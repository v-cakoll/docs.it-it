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
# <a name="trace-listeners"></a>Listener di traccia
Quando si usa **Trace**, **Debug** e <xref:System.Diagnostics.TraceSource>, è necessario disporre di un meccanismo per la raccolta e la registrazione dei messaggi inviati. I messaggi di traccia vengono ricevuti dai *listener*. La funzione di un listener è quella di raccogliere, archiviare e indirizzare i messaggi di traccia. I listener dirigono l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.  
  
 I listener sono disponibili per le classi **Debug**, **Trace** e <xref:System.Diagnostics.TraceSource>, ognuna delle quali può inviare il proprio output a un'ampia gamma di oggetti listener. Di seguito sono riportati i listener predefiniti comunemente usati:  
  
- <xref:System.Diagnostics.TextWriterTraceListener> reindirizza l'output a un'istanza della classe <xref:System.IO.TextWriter> o a qualsiasi oggetto che sia una classe <xref:System.IO.Stream>. Può anche scrivere nella console o in un file, perché si tratta di classi <xref:System.IO.Stream>.  
  
- <xref:System.Diagnostics.EventLogTraceListener> reindirizza l'output a un log eventi.  
  
- <xref:System.Diagnostics.DefaultTraceListener> genera messaggi **Write** e **WriteLine** in **OutputDebugString** e nel metodo **Debugger.Log**. In Visual Studio questo comportamento fa sì che i messaggi di debug vengano visualizzati nella finestra di output. I messaggi **Assert** non riusciti e **Fail** vengono generati anche nell'API Windows **OutputDebugString** e nel metodo **Debugger.Log** e provocano anche la visualizzazione di una finestra di messaggio. Questo comportamento è quello predefinito per i messaggi di **Debug** e **Trace**, perché **DefaultTraceListener** viene automaticamente incluso in ogni raccolta `Listeners` ed è l'unico listener incluso automaticamente.  
  
- <xref:System.Diagnostics.ConsoleTraceListener> reindirizza l'output di traccia o di debug all'output standard o al flusso di errori standard.  
  
- Tramite l'oggetto <xref:System.Diagnostics.DelimitedListTraceListener> l'output di traccia o di debug viene indirizzato a un writer di testo, ad esempio un writer di flusso oppure a un flusso, ad esempio un flusso di file. L'output di traccia è in un formato di testo delimitato che usa il delimitatore specificato dalla proprietà <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.  
  
- <xref:System.Diagnostics.XmlWriterTraceListener> reindirizza l'output di traccia o di debug come dati con codifica XML a un oggetto <xref:System.IO.TextWriter> o <xref:System.IO.Stream>, come <xref:System.IO.FileStream>.  
  
 Se si vuole che altri listener oltre a <xref:System.Diagnostics.DefaultTraceListener> ricevano l'output di **Debug**, **Trace** e <xref:System.Diagnostics.TraceSource>, è necessario aggiungerli alla raccolta `Listeners`. Per altre informazioni, vedere [Procedura: Creare e inizializzare listener di traccia](how-to-create-and-initialize-trace-listeners.md) e [Procedura: Usare TraceSource e filtri con listener di traccia](how-to-use-tracesource-and-filters-with-trace-listeners.md). Tutti i listener inclusi nella raccolta **Listeners** ricevono gli stessi messaggi dai metodi di output di traccia. Si supponga, ad esempio, di configurare due listener, **TextWriterTraceListener** ed **EventLogTraceListener**. Ogni listener riceve lo stesso messaggio. **TextWriterTraceListener** reindirizzerà l'output a un flusso, mentre **EventLogTraceListener** reindirizzerà l'output a un log eventi.  
  
 L'esempio seguente mostra come inviare l'output alla raccolta **Listeners**.  
  
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
  
 Poiché Debug e Trace condividono la stessa raccolta **Listeners**, se si aggiunge un oggetto listener a una raccolta **Debug.Listeners** nell'applicazione, l'oggetto viene aggiunto anche alla raccolta **Trace.Listeners**.  
  
 L'esempio seguente mostra come usare un listener per inviare informazioni di traccia a una console:  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a>Listener definiti dallo sviluppatore  
 È possibile definire listener personalizzati ereditando dalla classe di base **TraceListener** ed eseguendo l'override dei metodi della classe con metodi personalizzati. Per altre informazioni sulla creazione di listener definiti dallo sviluppatore, vedere <xref:System.Diagnostics.TraceListener> negli argomenti di riferimento su .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [Traccia e strumentazione di applicazioni](tracing-and-instrumenting-applications.md)
- [Opzioni di traccia](trace-switches.md)
