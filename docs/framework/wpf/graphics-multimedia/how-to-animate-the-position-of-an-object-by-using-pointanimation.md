---
title: 'Procedura: Animare la posizione di un oggetto utilizzando PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: e359e712f533c861a694c53848ca0eaeb289eb21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495553"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Procedura: Animare la posizione di un oggetto utilizzando PointAnimation
Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un'ellisse un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro. Nell'esempio viene animata la posizione di un <xref:System.Windows.Media.EllipseGeometry> usando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Grafica e funzionalità multimediali](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)
- [Animazione e temporizzazione](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
