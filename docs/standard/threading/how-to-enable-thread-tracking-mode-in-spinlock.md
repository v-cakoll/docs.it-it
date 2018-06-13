---
title: 'Procedura: abilitare la modalità di rilevamento thread in SpinLock'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93303ba84538a85350fd09b78f9963558668b91b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582109"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="1d0bb-102">Procedura: abilitare la modalità di rilevamento thread in SpinLock</span><span class="sxs-lookup"><span data-stu-id="1d0bb-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="1d0bb-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> è un blocco di esclusione reciproca di basso livello che è possibile usare per scenari con tempi di attesa molto brevi.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="1d0bb-104"><xref:System.Threading.SpinLock> non è rientrante.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="1d0bb-105">Dopo che un thread entra nel blocco, deve uscirne correttamente prima di potervi accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="1d0bb-106">In genere, qualsiasi tentativo di entrare di nuovo nel blocco causerebbe un deadlock e il debug dei deadlock può rivelarsi molto difficile.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="1d0bb-107">Come ausilio per lo sviluppo, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supporta una modalità di rilevamento dei thread che provoca la generazione di un'eccezione quando un thread tenta di entrare di nuovo in un blocco che già lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="1d0bb-108">Questo permette di individuare facilmente il punto in cui il thread non è uscito correttamente dal blocco.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="1d0bb-109">È possibile attivare la modalità di rilevamento dei thread usando il costruttore <xref:System.Threading.SpinLock>, che accetta un parametro di input booleano, e passando un argomento `true`.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="1d0bb-110">Dopo aver completato le fasi di sviluppo e test, disattivare la modalità di rilevamento dei thread per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d0bb-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d0bb-111">Example</span></span>  
 <span data-ttu-id="1d0bb-112">L'esempio seguente mostra la modalità di rilevamento dei thread.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="1d0bb-113">Le righe per l'uscita corretta dal blocco sono impostate come commento per simulare un errore di codifica che restituisce uno dei risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d0bb-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="1d0bb-114">Viene generata un'eccezione se l'oggetto <xref:System.Threading.SpinLock> è stato creato usando un argomento `true` (`True` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1d0bb-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="1d0bb-115">Viene generato un deadlock se l'oggetto <xref:System.Threading.SpinLock> è stato creato usando un argomento `false` (`False` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1d0bb-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="1d0bb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d0bb-116">See Also</span></span>  
 [<span data-ttu-id="1d0bb-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="1d0bb-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
