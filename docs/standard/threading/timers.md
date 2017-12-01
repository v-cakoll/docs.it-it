---
title: Timer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a>Timer
I timer sono oggetti leggeri che consentono di specificare un delegato da chiamare a un'ora specificata. Un thread nel pool di thread esegue l'operazione di attesa.  
  
 Utilizzando la <xref:System.Threading.Timer?displayProperty=nameWithType> classe è semplice. Si crea un **Timer**, passando un <xref:System.Threading.TimerCallback> delegato al metodo di callback, un oggetto che rappresenta lo stato che verrà passato al callback, un tempo di generazione iniziale e un'ora che rappresenta il periodo compreso tra le chiamate di callback. Per annullare un timer in sospeso, chiamare il **timer** (funzione).  
  
> [!NOTE]
>  Esistono altre due classi timer. La <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> classe è un controllo che funziona con finestre di progettazione visiva e deve essere usato in contesti dell'interfaccia utente; genera gli eventi nel thread dell'interfaccia utente. Il <xref:System.Timers.Timer?displayProperty=nameWithType> deriva dalla classe <xref:System.ComponentModel.Component>, pertanto può essere utilizzato con finestre di progettazione visiva; genera anche gli eventi, ma li genera in un <xref:System.Threading.ThreadPool> thread. Il <xref:System.Threading.Timer?displayProperty=nameWithType> classe crea i callback in un <xref:System.Threading.ThreadPool> thread e non utilizza il modello di eventi. Fornisce inoltre un oggetto di stato al metodo di callback, non altri timer. È estremamente semplice.  
  
 Nell'esempio seguente avvia un timer che inizia dopo un secondo (1000 millisecondi) e segni di graduazione ogni secondo finché non si preme il **invio** chiave. La variabile contenente il riferimento per il timer è un campo a livello di classe, per assicurarsi che il timer non sottoposte a garbage collection mentre è ancora in esecuzione. Per ulteriori informazioni sulla garbage collection aggressive, vedere <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Timer>  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
