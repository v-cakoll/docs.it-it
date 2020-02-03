---
title: Limitazioni della proprietà intervallo componente timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745236"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="2e468-102">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2e468-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="2e468-103">Il componente Windows Forms <xref:System.Windows.Forms.Timer> dispone di una proprietà <xref:System.Windows.Forms.Timer.Interval%2A> che specifica il numero di millisecondi che passano tra un evento timer e il successivo.</span><span class="sxs-lookup"><span data-stu-id="2e468-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="2e468-104">A meno che il componente non sia disabilitato, un timer continua a ricevere l'evento <xref:System.Windows.Forms.Timer.Tick> a intervalli di tempo approssimativamente uguali.</span><span class="sxs-lookup"><span data-stu-id="2e468-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="2e468-105">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2e468-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="2e468-106">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2e468-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="2e468-107">Proprietà Interval</span><span class="sxs-lookup"><span data-stu-id="2e468-107">The Interval Property</span></span>  
 <span data-ttu-id="2e468-108">La proprietà <xref:System.Windows.Forms.Timer.Interval%2A> presenta alcune limitazioni da tenere in considerazione durante la programmazione di un componente di <xref:System.Windows.Forms.Timer>:</span><span class="sxs-lookup"><span data-stu-id="2e468-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="2e468-109">Se l'applicazione o un'altra applicazione sta effettuando richieste elevate al sistema, ad esempio cicli lunghi, calcoli intensivi o accesso di unità, rete o porta, è possibile che l'applicazione non ottenga gli eventi del timer con la stessa frequenza con cui viene specificata la proprietà <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e468-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="2e468-110">Non è garantito che l'intervallo venga trascorso esattamente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="2e468-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="2e468-111">Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché provare a tenere traccia del tempo accumulato internamente.</span><span class="sxs-lookup"><span data-stu-id="2e468-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="2e468-112">La precisione della proprietà <xref:System.Windows.Forms.Timer.Interval%2A> è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="2e468-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="2e468-113">Alcuni computer forniscono un contatore ad alta risoluzione con una risoluzione superiore a millisecondi.</span><span class="sxs-lookup"><span data-stu-id="2e468-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="2e468-114">La disponibilità di tale contatore dipende dall'hardware del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="2e468-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e468-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e468-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="2e468-116">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="2e468-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="2e468-117">Panoramica sul componente Timer</span><span class="sxs-lookup"><span data-stu-id="2e468-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
