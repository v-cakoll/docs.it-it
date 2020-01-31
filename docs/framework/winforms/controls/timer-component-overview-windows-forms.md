---
title: Panoramica del componente Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742776"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="9e3df-102">Panoramica del componente Timer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9e3df-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="9e3df-103">Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="9e3df-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="9e3df-104">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="9e3df-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="9e3df-105">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9e3df-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="9e3df-106">Proprietà, metodi ed eventi chiave</span><span class="sxs-lookup"><span data-stu-id="9e3df-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="9e3df-107">La lunghezza degli intervalli è definita dalla proprietà <xref:System.Windows.Forms.Timer.Interval%2A>, il cui valore è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="9e3df-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="9e3df-108">Quando il componente è abilitato, l'evento <xref:System.Windows.Forms.Timer.Tick> viene generato ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="9e3df-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="9e3df-109">Qui è possibile aggiungere il codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9e3df-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="9e3df-110">Per altre informazioni, vedere [procedura: eseguire routine a intervalli prestabiliti con il componente Timer Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="9e3df-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="9e3df-111">I metodi principali del componente <xref:System.Windows.Forms.Timer> sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano e disattivano il timer.</span><span class="sxs-lookup"><span data-stu-id="9e3df-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="9e3df-112">Quando il timer viene disattivato, viene reimpostato; non è possibile sospendere un componente <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="9e3df-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e3df-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e3df-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="9e3df-114">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="9e3df-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="9e3df-115">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9e3df-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
