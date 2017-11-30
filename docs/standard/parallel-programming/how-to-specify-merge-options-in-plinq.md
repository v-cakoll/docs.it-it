---
title: 'Procedura: specificare le opzioni di merge in PLINQ'
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Procedura: specificare le opzioni di merge in PLINQ
In questo esempio viene illustrato come specificare le opzioni di unione che verranno applicate a tutti gli operatori successivi in una query PLINQ. Non è necessario impostare le opzioni di merge in modo esplicito, ma può migliorare le prestazioni. Per ulteriori informazioni sulle opzioni di unione, vedere [opzioni di Merge in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il comportamento delle opzioni di unione in uno scenario di base che dispone di un'origine non ordinata e si applica una funzione dispendiosa a ogni elemento.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 Nei casi in cui il <xref:System.Linq.ParallelMergeOptions.AutoBuffered> opzione comporta una latenza indesiderata prima viene restituito il primo elemento, provare il <xref:System.Linq.ParallelMergeOptions.NotBuffered> possibile produrre elementi di risultato più veloce ed efficiente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelMergeOptions>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
