---
title: 'Procedura: Accumulare valori di animazione durante i cicli ripetuti'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 6e98b7eefd0c30e728b60926096c0f082bc079ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587281"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Procedura: Accumulare valori di animazione durante i cicli ripetuti
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà da accumulare valori di animazione durante i cicli ripetuti.  
  
## <a name="example"></a>Esempio  
 Usare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà accumulare valori di base di un'animazione durante i cicli ripetuti. Ad esempio, se si imposta un'animazione per ripetere 9 volte (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "x 9") e si imposta la proprietà da animare compreso tra 10 e 15 (da = 10 a = 15), la proprietà viene animata da 10 a 15 durante il primo ciclo, da 15 a 20 durante il secondo ciclo , da 20 a 25 durante il ciclo di terzo e così via. Di conseguenza, ogni ciclo di animazione Usa il valore finale dell'animazione dal ciclo di animazione precedente come valore di base.  
  
 È possibile usare il `IsCumulative` proprietà con più semplici animazioni e la maggior parte delle animazioni con fotogrammi chiave. Per altre informazioni, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Nell'esempio seguente viene illustrato questo comportamento aggiungendo un'animazione alla larghezza di quattro rettangoli. Esempio:  
  
-   Aggiunge un'animazione con il primo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà `true`.  
  
-   Aggiunge un'animazione con secondo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà sul valore predefinito di `false`.  
  
-   Anima il terzo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `true`.  
  
-   Anima il rettangolo con ultimo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [Ripetere un'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
