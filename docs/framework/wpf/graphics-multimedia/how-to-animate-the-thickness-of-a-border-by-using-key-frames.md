---
title: 'Procedura: animare lo spessore di un bordo utilizzando frame chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 3081bff4cc3f05593d644121fbaff58bb652151b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Procedura: animare lo spessore di un bordo utilizzando frame chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Controls.Control.BorderThickness%2A> proprietà di un <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Controls.Control.BorderThickness%2A> proprietà di un <xref:System.Windows.Controls.Border>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante il primo mezzo secondo, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> classe per aumentare gradualmente lo spessore del bordo. Nell'esempio viene utilizzato <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> per creare un aumento lineare uniforme tra i valori.  
  
2.  Alla fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> classe per aumentare improvvisamente lo spessore del bordo. Fotogrammi chiave discreti come quelli derivati da <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> creare improvvisi tra due valori, ovvero, si scatti dell'animazione.  
  
3.  Durante i due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> classe per ridurre lo spessore del bordo. Fotogrammi chiave spline come quelli derivati da <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> proprietà. In questo fotogramma chiave l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Animare un valore BorderThickness](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
