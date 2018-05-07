---
title: 'Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0c2828215527a285943a79920de51fa42fe7a8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave
Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un <xref:System.Windows.Media.ArcSegment>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante il primo mezzo secondo dell'animazione, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe aumentare gradualmente la dimensione dell'arco. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2.  Alla fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> classe improvvisamente aumentare le dimensioni dell'arco. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> creano improvvisi tra due valori, ovvero le modifiche di dimensione si verificano improvvisamente e risultano immediatamente evidenti.  
  
3.  Su due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> classe per aumentare le dimensioni dell'arco. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> proprietà. In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
