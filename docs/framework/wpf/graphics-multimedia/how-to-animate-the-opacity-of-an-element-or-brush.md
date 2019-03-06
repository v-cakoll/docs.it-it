---
title: "Procedura: Animare l'opacità di un elemento o un pennello"
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: f07138a0b68fff050133d477074571c60cd8651e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363371"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Procedura: Animare l'opacità di un elemento o un pennello
Per rendere un elemento del framework di dissolvenza in entrata dalla visualizzazione, è possibile aggiungere un'animazione relativa <xref:System.Windows.UIElement.Opacity%2A> proprietà oppure è possibile aggiungere un'animazione la <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Brush> (o i pennelli) utilizzato per disegnare lo. Animazione dell'opacità dell'elemento rende e i relativi elementi figlio dissolvenza dalla visualizzazione, ma l'animazione il pennello utilizzato per disegnare l'elemento consente di essere più selettivo le dissolvenze quale parte dell'elemento. Ad esempio, è possibile animare l'opacità di un pennello utilizzato per disegnare lo sfondo del pulsante. Questa condizione comportava lo sfondo del pulsante applicare una dissolvenza in entrata e in uscita della visualizzazione, lasciando il relativo testo completamente opaco.  
  
> [!NOTE]
>  Animazione di <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.Brush> offre vantaggi nelle prestazioni rispetto all'animazione il <xref:System.Windows.UIElement.Opacity%2A> proprietà di un elemento.  
  
 Nell'esempio seguente, due pulsanti vengono animati, in modo che essi dissolvenza dalla visualizzazione. L'opacità del primo <xref:System.Windows.Controls.Button> viene animata da `1.0` al `0.0` tramite un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi. Anche il secondo pulsante è animato, ma l'opacità dell'oggetto SolidColorBrush utilizzato per disegnare il <xref:System.Windows.Controls.Control.Background%2A> viene animato piuttosto che l'opacità del pulsante di intero. Quando si esegue l'esempio, il primo pulsante si dissolve completamente dalla visualizzazione, mentre solo lo sfondo del secondo pulsante viene applicata la dissolvenza dalla visualizzazione. Il testo e il bordo rimangono completamente opachi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Codice è stato omesso da questo esempio. L'esempio completo viene inoltre illustrato come animare l'opacità di un <xref:System.Windows.Media.Color> all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.  Per un esempio completo, vedere la [animare l'opacità di un elemento](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
