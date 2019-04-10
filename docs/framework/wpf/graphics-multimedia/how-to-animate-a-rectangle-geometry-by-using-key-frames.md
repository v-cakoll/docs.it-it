---
title: "Procedura: Aggiungere un'animazione a un rettangolo usando fotogrammi chiave"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311344"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Procedura: Aggiungere un'animazione a un rettangolo usando fotogrammi chiave
In questo esempio illustra come animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry> usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearRectKeyFrame> classe per animare una modifica graduale nella posizione, larghezza e altezza di un rettangolo. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearRectKeyFrame> creano una transizione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo viene usata un'istanza del <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> classe per diminuire rapidamente l'altezza del rettangolo. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> creano cambiamenti improvvisi tra valori, vale a dire, la diminuzione di altezza si verifica rapidamente e risulta immediatamente evidente.  
  
3. I due secondi finali viene usata un'istanza del <xref:System.Windows.Media.Animation.SplineRectKeyFrame> classe per il rettangolo di ripristinare le dimensioni e la posizione originale. Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineRectKeyFrame> creano una transizione variabile tra i valori a seconda dei valori del <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> proprietà. In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
