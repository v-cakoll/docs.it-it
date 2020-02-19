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
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452844"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Procedura: animare la posizione o il colore di un cursore sfumatura
Questo esempio illustra come animare il <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di oggetti di <xref:System.Windows.Media.GradientStop>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono animati tre arresti sfumatura all'interno di una <xref:System.Windows.Media.LinearGradientBrush>. Nell'esempio vengono usate tre animazioni, ciascuna delle quali anima un diverso cursore sfumatura:  
  
- La prima animazione, una <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione al <xref:System.Windows.Media.GradientStop.Offset%2A> del primo cursore sfumatura da 0,0 a 1,0 e quindi nuovamente a 0,0. Di conseguenza, il primo colore della sfumatura si sposta dal lato sinistro al lato destro del rettangolo e quindi di nuovo al lato sinistro.  
  
- La seconda animazione, una <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione al <xref:System.Windows.Media.GradientStop.Color%2A> del secondo cursore sfumatura da <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> e quindi di nuovo a <xref:System.Windows.Media.Colors.Purple%2A>. Di conseguenza, il colore intermedio della sfumatura passa da viola a giallo a quello viola e viceversa.  
  
- La terza animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, anima l'opacità del terzo <xref:System.Windows.Media.GradientStop.Color%2A> del cursore sfumatura di-1 e quindi di nuovo. Di conseguenza, il terzo colore nella sfumatura scompare, quindi diventa di nuovo opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Sebbene in questo esempio venga utilizzato un <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione di oggetti <xref:System.Windows.Media.GradientStop> all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Per altri esempi, vedere l' [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.GradientStop>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
