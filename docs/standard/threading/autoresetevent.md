---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4ab06993eed4b39746875a6ef3ebfad5edbd2e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581703"
---
# <a name="autoresetevent"></a>AutoResetEvent
La classe <xref:System.Threading.AutoResetEvent> rappresenta un evento di handle di attesa locale che viene reimpostato automaticamente quando viene segnalato, dopo il rilascio di un singolo thread in attesa. Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle>. Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di ripristino automatici.  
  
 Un oggetto <xref:System.Threading.AutoResetEvent> viene reimpostato automaticamente su non segnalato dal sistema dopo il rilascio di un singolo thread in attesa. Se non c'è alcun thread in attesa, lo stato dell'oggetto evento resta segnalato. <xref:System.Threading.AutoResetEvent> corrisponde a una chiamata Win32 a `CreateEvent`, che specifica `false` per l'argomento `bManualReset`.  
  
 Per un esempio che usa <xref:System.Threading.AutoResetEvent>, vedere [Classe Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
