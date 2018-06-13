---
title: "Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 7f60a3cd3fc88c5bb2460864be6cee008dc672fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557622"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione
In questo esempio viene illustrato come aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà consente di specificare se si desidera che il valore di output di un'animazione aggiunto al valore iniziale (valore di base) di una proprietà animata. È possibile utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà con le animazioni di base e la maggior parte delle animazioni di fotogrammi chiave. Per ulteriori informazioni, vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Nell'esempio seguente viene illustrato l'effetto dell'uso di <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimation> e l'utilizzo di <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Accumulare valori di animazione durante i cicli ripetuti](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Animazione e temporizzazione](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
