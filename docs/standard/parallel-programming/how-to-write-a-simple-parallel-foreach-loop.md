---
title: 'Procedura: scrivere un ciclo Parallel.ForEach semplice'
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Procedura: scrivere un ciclo Parallel.ForEach semplice
In questo esempio viene illustrato come utilizzare un <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> ciclo per abilitare il parallelismo dei dati su qualsiasi <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> origine dati.  
  
> [!NOTE]
>  Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Oggetto <xref:System.Threading.Tasks.Parallel.ForEach%2A> ciclo funziona come un <xref:System.Threading.Tasks.Parallel.For%2A> ciclo. Raccolta di origine è partizionata e il lavoro pianificato in più thread in base all'ambiente di sistema. Il numero di processori nel sistema, la velocità del metodo in parallelo viene eseguito. Per alcune raccolte di origine, può risultare più veloce, a seconda delle dimensioni dell'origine e il tipo di lavoro viene eseguito un ciclo sequenziale. Per ulteriori informazioni sulle prestazioni, vedere [problemi potenziali nel parallelismo di dati e attività](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Per ulteriori informazioni sui cicli paralleli, vedere [procedura: scrivere un ciclo Parallel. for semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Per utilizzare <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una raccolta non generica, è possibile utilizzare il <xref:System.Linq.Enumerable.Cast%2A> metodo di estensione per convertire la raccolta in una raccolta generica, come illustrato nell'esempio seguente:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 È inoltre possibile utilizzare Parallel LINQ (PLINQ) per parallelizzare l'elaborazione di <xref:System.Collections.Generic.IEnumerable%601> origini dati. PLINQ consente di utilizzare la sintassi di query dichiarativa per esprimere il comportamento di ciclo. Per altre informazioni, vedere [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Copiare e incollare questo codice in un [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] progetto applicazione Console 2010.  
  
-   Aggiungere un riferimento a System.Drawing.dll  
  
-   Premere F5  
  
## <a name="see-also"></a>Vedere anche  
 [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
