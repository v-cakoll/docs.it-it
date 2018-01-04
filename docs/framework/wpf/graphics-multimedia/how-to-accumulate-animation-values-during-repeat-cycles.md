---
title: 'Procedura: accumulare valori di animazione durante i cicli ripetuti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a91856cdfcf1ca7ae87e8e571306170feecb7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Procedura: accumulare valori di animazione durante i cicli ripetuti
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di animazione nei cicli ripetuti.  
  
## <a name="example"></a>Esempio  
 Utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di base di un'animazione nei cicli ripetuti. Ad esempio, se si imposta un'animazione per ripetere 9 volte (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") e si imposta la proprietà da animare tra 10 e 15 (da = 10 a = 15), la proprietà viene animata da 10 a 15 durante il primo ciclo, da 15 a 20 durante il secondo ciclo , da 20 a 25 durante il ciclo terzo e così via. Di conseguenza, ogni ciclo di animazione utilizza il valore di animazione finale dal ciclo di animazione precedente come valore di base.  
  
 È possibile utilizzare il `IsCumulative` proprietà con le animazioni di base e la maggior parte delle animazioni di fotogrammi chiave. Per ulteriori informazioni, vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Nell'esempio seguente viene illustrato questo comportamento aggiungendo un'animazione alla larghezza di quattro rettangoli. Esempio:  
  
-   Aggiunge un'animazione al primo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà `true`.  
  
-   Aggiunge un'animazione con il secondo rettangolo <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà sul valore predefinito di `false`.  
  
-   Aggiunge un'animazione il terzo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `true`.  
  
-   Aggiunge un'animazione l'ultimo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [Ripetere un'animazione](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
