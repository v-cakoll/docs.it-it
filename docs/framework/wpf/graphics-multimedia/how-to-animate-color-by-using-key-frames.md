---
title: 'Procedura: animare il colore utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 7d89a1f9c24c93bd6b05265092bde09e8cf6eff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560332"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Procedura: animare il colore utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearColorKeyFrame> classe per modificare gradualmente il colore da verde a rosso. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearColorKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2.  Durante la fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> classe per modificare rapidamente il colore da rosso a giallo. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> creano modifiche improvvise tra valori, vale a dire, la modifica del colore in questa parte dell'animazione avviene in modo rapido e risulta immediatamente evidente.  
  
3.  Durante i due secondi finali, viene utilizzata un'istanza del <xref:System.Windows.Media.Animation.SplineColorKeyFrame> classe per modificare nuovamente il colore, questa volta da giallo a verde. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineColorKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> proprietà. In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
