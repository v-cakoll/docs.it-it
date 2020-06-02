---
title: "Procedura: Controllare l'ordine in una query PLINQ"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
ms.openlocfilehash: 80e199d75471eba219f1f3da12d307b6cd1d90cf
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285456"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Procedura: Controllare l'ordine in una query PLINQ
Questi esempi mostrano come controllare l'ordinamento in una query PLINQ usando il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
> [!WARNING]
> Lo scopo di questi esempi consiste principalmente nel mostrare l'utilizzo e la loro esecuzione potrebbe non essere più rapida delle query LINQ to Objects sequenziali equivalenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mantiene l'ordinamento della sequenza di origine. Questo comportamento è talvolta necessario. Ad esempio, alcuni operatori di query richiedono una sequenza di origine ordinata per produrre risultati corretti.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra alcuni operatori di query la cui sequenza di origine sarà probabilmente ordinata. Questi operatori funzioneranno in sequenze non ordinate, ma possono produrre risultati imprevisti.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Per eseguire questo metodo, incollarlo nella classe PLINQDataSample nel progetto [PLINQ Data Sample](plinq-data-sample.md) e premere F5.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come mantenere l'ordinamento per la prima parte di una query, rimuovere l'ordinamento per migliorare le prestazioni di una clausola join e quindi riapplicare l'ordinamento alla sequenza di risultati finale.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Per eseguire questo metodo, incollarlo nella classe PLINQDataSample nel progetto [PLINQ Data Sample](plinq-data-sample.md) e premere F5.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
