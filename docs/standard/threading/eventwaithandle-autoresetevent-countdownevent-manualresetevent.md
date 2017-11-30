---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Gli handle di attesa degli eventi consentono di sincronizzare le attività segnalandosi reciprocamente e attendendo segnali degli altri thread. Questi eventi di sincronizzazione sono basati sugli handle di attesa Win32 e possono essere suddivisi in due tipi: quelli che vengono reimpostati automaticamente quando vengono segnalati e quelli che devono essere reimpostati manualmente.  
  
 Handle di attesa eventi sono utili in molti degli stessi scenari di sincronizzazione di <xref:System.Threading.Monitor> classe. Handle di attesa eventi sono spesso più facili da utilizzare rispetto di <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> metodi e forniscono un controllo più efficiente della segnalazione. Gli handle di attesa dell'evento denominato possono inoltre essere usati per sincronizzare le attività nei domini delle applicazioni e nei processi, mentre i monitor sono locali rispetto a un dominio dell'applicazione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 La <xref:System.Threading.EventWaitHandle> classe può rappresentare un automatico o manuale Reimposta nonché eventi locali o eventi di sistema denominato.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Il <xref:System.Threading.AutoResetEvent> deriva dalla classe <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale viene reimpostato automaticamente.  
  
 [ManualResetEvent e ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Il <xref:System.Threading.ManualResetEvent> deriva dalla classe <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che deve essere reimpostato manualmente. La <xref:System.Threading.ManualResetEventSlim> classe è una versione più veloce e semplice che può essere utilizzata per gli eventi all'interno del processo stesso.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 La <xref:System.Threading.CountdownEvent> classe fornisce un metodo semplificato per implementare modelli di parallelismo di divisione e unione nel codice che usa handle di attesa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Il <xref:System.Threading.WaitHandle> classe è la classe base per il <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, e <xref:System.Threading.Mutex> classi. Contiene metodi statici, ad esempio <xref:System.Threading.WaitHandle.SignalAndWait%2A> e <xref:System.Threading.WaitHandle.WaitAll%2A> che sono utili quando si lavora con tutti i tipi di handle di attesa.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Nozioni di base sul threading gestito](../../../docs/standard/threading/managed-threading-basics.md)
