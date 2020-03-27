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
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344742"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Procedura: animare il colore utilizzando fotogrammi chiave
In questo esempio viene <xref:System.Windows.Media.SolidColorBrush.Color%2A> illustrato <xref:System.Windows.Media.SolidColorBrush> come animare l'oggetto di oggetto utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>oggetto . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, <xref:System.Windows.Media.Animation.LinearColorKeyFrame> utilizza un'istanza della classe per modificare gradualmente il colore da verde a rosso. I fotogrammi <xref:System.Windows.Media.Animation.LinearColorKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.  
  
2. Durante la fine del mezzo secondo successivo, <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> utilizza un'istanza della classe per modificare rapidamente il colore da rosso a giallo. I fotogrammi <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> chiave discreti come creano cambiamenti improvvisi tra i valori, ovvero il cambiamento di colore in questa parte dell'animazione si verifica rapidamente e non è sottile.  
  
3. Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplineColorKeyFrame> usa un'istanza della classe per cambiare nuovamente il colore, questa volta da giallo a verde. I fotogrammi <xref:System.Windows.Media.Animation.SplineColorKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà. In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
