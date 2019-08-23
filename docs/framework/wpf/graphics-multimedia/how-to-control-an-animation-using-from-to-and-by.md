---
title: "Procedura: Controllare un'animazione usando i valori From, To e By"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 812217a2905671567271687b974a435dd85cea47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930091"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedura: Controllare un'animazione usando i valori From, To e By
Con "from/to/by" o "Animation di base" viene creata una transizione tra due valori di destinazione. vedere [Cenni preliminari sull'animazione](animation-overview.md) per un'introduzione a diversi tipi di animazioni. Per impostare i valori di destinazione di un'animazione di base, <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>usare <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> , e.  Nella tabella seguente viene riepilogato il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>modo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>in cui <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> le proprietà, e possono essere utilizzate insieme o separatamente per determinare i valori di destinazione di un'animazione.  
  
|Proprietà specificate|Comportamento risultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore di base della proprietà a cui si sta aggiungendo un'animazione o al valore di output di un'animazione precedente, a seconda della configurazione della precedente animazione.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore specificato <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> dalla proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore specificato dalla somma <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> delle proprietà e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore di base della proprietà animata o da un valore di output di un'animazione precedente al valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore di base della proprietà animata o dal valore di output di un'animazione precedente alla somma di tale valore e del valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.|  
  
> [!NOTE]
> Non impostare sia la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà che la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà sulla stessa animazione.  
  
 Per usare altri metodi di interpolazione o aggiungere un'animazione tra più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Per ulteriori informazioni, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) .  
  
 Per informazioni sull'applicazione di più animazioni a una singola proprietà, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 Nell'esempio seguente vengono illustrati i diversi effetti <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>dell' <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>impostazione delle <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, e sulle animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://go.microsoft.com/fwlink/?LinkID=159988)
