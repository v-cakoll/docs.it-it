---
title: "Procedura: animare l'opacità di un elemento o un pennello"
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: a45bf0344c10e1214aa5218e25e9bd9a87d5ea60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Procedura: animare l'opacità di un elemento o un pennello
Per fare un elemento framework rimosso dalla visualizzazione, è possibile animare relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà oppure è possibile aggiungere un'animazione il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Brush> (o pennelli) utilizzato per disegnarlo. Animazione di opacità dell'elemento rende e relativi elementi figlio dissolvenza rimosso dalla visualizzazione, ma animazione il pennello usato per disegnare l'elemento consente di selezionare più selettivo sulla parte dell'elemento viene applicata la dissolvenza. Ad esempio, è possibile animare l'opacità di un pennello utilizzato per disegnare lo sfondo di un pulsante. Si verificherebbe lo sfondo del pulsante a dissolvenza in entrata e in uscita della visualizzazione, lasciando il testo completamente opaco.  
  
> [!NOTE]
>  Animazione di <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.Brush> offre vantaggi nelle prestazioni rispetto all'animazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà di un elemento.  
  
 Nell'esempio seguente, in modo che essi dissolvenza rimosso dalla visualizzazione vengono animati due pulsanti. L'opacità del primo <xref:System.Windows.Controls.Button> viene animata da `1.0` a `0.0` su un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi. Il secondo pulsante è inoltre animato, ma l'opacità dell'oggetto SolidColorBrush utilizzato per disegnare il <xref:System.Windows.Controls.Control.Background%2A> è animata anziché l'opacità dell'intero pulsante. Quando si esegue l'esempio, il primo pulsante Dissolvenza completamente rimosso dalla visualizzazione, mentre si visualizza solo lo sfondo del secondo pulsante. Il testo e il bordo rimangono completamente opachi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Codice è stato omesso da questo esempio. L'esempio completo viene inoltre illustrato come animare l'opacità di un <xref:System.Windows.Media.Color> all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.  Per un esempio completo, vedere il [animare l'opacità di un elemento](http://go.microsoft.com/fwlink/?LinkID=159968).
