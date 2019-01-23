---
title: Limitazioni del componente Timer Windows Form&#39;proprietà di Interval s
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 86cfcce65998d19aea8592ae33c5baf58e1ff0fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516954"
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="35e7b-102">Limitazioni del componente Timer Windows Form&#39;proprietà di Interval s</span><span class="sxs-lookup"><span data-stu-id="35e7b-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="35e7b-103">I moduli di Windows <xref:System.Windows.Forms.Timer> componente dispone di un <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che intercorre tra un evento timer e quella successiva.</span><span class="sxs-lookup"><span data-stu-id="35e7b-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="35e7b-104">A meno che il componente è disabilitato, un timer continua a ricevere il <xref:System.Windows.Forms.Timer.Tick> evento quasi uguale a intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="35e7b-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="35e7b-105">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="35e7b-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="35e7b-106">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="35e7b-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="35e7b-107">La proprietà di Interval</span><span class="sxs-lookup"><span data-stu-id="35e7b-107">The Interval Property</span></span>  
 <span data-ttu-id="35e7b-108">Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da prendere in considerazione quando si programma un <xref:System.Windows.Forms.Timer> componente:</span><span class="sxs-lookup"><span data-stu-id="35e7b-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="35e7b-109">Se l'applicazione o un'altra applicazione in esecuzione nel sistema, ad esempio cicli lungo, i calcoli con utilizzo intensivo, unità, rete o l'accesso alla porta, ovvero l'applicazione potrebbe non ricevere eventi timer con la frequenza come il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà specifica.</span><span class="sxs-lookup"><span data-stu-id="35e7b-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="35e7b-110">L'intervallo non è garantito l'esattezza ora.</span><span class="sxs-lookup"><span data-stu-id="35e7b-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="35e7b-111">Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché tentare di tenere traccia del tempo cumulato internamente.</span><span class="sxs-lookup"><span data-stu-id="35e7b-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="35e7b-112">La precisione del <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="35e7b-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="35e7b-113">Alcuni computer forniscono un contatore ad alta risoluzione che ha una risoluzione superiore a millisecondi.</span><span class="sxs-lookup"><span data-stu-id="35e7b-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="35e7b-114">La disponibilità di questo tipo di contatore dipende da hardware del processore del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="35e7b-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35e7b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35e7b-115">See also</span></span>
- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="35e7b-116">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="35e7b-116">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [<span data-ttu-id="35e7b-117">Panoramica sul componente Timer</span><span class="sxs-lookup"><span data-stu-id="35e7b-117">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
