---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>è una primitiva di sincronizzazione che sblocca i thread in attesa dopo che è stato segnalato un certo numero di volte. <xref:System.Threading.CountdownEvent>è progettato per scenari in cui in caso contrario è necessario utilizzare un <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> e diminuire manualmente una variabile prima di segnalare l'evento. In uno scenario di divisione e unione, ad esempio, è possibile creare solo un <xref:System.Threading.CountdownEvent> che presenta un numero di segnale di 5 e quindi avviare cinque elementi di lavoro sul thread del pool e ogni chiamata di elemento di lavoro <xref:System.Threading.CountdownEvent.Signal%2A> quando viene completato. Ogni chiamata a <xref:System.Threading.CountdownEvent.Signal%2A> decrementa il conteggio segnali 1. Nel thread principale, la chiamata a <xref:System.Threading.CountdownEvent.Wait%2A> verrà bloccata finché il segnale di conteggio è zero.  
  
> [!NOTE]
>  Per il codice che non devono interagire con l'API di sincronizzazione di .NET Framework legacy, è consigliabile utilizzare <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> oggetti o <xref:System.Threading.Tasks.Parallel.Invoke%2A> metodo per un approccio ancora più semplice per esprimere il parallelismo fork-join.  
  
 <xref:System.Threading.CountdownEvent>dispone di queste funzionalità aggiuntive:  
  
-   L'operazione di attesa può essere annullata tramite i token di annullamento.  
  
-   Il numero di segnale può essere incrementato dopo la creazione dell'istanza.  
  
-   Istanze possono essere riutilizzate dopo <xref:System.Threading.CountdownEvent.Wait%2A> ha restituito chiamando il <xref:System.Threading.CountdownEvent.Reset%2A> metodo.  
  
-   Le istanze espongono un <xref:System.Threading.WaitHandle> per l'integrazione con altre API di sincronizzazione di .NET Framework, ad esempio <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Utilizzo di base  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.CountdownEvent> con <xref:System.Threading.ThreadPool> gli elementi di lavoro.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent con annullamento  
 Nell'esempio seguente viene illustrato come annullare l'operazione di attesa in <xref:System.Threading.CountdownEvent> utilizzando un token di annullamento. Il modello di base segue il modello di annullamento unificato, che è stato introdotto in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Per ulteriori informazioni, vedere [annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Si noti che l'operazione di attesa non annulla il thread di segnalazione. In genere, annullamento viene applicato a un'operazione logica e che può includere in attesa dell'evento, nonché tutti gli elementi di lavoro che sta sincronizzando il tempo di attesa. In questo esempio, ogni elemento di lavoro viene passato una copia del token di annullamento stesso in modo da poter rispondere alla richiesta di annullamento.  
  
## <a name="see-also"></a>Vedere anche  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
