---
title: "Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 4b2bc79a7b652c34334d5a78d9c9af328993ff44
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279206"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="a72a9-102">Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi</span><span class="sxs-lookup"><span data-stu-id="a72a9-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="a72a9-103">L'esempio seguente mostra come usare un oggetto <xref:System.Threading.SpinWait?displayProperty=nameWithType> per implementare un'operazione di attesa a due fasi.</span><span class="sxs-lookup"><span data-stu-id="a72a9-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="a72a9-104">Nella prima fase, l'oggetto di sincronizzazione, `Latch`, ruota per alcuni cicli mentre controlla se il blocco è diventato disponibile.</span><span class="sxs-lookup"><span data-stu-id="a72a9-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="a72a9-105">Nella seconda fase, se il blocco diventa disponibile, il metodo `Wait` restituisce un risultato senza usare <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> per l'attesa; in caso contrario, `Wait` esegue l'attesa.</span><span class="sxs-lookup"><span data-stu-id="a72a9-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a72a9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a72a9-106">Example</span></span>  
 <span data-ttu-id="a72a9-107">Questo esempio illustra un'implementazione di base di una primitiva di sincronizzazione Latch.</span><span class="sxs-lookup"><span data-stu-id="a72a9-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="a72a9-108">È possibile usare questa struttura dei dati quando si prevedono tempi di attesa molto brevi.</span><span class="sxs-lookup"><span data-stu-id="a72a9-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="a72a9-109">Questo esempio viene fornito solo per scopi dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="a72a9-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="a72a9-110">Se sono necessarie funzionalità di tipo latch nel programma, è consigliabile usare <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a72a9-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="a72a9-111">Il latch usa l'oggetto <xref:System.Threading.SpinWait> per ruotare sul posto solo fino a quando la chiamata successiva a `SpinOnce` fa in modo che <xref:System.Threading.SpinWait> restituisca l'intervallo di tempo del thread.</span><span class="sxs-lookup"><span data-stu-id="a72a9-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="a72a9-112">A questo punto, il latch provoca il cambio di contesto chiamando <xref:System.Threading.WaitHandle.WaitOne%2A> su <xref:System.Threading.ManualResetEvent> e passando la parte restante del valore di timeout.</span><span class="sxs-lookup"><span data-stu-id="a72a9-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="a72a9-113">L'output di registrazione mostra la frequenza con cui il latch è stato in grado di migliorare le prestazioni acquisendo il blocco senza usare l'oggetto <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="a72a9-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72a9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a72a9-114">See also</span></span>

- [<span data-ttu-id="a72a9-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="a72a9-115">SpinWait</span></span>](spinwait.md)
- [<span data-ttu-id="a72a9-116">Oggetti e funzionalità di threading</span><span class="sxs-lookup"><span data-stu-id="a72a9-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)
