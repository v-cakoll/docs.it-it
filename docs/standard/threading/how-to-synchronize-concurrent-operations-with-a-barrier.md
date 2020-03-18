---
title: 'Procedura: sincronizzare operazioni simultanee con una barriera'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: 33098878764c2f8a8c1f83a122028da40b984243
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137966"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="a93dc-102">Procedura: sincronizzare operazioni simultanee con una barriera</span><span class="sxs-lookup"><span data-stu-id="a93dc-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="a93dc-103">L'esempio seguente mostra come sincronizzare le attività simultanee con un oggetto <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="a93dc-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a93dc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a93dc-104">Example</span></span>  
 <span data-ttu-id="a93dc-105">Lo scopo del programma seguente è quello di contare il numero di iterazioni (o fasi) necessarie per due thread in modo che ognuno trovi la propria metà della soluzione nella stessa fase usando un algoritmo di scelta casuale per riselezionare in ordine casuale le parole.</span><span class="sxs-lookup"><span data-stu-id="a93dc-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="a93dc-106">Dopo che ogni thread ha selezionato in ordine casuale le parole, l'operazione post-fase della barriera confronta i due risultati per verificare se è stato eseguito il rendering della frase completa con l'ordine corretto di parole.</span><span class="sxs-lookup"><span data-stu-id="a93dc-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="a93dc-107">Un oggetto <xref:System.Threading.Barrier> è un oggetto che impedisce alle singole attività in un'operazione parallela di continuare fino a quando tutte le attività non raggiungono la barriera.</span><span class="sxs-lookup"><span data-stu-id="a93dc-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="a93dc-108">È utile quando un'operazione parallela avviene in fasi e ogni fase richiede la sincronizzazione tra le attività.</span><span class="sxs-lookup"><span data-stu-id="a93dc-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="a93dc-109">In questo esempio l'operazione include due fasi.</span><span class="sxs-lookup"><span data-stu-id="a93dc-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="a93dc-110">Nella prima fase ogni attività riempie la propria sezione del buffer con dati.</span><span class="sxs-lookup"><span data-stu-id="a93dc-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="a93dc-111">Quando ogni attività finisce di riempire la propria sezione, segnala alla barriera che è pronta per continuare e quindi attende.</span><span class="sxs-lookup"><span data-stu-id="a93dc-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="a93dc-112">Quando tutte le attività hanno segnalato il completamento alla barriera, vengono sbloccate e inizia la seconda fase.</span><span class="sxs-lookup"><span data-stu-id="a93dc-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="a93dc-113">La barriera è necessaria perché la seconda fase richiede che ogni attività abbia accesso a tutti i dati che sono stati generati fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="a93dc-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="a93dc-114">Senza la barriera, le prime attività potrebbero cercare di leggere da buffer che non sono ancora stati riempiti da altre attività.</span><span class="sxs-lookup"><span data-stu-id="a93dc-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="a93dc-115">In questo modo, è possibile sincronizzare un numero qualsiasi di fasi.</span><span class="sxs-lookup"><span data-stu-id="a93dc-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93dc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a93dc-116">See also</span></span>

- [<span data-ttu-id="a93dc-117">Strutture di dati per la programmazione in parallelo</span><span class="sxs-lookup"><span data-stu-id="a93dc-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
