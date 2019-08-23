---
title: "Procedura: Aggiungere un'animazione a una proprietà usando uno storyboard"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: a7a2656d84d37d3e2726df009a07ccf29661df07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963036"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedura: Aggiungere un'animazione a una proprietà usando uno storyboard
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per aggiungere un'animazione alle proprietà. Per animare una proprietà usando un oggetto <xref:System.Windows.Media.Animation.Storyboard>, creare un'animazione per ogni proprietà che si desidera animare e creare anche un oggetto <xref:System.Windows.Media.Animation.Storyboard> per contenere le animazioni.  
  
 Il tipo di proprietà determina il tipo di animazione da usare. Ad esempio, per aggiungere un'animazione a una proprietà <xref:System.Double> che accetta valori, <xref:System.Windows.Media.Animation.DoubleAnimation>usare un oggetto. Le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> e associate specificano l'oggetto e la proprietà a cui viene applicata l'animazione.  
  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilizzare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione e un <xref:System.Windows.EventTrigger>oggetto. Inizia l' <xref:System.Windows.Media.Animation.BeginStoryboard> azione quando si verifica l'evento specificato dalla relativa <xref:System.Windows.EventTrigger.RoutedEvent%2A> proprietà. <xref:System.Windows.EventTrigger> L' <xref:System.Windows.Media.Animation.BeginStoryboard> azione<xref:System.Windows.Media.Animation.Storyboard>avvia.  
  
 Nell'esempio seguente vengono <xref:System.Windows.Media.Animation.Storyboard> usati gli oggetti per animare due <xref:System.Windows.Controls.Button> controlli. Per modificare le dimensioni del primo pulsante, il relativo <xref:System.Windows.FrameworkElement.Width%2A> oggetto viene animato. Per modificare il colore del secondo pulsante, la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà <xref:System.Windows.Media.SolidColorBrush> di viene utilizzata per impostare l'oggetto <xref:System.Windows.Controls.Control.Background%2A> del pulsante animato.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Sebbene le animazioni possano <xref:System.Windows.FrameworkElement> essere destinate a un oggetto, ad esempio <xref:System.Windows.Controls.Control> o <xref:System.Windows.Media.Transform> <xref:System.Windows.Media.Brush> <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Freezable> e a un oggetto, ad esempio o, solo gli elementi <xref:System.Windows.FrameworkElement.Name%2A> del Framework hanno una proprietà. Per assegnare un nome a un oggetto freezable in modo che possa essere la destinazione di un'animazione, usare [x:Name Directive](../../xaml-services/x-name-directive.md), come illustrato nell'esempio precedente.  
  
 Se si usa il codice, è necessario creare <xref:System.Windows.NameScope> un oggetto <xref:System.Windows.FrameworkElement> per un oggetto e registrare i nomi degli oggetti a cui <xref:System.Windows.FrameworkElement>aggiungere un'animazione. Per avviare le animazioni nel codice, usare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione con un <xref:System.Windows.EventTrigger>oggetto. Facoltativamente, è possibile usare un gestore eventi e il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo di <xref:System.Windows.Media.Animation.Storyboard>. Nell'esempio seguente viene illustrato come utilizzare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Per altre informazioni sulle animazioni e storyboard, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Se si usa il codice, non si è limitati all' <xref:System.Windows.Media.Animation.Storyboard> uso di oggetti per animare le proprietà. Per altre informazioni ed esempi, vedere [Animare una proprietà senza utilizzare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) e [Animare una proprietà utilizzando un oggetto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
