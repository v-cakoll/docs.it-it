---
title: Parallel LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
ms.openlocfilehash: 1ea880c6403a5fc8b26ba67fe21dfce79c4683db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140043"
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="2f28d-102">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="2f28d-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="2f28d-103">Parallel LINQ (PLINQ) è un'implementazione parallela di LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="2f28d-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="2f28d-104">PLINQ implementa il set completo di operatori di query standard LINQ come metodi di estensione per lo spazio dei nomi <xref:System.Linq> e dispone di operatori aggiuntivi per le operazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="2f28d-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="2f28d-105">PLINQ combina la semplicità e la leggibilità della sintassi di LINQ con la potenza di programmazione in parallelo.</span><span class="sxs-lookup"><span data-stu-id="2f28d-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="2f28d-106">Proprio come il codice destinato alla Task Parallel Library, le query di PLINQ ridimensionano il livello di concorrenza in base alle funzionalità del computer host.</span><span class="sxs-lookup"><span data-stu-id="2f28d-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="2f28d-107">In molti scenari, PLINQ può aumentare notevolmente la velocità delle query di LINQ to Objects usando tutti i core disponibili nel computer host in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="2f28d-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="2f28d-108">Il miglioramento nella prestazione comporta una potenza di elaborazione ad alte prestazioni sul desktop.</span><span class="sxs-lookup"><span data-stu-id="2f28d-108">This increased performance brings high-performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f28d-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2f28d-109">In This Section</span></span>  
 [<span data-ttu-id="2f28d-110">Introduzione a PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="2f28d-111">Informazioni sull'aumento di velocità in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="2f28d-112">Conservazione dell'ordine in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="2f28d-113">Opzioni di merge in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="2f28d-114">Procedura: Creare ed eseguire una query PLINQ semplice</span><span class="sxs-lookup"><span data-stu-id="2f28d-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="2f28d-115">Procedura: Controllare l'ordine in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="2f28d-116">Procedura: Combinare query LINQ parallele e sequenziali</span><span class="sxs-lookup"><span data-stu-id="2f28d-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="2f28d-117">Procedura: Gestire le eccezioni in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="2f28d-118">Procedura: Annullare una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="2f28d-119">Procedura: Scrivere una funzione di aggregazione PLINQ personalizzata</span><span class="sxs-lookup"><span data-stu-id="2f28d-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="2f28d-120">Procedura: Specificare la modalità di esecuzione in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="2f28d-121">Procedura: Specificare le opzioni di merge in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="2f28d-122">Procedura: Scorrere le directory dei file con PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="2f28d-123">Procedura: Misurare le prestazioni di esecuzione delle query di PLINQ</span><span class="sxs-lookup"><span data-stu-id="2f28d-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="2f28d-124">PLINQ Data Sample</span><span class="sxs-lookup"><span data-stu-id="2f28d-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f28d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f28d-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="2f28d-126">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="2f28d-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="2f28d-127">LINQ (Language-Integrated Query) - C#</span><span class="sxs-lookup"><span data-stu-id="2f28d-127">Language-Integrated Query (LINQ) - C#</span></span>](../../csharp/programming-guide/concepts/linq/index.md)  
- [<span data-ttu-id="2f28d-128">LINQ (Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f28d-128">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)  
