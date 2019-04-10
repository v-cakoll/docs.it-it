---
title: "Procedura: Aggiungere un'animazione a un oggetto double usando i fotogrammi chiave"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 73cbeab8aee566313bad8e8a18a5500374287de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305585"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Procedura: Aggiungere un'animazione a un oggetto double usando i fotogrammi chiave
In questo esempio illustra come animare il valore di una proprietà che accetta un <xref:System.Double> usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un rettangolo in una schermata. L'esempio Usa il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di un <xref:System.Windows.Media.TranslateTransform> applicato a un <xref:System.Windows.Shapes.Rectangle>. Questa animazione, ripetuta all'infinito, usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi tre secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> classe per spostare il rettangolo lungo un tracciato a una velocità costante dalla posizione iniziale alla posizione 500. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> creano una transizione lineare uniforme tra i valori.  
  
2. Alla fine del quarto secondo, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> classe per spostare rapidamente il rettangolo alla posizione successiva. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> creano salti improvvisi tra valori. In questo esempio, il rettangolo si trova in corrispondenza della posizione iniziale e improvvisamente appare nella posizione 500.  
  
3. Nei due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> classe per riportare il rettangolo alla posizione iniziale. Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> creano una transizione variabile tra i valori a seconda del valore del <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> proprietà. In questo esempio, il rettangolo inizia a spostarsi lentamente e quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio usano un' <xref:System.Windows.Media.Animation.Storyboard> oggetto a cui applicare il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. In alternativa, quando si applica una sola animazione al codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un <xref:System.Windows.Media.Animation.Storyboard>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
