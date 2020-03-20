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
ms.openlocfilehash: 0b4bf6d4963f32ad83f762fce73c805197ff9c9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181848"
---
# <a name="property-animation-techniques-overview"></a>Cenni preliminari sulle tecniche di animazione delle proprietà
Questo argomento descrive i diversi metodi di animazione delle proprietà: storyboard, animazioni locali, orologi e animazioni per fotogramma.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è necessario conoscere le funzionalità di base delle animazioni descritte nella sezione [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="summary"></a>
## <a name="different-ways-to-animate"></a>Diversi modi per aggiungere un'animazione  
 Poiché esistono diversi scenari per le proprietà di animazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce numerosi approcci per aggiungere un'animazione a tali proprietà.  
  
 Per ciascun approccio, la tabella seguente indica se può essere usato per istanza, negli stili, nei modelli di controllo o nei modelli di dati. Se può essere usato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e se consente di controllare l'animazione in modo interattivo.  "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.  
  
|Tecnica di animazione|Scenari|Supporta XAML|Controllabile in modo interattivo|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Animazione storyboard|Per istanza, <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate>, ,<xref:System.Windows.DataTemplate>|Sì|Sì|  
|Animazione locale|Per istanza|No|No|  
|Animazione orologio|Per istanza|No|Sì|  
|Animazione per fotogramma|Per istanza|No|N/D|  
  
<a name="storyboard_animations"></a>
## <a name="storyboard-animations"></a>Animazioni storyboard  
 Utilizzare <xref:System.Windows.Media.Animation.Storyboard> un quando si desidera definire [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e applicare le animazioni in , controllare in modo interattivo <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate> le <xref:System.Windows.DataTemplate>animazioni dopo l'avvio, creare una struttura ad albero complessa di animazioni o animare in un oggetto , o . Affinché un oggetto venga <xref:System.Windows.Media.Animation.Storyboard>animato da <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>un oggetto , deve essere <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>un oggetto o , oppure deve essere utilizzato per impostare un oggetto o . Per altri dettagli, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 Un <xref:System.Windows.Media.Animation.Storyboard> è un tipo <xref:System.Windows.Media.Animation.Timeline> speciale di contenitore che fornisce informazioni di destinazione per le animazioni in esso contenute. Per aggiungere <xref:System.Windows.Media.Animation.Storyboard>un'animazione con un oggetto , è necessario completare i tre passaggi seguenti.  
  
1. Dichiarare <xref:System.Windows.Media.Animation.Storyboard> una e una o più animazioni.  
  
2. Utilizzare <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> le <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà e associate per specificare l'oggetto di destinazione e la proprietà di ogni animazione.  
  
3. (Solo codice) Definire <xref:System.Windows.NameScope> un <xref:System.Windows.FrameworkElement> oggetto <xref:System.Windows.FrameworkContentElement>per un oggetto o . Registrare i nomi degli oggetti <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>da animare con tale o .  
  
4. Iniziare <xref:System.Windows.Media.Animation.Storyboard>il file .  
  
 L'inizio di un <xref:System.Windows.Media.Animation.Storyboard> applica le animazioni alle proprietà che animano e le avvia. Esistono due modi per <xref:System.Windows.Media.Animation.Storyboard>iniziare un <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> : è <xref:System.Windows.Media.Animation.Storyboard> possibile utilizzare il metodo <xref:System.Windows.Media.Animation.BeginStoryboard> fornito dalla classe oppure è possibile utilizzare un'azione. L'unico modo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per animare <xref:System.Windows.Media.Animation.BeginStoryboard> in consiste nell'utilizzare un'azione. <xref:System.Windows.Media.Animation.BeginStoryboard> Un'azione può essere <xref:System.Windows.EventTrigger>utilizzata <xref:System.Windows.Trigger>in <xref:System.Windows.DataTrigger>un oggetto , property o .  
  
 Nella tabella seguente vengono illustrate <xref:System.Windows.Media.Animation.Storyboard> le diverse posizioni in cui è supportata ogni tecnica di inizio: per istanza, stile, modello di controllo e modello di dati.  
  
|Storyboard iniziato usando…|Per istanza|Style|Modello di controllo|Modello di dati|Esempio|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.EventTrigger>|Sì|Sì|Sì|Sì|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e una proprietà<xref:System.Windows.Trigger>|No|Sì|Sì|Sì|[Attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.DataTrigger>|No|Sì|Sì|Sì|[Procedura: Attivare un'animazione quando i dati vengono modificati](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sì|No|No|No|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Per ulteriori <xref:System.Windows.Media.Animation.Storyboard> informazioni sugli oggetti, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
## <a name="local-animations"></a>Animazioni locali  
 Le animazioni locali forniscono un modo <xref:System.Windows.Media.Animation.Animatable> pratico per animare una proprietà di dipendenza di qualsiasi oggetto. Usare le animazioni locali per applicare una singola animazione a una proprietà, senza bisogno di controllare in modo interattivo l'animazione dopo l'avvio. A <xref:System.Windows.Media.Animation.Storyboard> differenza di un'animazione, un'animazione locale <xref:System.Windows.FrameworkElement> può <xref:System.Windows.FrameworkContentElement>animare un oggetto non associato a un oggetto o un oggetto . Inoltre, non è necessario <xref:System.Windows.NameScope> definire un per questo tipo di animazione.  
  
 Le animazioni locali possono essere usate solo nel codice e non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati. Un'animazione locale non può essere controllata in modo interattivo dopo l'avvio.  
  
 Per aggiungere un'animazione usando un'animazione locale, completare i passaggi seguenti.  
  
1. Creare <xref:System.Windows.Media.Animation.AnimationTimeline> un oggetto.  
  
2. Utilizzare <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> il metodo dell'oggetto che si <xref:System.Windows.Media.Animation.AnimationTimeline> desidera animare per applicare l'oggetto alla proprietà specificata.  
  
 Nell'esempio seguente viene illustrato come animare <xref:System.Windows.Controls.Button>la larghezza e il colore di sfondo di un oggetto .  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Animazioni orologio  
 Utilizzare <xref:System.Windows.Media.MediaPlayer.Clock%2A> gli oggetti quando si <xref:System.Windows.Media.Animation.Storyboard> desidera aggiungere un'animazione senza utilizzare un oggetto e creare alberi di temporizzazione complessi o controllare in modo interattivo le animazioni dopo l'avvio. È possibile usare Clock oggetti per animare una proprietà di dipendenza di qualsiasi <xref:System.Windows.Media.Animation.Animatable> oggetto.  
  
 Non è <xref:System.Windows.Media.Animation.Clock> possibile utilizzare gli oggetti direttamente per animare negli stili, nei modelli di controllo o nei modelli di dati. Il sistema di animazione <xref:System.Windows.Media.Animation.Clock> e temporizzazione utilizza effettivamente oggetti per aggiungere un'animazione negli stili, nei modelli di controllo e nei modelli di dati, ma deve creare tali <xref:System.Windows.Media.Animation.Clock> oggetti automaticamente da un <xref:System.Windows.Media.Animation.Storyboard>oggetto . Per ulteriori informazioni sulla <xref:System.Windows.Media.Animation.Storyboard> relazione <xref:System.Windows.Media.Animation.Clock> tra oggetti e oggetti, vedere Cenni preliminari sul [sistema di animazione e di temporizzazione.](animation-and-timing-system-overview.md)  
  
 Per applicare <xref:System.Windows.Media.Animation.Clock> un singolo a una proprietà, completare i passaggi seguenti.  
  
1. Creare <xref:System.Windows.Media.Animation.AnimationTimeline> un oggetto.  
  
2. Utilizzare <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> il metodo <xref:System.Windows.Media.Animation.AnimationTimeline> di <xref:System.Windows.Media.Animation.AnimationClock>per creare un file .  
  
3. Utilizzare <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> il metodo dell'oggetto che si <xref:System.Windows.Media.Animation.AnimationClock> desidera animare per applicare l'oggetto alla proprietà specificata.  
  
 Nell'esempio seguente viene <xref:System.Windows.Media.Animation.AnimationClock> illustrato come creare un e applicarlo a due proprietà simili.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Per creare un albero di temporizzazione e usarne le proprietà animate, completare i passaggi seguenti.  
  
1. Utilizzare <xref:System.Windows.Media.Animation.ParallelTimeline> <xref:System.Windows.Media.Animation.AnimationTimeline> e oggetti per creare l'albero di temporizzazione.  
  
2. Utilizzare <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> la radice <xref:System.Windows.Media.Animation.ParallelTimeline> per <xref:System.Windows.Media.Animation.ClockGroup>creare un file .  
  
3. Scorrere <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> l'oggetto <xref:System.Windows.Media.Animation.ClockGroup> dell'oggetto <xref:System.Windows.Media.Animation.Clock> e applicarne gli oggetti figlio. Per <xref:System.Windows.Media.Animation.AnimationClock> ogni elemento <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> figlio, utilizzare il metodo dell'oggetto <xref:System.Windows.Media.Animation.AnimationClock> che si desidera animare per applicare l'oggetto alla proprietà specificata  
  
 Per altre informazioni sugli oggetti Clock, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Animazione per fotogramma: ignorare il sistema di animazione e di temporizzazione  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove ciascun passaggio dell'animazione richiede che gli oggetti siano ricalcolati in base all'ultima serie di interazioni dell'oggetto.  
  
 Le animazioni per fotogramma non possono essere definite negli stili, nei modelli di controllo o nei modelli di dati.  
  
 Per animare fotogramma per fotogramma, registrate per l'evento <xref:System.Windows.Media.CompositionTarget.Rendering> dell'oggetto che contiene gli oggetti da animare. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti cui si desidera aggiungere un'animazione con tali valori.  
  
 Per ottenere il tempo di presentazione <xref:System.EventArgs> per il fotogramma <xref:System.Windows.Media.RenderingEventArgs>corrente, è <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> possibile eseguire il cast dell'oggetto associato a questo evento come , che forniscono una proprietà che è possibile utilizzare per ottenere il tempo di rendering del fotogramma corrente.  
  
 Per ulteriori informazioni, <xref:System.Windows.Media.CompositionTarget.Rendering> vedere la pagina.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md)
