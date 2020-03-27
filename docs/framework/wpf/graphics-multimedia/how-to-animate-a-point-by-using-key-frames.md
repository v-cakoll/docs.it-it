---
title: 'Procedura: animare un punto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344872"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Procedura: animare un punto utilizzando fotogrammi chiave
In questo esempio viene <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> illustrato come <xref:System.Windows.Point>utilizzare la classe per animare un oggetto .  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un'ellisse lungo un tracciato triangolare. Nell'esempio <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> viene utilizzata <xref:System.Windows.Media.EllipseGeometry.Center%2A> la classe <xref:System.Windows.Media.EllipseGeometry>per animare la proprietà di un oggetto . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante il primo mezzo secondo, <xref:System.Windows.Media.Animation.LinearPointKeyFrame> utilizza un'istanza della classe per spostare l'ellisse lungo un percorso a una velocità costante dalla posizione iniziale. I fotogrammi <xref:System.Windows.Media.Animation.LinearPointKeyFrame> chiave lineari, come quello di creare un'interpolazione lineare uniforme tra valori.  
  
2. Durante la fine del mezzo secondo successivo, <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> utilizza un'istanza della classe per spostare improvvisamente l'ellisse lungo il percorso alla posizione successiva. I fotogrammi <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> chiave discreti, come ad esempio, creano salti improvvisi tra valori.  
  
3. Durante gli ultimi due secondi, <xref:System.Windows.Media.Animation.SplinePointKeyFrame> utilizza un'istanza della classe per spostare l'ellisse nella posizione iniziale. I fotogrammi <xref:System.Windows.Media.Animation.SplinePointKeyFrame> chiave della spline, ad esempio, <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> creano una transizione variabile tra i valori in base ai valori della proprietà. In questo esempio, l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Per coerenza con altri esempi di animazione, <xref:System.Windows.Media.Animation.Storyboard> nelle versioni <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>di codice di questo esempio viene utilizzato un oggetto per applicare l'oggetto . Tuttavia, quando si applica una singola animazione nel <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> codice, è <xref:System.Windows.Media.Animation.Storyboard>più semplice utilizzare il metodo anziché un oggetto . Per un esempio, consultate [Animare una proprietà senza usare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
