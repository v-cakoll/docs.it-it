---
title: 'Procedura: Modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358275"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="2d9fe-102">Procedura: Modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="2d9fe-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="2d9fe-103">Oggetto <xref:System.Windows.Media.Animation.ClockController> dell'oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> proprietà consente di modificare la velocità di un <xref:System.Windows.Media.Animation.Clock> senza alterare il <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> dell'orologio <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="2d9fe-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="2d9fe-104">Nell'esempio seguente, un <xref:System.Windows.Media.Animation.ClockController> viene usato per modificare in modo interattivo la <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> di un orologio.</span><span class="sxs-lookup"><span data-stu-id="2d9fe-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="2d9fe-105">Il <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> evento e il clock <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> proprietà vengono utilizzati per visualizzare la velocità del clock corrente globale ogni volta che l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> viene modificato.</span><span class="sxs-lookup"><span data-stu-id="2d9fe-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d9fe-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d9fe-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
