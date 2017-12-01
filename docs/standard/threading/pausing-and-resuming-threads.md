---
title: Sospensione e ripresa di thread
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
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>Sospensione e ripresa di thread
Le tecniche più comuni per sincronizzare le attività dei thread consistono nel blocco e nel rilascio dei thread oppure nel blocco di oggetti o aree di codice. Per altre informazioni su questi meccanismi di blocco, vedere [Panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 È anche possibile fare in modo che i thread vengano sospesi automaticamente. Quando i thread sono bloccati o sospesi, è possibile usare un'eccezione <xref:System.Threading.ThreadInterruptedException> per interromperne lo stato di attesa.  
  
## <a name="the-threadsleep-method"></a>Metodo Thread.Sleep  
 La chiamata di <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> (metodo), il thread corrente viene bloccato immediatamente per il numero di millisecondi o l'intervallo di tempo passare al metodo e restituisce il resto della porzione di tempo a un altro thread. Una volta trascorso tale intervallo, il thread inattivo riprende l'esecuzione.  
  
 Un thread non può chiamare <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> su un altro thread.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>è un metodo statico che determinano sempre il thread corrente allo stato di sospensione.  
  
 La chiamata <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valore di <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> fa sì che un thread rimarrà sospeso finché verrà interrotto da un altro thread che chiama il <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> metodo sul thread inattivo o fino a quando non viene terminata da una chiamata al relativo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo.  L'esempio seguente illustra entrambi i metodi per interrompere un thread inattivo.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Interruzione di thread  
 È possibile interrompere un thread in attesa chiamando il <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> metodo sul thread bloccato per generare un <xref:System.Threading.ThreadInterruptedException>, che interrompe il thread di chiamata di blocco. Il thread dovrebbe intercettare l'eccezione <xref:System.Threading.ThreadInterruptedException> ed eseguire le operazioni appropriate per continuare a funzionare. Se il thread ignora l'eccezione, l'ambiente di esecuzione la intercetta e interrompe il thread.  
  
> [!NOTE]
>  Se il thread di destinazione non è bloccato al momento della chiamata del metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, il thread non subisce interruzioni finché non viene bloccato. Se il thread non si blocca, verrà completato senza subire alcuna interruzione.  
  
 Se un'attesa è di tipo gestito, sia <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> che <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> riporteranno immediatamente il thread allo stato di attività. Caso di un'attesa non gestita (ad esempio, una chiamata PInvoke per Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) funzione), né <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> né <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> può assumere il controllo del thread fino alla restituzione o alla chiamata nel codice gestito. Di seguito è descritto il comportamento nel codice gestito.  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadInterruptedException> nel thread di destinazione.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>riattivazione di un thread qualsiasi attesa e provoca un <xref:System.Threading.ThreadAbortException> generata sul thread. Per informazioni dettagliate, vedere [Eliminazione definitiva di thread](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
