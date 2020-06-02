---
title: "Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 4b2bc79a7b652c34334d5a78d9c9af328993ff44
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279206"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi
L'esempio seguente mostra come usare un oggetto <xref:System.Threading.SpinWait?displayProperty=nameWithType> per implementare un'operazione di attesa a due fasi. Nella prima fase, l'oggetto di sincronizzazione, `Latch`, ruota per alcuni cicli mentre controlla se il blocco è diventato disponibile. Nella seconda fase, se il blocco diventa disponibile, il metodo `Wait` restituisce un risultato senza usare <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> per l'attesa; in caso contrario, `Wait` esegue l'attesa.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra un'implementazione di base di una primitiva di sincronizzazione Latch. È possibile usare questa struttura dei dati quando si prevedono tempi di attesa molto brevi. Questo esempio viene fornito solo per scopi dimostrativi. Se sono necessarie funzionalità di tipo latch nel programma, è consigliabile usare <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Il latch usa l'oggetto <xref:System.Threading.SpinWait> per ruotare sul posto solo fino a quando la chiamata successiva a `SpinOnce` fa in modo che <xref:System.Threading.SpinWait> restituisca l'intervallo di tempo del thread. A questo punto, il latch provoca il cambio di contesto chiamando <xref:System.Threading.WaitHandle.WaitOne%2A> su <xref:System.Threading.ManualResetEvent> e passando la parte restante del valore di timeout.  
  
 L'output di registrazione mostra la frequenza con cui il latch è stato in grado di migliorare le prestazioni acquisendo il blocco senza usare l'oggetto <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>Vedere anche

- [SpinWait](spinwait.md)
- [Oggetti e funzionalità di threading](threading-objects-and-features.md)
