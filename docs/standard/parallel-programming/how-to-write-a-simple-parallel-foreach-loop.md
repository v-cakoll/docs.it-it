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
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="446ff-102">Procedura: scrivere un ciclo Parallel.ForEach semplice</span><span class="sxs-lookup"><span data-stu-id="446ff-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="446ff-103">In questo esempio viene illustrato come utilizzare un <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> ciclo per abilitare il parallelismo dei dati su qualsiasi <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> origine dati.</span><span class="sxs-lookup"><span data-stu-id="446ff-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="446ff-104">Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ.</span><span class="sxs-lookup"><span data-stu-id="446ff-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="446ff-105">Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="446ff-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="446ff-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="446ff-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="446ff-107">Oggetto <xref:System.Threading.Tasks.Parallel.ForEach%2A> ciclo funziona come un <xref:System.Threading.Tasks.Parallel.For%2A> ciclo.</span><span class="sxs-lookup"><span data-stu-id="446ff-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="446ff-108">Raccolta di origine è partizionata e il lavoro pianificato in più thread in base all'ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="446ff-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="446ff-109">Il numero di processori nel sistema, la velocità del metodo in parallelo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="446ff-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="446ff-110">Per alcune raccolte di origine, può risultare più veloce, a seconda delle dimensioni dell'origine e il tipo di lavoro viene eseguito un ciclo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="446ff-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="446ff-111">Per ulteriori informazioni sulle prestazioni, vedere [problemi potenziali nel parallelismo di dati e attività](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span><span class="sxs-lookup"><span data-stu-id="446ff-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="446ff-112">Per ulteriori informazioni sui cicli paralleli, vedere [procedura: scrivere un ciclo Parallel. for semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="446ff-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="446ff-113">Per utilizzare <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una raccolta non generica, è possibile utilizzare il <xref:System.Linq.Enumerable.Cast%2A> metodo di estensione per convertire la raccolta in una raccolta generica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="446ff-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="446ff-114">È inoltre possibile utilizzare Parallel LINQ (PLINQ) per parallelizzare l'elaborazione di <xref:System.Collections.Generic.IEnumerable%601> origini dati.</span><span class="sxs-lookup"><span data-stu-id="446ff-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="446ff-115">PLINQ consente di utilizzare la sintassi di query dichiarativa per esprimere il comportamento di ciclo.</span><span class="sxs-lookup"><span data-stu-id="446ff-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="446ff-116">Per altre informazioni, vedere [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="446ff-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="446ff-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="446ff-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="446ff-118">Copiare e incollare questo codice in un [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] progetto applicazione Console 2010.</span><span class="sxs-lookup"><span data-stu-id="446ff-118">Copy and paste this code into a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="446ff-119">Aggiungere un riferimento a System.Drawing.dll</span><span class="sxs-lookup"><span data-stu-id="446ff-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="446ff-120">Premere F5</span><span class="sxs-lookup"><span data-stu-id="446ff-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446ff-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="446ff-121">See Also</span></span>  
 [<span data-ttu-id="446ff-122">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="446ff-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="446ff-123">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="446ff-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="446ff-124">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="446ff-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
