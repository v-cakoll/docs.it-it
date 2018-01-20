---
title: Abilitazione della traccia di rete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 8f6a23ce156941291fe499b6402061639569815c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="enabling-network-tracing"></a>Abilitazione della traccia di rete
La funzionalità di traccia di rete consente di accedere alle informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita. È necessario completare le attività seguenti per abilitare la traccia di rete nell'applicazione:  
  
-   Compilare il codice con la traccia abilitata. Per altre informazioni sulle opzioni del compilatore necessarie per abilitare la traccia, vedere [Procedura: compilare in modo condizionale con traccia e debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
-   Specificare una destinazione per l'output di traccia.  
  
-   Configurare il comportamento della traccia di rete. Per informazioni dettagliate, vedere [Procedura: Configurare la traccia di rete](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
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
 [Interpretazione della traccia di rete](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Traccia di rete in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 [Introduzione alla strumentazione e alla traccia](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
