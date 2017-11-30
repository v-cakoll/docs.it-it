---
title: 'Procedura: sincronizzare operazioni simultanee con una barriera'
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Procedura: sincronizzare operazioni simultanee con una barriera
Nell'esempio seguente viene illustrato come sincronizzare le attività simultanee con una <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Esempio  
 Lo scopo del programma seguente è per contare il numero di iterazioni (o fasi) sono necessari per due thread per ogni ricerca relativa metà della soluzione sulla stessa fase utilizzando un algoritmo di casualità riassegnare le parole. Dopo ogni thread ha mescolate le proprie parole, l'operazione di post-fase barriera confronta i due risultati per vedere se è stato eseguito il rendering della frase completa nell'ordine corretto di word.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Oggetto <xref:System.Threading.Barrier> è un oggetto che impedisce di singole attività in un'operazione parallela non potrà continuare fino a quando tutte le attività di raggiungono la barriera. È utile quando si verifica un'operazione parallela in fasi e ogni fase richiede la sincronizzazione tra le attività. In questo esempio sono presenti due fasi per l'operazione. Nella prima fase, ogni attività riempie la relativa sezione del buffer con dati. Quando ogni attività viene completata la compilazione di sezione, l'attività segnala la barriera che è pronto per continuare, quindi attende. Quando tutte le attività hanno eseguito la barriera, inizia la seconda fase vengono sbloccate. La barriera è necessaria perché la seconda fase richiede che ogni attività abbia accesso a tutti i dati che è stato generato a questo punto. Senza la barriera, le attività da completare prima potrebbero tentare di leggere dal buffer non sono stati compilati ancora da altre attività. È possibile sincronizzare un numero qualsiasi di fasi in questo modo.  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di dati per la programmazione in parallelo](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
