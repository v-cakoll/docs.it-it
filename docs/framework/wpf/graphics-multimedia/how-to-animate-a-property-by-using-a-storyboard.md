---
title: 'Procedura: animare una proprietà utilizzando uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 6cfce9a5b070a23ed9ac03473888bf572b61393b
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559638"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedura: animare una proprietà utilizzando uno storyboard
Questo esempio illustra come usare un <xref:System.Windows.Media.Animation.Storyboard> per aggiungere un'animazione alle proprietà. Per animare una proprietà utilizzando un <xref:System.Windows.Media.Animation.Storyboard>, creare un'animazione per ogni proprietà che si desidera animare e creare anche un <xref:System.Windows.Media.Animation.Storyboard> per contenere le animazioni.  
  
 Il tipo di proprietà determina il tipo di animazione da usare. Ad esempio, per aggiungere un'animazione a una proprietà che accetta valori di <xref:System.Double>, utilizzare una <xref:System.Windows.Media.Animation.DoubleAnimation>. Le proprietà associate <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> specificano l'oggetto e la proprietà a cui viene applicata l'animazione.  
  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilizzare un'azione <xref:System.Windows.Media.Animation.BeginStoryboard> e un <xref:System.Windows.EventTrigger>. Il <xref:System.Windows.EventTrigger> avvia l'azione <xref:System.Windows.Media.Animation.BeginStoryboard> quando si verifica l'evento specificato dalla relativa proprietà <xref:System.Windows.EventTrigger.RoutedEvent%2A>. L'azione <xref:System.Windows.Media.Animation.BeginStoryboard> avvia l'<xref:System.Windows.Media.Animation.Storyboard>.  
  
 Nell'esempio seguente vengono utilizzati oggetti <xref:System.Windows.Media.Animation.Storyboard> per animare due controlli <xref:System.Windows.Controls.Button>. Per modificare le dimensioni del primo pulsante, il <xref:System.Windows.FrameworkElement.Width%2A> viene animato. Per modificare il colore del secondo pulsante, viene utilizzata la proprietà <xref:System.Windows.Media.SolidColorBrush.Color%2A> della <xref:System.Windows.Media.SolidColorBrush> per impostare il <xref:System.Windows.Controls.Control.Background%2A> del pulsante animato.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Sebbene le animazioni possano essere destinate a un oggetto <xref:System.Windows.FrameworkElement>, ad esempio un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>e un oggetto <xref:System.Windows.Freezable>, ad esempio un <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, solo gli elementi del Framework hanno una proprietà di <xref:System.Windows.FrameworkElement.Name%2A>. Per assegnare un nome a un oggetto freezable in modo che possa essere la destinazione di un'animazione, usare [x:Name Directive](../../../desktop-wpf/xaml-services/xname-directive.md), come illustrato nell'esempio precedente.  
  
 Se si usa il codice, è necessario creare un <xref:System.Windows.NameScope> per una <xref:System.Windows.FrameworkElement> e registrare i nomi degli oggetti per aggiungere un'animazione a tale <xref:System.Windows.FrameworkElement>. Per avviare le animazioni nel codice, usare un'azione <xref:System.Windows.Media.Animation.BeginStoryboard> con una <xref:System.Windows.EventTrigger>. Facoltativamente, è possibile usare un gestore eventi e il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> di <xref:System.Windows.Media.Animation.Storyboard>. Nell'esempio seguente viene illustrato come utilizzare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Per altre informazioni sulle animazioni e storyboard, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Se si usa il codice, non si è limitati all'uso di <xref:System.Windows.Media.Animation.Storyboard> oggetti per aggiungere un'animazione alle proprietà. Per altre informazioni ed esempi, vedere [Animare una proprietà senza utilizzare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) e [Animare una proprietà utilizzando un oggetto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
