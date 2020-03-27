---
title: 'Procedura: animare lo spessore di un bordo utilizzando frame chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344697"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Procedura: animare lo spessore di un bordo utilizzando frame chiave
In questo esempio viene <xref:System.Windows.Controls.Control.BorderThickness%2A> illustrato <xref:System.Windows.Controls.Border>come animare la proprietà di un oggetto .  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Controls.Control.BorderThickness%2A> proprietà di un <xref:System.Windows.Controls.Border>oggetto . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante il primo mezzo secondo, <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> utilizza un'istanza della classe per aumentare gradualmente lo spessore del bordo. Nell'esempio <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> viene utilizzato per creare un aumento lineare uniforme tra i valori.  
  
2. Alla fine del mezzo secondo successivo, utilizza <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> un'istanza della classe per aumentare improvvisamente lo spessore del bordo. I fotogrammi chiave discreti come quelli derivati da <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> creano salti improvvisi tra i valori, ovvero il movimento dell'animazione è a scatti.  
  
3. Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> utilizza un'istanza della classe per ridurre lo spessore del bordo. I fotogrammi chiave spline come quelli derivati da <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> creano <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> una transizione variabile tra valori in base ai valori della proprietà. In questo fotogramma chiave l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
- [Animare un valore BorderThickness](../controls/how-to-animate-a-borderthickness-value.md)
