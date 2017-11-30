---
title: "Procedura: animare una proprietà utilizzando uno storyboard"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2129ea06e8c92b3912d2abdd3d1a63e651ac59e1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedura: animare una proprietà utilizzando uno storyboard
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per animare le proprietà. Per aggiungere un'animazione a una proprietà tramite un <xref:System.Windows.Media.Animation.Storyboard>, creare un'animazione per ogni proprietà che si desidera animare e creare inoltre un <xref:System.Windows.Media.Animation.Storyboard> per contenere le animazioni.  
  
 Il tipo di proprietà determina il tipo di animazione da usare. Ad esempio, per aggiungere un'animazione a una proprietà che accetta <xref:System.Double> valori, utilizzare un <xref:System.Windows.Media.Animation.DoubleAnimation>. Il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> le proprietà associate specificano l'oggetto e proprietà a cui è applicata l'animazione.  
  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilizzare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione e un <xref:System.Windows.EventTrigger>. Il <xref:System.Windows.EventTrigger> inizia il <xref:System.Windows.Media.Animation.BeginStoryboard> azione quando l'evento che viene specificato dal relativo <xref:System.Windows.EventTrigger.RoutedEvent%2A> proprietà presente. Il <xref:System.Windows.Media.Animation.BeginStoryboard> azione avvia il <xref:System.Windows.Media.Animation.Storyboard>.  
  
 L'esempio seguente usa <xref:System.Windows.Media.Animation.Storyboard> oggetti da cui iniziare l'animazione due <xref:System.Windows.Controls.Button> controlli. Per modificare il primo pulsante dimensioni, il relativo <xref:System.Windows.FrameworkElement.Width%2A> viene animata. Per modificare il secondo pulsante colore, la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà del <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il <xref:System.Windows.Controls.Control.Background%2A> del pulsante che viene animato.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Sebbene le animazioni possono essere destinate a un <xref:System.Windows.FrameworkElement> dell'oggetto, ad esempio un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>e un <xref:System.Windows.Freezable> dell'oggetto, ad esempio un <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, solo gli elementi del framework sono un <xref:System.Windows.FrameworkElement.Name%2A> proprietà. Per assegnare un nome a un oggetto freezable in modo che possa essere la destinazione di un'animazione, usare [x:Name Directive](../../../../docs/framework/xaml-services/x-name-directive.md), come illustrato nell'esempio precedente.  
  
 Se si utilizza codice, è necessario creare un <xref:System.Windows.NameScope> per un <xref:System.Windows.FrameworkElement> e registrare i nomi degli oggetti da animare con <xref:System.Windows.FrameworkElement>. Per avviare le animazioni nel codice, utilizzare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione con un <xref:System.Windows.EventTrigger>. Facoltativamente, è possibile utilizzare un gestore eventi e <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo <xref:System.Windows.Media.Animation.Storyboard>. Nell'esempio seguente viene illustrato come utilizzare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Per altre informazioni sulle animazioni e storyboard, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Se si utilizza codice, non si è limitati all'uso di <xref:System.Windows.Media.Animation.Storyboard> oggetti per applicare l'animazione. Per altre informazioni ed esempi, vedere [Animare una proprietà senza utilizzare uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) e [Animare una proprietà utilizzando un oggetto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).
