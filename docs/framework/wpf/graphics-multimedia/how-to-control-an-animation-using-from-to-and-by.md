---
title: 'Procedura: controllare un''animazione mediante i valori From, To e By'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedura: controllare un'animazione mediante i valori From, To e By
Un "da/a/da" o "base" viene creata una transizione tra due valori di destinazione (vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) per un'introduzione ai tipi diversi di animazioni). Per impostare i valori di destinazione di un'animazione di base, utilizzare il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.  Nella tabella seguente sono riepilogati come <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà possono essere utilizzate insieme o separatamente i valori per determinare una destinazione di un'animazione.  
  
|Proprietà specificate|Comportamento|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|L'avanzamento dell'animazione dal valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore di base della proprietà viene aggiunta un'animazione o animazione precedente valore, a seconda della configurazione l'animazione precedente di output.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'avanzamento dell'animazione dal valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà sul valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'avanzamento dell'animazione dal valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà sul valore specificato per la somma del <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Avanzamento dell'animazione dal valore di base della proprietà animata o un'animazione precedente il valore specificato dal valore di output di <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'avanzamento dell'animazione dal valore di base della proprietà viene aggiunta un'animazione o animazione precedente valore di output per la somma di tale valore e il valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.|  
  
> [!NOTE]
>  Non impostare entrambi i <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà sulla stessa animazione.  
  
 Per usare altri metodi di interpolazione o aggiungere un'animazione tra più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Vedere [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) per ulteriori informazioni.  
  
 Per informazioni sull'applicazione di animazioni più di una singola proprietà, vedere [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 L'esempio seguente mostra i diversi effetti dell'impostazione <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Esempio di valori di destinazione dell'animazione From/To/By](http://go.microsoft.com/fwlink/?LinkID=159988)
