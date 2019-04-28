---
title: "Procedura: Aggiungere un'animazione alla posizione di un oggetto usando PointAnimation"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651350"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Procedura: Aggiungere un'animazione alla posizione di un oggetto usando PointAnimation
Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un'ellisse un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro. Nell'esempio viene animata la posizione di un <xref:System.Windows.Media.EllipseGeometry> usando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e funzionalità multimediali](index.md)
- [Procedure relative alla grafica](graphics-how-to-topics.md)
- [Animazione e temporizzazione procedure](animation-and-timing-how-to-topics.md)
