---
title: 'Procedura: utilizzare SpinWait per implementare un''operazione di attesa a due fasi'
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="70936-102">Procedura: utilizzare SpinWait per implementare un'operazione di attesa a due fasi</span><span class="sxs-lookup"><span data-stu-id="70936-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="70936-103">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.SpinWait?displayProperty=nameWithType> oggetto per implementare un'operazione di attesa a due fasi.</span><span class="sxs-lookup"><span data-stu-id="70936-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="70936-104">Nella prima fase, l'oggetto di sincronizzazione, un `Latch`, Ruota per alcuni cicli mentre viene verificato se il blocco è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="70936-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="70936-105">Nella seconda fase, se il blocco diventa disponibile, il `Wait` metodo viene restituito senza utilizzare il <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> per eseguire l'attesa; in caso contrario, `Wait` esegue l'attesa.</span><span class="sxs-lookup"><span data-stu-id="70936-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70936-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="70936-106">Example</span></span>  
 <span data-ttu-id="70936-107">Questo esempio illustra un'implementazione di base di una sincronizzazione Latch primitivi.</span><span class="sxs-lookup"><span data-stu-id="70936-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="70936-108">È possibile utilizzare questa struttura di dati quando si prevedono tempi di attesa molto brevi.</span><span class="sxs-lookup"><span data-stu-id="70936-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="70936-109">Questo esempio è solo per scopi dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="70936-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="70936-110">Se sono necessarie funzionalità di tipo di latch nel programma, è consigliabile utilizzare <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70936-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="70936-111">Il latch utilizza il <xref:System.Threading.SpinWait> oggetto da ruotare sul posto solo fino alla chiamata successiva a `SpinOnce` provoca il <xref:System.Threading.SpinWait> per produrre l'intervallo di tempo del thread.</span><span class="sxs-lookup"><span data-stu-id="70936-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="70936-112">A questo punto, il latch provoca il proprio cambio di contesto chiamando <xref:System.Threading.WaitHandle.WaitOne%2A> sul <xref:System.Threading.ManualResetEvent> e passando la parte restante del valore di timeout.</span><span class="sxs-lookup"><span data-stu-id="70936-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="70936-113">L'output di registrazione Mostra la frequenza con cui il fermo è stato in grado di migliorare le prestazioni dell'acquisizione del blocco senza utilizzare il <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="70936-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70936-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70936-114">See Also</span></span>  
 [<span data-ttu-id="70936-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="70936-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="70936-116">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="70936-116">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>
