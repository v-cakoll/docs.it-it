---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 543853f581436a5fb7e5c897012b99bef20dc289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Gli handle di attesa degli eventi consentono di sincronizzare le attività segnalandosi reciprocamente e attendendo segnali degli altri thread. Questi eventi di sincronizzazione sono basati sugli handle di attesa Win32 e possono essere suddivisi in due tipi: quelli che vengono reimpostati automaticamente quando vengono segnalati e quelli che devono essere reimpostati manualmente.  
  
 Gli handle di attesa degli eventi sono utili in molti degli scenari di sincronizzazione della classe <xref:System.Threading.Monitor>. Gli handle di attesa degli eventi sono spesso più facili da usare dei metodi <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> e offrono un controllo maggiore sulla segnalazione. Gli handle di attesa dell'evento denominato possono inoltre essere usati per sincronizzare le attività nei domini delle applicazioni e nei processi, mentre i monitor sono locali rispetto a un dominio dell'applicazione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 La classe <xref:System.Threading.EventWaitHandle> può rappresentare sia gli eventi di reimpostazione automatici che quelli manuali, nonché gli eventi locali o gli eventi del sistema denominato.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 La classe <xref:System.Threading.AutoResetEvent> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che viene reimpostato automaticamente.  
  
 [ManualResetEvent e ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 La classe <xref:System.Threading.ManualResetEvent> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che deve essere reimpostato manualmente. La classe <xref:System.Threading.ManualResetEventSlim> è una versione leggera e più veloce che può essere usata per gli eventi all'interno del processo stesso.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 La classe <xref:System.Threading.CountdownEvent> fornisce un metodo semplificato per implementare modelli di parallelismo fork/join nel codice che sfrutta gli handle di attesa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 La classe <xref:System.Threading.WaitHandle> è la classe di base per le classi <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> e <xref:System.Threading.Mutex>. Contiene metodi statici, ad esempio <xref:System.Threading.WaitHandle.SignalAndWait%2A> e <xref:System.Threading.WaitHandle.WaitAll%2A>, che sono utili quando si usano tutti i tipi di handle di attesa.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Nozioni di base sul threading gestito](../../../docs/standard/threading/managed-threading-basics.md)
