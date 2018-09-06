---
title: 'Procedura: animare la posizione o il colore di un cursore sfumatura'
ms.date: 03/30/2017
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
ms.openlocfilehash: fcbb546b64810416d3f7dbe052da77b7bc941e7a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43867427"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Procedura: animare la posizione o il colore di un cursore sfumatura
In questo esempio illustra come animare la <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di <xref:System.Windows.Media.GradientStop> oggetti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente anima tre sfumatura all'interno di un <xref:System.Windows.Media.LinearGradientBrush>. L'esempio Usa tre animazioni, ognuna delle quali anima un cursore sfumatura diversi:  
  
-   La prima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione il prima del cursore sfumatura <xref:System.Windows.Media.GradientStop.Offset%2A> da 0,0 a 1,0 e quindi nuovamente su 0,0. Di conseguenza, il primo colore in sfumatura si sposta da sinistra al lato destro del rettangolo e quindi eseguire il backup sul lato sinistro.  
  
-   La seconda animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione di secondo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> dal <xref:System.Windows.Media.Colors.Purple%2A> al <xref:System.Windows.Media.Colors.Yellow%2A> e quindi tornare alla <xref:System.Windows.Media.Colors.Purple%2A>. Di conseguenza, il colore intermedio della sfumatura cambia da viola in giallo e nuovamente in viola.  
  
-   La terza animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, consente di animare l'opacità del terzo cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> da -1 e poi di nuovo. Di conseguenza, il terzo colore della sfumatura di dissolvenza e quindi diventa nuovamente opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Sebbene questo esempio Usa un' <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione <xref:System.Windows.Media.GradientStop> oggetti all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Per altri esempi, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.GradientStop>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
