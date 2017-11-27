---
title: "Procedura: animare l'opacità di un elemento o un pennello"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 808d29292e176af8d3af1fc0f4a02c48ee05ea35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Procedura: animare l'opacità di un elemento o un pennello
Per fare un elemento framework rimosso dalla visualizzazione, è possibile animare relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà oppure è possibile aggiungere un'animazione il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Brush> (o pennelli) utilizzato per disegnarlo. Animazione di opacità dell'elemento rende e relativi elementi figlio dissolvenza rimosso dalla visualizzazione, ma animazione il pennello usato per disegnare l'elemento consente di selezionare più selettivo sulla parte dell'elemento viene applicata la dissolvenza. Ad esempio, è possibile animare l'opacità di un pennello utilizzato per disegnare lo sfondo di un pulsante. Si verificherebbe lo sfondo del pulsante a dissolvenza in entrata e in uscita della visualizzazione, lasciando il testo completamente opaco.  
  
> [!NOTE]
>  Animazione di <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.Brush> offre vantaggi nelle prestazioni rispetto all'animazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà di un elemento.  
  
 Nell'esempio seguente, in modo che essi dissolvenza rimosso dalla visualizzazione vengono animati due pulsanti. L'opacità del primo <xref:System.Windows.Controls.Button> viene animata da `1.0` a `0.0` su un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi. Il secondo pulsante è inoltre animato, ma l'opacità dell'oggetto SolidColorBrush utilizzato per disegnare il <xref:System.Windows.Controls.Control.Background%2A> è animata anziché l'opacità dell'intero pulsante. Quando si esegue l'esempio, il primo pulsante Dissolvenza completamente rimosso dalla visualizzazione, mentre si visualizza solo lo sfondo del secondo pulsante. Il testo e il bordo rimangono completamente opachi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Codice è stato omesso da questo esempio. L'esempio completo viene inoltre illustrato come animare l'opacità di un <xref:System.Windows.Media.Color> all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.  Per un esempio completo, vedere il [animare l'opacità di un elemento](http://go.microsoft.com/fwlink/?LinkID=159968).
