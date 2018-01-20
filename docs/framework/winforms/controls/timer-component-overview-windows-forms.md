---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90296d2741a96e8788bf7a9b18bf3ea303ad2bae
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="3b0e1-102">Cenni preliminari sul componente Timer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="3b0e1-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="3b0e1-103">Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="3b0e1-104">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="3b0e1-105">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="3b0e1-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="3b0e1-106">Proprietà, metodi ed eventi principali</span><span class="sxs-lookup"><span data-stu-id="3b0e1-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="3b0e1-107">La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà il cui valore è espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="3b0e1-108">Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> evento viene generato ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="3b0e1-109">Si tratta in cui è necessario aggiungere codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="3b0e1-110">Per ulteriori informazioni, vedere [procedura: eseguire routine a intervalli impostato con il componente Timer di Windows Form](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="3b0e1-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="3b0e1-111">I metodi principali del <xref:System.Windows.Forms.Timer> componente sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che il timer di attivare e disattivare.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="3b0e1-112">Quando il timer è disattivato, Ripristina; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0e1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b0e1-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="3b0e1-114">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="3b0e1-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="3b0e1-115">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3b0e1-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
