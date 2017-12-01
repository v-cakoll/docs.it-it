---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>è un tipo di sincronizzazione leggera che è possibile utilizzare in scenari di basso livello per evitare i cambi di contesto dispendiosi e le transizioni del kernel che sono necessari per gli eventi del kernel. Nei computer multicore, quando una risorsa non devono essere mantenuti per lunghi periodi di tempo, può essere più efficiente per un thread in attesa per poche decine o centinaia di cicli di selezione in modalità utente e quindi ritenterà di acquisire la risorsa. Se la risorsa è disponibile dopo la rotazione, è stato salvato diverse migliaia di cicli. Se la risorsa non è ancora disponibile, è dedicato solo alcuni cicli e può comunque immettere un periodo di attesa basata sul kernel. Questa combinazione di spin-attesa è talvolta detta un *operazione di attesa a due fasi*.  
  
 <xref:System.Threading.SpinWait>è progettato per essere utilizzato in combinazione con i tipi di .NET Framework che eseguono il wrapping di eventi kernel, ad esempio <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait>può inoltre essere utilizzato da solo per la funzionalità di base rotante in un unico programma.  
  
 <xref:System.Threading.SpinWait>è molto più di un ciclo vuoto. Viene implementato con attenzione per fornire il comportamento di spin corretto per il caso generale, e se stesso avvierà commutazioni di contesto se lo spin è sufficientemente lunga (approssimativamente la quantità di tempo necessaria per una transizione kernel). Ad esempio, nei computer di core singolo, <xref:System.Threading.SpinWait> restituisce l'intervallo di tempo del thread immediatamente perché spin blocca l'avanzamento in tutti i thread. <xref:System.Threading.SpinWait>Restituisce inoltre anche nei computer multicore per impedire che il thread in attesa di blocco thread con priorità superiore o il garbage collector. Pertanto, se si utilizza un <xref:System.Threading.SpinWait> in un'operazione di attesa a due fasi, è consigliabile richiamare l'attesa del kernel prima il <xref:System.Threading.SpinWait> stesso avvii un cambio di contesto. <xref:System.Threading.SpinWait>fornisce il <xref:System.Threading.SpinWait.NextSpinWillYield%2A> proprietà, è possibile controllare prima di ogni chiamata a <xref:System.Threading.SpinWait.SpinOnce%2A>. Quando la proprietà restituisce `true`, avviare la propria operazione di attesa. Per un esempio, vedere [procedura: utilizzare SpinWait per implementare un'operazione di attesa in due fasi](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Se non si esegue un'operazione di attesa a due fasi, ma solo uno spin finché una condizione è true, è possibile abilitare <xref:System.Threading.SpinWait> per eseguire il relativo contesto opzioni in modo che sia un elemento positivo nell'ambiente del sistema operativo Windows. L'esempio di base seguente viene illustrato un <xref:System.Threading.SpinWait> in uno stack senza blocco. Se è necessario uno stack di thread-safe, ad alte prestazioni, è consigliabile utilizzare <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
