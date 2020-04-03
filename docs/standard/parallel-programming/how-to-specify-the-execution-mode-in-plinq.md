---
title: 'Procedura: specificare la modalità di esecuzione in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: f035dbcd5091d81a3cce3b9e9e683d836fe84bb7
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635818"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Procedura: specificare la modalità di esecuzione in PLINQ

Questo esempio mostra come forzare PLINQ a ignorare l'euristica predefinita e parallelizzare una query indipendentemente dalla relativa forma.  
  
> [!NOTE]
> Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente della query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ è progettato per sfruttare le opportunità di parallelizzazione. Tuttavia, l'esecuzione parallela non è vantaggiosa per tutte le query. Ad esempio, quando una query contiene un singolo delegato utente che esegue poco lavoro, la query verrà in genere eseguita più velocemente in sequenza. L'esecuzione sequenziale è più veloce perché l'overhead implicato nell'abilitazione della parallelizzazione dell'esecuzione è più costoso della velocità ottenuta. PLINQ pertanto non parallelizza automaticamente ogni query. Esamina prima di tutto la forma della query e i vari operatori inclusi. In base a questa analisi, in modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza. In alcuni casi, tuttavia, l'utente potrebbe avere più informazioni sulla query rispetto a quelle che PLINQ è in grado di determinare dall'analisi. Ad esempio, è possibile sapere che un delegato è costoso e che la query trarrà sicuramente vantaggio dalla parallelizzazione. In questi casi, è possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e specificare il valore <xref:System.Linq.ParallelExecutionMode.ForceParallelism> per indicare a PLINQ di eseguire sempre la query in parallelo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Tagliare e incollare questo codice nell'[esempio di dati PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) e chiamare il metodo da `Main`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
