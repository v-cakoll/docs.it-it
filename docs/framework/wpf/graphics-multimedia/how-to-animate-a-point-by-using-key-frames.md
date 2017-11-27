---
title: 'Procedura: animare un punto utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f574f85a5840e8bbe2d6c026d57a4cc28bd8a797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Procedura: animare un punto utilizzando fotogrammi chiave
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe animare un <xref:System.Windows.Point>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un'ellisse lungo un tracciato triangolare. Nell'esempio viene utilizzato il <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà di un <xref:System.Windows.Media.EllipseGeometry>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante il primo mezzo secondo, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearPointKeyFrame> classe per spostare l'ellisse lungo un percorso a una velocità costante dalla posizione iniziale. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crea un'interpolazione lineare uniforme tra i valori.  
  
2.  Durante la fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> classe per spostare rapidamente l'ellisse lungo il percorso alla posizione successiva. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> creare improvvisi tra due valori.  
  
3.  Durante i due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplinePointKeyFrame> classe per riportare l'ellisse nella posizione iniziale. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplinePointKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> proprietà. In questo esempio, l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Per coerenza con gli altri esempi di animazione, nelle versioni del codice di questo esempio viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard> oggetto a cui applicare il <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>. Tuttavia, quando si applica un'animazione sola nel codice, è più semplice l'utilizzo di <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo anziché un <xref:System.Windows.Media.Animation.Storyboard>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
