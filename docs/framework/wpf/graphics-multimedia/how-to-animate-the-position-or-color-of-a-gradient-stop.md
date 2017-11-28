---
title: 'Procedura: animare la posizione o il colore di un cursore sfumatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968d285d8a3345da9810f0ba4797bf8b2e33d36e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Procedura: animare la posizione o il colore di un cursore sfumatura
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di <xref:System.Windows.Media.GradientStop> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente aggiunge un'animazione tre cursori sfumatura all'interno di un <xref:System.Windows.Media.LinearGradientBrush>. L'esempio utilizza tre animazioni, ognuno dei quali aggiunge un'animazione a un cursore sfumatura diversi:  
  
-   La prima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione il primo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Offset%2A> da 0,0 a 1,0 e quindi nuovamente su 0,0. Di conseguenza, il primo sfumatura si sposta da sinistra a destra del rettangolo di colore e quindi tornare a sinistra.  
  
-   La seconda animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione il secondo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> da <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> e quindi nuovamente <xref:System.Windows.Media.Colors.Purple%2A>. Di conseguenza, il colore intermedio della sfumatura cambia da viola giallo e tornare al viola.  
  
-   La terza animazione, un altro <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione l'opacità del terzo sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> per -1 e quindi eseguire il backup. Di conseguenza, il terzo colore della sfumatura di dissolvenza e quindi diventa opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Sebbene questo esempio viene utilizzato un <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione <xref:System.Windows.Media.GradientStop> oggetti all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Per ulteriori esempi, vedere il [esempio](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.GradientStop>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
