---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 6e453f6b7718c6c5be3109f51153a3f5e4b5b6f4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784608"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="8e536-102">Cenni preliminari sul componente Timer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="8e536-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="8e536-103">Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="8e536-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="8e536-104">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8e536-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="8e536-105">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="8e536-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="8e536-106">Le proprietà di chiave, metodi ed eventi</span><span class="sxs-lookup"><span data-stu-id="8e536-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="8e536-107">La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="8e536-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="8e536-108">Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> l'evento viene generato ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="8e536-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="8e536-109">Si tratta in cui si aggiungerà codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8e536-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="8e536-110">Per altre informazioni, vedere [procedura: eseguire routine a intervalli impostata con il componente Timer di Windows Form](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="8e536-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="8e536-111">I metodi principali dei <xref:System.Windows.Forms.Timer> componente vengono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano il timer e disattivare.</span><span class="sxs-lookup"><span data-stu-id="8e536-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="8e536-112">Quando il timer è disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="8e536-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e536-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e536-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="8e536-114">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="8e536-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="8e536-115">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8e536-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
