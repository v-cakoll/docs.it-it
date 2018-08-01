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
ms.openlocfilehash: c1785ce223f0dcd4da7ea6ef9fa3a3e897a39dca
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143518"
---
# <a name="autoresetevent"></a>AutoResetEvent
La classe <xref:System.Threading.AutoResetEvent> rappresenta un evento di handle di attesa locale che viene reimpostato automaticamente quando viene segnalato, dopo il rilascio di un singolo thread in attesa. Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle>. Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di ripristino automatici.  
  
 Un oggetto <xref:System.Threading.AutoResetEvent> viene reimpostato automaticamente su non segnalato dal sistema dopo il rilascio di un singolo thread in attesa. Se non c'è alcun thread in attesa, lo stato dell'oggetto evento resta segnalato. <xref:System.Threading.AutoResetEvent> corrisponde a una chiamata Win32 a `CreateEvent`, che specifica `false` per l'argomento `bManualReset`.  
  
 Per un esempio che usa <xref:System.Threading.AutoResetEvent>, vedere <xref:System.Threading.Monitor>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
