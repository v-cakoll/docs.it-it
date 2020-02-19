---
title: "Procedura: controllare un'animazione mediante i valori From, To e By"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451785"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedura: controllare un'animazione mediante i valori From, To e By
Con "from/to/by" o "Animation di base" viene creata una transizione tra due valori di destinazione. vedere [Cenni preliminari sull'animazione](animation-overview.md) per un'introduzione a diversi tipi di animazioni. Per impostare i valori di destinazione di un'animazione di base, utilizzare le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  Nella tabella seguente viene riepilogato il modo in cui le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> possono essere utilizzate insieme o separatamente per determinare i valori di destinazione di un'animazione.  
  
|Proprietà specificate|Comportamento|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|L'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> al valore di base della proprietà a cui si sta aggiungendo un'animazione o al valore di output di un'animazione precedente, a seconda della configurazione dell'animazione precedente.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> al valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> al valore specificato dalla somma delle proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore di base della proprietà animata o da un valore di output di un'animazione precedente al valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore di base della proprietà animata o dal valore di output di un'animazione precedente alla somma di tale valore e del valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
  
> [!NOTE]
> Non impostare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> e la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> nella stessa animazione.  
  
 Per usare altri metodi di interpolazione o aggiungere un'animazione tra più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Per ulteriori informazioni, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) .  
  
 Per informazioni sull'applicazione di più animazioni a una singola proprietà, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 Nell'esempio seguente vengono illustrati i diversi effetti dell'impostazione delle proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>e <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> sulle animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
