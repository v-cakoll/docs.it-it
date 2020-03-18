---
title: 'Procedura: sincronizzare operazioni simultanee con una barriera'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: 33098878764c2f8a8c1f83a122028da40b984243
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137966"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Procedura: sincronizzare operazioni simultanee con una barriera
L'esempio seguente mostra come sincronizzare le attività simultanee con un oggetto <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Esempio  
 Lo scopo del programma seguente è quello di contare il numero di iterazioni (o fasi) necessarie per due thread in modo che ognuno trovi la propria metà della soluzione nella stessa fase usando un algoritmo di scelta casuale per riselezionare in ordine casuale le parole. Dopo che ogni thread ha selezionato in ordine casuale le parole, l'operazione post-fase della barriera confronta i due risultati per verificare se è stato eseguito il rendering della frase completa con l'ordine corretto di parole.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Un oggetto <xref:System.Threading.Barrier> è un oggetto che impedisce alle singole attività in un'operazione parallela di continuare fino a quando tutte le attività non raggiungono la barriera. È utile quando un'operazione parallela avviene in fasi e ogni fase richiede la sincronizzazione tra le attività. In questo esempio l'operazione include due fasi. Nella prima fase ogni attività riempie la propria sezione del buffer con dati. Quando ogni attività finisce di riempire la propria sezione, segnala alla barriera che è pronta per continuare e quindi attende. Quando tutte le attività hanno segnalato il completamento alla barriera, vengono sbloccate e inizia la seconda fase. La barriera è necessaria perché la seconda fase richiede che ogni attività abbia accesso a tutti i dati che sono stati generati fino a questo punto. Senza la barriera, le prime attività potrebbero cercare di leggere da buffer che non sono ancora stati riempiti da altre attività. In questo modo, è possibile sincronizzare un numero qualsiasi di fasi.  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di dati per la programmazione in parallelo](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
