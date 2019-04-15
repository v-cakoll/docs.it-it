---
title: Abilitazione della traccia di rete
ms.date: 03/30/2017
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
ms.openlocfilehash: 50ad01376f3de9cda26f6b00e2d32fc8d3dabdcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169715"
---
# <a name="enabling-network-tracing"></a>Abilitazione della traccia di rete
La funzionalità di traccia di rete consente di accedere alle informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita. È necessario completare le attività seguenti per abilitare la traccia di rete nell'applicazione:  
  
-   Compilare il codice con la traccia abilitata. Vedere [How to: Compilare in modo condizionale con traccia e debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) per altre informazioni sulle opzioni del compilatore necessarie per abilitare la traccia.  
  
-   Specificare una destinazione per l'output di traccia.  
  
-   Configurare il comportamento della traccia di rete. Vedere [How to: Configurare la traccia di rete](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) per informazioni dettagliate.  
  
 Le destinazioni di traccia più comuni, dette anche listener di traccia, sono il listener predefinito e il file di log.  
  
 La traccia usa il listener predefinito se non si specifica un listener di traccia. Per visualizzare i messaggi inviati al listener predefinito, è possibile eseguire il codice in un debugger abilitato per il codice gestito, ad esempio il debugger CLR, fornito con .NET Framework SDK, o DBwin32.exe, fornito con Windows SDK. Usando il debugger CLR, i messaggi di traccia vengono visualizzati nella finestra **Output**.  
  
 Se si preferisce usare un file per ricevere le tracce, è possibile specificare un file di log usando le impostazioni di configurazione, come illustrato nell'esempio seguente. Per informazioni generali sui file di configurazione, vedere [File di configurazione](../../../docs/framework/configure-apps/index.md).  
  
 Per inviare le tracce a un file di log, aggiungere il nodo seguente al nodo `<system.diagnostics>` del file di configurazione appropriato (applicazione o computer). È possibile modificare il nome del file (trace.log) in base alle esigenze.  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Interpretazione della traccia di rete](../../../docs/framework/network-programming/interpreting-network-tracing.md)
- [Tracciatura di rete in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)
- [Traccia e strumentazione di applicazioni](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
