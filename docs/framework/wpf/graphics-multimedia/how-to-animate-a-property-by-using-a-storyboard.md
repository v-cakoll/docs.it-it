---
title: 'Procedura: animare una proprietà utilizzando uno storyboard'
description: Animare l'interfaccia utente con animazioni e storyboard per le proprietà in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f21b606751b845905a7bde6d3a7658b214369cc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853744"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedura: animare una proprietà utilizzando uno storyboard
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per aggiungere un'animazione alle proprietà. Per animare una proprietà usando un oggetto <xref:System.Windows.Media.Animation.Storyboard> , creare un'animazione per ogni proprietà che si desidera animare e creare anche un oggetto <xref:System.Windows.Media.Animation.Storyboard> per contenere le animazioni.  
  
 Il tipo di proprietà determina il tipo di animazione da usare. Ad esempio, per aggiungere un'animazione a una proprietà che accetta <xref:System.Double> valori, usare un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> . Le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà e associate specificano l'oggetto e la proprietà a cui viene applicata l'animazione.  
  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , utilizzare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione e un oggetto <xref:System.Windows.EventTrigger> . <xref:System.Windows.EventTrigger>Inizia l' <xref:System.Windows.Media.Animation.BeginStoryboard> azione quando si verifica l'evento specificato dalla relativa <xref:System.Windows.EventTrigger.RoutedEvent%2A> Proprietà. L' <xref:System.Windows.Media.Animation.BeginStoryboard> azione avvia <xref:System.Windows.Media.Animation.Storyboard> .  
  
 Nell'esempio seguente vengono usati <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per animare due <xref:System.Windows.Controls.Button> controlli. Per modificare le dimensioni del primo pulsante, il relativo oggetto <xref:System.Windows.FrameworkElement.Width%2A> viene animato. Per modificare il colore del secondo pulsante, la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di <xref:System.Windows.Media.SolidColorBrush> viene utilizzata per impostare l'oggetto <xref:System.Windows.Controls.Control.Background%2A> del pulsante animato.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Sebbene le animazioni possano essere destinate a un <xref:System.Windows.FrameworkElement> oggetto, ad esempio <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel> , e a un <xref:System.Windows.Freezable> oggetto, ad esempio <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform> , solo gli elementi del Framework hanno una <xref:System.Windows.FrameworkElement.Name%2A> Proprietà. Per assegnare un nome a un oggetto freezable in modo che possa essere la destinazione di un'animazione, usare [x:Name Directive](../../../desktop-wpf/xaml-services/xname-directive.md), come illustrato nell'esempio precedente.  
  
 Se si usa il codice, è necessario creare un oggetto <xref:System.Windows.NameScope> per un oggetto <xref:System.Windows.FrameworkElement> e registrare i nomi degli oggetti a cui aggiungere un'animazione <xref:System.Windows.FrameworkElement> . Per avviare le animazioni nel codice, usare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione con un oggetto <xref:System.Windows.EventTrigger> . Facoltativamente, è possibile usare un gestore eventi e il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo di <xref:System.Windows.Media.Animation.Storyboard> . Nell'esempio seguente viene illustrato come utilizzare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Per altre informazioni sulle animazioni e storyboard, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Se si usa il codice, non si è limitati all'uso di <xref:System.Windows.Media.Animation.Storyboard> oggetti per animare le proprietà. Per altre informazioni ed esempi, vedere [Animare una proprietà senza utilizzare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md) e [Animare una proprietà utilizzando un oggetto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
