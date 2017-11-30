---
title: "Cenni preliminari sulle tecniche di animazione delle proprietà"
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
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a8c196ea15617b13abe8311f8501ab32fd320c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-animation-techniques-overview"></a>Cenni preliminari sulle tecniche di animazione delle proprietà
Questo argomento descrive i diversi metodi di animazione delle proprietà: storyboard, animazioni locali, orologi e animazioni per fotogramma.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni descritte nella sezione [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>Diversi modi per aggiungere un'animazione  
 Poiché esistono diversi scenari per le proprietà di animazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce numerosi approcci per aggiungere un'animazione a tali proprietà.  
  
 Per ciascun approccio, la tabella seguente indica se può essere usato per istanza, negli stili, nei modelli di controllo o nei modelli di dati. Se può essere usato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e se consente di controllare l'animazione in modo interattivo.  "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.  
  
|Tecnica di animazione|Scenari|Supporta XAML|Controllabile in modo interattivo|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Animazione storyboard|Per ogni istanza <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>,<xref:System.Windows.DataTemplate>|Sì|Sì|  
|Animazione locale|Per istanza|No|No|  
|Animazione orologio|Per istanza|No|Sì|  
|Animazione per fotogramma|Per istanza|No|N/D|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>Animazioni storyboard  
 Utilizzare un <xref:System.Windows.Media.Animation.Storyboard> quando si desidera definire e applicare le animazioni in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in modo interattivo per controllare le animazioni dopo l'avvio, creare una struttura ad albero complesso di animazioni o applicare un'animazione a un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>. Per un oggetto sia animato da un <xref:System.Windows.Media.Animation.Storyboard>, deve essere un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, oppure deve essere utilizzato per impostare un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Per altri dettagli, vedere [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo speciale di contenitore <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni per le animazioni che contiene. Per aggiungere un'animazione con un <xref:System.Windows.Media.Animation.Storyboard>, aver completato i tre passaggi seguenti.  
  
1.  Dichiarare un <xref:System.Windows.Media.Animation.Storyboard> e le animazioni di uno o più.  
  
2.  Utilizzare il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> allegati le proprietà per specificare l'oggetto di destinazione e la proprietà di ogni animazione.  
  
3.  (Solo codice) Definire un <xref:System.Windows.NameScope> per un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Registrare i nomi degli oggetti da animare con <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
4.  Iniziare il <xref:System.Windows.Media.Animation.Storyboard>.  
  
 A partire da un <xref:System.Windows.Media.Animation.Storyboard> applica le animazioni a proprietà animate e avvio. Esistono due modi per iniziare un <xref:System.Windows.Media.Animation.Storyboard>: è possibile utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> fornito dal metodo di <xref:System.Windows.Media.Animation.Storyboard> classe oppure è possibile utilizzare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione. L'unico modo per aggiungere un'animazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nell'usare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione. Oggetto <xref:System.Windows.Media.Animation.BeginStoryboard> azione può essere utilizzata un <xref:System.Windows.EventTrigger>, proprietà <xref:System.Windows.Trigger>, o un <xref:System.Windows.DataTrigger>.  
  
 La tabella seguente illustra le diverse posizioni in cui ogni <xref:System.Windows.Media.Animation.Storyboard> iniziare tecnica è supportata: per ogni istanza, stile, modello di controllo e il modello di dati.  
  
|Storyboard iniziato usando…|Per istanza|Stile|Modello di controllo|Modello di dati|Esempio|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un oggetto<xref:System.Windows.EventTrigger>|Sì|Sì|Sì|Sì|[Animare una proprietà utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e una proprietà<xref:System.Windows.Trigger>|No|Sì|Sì|Sì|[Attivare un'animazione quando il valore di una proprietà viene modificato](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.DataTrigger>|No|Sì|Sì|Sì|[Procedura: Attivare un'animazione quando i dati vengono modificati](http://msdn.microsoft.com/en-us/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sì|No|No|No|[Animare una proprietà utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.Animation.Storyboard> degli oggetti, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## <a name="local-animations"></a>Animazioni locali  
 Le animazioni locali costituiscono un modo pratico per aggiungere un'animazione a una proprietà di dipendenza di qualsiasi <xref:System.Windows.Media.Animation.Animatable> oggetto. Usare le animazioni locali per applicare una singola animazione a una proprietà, senza bisogno di controllare in modo interattivo l'animazione dopo l'avvio. A differenza di un <xref:System.Windows.Media.Animation.Storyboard> animazione, un'animazione locale può animare un oggetto che non è associato a un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Inoltre, non è necessario definire un <xref:System.Windows.NameScope> per questo tipo di animazione.  
  
 Le animazioni locali possono essere usate solo nel codice e non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati. Un'animazione locale non può essere controllata in modo interattivo dopo l'avvio.  
  
 Per aggiungere un'animazione usando un'animazione locale, completare i passaggi seguenti.  
  
1.  Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> oggetto.  
  
2.  Utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationTimeline> alla proprietà specificati.  
  
 Nell'esempio seguente viene illustrato come animare il colore di sfondo e di larghezza di un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Animazioni orologio  
 Utilizzare <xref:System.Windows.Media.MediaPlayer.Clock%2A> oggetti quando si desidera aggiungere un'animazione senza utilizzare un <xref:System.Windows.Media.Animation.Storyboard> e si desidera creare strutture ad albero di temporizzazione complessi o controllare in modo interattivo le animazioni dopo l'avvio. È possibile utilizzare gli oggetti Clock per aggiungere un'animazione a una proprietà di dipendenza di qualsiasi <xref:System.Windows.Media.Animation.Animatable> oggetto.  
  
 Non è possibile utilizzare <xref:System.Windows.Media.Animation.Clock> oggetti controllano direttamente l'animare negli stili, modelli o i modelli di dati. (Il sistema di animazione e temporizzazione utilizza effettivamente <xref:System.Windows.Media.Animation.Clock> oggetti da animare gli stili, modelli di controllo e i modelli di dati, ma è necessario creare quelli <xref:System.Windows.Media.Animation.Clock> oggetti per l'utente da un <xref:System.Windows.Media.Animation.Storyboard>. Per ulteriori informazioni sulla relazione tra <xref:System.Windows.Media.Animation.Storyboard> oggetti e <xref:System.Windows.Media.Animation.Clock> degli oggetti, vedere il [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).)  
  
 Per applicare un singolo <xref:System.Windows.Media.Animation.Clock> a una proprietà, la procedura seguente.  
  
1.  Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> oggetto.  
  
2.  Utilizzare il <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> metodo il <xref:System.Windows.Media.Animation.AnimationTimeline> per creare un <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Utilizzare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationClock> per la proprietà specificata.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Per creare un albero di temporizzazione e usarne le proprietà animate, completare i passaggi seguenti.  
  
1.  Utilizzare <xref:System.Windows.Media.Animation.ParallelTimeline> e <xref:System.Windows.Media.Animation.AnimationTimeline> gli oggetti per creare la struttura ad albero di temporizzazione.  
  
2.  Utilizzare il <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> della radice <xref:System.Windows.Media.Animation.ParallelTimeline> per creare un <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Scorrere il <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> del <xref:System.Windows.Media.Animation.ClockGroup> e applicare figlio <xref:System.Windows.Media.Animation.Clock> oggetti. Per ogni <xref:System.Windows.Media.Animation.AnimationClock> figlio, utilizzare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationClock> per la proprietà specificata  
  
 Per altre informazioni sugli oggetti Clock, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Animazione per fotogramma: ignorare il sistema di animazione e di temporizzazione  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove ciascun passaggio dell'animazione richiede che gli oggetti siano ricalcolati in base all'ultima serie di interazioni dell'oggetto.  
  
 Le animazioni per fotogramma non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati.  
  
 Per aggiungere un'animazione frame singolarmente, si registra per il <xref:System.Windows.Media.CompositionTarget.Rendering> evento dell'oggetto che contiene gli oggetti a cui si desidera aggiungere un'animazione. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti cui si desidera aggiungere un'animazione con tali valori.  
  
 Per ottenere l'ora di presentazione per il frame corrente, il <xref:System.EventArgs> associato a questo evento può essere eseguito il cast come <xref:System.Windows.Media.RenderingEventArgs>, che forniscono un <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> i tempi di rendering della proprietà che è possibile utilizzare per ottenere il frame corrente.  
  
 Per ulteriori informazioni, vedere il <xref:System.Windows.Media.CompositionTarget.Rendering> pagina.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Cenni preliminari sull'animazione e sul sistema di temporizzazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
