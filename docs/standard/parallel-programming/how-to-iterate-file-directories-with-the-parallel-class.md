---
title: 'Procedura: scorrere le directory dei file con la classe Parallel'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
ms.openlocfilehash: fda8443666d1c90b31cf02c2f925d1c89243a8e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091324"
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a>Procedura: scorrere le directory dei file con la classe Parallel
In molti casi, l'iterazione di file è un'operazione che può essere facilmente parallelizzata. L'argomento [Procedura: Scorrere le directory dei file con PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) illustra il modo più semplice per eseguire questa attività per molti scenari. L'operazione può però diventare complessa quando il codice deve gestire molti tipi di eccezioni che possono verificarsi durante l'accesso al file system. L'esempio seguente mostra uno degli approcci al problema. Viene usata un'iterazione basata su stack per attraversare tutti i file e le cartelle in una directory specificata e il codice può intercettare e gestire diverse eccezioni. Naturalmente, la modalità di gestione delle eccezioni dipende dell'utente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente le directory vengono iterate in modo sequenziale, ma i file vengono elaborati in parallelo. Questo è probabilmente l'approccio migliore quando si ha un rapporto file/directory elevato. È anche possibile parallelizzare l'iterazione nella directory e accedere a ogni file in modo sequenziale. Probabilmente parallelizzare entrambi i cicli non rappresenta una scelta efficace, a meno che il computer di destinazione non abbia un numero elevato di processori. Tuttavia, come in tutti i casi, è necessario testare l'applicazione attentamente per determinare l'approccio migliore.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 In questo esempio, l'I/O di file viene eseguito in modo sincrono. In presenza di file di grandi dimensioni o connessioni di rete lente, potrebbe essere preferibile accedere ai file in modo asincrono. È possibile combinare le tecniche di I/O asincrone con l'iterazione parallela. Per altre informazioni, vedere [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
 Nell'esempio viene utilizzata la variabile locale `fileCount` per gestire il conteggio del numero totale di file elaborati. Dal momento che è possibile accedere alla variabile contemporaneamente da più attività, l'accesso a essa viene sincronizzato chiamando il metodo <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>.  
  
 Si noti che se viene generata un'eccezione nel thread principale, i thread avviati dal metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A> possono rimanere in esecuzione. Per arrestare questi thread, è possibile impostare una variabile booleana nei gestori di eccezioni e controllarne il valore in ogni iterazione del ciclo parallelo. Se il valore indica che è stata generata un'eccezione, usare la variabile <xref:System.Threading.Tasks.ParallelLoopState> per arrestare o interrompere il ciclo. Per altre informazioni, vedere [Procedura: arrestare o interrompere un ciclo Parallel.For](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd460721(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
