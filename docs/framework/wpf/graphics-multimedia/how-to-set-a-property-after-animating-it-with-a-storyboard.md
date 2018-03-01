---
title: "Procedura: impostare una proprietà dopo averla animata con uno storyboard"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ffc534549f5b114a07f09326be72c1968d178a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Procedura: impostare una proprietà dopo averla animata con uno storyboard
In alcuni casi, potrebbe sembrare che non è possibile modificare il valore di una proprietà dopo che è stato animato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un <xref:System.Windows.Media.Animation.Storyboard> viene utilizzato per animare il colore di un <xref:System.Windows.Media.SolidColorBrush>. Quando si fa clic sul pulsante, viene attivato lo storyboard. Il <xref:System.Windows.Media.Animation.Timeline.Completed> evento viene gestito in modo che il programma riceve una notifica quando il <xref:System.Windows.Media.Animation.ColorAnimation> viene completata.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Esempio  
 Dopo il <xref:System.Windows.Media.Animation.ColorAnimation> viene completato, il programma tenta di modificare il colore del pennello in blu.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Il codice precedente non sembra eseguire alcuna azione: il pennello rimane giallo, che corrisponde al valore fornito per il <xref:System.Windows.Media.Animation.ColorAnimation> che animato il pennello. Il valore della proprietà sottostante (il valore di base) viene effettivamente modificato in blu. Tuttavia, il valore effettivo o corrente rimane giallo perché il <xref:System.Windows.Media.Animation.ColorAnimation> sta ancora eseguendo l'override del valore di base. Se si desidera il valore di base per diventare di nuovo il valore effettivo, è necessario interrompere l'animazione dall'influenzare la proprietà. Esistono tre modi per eseguire questa operazione con le animazioni storyboard:  
  
-   Impostare l'animazione <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà<xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   Rimuovere l'intero Storyboard.  
  
-   Rimuovere l'animazione della proprietà singole.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Impostare la proprietà dell'animazione FillBehavior Stop  
 Impostando <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> a <xref:System.Windows.Media.Animation.FillBehavior.Stop>, si indica all'animazione di interrompere l'effetto sulla proprietà di destinazione dopo aver raggiunto la fine del periodo attivo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Rimuovere l'intero storyboard  
 Utilizzando un <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger o <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> (metodo), si indicano le animazioni storyboard di interrompere l'effetto sulle proprietà di destinazione. La differenza tra questo approccio e l'impostazione di <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> è di proprietà che è possibile rimuovere lo storyboard in qualsiasi momento, mentre il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà ha effetto solo quando l'animazione raggiunge la fine del periodo attivo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Rimuovere un'animazione a una singola proprietà  
 Un'altra tecnica per arrestare un effetto di animazione su una proprietà consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo dell'oggetto viene aggiunta un'animazione. Specificare la proprietà viene aggiunta un'animazione come primo parametro e `null` come il secondo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Questa tecnica funziona anche per le animazioni non storyboard.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
