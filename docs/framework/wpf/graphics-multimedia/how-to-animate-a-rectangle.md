---
title: 'Procedura: animare un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 10d9f3b99e9a2c9b9aef795a8f7108c043e4267a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561430"
---
# <a name="how-to-animate-a-rectangle"></a>Procedura: animare un rettangolo
Questo esempio illustra come animare le modifiche apportate alle dimensioni e alla posizione di un rettangolo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un'istanza del <xref:System.Windows.Media.Animation.RectAnimation> classe da cui iniziare l'animazione di <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>, che aggiunge un'animazione delle modifiche per le dimensioni e la posizione del rettangolo.  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.RectAnimation>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.RectangleGeometry>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Grafica e funzionalità multimediali](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [Animazione e temporizzazione](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
