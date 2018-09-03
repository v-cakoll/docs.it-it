---
title: ManualResetEvent e ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4a6950d17fef60298a2e47b63bec068554b2b8b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43390501"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent e ManualResetEventSlim
La classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> rappresenta un evento di handle di attesa locale che deve essere reimpostato manualmente dopo essere stato segnalato. Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di impostazione del manuale.  
  
 Un oggetto <xref:System.Threading.ManualResetEvent> rimane segnalato finché non viene chiamato il metodo <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>. Qualsiasi numero di thread in attesa, o di thread che attende l'evento dopo che è stato segnalato, può essere rilasciato mentre viene segnalato lo stato dell'oggetto. <xref:System.Threading.ManualResetEvent> corrisponde a una chiamata Win32 a `CreateEvent`, che specifica `true` per l'argomento `bManualReset`.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] è possibile usare la classe <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> per ottenere prestazioni migliori quando si prevedono tempi di attesa molto brevi e quando l'evento non supera un limite di processo. <xref:System.Threading.ManualResetEventSlim> usa una rotazione per un breve periodo di tempo mentre si attende che l'evento venga segnalato. Quando i tempi di attesa sono brevi, la rotazione può essere molto meno costosa rispetto all'attesa tramite handle di attesa. Se tuttavia l'evento non viene segnalato entro un determinato periodo di tempo, <xref:System.Threading.ManualResetEventSlim> ricorre a una normale attesa di handle dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Handle di attesa](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore e SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
