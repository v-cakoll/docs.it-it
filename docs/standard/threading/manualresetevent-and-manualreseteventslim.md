---
title: ManualResetEvent e ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent e ManualResetEventSlim
La <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> classe rappresenta un evento di handle di attesa locale che deve essere reimpostato manualmente dopo essere stato segnalato. Questa classe rappresenta un caso speciale della relativa classe base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di impostazione del manuale.  
  
 Oggetto <xref:System.Threading.ManualResetEvent> oggetto rimane segnalato fino a quando il relativo <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> metodo viene chiamato. Qualsiasi numero di thread in attesa, o di thread che attende l'evento dopo che è stato segnalato, può essere rilasciato mentre viene segnalato lo stato dell'oggetto. <xref:System.Threading.ManualResetEvent>corrisponde a un Win32 `CreateEvent` chiama, specificando `true` per il `bManualReset` argomento.  
  
 Nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare la <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> classe per ottenere prestazioni migliori quando si prevedono tempi di attesa molto brevi e quando l'evento non supera un limite di processo. <xref:System.Threading.ManualResetEventSlim>utilizza spin per un breve periodo di tempo durante l'attesa per l'evento venga segnalato. Quando i tempi di attesa sono brevi, la rotazione può essere molto meno costosa rispetto all'attesa tramite handle di attesa. Tuttavia, se l'evento non viene segnalato all'interno di un determinato periodo di tempo, <xref:System.Threading.ManualResetEventSlim> ricorre a un periodo di attesa di handle di evento regolare.  
  
## <a name="see-also"></a>Vedere anche  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore e SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
