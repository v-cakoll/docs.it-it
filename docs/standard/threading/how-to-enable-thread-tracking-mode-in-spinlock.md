---
title: "Procedura: abilitare la modalità di rilevamento thread in SpinLock"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="30dac-102">Procedura: abilitare la modalità di rilevamento thread in SpinLock</span><span class="sxs-lookup"><span data-stu-id="30dac-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="30dac-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>è un blocco a esclusione reciproca di basso livello che è possibile utilizzare per gli scenari con tempi di attesa molto brevi.</span><span class="sxs-lookup"><span data-stu-id="30dac-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="30dac-104"><xref:System.Threading.SpinLock>non è rientrante.</span><span class="sxs-lookup"><span data-stu-id="30dac-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="30dac-105">Dopo che un thread viene inserito il blocco, è necessario uscirne correttamente prima di potervi accedere nuovamente.</span><span class="sxs-lookup"><span data-stu-id="30dac-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="30dac-106">In genere, qualsiasi tentativo di immettere di nuovo il blocco causerebbe un deadlock e deadlock possono essere molto difficili eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="30dac-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="30dac-107">Come ausilio per lo sviluppo, di <xref:System.Threading.SpinLock?displayProperty=nameWithType> supporta una modalità di rilevamento thread che genera un'eccezione generata quando un thread tenta di immettere nuovamente un blocco che contiene già.</span><span class="sxs-lookup"><span data-stu-id="30dac-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="30dac-108">Ciò consente di che individuare più facilmente il punto in cui il blocco non è stato terminato correttamente.</span><span class="sxs-lookup"><span data-stu-id="30dac-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="30dac-109">È possibile attivare la modalità di rilevamento thread usando il <xref:System.Threading.SpinLock> costruttore che accetta un valore booleano di input e passando un argomento di `true`.</span><span class="sxs-lookup"><span data-stu-id="30dac-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="30dac-110">Dopo aver completato le fasi di sviluppo e test, disattivare la modalità di rilevamento thread per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="30dac-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30dac-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="30dac-111">Example</span></span>  
 <span data-ttu-id="30dac-112">Nell'esempio seguente illustra la modalità di rilevamento thread.</span><span class="sxs-lookup"><span data-stu-id="30dac-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="30dac-113">Sono impostate come commento le righe che uscirne correttamente per simulare un errore di codifica che causa uno dei risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="30dac-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="30dac-114">Viene generata un'eccezione se il <xref:System.Threading.SpinLock> è stato creato utilizzando un argomento di `true` (`True` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="30dac-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="30dac-115">Un deadlock se la <xref:System.Threading.SpinLock> è stato creato utilizzando un argomento di `false` (`False` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="30dac-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="30dac-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30dac-116">See Also</span></span>  
 [<span data-ttu-id="30dac-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="30dac-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
