---
title: 'Procedura: sincronizzare operazioni simultanee con una barriera'
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="dab6a-102">Procedura: sincronizzare operazioni simultanee con una barriera</span><span class="sxs-lookup"><span data-stu-id="dab6a-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="dab6a-103">Nell'esempio seguente viene illustrato come sincronizzare le attività simultanee con una <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="dab6a-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dab6a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dab6a-104">Example</span></span>  
 <span data-ttu-id="dab6a-105">Lo scopo del programma seguente è per contare il numero di iterazioni (o fasi) sono necessari per due thread per ogni ricerca relativa metà della soluzione sulla stessa fase utilizzando un algoritmo di casualità riassegnare le parole.</span><span class="sxs-lookup"><span data-stu-id="dab6a-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="dab6a-106">Dopo ogni thread ha mescolate le proprie parole, l'operazione di post-fase barriera confronta i due risultati per vedere se è stato eseguito il rendering della frase completa nell'ordine corretto di word.</span><span class="sxs-lookup"><span data-stu-id="dab6a-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="dab6a-107">Oggetto <xref:System.Threading.Barrier> è un oggetto che impedisce di singole attività in un'operazione parallela non potrà continuare fino a quando tutte le attività di raggiungono la barriera.</span><span class="sxs-lookup"><span data-stu-id="dab6a-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="dab6a-108">È utile quando si verifica un'operazione parallela in fasi e ogni fase richiede la sincronizzazione tra le attività.</span><span class="sxs-lookup"><span data-stu-id="dab6a-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="dab6a-109">In questo esempio sono presenti due fasi per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="dab6a-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="dab6a-110">Nella prima fase, ogni attività riempie la relativa sezione del buffer con dati.</span><span class="sxs-lookup"><span data-stu-id="dab6a-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="dab6a-111">Quando ogni attività viene completata la compilazione di sezione, l'attività segnala la barriera che è pronto per continuare, quindi attende.</span><span class="sxs-lookup"><span data-stu-id="dab6a-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="dab6a-112">Quando tutte le attività hanno eseguito la barriera, inizia la seconda fase vengono sbloccate.</span><span class="sxs-lookup"><span data-stu-id="dab6a-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="dab6a-113">La barriera è necessaria perché la seconda fase richiede che ogni attività abbia accesso a tutti i dati che è stato generato a questo punto.</span><span class="sxs-lookup"><span data-stu-id="dab6a-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="dab6a-114">Senza la barriera, le attività da completare prima potrebbero tentare di leggere dal buffer non sono stati compilati ancora da altre attività.</span><span class="sxs-lookup"><span data-stu-id="dab6a-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="dab6a-115">È possibile sincronizzare un numero qualsiasi di fasi in questo modo.</span><span class="sxs-lookup"><span data-stu-id="dab6a-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab6a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dab6a-116">See Also</span></span>  
 [<span data-ttu-id="dab6a-117">Strutture di dati per la programmazione in parallelo</span><span class="sxs-lookup"><span data-stu-id="dab6a-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
