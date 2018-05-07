---
title: 'Procedura: modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 126d260fbd59c1c35d8f56be6aa7dabe7688fa32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Procedura: modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale
Oggetto <xref:System.Windows.Media.Animation.ClockController> dell'oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> proprietà consente di modificare la velocità di un <xref:System.Windows.Media.Animation.Clock> senza alterare il <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> dell'orologio <xref:System.Windows.Media.Animation.Timeline>. Nell'esempio seguente, un <xref:System.Windows.Media.Animation.ClockController> viene utilizzato per modificare in modo interattivo il <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> di un orologio. Il <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> evento e il clock <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> proprietà consentono di visualizzare la velocità del clock corrente globale ogni volta che l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> viene modificato.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
