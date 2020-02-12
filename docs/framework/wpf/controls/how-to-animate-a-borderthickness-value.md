---
title: 'Procedura: animare un valore BorderThickness'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124663"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Procedura: animare un valore BorderThickness
Questo esempio illustra come animare le modifiche allo spessore di un bordo usando la classe <xref:System.Windows.Media.Animation.ThicknessAnimation>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene animato lo spessore di un bordo utilizzando <xref:System.Windows.Media.Animation.ThicknessAnimation>. Nell'esempio viene utilizzata la proprietà <xref:System.Windows.Controls.Border.BorderThickness%2A> di <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Per l'esempio completo, vedere [raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Procedure per l'animazione e l'intervallo](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Animare lo spessore di un bordo usando i fotogrammi chiave](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
