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
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="5f214-102">Procedura: controllare l'ordine in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="5f214-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="5f214-103">In questi esempi viene illustrato come controllare l'ordinamento in una query PLINQ tramite il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="5f214-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5f214-104">Questi esempi vengono principalmente per illustrare l'uso e possono o non possono essere eseguite più velocemente rispetto a LINQ sequenziali equivalenti alle query di oggetti.</span><span class="sxs-lookup"><span data-stu-id="5f214-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f214-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f214-105">Example</span></span>  
 <span data-ttu-id="5f214-106">Nell'esempio seguente consente di mantenere l'ordine della sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="5f214-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="5f214-107">Ciò è talvolta necessario; ad esempio alcuni operatori di query richiedono una sequenza di origine ordinato per ottenere risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="5f214-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="5f214-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f214-108">Example</span></span>  
 <span data-ttu-id="5f214-109">L'esempio seguente mostra alcuni operatori di sequenza i cui origine è probabilmente previsto devono essere ordinati di query.</span><span class="sxs-lookup"><span data-stu-id="5f214-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="5f214-110">Questi operatori funzionerà su sequenze non ordinate, ma potrebbero produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="5f214-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="5f214-111">Per eseguire questo metodo, incollare il codice nella classe PLINQDataSample il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto e premere F5.</span><span class="sxs-lookup"><span data-stu-id="5f214-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f214-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f214-112">Example</span></span>  
 <span data-ttu-id="5f214-113">Nell'esempio seguente viene illustrato come mantenere l'ordinamento per la prima parte di una query, quindi rimuovere l'ordinamento per migliorare le prestazioni di una clausola join e quindi riapplicare l'ordine della sequenza di risultati finale.</span><span class="sxs-lookup"><span data-stu-id="5f214-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="5f214-114">Per eseguire questo metodo, incollare il codice nella classe PLINQDataSample il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto e premere F5.</span><span class="sxs-lookup"><span data-stu-id="5f214-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f214-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f214-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="5f214-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="5f214-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
