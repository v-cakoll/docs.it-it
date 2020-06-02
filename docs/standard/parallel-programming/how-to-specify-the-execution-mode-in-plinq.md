---
title: 'Procedura: Specificare la modalità di esecuzione in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: 39ccde003b60ac9cbcff7ab824103a9cf37cc453
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288095"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Procedura: Specificare la modalità di esecuzione in PLINQ

Questo esempio mostra come forzare PLINQ a ignorare l'euristica predefinita e parallelizzare una query indipendentemente dalla relativa forma.  
  
> [!NOTE]
> Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ è progettato per sfruttare le opportunità di parallelizzazione. Tuttavia, l'esecuzione parallela non è vantaggiosa per tutte le query. Se, ad esempio, una query contiene un solo delegato utente che non funziona, la query viene in genere eseguita più velocemente in modo sequenziale. L'esecuzione sequenziale è più veloce perché l'overhead richiesto per l'abilitazione dell'esecuzione di parallelizzazione è più costoso rispetto all'aumento di velocità ottenuto. PLINQ pertanto non parallelizza automaticamente ogni query. Esamina prima di tutto la forma della query e i vari operatori inclusi. In base a questa analisi, in modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza. In alcuni casi, tuttavia, l'utente potrebbe avere più informazioni sulla query rispetto a quelle che PLINQ è in grado di determinare dall'analisi. È ad esempio possibile che un delegato sia dispendioso e che la query possa trarre vantaggio dalla parallelizzazione. In questi casi, è possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e specificare il valore <xref:System.Linq.ParallelExecutionMode.ForceParallelism> per indicare a PLINQ di eseguire sempre la query in parallelo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Tagliare e incollare questo codice nell'[esempio di dati PLINQ](plinq-data-sample.md) e chiamare il metodo da `Main`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
