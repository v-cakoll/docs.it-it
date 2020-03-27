---
title: 'Procedura: animare un oggetto Double utilizzando i fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344945"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Procedura: animare un oggetto Double utilizzando i fotogrammi chiave
In questo esempio viene illustrato come animare <xref:System.Double> il valore di una proprietà che accetta utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un rettangolo in una schermata. Nell'esempio <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> viene utilizzata <xref:System.Windows.Media.TranslateTransform.X%2A> la classe <xref:System.Windows.Media.TranslateTransform> per <xref:System.Windows.Shapes.Rectangle>animare la proprietà di un oggetto applicato a un oggetto . Questa animazione, ripetuta all'infinito, usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi tre secondi, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> utilizza un'istanza della classe per spostare il rettangolo lungo un percorso a una velocità costante dalla posizione iniziale alla posizione 500. I fotogrammi <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> chiave lineari come creano una transizione lineare uniforme tra i valori.  
  
2. Alla fine del quarto secondo, utilizza <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> un'istanza della classe per spostare improvvisamente il rettangolo nella posizione successiva. I fotogrammi <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> chiave discreti, come ad esempio, creano salti improvvisi tra valori. In questo esempio, il rettangolo si trova in corrispondenza della posizione iniziale e improvvisamente appare nella posizione 500.  
  
3. Nei due secondi finali, utilizza <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> un'istanza della classe per spostare il rettangolo nella posizione iniziale. I fotogrammi <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> chiave della spline, come ad <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> esempio, creano una transizione variabile tra i valori in base al valore della proprietà. In questo esempio, il rettangolo inizia a spostarsi lentamente e quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Per coerenza con altri esempi di animazione, <xref:System.Windows.Media.Animation.Storyboard> nelle versioni <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>di codice di questo esempio viene utilizzato un oggetto per applicare l'oggetto . In alternativa, quando si applica una singola animazione <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nel codice, <xref:System.Windows.Media.Animation.Storyboard>è più semplice utilizzare il metodo anziché un oggetto . Per un esempio, consultate [Animare una proprietà senza usare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
