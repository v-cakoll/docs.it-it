---
title: 'Procedura: gestire le eccezioni in una query PLINQ'
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Procedura: gestire le eccezioni in una query PLINQ
Nel primo esempio in questo argomento viene illustrato come gestire il <xref:System.AggregateException?displayProperty=nameWithType> che possono essere generate da una query PLINQ quando viene eseguita. Nel secondo esempio viene illustrato come inserire i blocchi try-catch all'interno dei delegati, più vicino possibile a cui verrà generata l'eccezione. In questo modo, è possibile intercettarle appena che si verificano e probabilmente continuare l'esecuzione di query. Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.  
  
 In alcuni casi quando PLINQ esegue il fallback all'esecuzione sequenziale e si verifica un'eccezione, l'eccezione può essere propagata direttamente e non il wrapping in un <xref:System.AggregateException>. Inoltre, <xref:System.Threading.ThreadAbortException>vengono sempre propagate direttamente.  
  
> [!NOTE]
>  Quando "Just My Code" è abilitato, Visual interruzione sulla riga che genera l'eccezione e verrà visualizzato un messaggio di errore simile a "eccezione non gestita dal codice utente". Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.  
>   
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come inserire i blocchi try-catch intorno al codice che esegue la query per rilevare qualsiasi <xref:System.AggregateException?displayProperty=nameWithType>s che vengono generate.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 In questo esempio, la query non può continuare dopo la generazione dell'eccezione. Una volta che il codice dell'applicazione rileva l'eccezione, PLINQ è già stato arrestato la query su tutti i thread.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come inserire un blocco try-catch a un delegato consentono di rilevare un'eccezione e continuare l'esecuzione della query.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Per compilare ed eseguire questi esempi, copiarli nell'esempio di PLINQ, dati di esempio e chiamare il metodo principale.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Non rilevare un'eccezione a meno che non si sa come gestire in modo tale da non danneggiare lo stato del programma.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
