---
title: "Procedura: Controllare un'animazione usando i valori From, To e By"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 56522ee5bd4391e43c261558b2fa622234c9ea3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008785"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedura: Controllare un'animazione usando i valori From, To e By
Un "From/To/By" o "un'animazione base" Crea una transizione tra due valori di destinazione (vedere [Cenni preliminari sull'animazione](animation-overview.md) per un'introduzione ai diversi tipi di animazioni). Per impostare i valori di destinazione di un'animazione di base, usare il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.  La tabella seguente riepiloga il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà possono essere usate insieme o separatamente per destinazione di un'animazione di determinare i valori.  
  
|Proprietà specificate|Comportamento|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|L'animazione avanza dal valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore di base della proprietà animata o da un'animazione precedente valore, a seconda del modo in cui è configurata l'animazione precedente di output.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> sul valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà sul valore specificato per la somma del <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore di base della proprietà animata o valore sul valore specificato dall'output dell'animazione precedente il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore di base della proprietà animata o un'animazione precedente valore di output per la somma di quel valore e il valore specificato per il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.|  
  
> [!NOTE]
>  Non impostare entrambe le <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà e il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà sulla stessa animazione.  
  
 Per usare altri metodi di interpolazione o aggiungere un'animazione tra più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Visualizzare [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) per altre informazioni.  
  
 Per informazioni sull'applicazione di più animazioni a una singola proprietà, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 L'esempio seguente illustra i diversi effetti dell'impostazione <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà sulle animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://go.microsoft.com/fwlink/?LinkID=159988)
