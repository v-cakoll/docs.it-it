---
title: 'Procedura: controllare l''ordine in una query PLINQ'
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Procedura: controllare l'ordine in una query PLINQ
In questi esempi viene illustrato come controllare l'ordinamento in una query PLINQ tramite il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> metodo di estensione.  
  
> [!WARNING]
>  Questi esempi vengono principalmente per illustrare l'uso e possono o non possono essere eseguite più velocemente rispetto a LINQ sequenziali equivalenti alle query di oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di mantenere l'ordine della sequenza di origine. Ciò è talvolta necessario; ad esempio alcuni operatori di query richiedono una sequenza di origine ordinato per ottenere risultati corretti.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra alcuni operatori di sequenza i cui origine è probabilmente previsto devono essere ordinati di query. Questi operatori funzionerà su sequenze non ordinate, ma potrebbero produrre risultati imprevisti.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Per eseguire questo metodo, incollare il codice nella classe PLINQDataSample il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto e premere F5.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come mantenere l'ordinamento per la prima parte di una query, quindi rimuovere l'ordinamento per migliorare le prestazioni di una clausola join e quindi riapplicare l'ordine della sequenza di risultati finale.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Per eseguire questo metodo, incollare il codice nella classe PLINQDataSample il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto e premere F5.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
