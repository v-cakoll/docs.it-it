---
title: 'Procedura: combinare query LINQ parallele e sequenziali'
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Procedura: combinare query LINQ parallele e sequenziali
In questo esempio viene illustrato come utilizzare il <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metodo per indicare a elaborare in modo sequenziale tutti gli operatori successivi nella query PLINQ. Anche se è in genere inferiore a parallelo elaborazione sequenza, in alcuni casi è necessario ottenere risultati corretti.  
  
> [!WARNING]
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato uno scenario in cui <xref:System.Linq.ParallelEnumerable.AsSequential%2A> è obbligatorio, in particolare per conservare l'ordine è stata stabilita in una clausola della query precedente.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare ed eseguire il codice, incollarlo il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto, aggiungere una riga per chiamare il metodo dal `Main`, e premere F5.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
