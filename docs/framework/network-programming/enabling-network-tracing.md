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
ms.openlocfilehash: 61ffd422463ca70cc34c39dd216ce8e660809dcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180886"
---
# <a name="enabling-network-tracing"></a>Abilitazione della traccia di rete
La funzionalità di traccia di rete consente di accedere alle informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita. È necessario completare le attività seguenti per abilitare la traccia di rete nell'applicazione:  
  
- Compilare il codice con la traccia abilitata. Per altre informazioni sulle opzioni del compilatore necessarie per abilitare la traccia, vedere [Procedura: compilare in modo condizionale con traccia e debug](../debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
- Specificare una destinazione per l'output di traccia.  
  
- Configurare il comportamento della traccia di rete. Per informazioni dettagliate, vedere [Procedura: Configurare la traccia di rete](how-to-configure-network-tracing.md).  
  
 Le destinazioni di traccia più comuni, dette anche listener di traccia, sono il listener predefinito e il file di log.  
  
 La traccia usa il listener predefinito se non si specifica un listener di traccia. Per visualizzare i messaggi inviati al listener predefinito, è possibile eseguire il codice in un debugger abilitato per il codice gestito, ad esempio il debugger CLR, fornito con .NET Framework SDK, o DBwin32.exe, fornito con Windows SDK. Usando il debugger CLR, i messaggi di traccia vengono visualizzati nella finestra **Output**.  
  
 Se si preferisce usare un file per ricevere le tracce, è possibile specificare un file di log usando le impostazioni di configurazione, come illustrato nell'esempio seguente. Per informazioni generali sui file di configurazione, vedere [File di configurazione](../configure-apps/index.md).  
  
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

- [Interpretazione della traccia di rete](interpreting-network-tracing.md)
- [Traccia di rete in .NET Framework](network-tracing.md)
- [Traccia e strumentazione di applicazioni](../debug-trace-profile/tracing-and-instrumenting-applications.md)
