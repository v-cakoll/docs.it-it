---
title: 'Procedura: utilizzare SpinWait per implementare un''operazione di attesa a due fasi'
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi
Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.SpinWait?displayProperty=nameWithType> oggetto per implementare un'operazione di attesa a due fasi. Nella prima fase, l'oggetto di sincronizzazione, un `Latch`, Ruota per alcuni cicli mentre viene verificato se il blocco è più disponibile. Nella seconda fase, se il blocco diventa disponibile, il `Wait` metodo viene restituito senza utilizzare il <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> per eseguire l'attesa; in caso contrario, `Wait` esegue l'attesa.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra un'implementazione di base di una sincronizzazione Latch primitivi. È possibile utilizzare questa struttura di dati quando si prevedono tempi di attesa molto brevi. Questo esempio è solo per scopi dimostrativi. Se sono necessarie funzionalità di tipo di latch nel programma, è consigliabile utilizzare <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Il latch utilizza il <xref:System.Threading.SpinWait> oggetto da ruotare sul posto solo fino alla chiamata successiva a `SpinOnce` provoca il <xref:System.Threading.SpinWait> per produrre l'intervallo di tempo del thread. A questo punto, il latch provoca il proprio cambio di contesto chiamando <xref:System.Threading.WaitHandle.WaitOne%2A> sul <xref:System.Threading.ManualResetEvent> e passando la parte restante del valore di timeout.  
  
 L'output di registrazione Mostra la frequenza con cui il fermo è stato in grado di migliorare le prestazioni dell'acquisizione del blocco senza utilizzare il <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>Vedere anche  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)
