---
title: 'Procedura: animare un rettangolo utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344685"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Procedura: animare un rettangolo utilizzando fotogrammi chiave
In questo esempio viene <xref:System.Windows.Media.RectangleGeometry.Rect%2A> illustrato <xref:System.Windows.Media.RectangleGeometry> come animare la proprietà di un utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>oggetto . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, <xref:System.Windows.Media.Animation.LinearRectKeyFrame> utilizza un'istanza della classe per animare una modifica graduale della posizione, larghezza e altezza di un rettangolo. I fotogrammi <xref:System.Windows.Media.Animation.LinearRectKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.  
  
2. Durante la fine del mezzo secondo successivo, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> utilizza un'istanza della classe per ridurre improvvisamente l'altezza del rettangolo. Fotogrammi chiave <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> discreti come creano cambiamenti improvvisi tra i valori, cioè la diminuzione dell'altezza si verifica rapidamente e non è sottile.  
  
3. Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplineRectKeyFrame> utilizza un'istanza della classe per riportare il rettangolo alle dimensioni e alla posizione originali. I fotogrammi <xref:System.Windows.Media.Animation.SplineRectKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà. In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
