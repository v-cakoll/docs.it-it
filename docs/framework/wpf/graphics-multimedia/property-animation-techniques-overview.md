---
title: Cenni preliminari sulle tecniche di animazione delle proprietà
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: ebee350f69b5c5e4f9d38c452b9c87bf003528ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317909"
---
# <a name="property-animation-techniques-overview"></a>Cenni preliminari sulle tecniche di animazione delle proprietà
Questo argomento descrive i diversi metodi di animazione delle proprietà: storyboard, animazioni locali, orologi e animazioni per fotogramma.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni descritte nella sezione [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>Diversi modi per aggiungere un'animazione  
 Poiché esistono diversi scenari per le proprietà di animazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce numerosi approcci per aggiungere un'animazione a tali proprietà.  
  
 Per ciascun approccio, la tabella seguente indica se può essere usato per istanza, negli stili, nei modelli di controllo o nei modelli di dati. Se può essere usato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e se consente di controllare l'animazione in modo interattivo.  "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.  
  
|Tecnica di animazione|Scenari|Supporta XAML|Controllabile in modo interattivo|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Animazione storyboard|Per-instance, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Yes|Yes|  
|Animazione locale|Per istanza|No|No|  
|Animazione orologio|Per istanza|No|Yes|  
|Animazione per fotogramma|Per istanza|No|N/D|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>Animazioni storyboard  
 Usare un <xref:System.Windows.Media.Animation.Storyboard> quando si desidera definire e applicare le animazioni in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in modo interattivo per controllare le animazioni dopo l'avvio, creare un albero complesso di animazioni o aggiungere un'animazione in un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>. Per un oggetto da animare da un <xref:System.Windows.Media.Animation.Storyboard>, deve essere un <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement>, oppure deve essere utilizzato per impostare una <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Per altri dettagli, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo speciale di contenitore <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni di destinazione per le animazioni che contiene. Per aggiungere un'animazione con una <xref:System.Windows.Media.Animation.Storyboard>, completare i tre passaggi seguenti.  
  
1. Dichiarare un <xref:System.Windows.Media.Animation.Storyboard> e uno o più animazioni.  
  
2. Usare la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> collegati per specificare l'oggetto di destinazione e la proprietà di ogni animazione.  
  
3. (Solo codice) Definire un <xref:System.Windows.NameScope> per un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Registrare i nomi degli oggetti da animare con quella <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
4. Iniziare il <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Inizia un <xref:System.Windows.Media.Animation.Storyboard> applicare animazioni alle proprietà e le avvia. Esistono due modi per iniziare una <xref:System.Windows.Media.Animation.Storyboard>: è possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo fornito dalle <xref:System.Windows.Media.Animation.Storyboard> classe oppure è possibile usare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione. L'unico modo per aggiungere un'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nell'usare un <xref:System.Windows.Media.Animation.BeginStoryboard> azione. Oggetto <xref:System.Windows.Media.Animation.BeginStoryboard> azione può essere usata un' <xref:System.Windows.EventTrigger>, proprietà <xref:System.Windows.Trigger>, o un <xref:System.Windows.DataTrigger>.  
  
 La tabella seguente illustra le diverse posizioni in cui ogni <xref:System.Windows.Media.Animation.Storyboard> iniziare tecnica è supportata: per istanza, stile, modello di controllo e modello di dati.  
  
|Storyboard iniziato usando…|Per istanza|Stile|Modello di controllo|Modello di dati|Esempio|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e un oggetto <xref:System.Windows.EventTrigger>|Yes|Yes|Yes|Yes|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e una proprietà <xref:System.Windows.Trigger>|No|Yes|Yes|Yes|[Attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e un oggetto <xref:System.Windows.DataTrigger>|No|Yes|Yes|Yes|[Procedura: Attivare un'animazione alla modifica dei dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Yes|No|No|No|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Per altre informazioni sulle <xref:System.Windows.Media.Animation.Storyboard> oggetti, vedere la [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
## <a name="local-animations"></a>Animazioni locali  
 Le animazioni locali costituiscono un modo pratico per animare una proprietà di dipendenza di qualsiasi <xref:System.Windows.Media.Animation.Animatable> oggetto. Usare le animazioni locali per applicare una singola animazione a una proprietà, senza bisogno di controllare in modo interattivo l'animazione dopo l'avvio. A differenza di una <xref:System.Windows.Media.Animation.Storyboard> animazione, un'animazione locale può aggiungere un'animazione a un oggetto che non è associato un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.FrameworkContentElement>. Inoltre, non è necessario definire un <xref:System.Windows.NameScope> per questo tipo di animazione.  
  
 Le animazioni locali possono essere usate solo nel codice e non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati. Un'animazione locale non può essere controllata in modo interattivo dopo l'avvio.  
  
 Per aggiungere un'animazione usando un'animazione locale, completare i passaggi seguenti.  
  
1. Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> oggetto.  
  
2. Usare la <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationTimeline> alla proprietà specificato.  
  
 Nell'esempio seguente illustra come animare il colore di larghezza e lo sfondo di un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Animazioni orologio  
 Uso <xref:System.Windows.Media.MediaPlayer.Clock%2A> gli oggetti quando si desidera aggiungere un'animazione senza usare un <xref:System.Windows.Media.Animation.Storyboard> e si desidera creare alberi complessi di temporizzazione o controllare in modo interattivo le animazioni dopo l'avvio. È possibile usare gli oggetti Clock per animare una proprietà di dipendenza di qualsiasi <xref:System.Windows.Media.Animation.Animatable> oggetto.  
  
 Non è possibile usare <xref:System.Windows.Media.Animation.Clock> oggetti per aggiungere un'animazione negli stili, controllano direttamente i modelli o nei modelli di dati. (Il sistema di animazione e temporizzazione Usa effettivamente <xref:System.Windows.Media.Animation.Clock> gli oggetti per eseguire l'animazione negli stili, modelli di controllo e i modelli di dati, ma è necessario creare quelle <xref:System.Windows.Media.Animation.Clock> gli oggetti per l'utente da un <xref:System.Windows.Media.Animation.Storyboard>. Per altre informazioni sulla relazione tra <xref:System.Windows.Media.Animation.Storyboard> gli oggetti e <xref:System.Windows.Media.Animation.Clock> oggetti, vedere la [Cenni preliminari sul sistema di temporizzazione e animazione](animation-and-timing-system-overview.md).)  
  
 Per applicare un singolo <xref:System.Windows.Media.Animation.Clock> a una proprietà, la procedura seguente.  
  
1. Creare un <xref:System.Windows.Media.Animation.AnimationTimeline> oggetto.  
  
2. Usare la <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> metodo per il <xref:System.Windows.Media.Animation.AnimationTimeline> per creare un <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3. Usare la <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationClock> alla proprietà specificata.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Per creare un albero di temporizzazione e usarne le proprietà animate, completare i passaggi seguenti.  
  
1. Uso <xref:System.Windows.Media.Animation.ParallelTimeline> e <xref:System.Windows.Media.Animation.AnimationTimeline> oggetti per creare l'albero di temporizzazione.  
  
2. Usare la <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> dell'oggetto radice <xref:System.Windows.Media.Animation.ParallelTimeline> per creare un <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3. Eseguire l'iterazione attraverso il <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> del <xref:System.Windows.Media.Animation.ClockGroup> e applicare figlio <xref:System.Windows.Media.Animation.Clock> oggetti. Per ognuno <xref:System.Windows.Media.Animation.AnimationClock> figlio, utilizzare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> metodo dell'oggetto che si desidera aggiungere un'animazione per applicare il <xref:System.Windows.Media.Animation.AnimationClock> alla proprietà specificata  
  
 Per altre informazioni sugli oggetti Clock, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Animazione per fotogramma: Ignorare il sistema di temporizzazione e animazione  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove ciascun passaggio dell'animazione richiede che gli oggetti siano ricalcolati in base all'ultima serie di interazioni dell'oggetto.  
  
 Le animazioni per fotogramma non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati.  
  
 Per aggiungere un'animazione fotogramma per fotogramma, ci si registra per la <xref:System.Windows.Media.CompositionTarget.Rendering> evento dell'oggetto che contiene gli oggetti da animare. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti cui si desidera aggiungere un'animazione con tali valori.  
  
 Per ottenere l'ora di presentazione per il frame corrente, il <xref:System.EventArgs> associato a questo evento può essere convertito come <xref:System.Windows.Media.RenderingEventArgs>, che forniscono un <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> ora di rendering del proprietà che è possibile usare per ottenere il frame corrente.  
  
 Per altre informazioni, vedere il <xref:System.Windows.Media.CompositionTarget.Rendering> pagina.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Panoramica sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md)
