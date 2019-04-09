---
title: 'Procedura: Animare un valore BorderThickness'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 10e177d1f6d6add4638ce14af900e75d7e363890
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150735"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Procedura: Animare un valore BorderThickness
Questo esempio illustra come animare le modifiche apportate allo spessore del bordo di un'usando il <xref:System.Windows.Media.Animation.ThicknessAnimation> classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente anima lo spessore di un bordo usando <xref:System.Windows.Media.Animation.ThicknessAnimation>. L'esempio Usa la <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà di <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Per l'esempio completo, vedere [raccolta di esempi di animazione](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Aggiungere un'animazione allo spessore di un bordo usando i fotogrammi chiave](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
