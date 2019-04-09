---
title: "Procedura: Aggiungere un'animazione a un rettangolo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151008"
---
# <a name="how-to-animate-a-rectangle"></a>Procedura: Aggiungere un'animazione a un rettangolo
Questo esempio illustra come animare le modifiche apportate alle dimensioni e alla posizione di un rettangolo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un'istanza del <xref:System.Windows.Media.Animation.RectAnimation> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>, che anima le modifiche alle dimensioni e posizione del rettangolo.  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e funzionalità multimediali](index.md)
- [Procedure relative alle funzionalità grafiche](graphics-how-to-topics.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
