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
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59ffff3019f10874bd2df977b80d46e903d13613
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Procedura: specificare le opzioni di merge in PLINQ
Questo esempio mostra come specificare le opzioni di merge che verranno applicate a tutti gli operatori successivi in una query PLINQ. Non è necessario impostare le opzioni di merge in modo esplicito, ma facendolo è possibile migliorare le prestazioni. Per altre informazioni sulle opzioni di merge, vedere [Opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra il comportamento delle opzioni di merge in uno scenario di base che ha un'origine non ordinata e applica una funzione complessa a ogni elemento.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 Nei casi in cui l'opzione <xref:System.Linq.ParallelMergeOptions.AutoBuffered> comporta una latenza indesiderata prima della restituzione del primo elemento, provare a usare l'opzione <xref:System.Linq.ParallelMergeOptions.NotBuffered> per restituire gli elementi del risultato in modo più rapido e semplice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelMergeOptions>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
