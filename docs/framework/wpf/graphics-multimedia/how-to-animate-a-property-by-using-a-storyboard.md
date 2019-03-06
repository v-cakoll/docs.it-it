---
title: 'Procedura: Animare una proprietà utilizzando uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f6064368b4f5e4fa8324b4039d734d4430cd9174
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364710"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedura: Animare una proprietà utilizzando uno storyboard
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per animare le proprietà. Animare una proprietà usando un <xref:System.Windows.Media.Animation.Storyboard>, creare un'animazione per ogni proprietà che si desidera animare e creare inoltre un <xref:System.Windows.Media.Animation.Storyboard> per contenere le animazioni.  
  
 Il tipo di proprietà determina il tipo di animazione da usare. Ad esempio, per animare una proprietà che accetta <xref:System.Double> valori, usare un <xref:System.Windows.Media.Animation.DoubleAnimation>. Il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> specificano l'oggetto e proprietà a cui viene applicata l'animazione.  
  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], usare una <xref:System.Windows.Media.Animation.BeginStoryboard> azione e un <xref:System.Windows.EventTrigger>. Il <xref:System.Windows.EventTrigger> inizia il <xref:System.Windows.Media.Animation.BeginStoryboard> azione quando l'evento che viene specificato dal relativo <xref:System.Windows.EventTrigger.RoutedEvent%2A> proprietà si trova. Il <xref:System.Windows.Media.Animation.BeginStoryboard> azione avvia il <xref:System.Windows.Media.Animation.Storyboard>.  
  
 L'esempio seguente usa <xref:System.Windows.Media.Animation.Storyboard> oggetti da animare due <xref:System.Windows.Controls.Button> controlli. Effettuare il primo pulsante di modifica, le dimensioni relative <xref:System.Windows.FrameworkElement.Width%2A> viene animata. Per modificare il secondo pulsante colore, il <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà del <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il <xref:System.Windows.Controls.Control.Background%2A> del pulsante che viene animato.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Anche se le animazioni possono essere destinate a un <xref:System.Windows.FrameworkElement> dell'oggetto, ad esempio un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>e un <xref:System.Windows.Freezable> dell'oggetto, ad esempio un <xref:System.Windows.Media.Brush> oppure <xref:System.Windows.Media.Transform>, solo gli elementi framework hanno un <xref:System.Windows.FrameworkElement.Name%2A> proprietà. Per assegnare un nome a un oggetto freezable in modo che possa essere la destinazione di un'animazione, usare [x:Name Directive](../../xaml-services/x-name-directive.md), come illustrato nell'esempio precedente.  
  
 Se si usa codice, è necessario creare un <xref:System.Windows.NameScope> per un <xref:System.Windows.FrameworkElement> e registrare i nomi degli oggetti da animare con <xref:System.Windows.FrameworkElement>. Per avviare le animazioni nel codice, usare una <xref:System.Windows.Media.Animation.BeginStoryboard> azione con un <xref:System.Windows.EventTrigger>. Facoltativamente, è possibile usare un gestore dell'evento e il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo <xref:System.Windows.Media.Animation.Storyboard>. Nell'esempio seguente viene illustrato come utilizzare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Per altre informazioni sulle animazioni e storyboard, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Se si usa codice, non si è limitati all'uso di <xref:System.Windows.Media.Animation.Storyboard> oggetti per animare le proprietà. Per altre informazioni ed esempi, vedere [Animare una proprietà senza utilizzare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) e [Animare una proprietà utilizzando un oggetto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
