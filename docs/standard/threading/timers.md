---
title: Timer
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
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 80b4cee03e934d3aec98ca323aac43f934c56455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="timers"></a><span data-ttu-id="62267-102">Timer</span><span class="sxs-lookup"><span data-stu-id="62267-102">Timers</span></span>
<span data-ttu-id="62267-103">I timer sono oggetti leggeri che consentono di specificare un delegato da chiamare a un'ora specificata.</span><span class="sxs-lookup"><span data-stu-id="62267-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="62267-104">Un thread nel pool di thread esegue l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="62267-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="62267-105">L'uso della classe <xref:System.Threading.Timer?displayProperty=nameWithType> è semplice.</span><span class="sxs-lookup"><span data-stu-id="62267-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="62267-106">Si crea un **timer**, passando un delegato <xref:System.Threading.TimerCallback> al metodo di callback, un oggetto che rappresenta lo stato che verrà passato al callback, un'ora di generazione iniziale e un'ora che rappresenta il periodo compreso tra le chiamate di callback.</span><span class="sxs-lookup"><span data-stu-id="62267-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="62267-107">Per annullare un timer in sospeso, chiamare la funzione **Timer.Dispose**.</span><span class="sxs-lookup"><span data-stu-id="62267-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62267-108">Esistono altre due classi di timer.</span><span class="sxs-lookup"><span data-stu-id="62267-108">There are two other timer classes.</span></span> <span data-ttu-id="62267-109">La classe <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> è un controllo che funziona con finestre di progettazione visiva e deve essere usata nei contesti dell'interfaccia utente; genera eventi nel thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="62267-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="62267-110">La classe <xref:System.Timers.Timer?displayProperty=nameWithType> deriva da <xref:System.ComponentModel.Component> e pertanto può essere usata con le finestre di progettazione visiva; anch'essa genera eventi, ma li genera in un thread <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="62267-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="62267-111">La classe <xref:System.Threading.Timer?displayProperty=nameWithType> crea i callback in un thread <xref:System.Threading.ThreadPool> senza usare il modello di eventi.</span><span class="sxs-lookup"><span data-stu-id="62267-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="62267-112">A differenza di altri timer, fornisce inoltre un oggetto di stato al metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="62267-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="62267-113">È estremamente semplice.</span><span class="sxs-lookup"><span data-stu-id="62267-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="62267-114">Nell'esempio seguente viene avviato un timer che inizia dopo un secondo (1000 millisecondi) e segna ogni secondo finché non si preme il tasto **Invio**.</span><span class="sxs-lookup"><span data-stu-id="62267-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="62267-115">La variabile contenente il riferimento al timer è un campo a livello di classe, per assicurarsi che il timer non venga sottoposto al processo di garbage collection mentre è ancora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62267-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="62267-116">Per altre informazioni sul garbage collection, vedere <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="62267-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="62267-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62267-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="62267-118">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="62267-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
