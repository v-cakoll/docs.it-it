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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010189"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Procedura: Modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale
Oggetto <xref:System.Windows.Media.Animation.ClockController> dell'oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> proprietà consente di modificare la velocità di un <xref:System.Windows.Media.Animation.Clock> senza alterare il <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> dell'orologio <xref:System.Windows.Media.Animation.Timeline>. Nell'esempio seguente, un <xref:System.Windows.Media.Animation.ClockController> viene usato per modificare in modo interattivo la <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> di un orologio. Il <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> evento e il clock <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> proprietà vengono utilizzati per visualizzare la velocità del clock corrente globale ogni volta che l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> viene modificato.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
