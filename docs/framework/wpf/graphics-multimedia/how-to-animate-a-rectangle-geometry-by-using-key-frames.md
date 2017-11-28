---
title: 'Procedura: animare un rettangolo utilizzando fotogrammi chiave'
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
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6c23f894b6fa93a3889356416bd95f61fff8beb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Procedura: animare un rettangolo utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry> utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1.  Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearRectKeyFrame> classe per aggiungere un'animazione a una modifica graduale nella posizione, larghezza e altezza di un rettangolo. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearRectKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2.  Durante la fine della riga successiva viene utilizzata un'istanza di mezzo secondo, il <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> classe improvvisamente diminuire l'altezza del rettangolo. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> creano modifiche improvvise tra valori, vale a dire, la riduzione dell'altezza avviene in modo rapido e risulta immediatamente evidente.  
  
3.  Durante i due secondi finali, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.SplineRectKeyFrame> classe per il rettangolo di ripristinare le dimensioni e la posizione originale. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineRectKeyFrame> creare una transizione tra i valori in base ai valori delle variabile di <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> proprietà. In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
