---
title: 'Procedura: animare una stringa utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344677"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Procedura: animare una stringa utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare <xref:System.Windows.Controls.ContentControl.Content%2A> una stringa, che in questo esempio è la proprietà di un <xref:System.Windows.Controls.Button> controllo, utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button>oggetto .  
  
 Tutti i fotogrammi chiave di questo <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> esempio usano un'istanza della classe perché un'animazione di stringa creata con fotogrammi chiave può utilizzare solo fotogrammi chiave discreti. I fotogrammi <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> chiave discreti come creano salti improvvisi tra i valori, ovvero le modifiche all'animazione si verificano rapidamente e non sono sottili.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
