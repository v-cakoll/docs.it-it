---
title: 'Procedura: scorrere le directory dei file con la classe Parallel'
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
helpviewer_keywords: parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c21aadf70eaccafc8c8ec9c4efefff1c66abc6b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a>Procedura: scorrere le directory dei file con la classe Parallel
In molti casi, l'iterazione di file è un'operazione che può essere facilmente eseguito in parallelo. L'argomento [procedura: scorrere le directory di File con PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) viene illustrato il modo più semplice per eseguire questa attività per molti scenari. Tuttavia, complessità può verificarsi quando il codice deve affrontare molti tipi di eccezioni che possono verificarsi durante l'accesso al file system. Nell'esempio seguente viene illustrato uno degli approcci disponibili per il problema. Un'iterazione basata su stack viene utilizzato per scorrere tutti i file e cartelle in una directory specificata e consente il codice rilevare e gestire le eccezioni diverse. Naturalmente, la modalità di gestione delle eccezioni è responsabilità dell'utente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente le directory vengono iterate in modo sequenziale, ma i file vengono elaborati in parallelo. Si tratta probabilmente l'approccio migliore quando si dispone di un rapporto elevato di file e directory. È inoltre possibile parallelizzare l'iterazione di directory e accedere a ogni file in modo sequenziale. Probabilmente non è efficiente per parallelizzare i cicli di entrambi, a meno che la destinazione specifica di un computer con un numero elevato di processori. Tuttavia, come in tutti i casi, è necessario testare l'applicazione attentamente per determinare l'approccio migliore.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 In questo esempio, il file dei / o viene eseguito in modo sincrono. Quando si utilizzano connessioni di rete lenta o file di grandi dimensioni, potrebbe essere preferibile per accedere ai file in modo asincrono. È possibile combinare le tecniche dei / o asincrone con iterazione parallela. Per altre informazioni, vedere [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
 Nell'esempio viene utilizzata la variabile locale `fileCount` per gestire il conteggio del numero totale di file elaborati. Dal momento che è possibile accedere alla variabile contemporaneamente da più attività, l'accesso a essa viene sincronizzato chiamando il metodo <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>.  
  
 Si noti che se viene generata un'eccezione nell'oggetto principale thread, i thread avviati dal <xref:System.Threading.Tasks.Parallel.ForEach%2A> metodo potrebbe continuare a eseguire. Per arrestare questi thread, è possibile impostare una variabile booleana nei gestori di eccezioni e controllarne il valore in ogni iterazione del ciclo parallelo. Se il valore indica che è stata generata un'eccezione, utilizzare il <xref:System.Threading.Tasks.ParallelLoopState> variabile per arrestare o interrompere il ciclo. Per ulteriori informazioni, vedere [procedura: arrestare o interrompere un ciclo Parallel. for](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).  
  
## <a name="see-also"></a>Vedere anche  
 [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
