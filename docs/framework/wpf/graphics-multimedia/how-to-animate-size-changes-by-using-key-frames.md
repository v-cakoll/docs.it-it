---
title: 'Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344639"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave
Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un oggetto <xref:System.Windows.Media.ArcSegment>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante il primo mezzo secondo dell'animazione, utilizza un'istanza della <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe per aumentare gradualmente le dimensioni dell'arco. I fotogrammi <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.  
  
2. Alla fine del mezzo secondo successivo, utilizza <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> un'istanza della classe per aumentare improvvisamente le dimensioni dell'arco. I fotogrammi <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> chiave discreti come creano salti improvvisi tra i valori, cioè i cambiamenti delle dimensioni si verificano improvvisamente e non sono sottili.  
  
3. Negli ultimi due secondi, utilizza <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> un'istanza della classe per aumentare le dimensioni dell'arco. I fotogrammi <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà. In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
