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
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3aef90c1a1160905662f93a83d6536f6d804b179
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="6fe23-102">Procedura: controllare l'ordine in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="6fe23-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="6fe23-103">Questi esempi mostrano come controllare l'ordinamento in una query PLINQ usando il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fe23-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6fe23-104">Lo scopo di questi esempi consiste principalmente nel mostrare l'utilizzo e la loro esecuzione potrebbe non essere più rapida delle query LINQ to Objects sequenziali equivalenti.</span><span class="sxs-lookup"><span data-stu-id="6fe23-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe23-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fe23-105">Example</span></span>  
 <span data-ttu-id="6fe23-106">L'esempio seguente mantiene l'ordinamento della sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="6fe23-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="6fe23-107">Questo comportamento è talvolta necessario. Ad esempio, alcuni operatori di query richiedono una sequenza di origine ordinata per produrre risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="6fe23-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="6fe23-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fe23-108">Example</span></span>  
 <span data-ttu-id="6fe23-109">L'esempio seguente mostra alcuni operatori di query la cui sequenza di origine sarà probabilmente ordinata.</span><span class="sxs-lookup"><span data-stu-id="6fe23-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="6fe23-110">Questi operatori funzioneranno in sequenze non ordinate, ma possono produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="6fe23-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="6fe23-111">Per eseguire questo metodo, incollarlo nella classe PLINQDataSample nel progetto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) e premere F5.</span><span class="sxs-lookup"><span data-stu-id="6fe23-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe23-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fe23-112">Example</span></span>  
 <span data-ttu-id="6fe23-113">L'esempio seguente mostra come mantenere l'ordinamento per la prima parte di una query, rimuovere l'ordinamento per migliorare le prestazioni di una clausola join e quindi riapplicare l'ordinamento alla sequenza di risultati finale.</span><span class="sxs-lookup"><span data-stu-id="6fe23-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="6fe23-114">Per eseguire questo metodo, incollarlo nella classe PLINQDataSample nel progetto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) e premere F5.</span><span class="sxs-lookup"><span data-stu-id="6fe23-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe23-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fe23-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="6fe23-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="6fe23-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
