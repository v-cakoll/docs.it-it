---
title: Limitazioni del componente Timer di Windows Form&#39;proprietà Interval s
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9c42a0946cf29415f7bb12345da6784e0c276d5
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="9baa3-102">Limitazioni del componente Timer di Windows Form&#39;proprietà Interval s</span><span class="sxs-lookup"><span data-stu-id="9baa3-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="9baa3-103">Windows Form <xref:System.Windows.Forms.Timer> componente dispone di un <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che intercorre tra un evento timer e quello successivo.</span><span class="sxs-lookup"><span data-stu-id="9baa3-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="9baa3-104">A meno che il componente è disabilitato, un timer continuerà a ricevere il <xref:System.Windows.Forms.Timer.Tick> evento quasi uguale a intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="9baa3-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="9baa3-105">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="9baa3-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="9baa3-106">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="9baa3-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="9baa3-107">La proprietà Interval</span><span class="sxs-lookup"><span data-stu-id="9baa3-107">The Interval Property</span></span>  
 <span data-ttu-id="9baa3-108">Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da prendere in considerazione quando si programma un <xref:System.Windows.Forms.Timer> componente:</span><span class="sxs-lookup"><span data-stu-id="9baa3-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="9baa3-109">Se l'applicazione o un'altra applicazione in esecuzione nel sistema, ad esempio cicli lunghi, calcoli, unità, rete o accesso alle porte, l'applicazione potrebbe non ricevere gli eventi del timer più spesso come il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà specifica.</span><span class="sxs-lookup"><span data-stu-id="9baa3-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="9baa3-110">L'intervallo non è garantita l'esattezza ora.</span><span class="sxs-lookup"><span data-stu-id="9baa3-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="9baa3-111">Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché tentare di tenere traccia del tempo accumulato internamente.</span><span class="sxs-lookup"><span data-stu-id="9baa3-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="9baa3-112">La precisione del <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="9baa3-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="9baa3-113">Alcuni computer forniscono un contatore ad alta risoluzione con risoluzione superiore a millisecondi.</span><span class="sxs-lookup"><span data-stu-id="9baa3-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="9baa3-114">La disponibilità di tale contatore dipende dall'hardware del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="9baa3-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="9baa3-115">Per altre informazioni, vedere l'articolo 172338, "Modalità per utilizzare QueryPerformanceCounter a tempo codice," nella Microsoft Knowledge Base al http://support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9baa3-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9baa3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9baa3-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="9baa3-117">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="9baa3-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="9baa3-118">Panoramica sul componente Timer</span><span class="sxs-lookup"><span data-stu-id="9baa3-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
