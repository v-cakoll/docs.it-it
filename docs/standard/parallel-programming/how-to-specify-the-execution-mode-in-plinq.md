---
title: "Procedura: specificare la modalità di esecuzione in PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Procedura: specificare la modalità di esecuzione in PLINQ
In questo esempio viene illustrato come forzare PLINQ per ignorare le proprie regole euristiche predefinite e la parallelizzazione di una query indipendentemente dalla forma della query.  
  
> [!WARNING]
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ è progettato per sfruttare le opportunità di parallelizzazione. Tuttavia, non tutte le query trarre vantaggio dall'esecuzione parallela. Ad esempio, quando una query contiene un delegato di singolo utente che esegue un intervento minimo, eseguirà la query in genere più veloce in sequenza. In questo modo l'overhead necessario per consentire l'esecuzione parallela rappresenta uno è più costoso di un aumento di velocità ottenuti. Pertanto, PLINQ non parallelizza automaticamente tutte le query. Viene innanzitutto esaminato la forma di query e i vari operatori che lo compongono. In base a questa analisi, nella modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza. Tuttavia, in alcuni casi è possibile conoscere più query di PLINQ è in grado di determinare dall'analisi. Ad esempio, si potrebbe sapere che un delegato è molto costoso e che la query verrà sicuramente sfruttano la parallelizzazione. In questi casi, è possibile utilizzare il <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> (metodo) e specificare il <xref:System.Linq.ParallelExecutionMode.ForceParallelism> valore per indicare alla query vengono eseguite sempre come parallelo PLINQ.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Tagliare e incollare questo codice nel [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) e chiamare il metodo da `Main`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
