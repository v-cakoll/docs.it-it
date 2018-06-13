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
ms.openlocfilehash: 4adeb858ab1b69ef1b00f7bf3b6868dbcbbc4154
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557433"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Procedura: animare un oggetto Double utilizzando i fotogrammi chiave
In questo esempio viene illustrato come animare il valore di una proprietà che accetta un <xref:System.Double> utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un rettangolo in una schermata. Nell'esempio viene utilizzato il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di un <xref:System.Windows.Media.TranslateTransform> applicato a un <xref:System.Windows.Shapes.Rectangle>. Questa animazione, ripetuta all'infinito, usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante i primi tre secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> classe per spostare il rettangolo lungo un percorso a una velocità costante dalla posizione iniziale alla posizione 500. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2.  Alla fine del quarto secondo, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> classe per spostare rapidamente il rettangolo alla posizione successiva. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> creare improvvisi tra due valori. In questo esempio, il rettangolo si trova in corrispondenza della posizione iniziale e improvvisamente appare nella posizione 500.  
  
3.  Nei due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> classe per riportare il rettangolo nella posizione iniziale. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> creare una transizione tra i valori in base al valore della variabile di <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> proprietà. In questo esempio, il rettangolo inizia a spostarsi lentamente e quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Per coerenza con gli altri esempi di animazione, nelle versioni del codice di questo esempio viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard> oggetto a cui applicare il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. In alternativa, quando si applica un'animazione sola nel codice, è più semplice l'utilizzo di <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo anziché un <xref:System.Windows.Media.Animation.Storyboard>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
