---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583152"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent

Gli handle di attesa degli eventi consentono di sincronizzare le attività segnalandosi reciprocamente e attendendo segnali degli altri thread. Questi eventi di sincronizzazione sono basati sugli handle di attesa del sistema operativo e possono essere suddivisi in due tipi: quelli che vengono reimpostati automaticamente quando vengono segnalati e quelli che devono essere reimpostati manualmente.  
  
Gli handle di attesa degli eventi sono utili in molti degli scenari di sincronizzazione della classe <xref:System.Threading.Monitor>. Gli handle di attesa degli eventi sono spesso più facili da usare dei metodi <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> e offrono un controllo maggiore sulla segnalazione. Gli handle di attesa dell'evento denominato possono inoltre essere usati per sincronizzare le attività nei domini delle applicazioni e nei processi, mentre i monitor sono locali rispetto a un dominio dell'applicazione.  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [EventWaitHandle](eventwaithandle.md)  
 La classe <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> può rappresentare sia gli eventi di reimpostazione automatici che quelli manuali, nonché gli eventi locali o gli eventi del sistema denominato.  
  
 [AutoResetEvent](autoresetevent.md)  
 La classe <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che viene reimpostato automaticamente.  
  
 [ManualResetEvent e ManualResetEventSlim](manualresetevent-and-manualreseteventslim.md)  
 La classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che deve essere reimpostato manualmente. La classe <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> è una versione leggera e più veloce che può essere usata per gli eventi all'interno del processo stesso.  
  
 [CountdownEvent](countdownevent.md)  
 La classe <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> fornisce un metodo semplificato per implementare modelli di parallelismo fork/join nel codice che sfrutta gli handle di attesa.  

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
- [Nozioni di base sul threading gestito](managed-threading-basics.md)
