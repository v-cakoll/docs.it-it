---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: 628d6a96606117d447c61d01595d13dd4a957ce4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138120"
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType> è una primitiva di sincronizzazione che sblocca i thread in attesa dopo che è stata segnalata un certo numero di volte. <xref:System.Threading.CountdownEvent> è progettato per gli scenari in cui altrimenti sarebbe necessario usare <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> e diminuire manualmente una variabile prima di segnalare l'evento. In uno scenario di fork/join, ad esempio, è sufficiente creare una classe <xref:System.Threading.CountdownEvent> con un conteggio di segnali pari a 5 e quindi avviare cinque elementi di lavoro nel pool di thread e fare in modo che ogni elemento di lavoro chiami <xref:System.Threading.CountdownEvent.Signal%2A> quando viene completato. Ogni chiamata a <xref:System.Threading.CountdownEvent.Signal%2A> riduce il conteggio di segnali di 1. Nel thread principale la chiamata a <xref:System.Threading.CountdownEvent.Wait%2A> verrà bloccata finché il conteggio dei segnali sarà pari a zero.  
  
> [!NOTE]
> Per il codice che non deve interagire con le API di sincronizzazione di .NET Framework legacy, considerare la possibilità di usare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o il metodo <xref:System.Threading.Tasks.Parallel.Invoke%2A> per un approccio ancora più semplice per esprimere il parallelismo fork/join.  
  
 <xref:System.Threading.CountdownEvent> ha queste funzionalità aggiuntive:  
  
- L'operazione di attesa può essere annullata tramite i token di annullamento.  
  
- Il conteggio dei segnali può essere incrementato dopo la creazione dell'istanza.  
  
- Le istanze possono essere riutilizzate dopo che <xref:System.Threading.CountdownEvent.Wait%2A> è stato restituito chiamando il metodo <xref:System.Threading.CountdownEvent.Reset%2A>.  
  
- Le istanze espongono una classe <xref:System.Threading.WaitHandle> per l'integrazione con altre API di sincronizzazione di .NET Framework, ad esempio <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Utilizzo di base  
 L'esempio seguente illustra come usare una classe <xref:System.Threading.CountdownEvent> con gli elementi di lavoro <xref:System.Threading.ThreadPool>.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent con annullamento  
 L'esempio seguente illustrato come annullare l'operazione di attesa in <xref:System.Threading.CountdownEvent> usando un token di annullamento. Lo schema di base segue il modello per l'annullamento unificato, introdotto in .NET Framework 4. Per ulteriori informazioni, vedere [Annullamento nei thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Si noti che l'operazione di attesa non annulla i thread che la segnalano. L'annullamento viene in genere applicato a un'operazione logica, inclusa l'attesa dell'evento, ma anche di tutti gli elementi di lavoro che l'attesa sta sincronizzando. In questo esempio a ogni elemento di lavoro viene passata una copia dello stesso token di annullamento in modo che possa rispondere alla richiesta di annullamento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
