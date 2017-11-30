---
title: 'Procedura: personalizzare i segni di graduazione di un controllo Slider'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d266d85e10ca8e77cd32338096cf3a3b761c188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Procedura: personalizzare i segni di graduazione di un controllo Slider
In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Slider> controllo con i segni di graduazione.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.TickBar> viene visualizzato quando imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None>, ovvero il valore predefinito.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> che consente di visualizzare i segni di graduazione. Il <xref:System.Windows.Controls.Slider.TickPlacement%2A> e <xref:System.Windows.Controls.Slider.TickFrequency%2A> definiscono la posizione dei segni di graduazione e l'intervallo tra di essi. Quando si sposta il <xref:System.Windows.Controls.Primitives.Thumb>, le descrizioni comandi forniscono il valore di <xref:System.Windows.Controls.Slider>. Il <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> proprietà definisce in cui si verificano le descrizioni comandi. Il <xref:System.Windows.Controls.Primitives.Thumb> movimenti corrispondono alla posizione dei segni di graduazione poiché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostato su `true`.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà da creare segni di graduazione lungo la <xref:System.Windows.Controls.Slider> in modo intermittente.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Procedure relative a Slider](http://msdn.microsoft.com/en-us/534be86c-afb2-425d-8186-631278a9925e)
