---
title: Cenni preliminari sull'animazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: f0f55c948d10c61ebab57f47e3461531ccf5f610
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559716"
---
# <a name="animation-overview"></a>Cenni preliminari sull'animazione

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un potente set di funzionalità di grafica e layout che consentono di creare interfacce utente attraenti e documenti accattivanti. L'animazione può migliorare ulteriormente l'aspetto e la facilità di uso dell'interfaccia utente. Semplicemente animando un colore di sfondo o applicando un <xref:System.Windows.Media.Transform>animato, è possibile creare transizioni di schermo drammatiche o fornire segnali visivi utili.

Questa panoramica offre un'introduzione al sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazione e temporizzazione. Si concentra sull'animazione di oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usando gli storyboard.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Introduzione alle animazioni

L'animazione è un'illusione ottica creata scorrendo rapidamente una serie di immagini, ognuna leggermente diversa dall'ultima. Il cervello percepisce il gruppo di immagini come un'unica scena che si modifica. Nei film questa illusione viene creata usando fotocamere che registrano molte fotografie (fotogrammi) al secondo. Quando i fotogrammi vengono riprodotti con un proiettore, il pubblico vede un'immagine in movimento.

L'animazione in un computer è simile. Un programma che applica una dissolvenza in uscita al disegno di un rettangolo funziona ad esempio nel modo indicato di seguito.

- Il programma crea un timer.

- Il programma controlla il timer a intervalli stabiliti per rilevare la quantità di tempo trascorso.

- Ogni volta che il programma controlla il timer, calcola anche il valore di opacità per il rettangolo in base al tempo trascorso.

- Il programma aggiorna quindi il rettangolo in base al nuovo valore e lo ridisegna.

Prima di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], gli sviluppatori Microsoft Windows dovevano creare e gestire i propri sistemi di temporizzazione o utilizzare librerie personalizzate speciali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include un sistema di temporizzazione efficiente esposto tramite codice gestito e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e integrato in modo approfondito in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework. Le funzionalità disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplificano l'applicazione di animazioni ai controlli e ad altri oggetti grafici.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue in modo efficiente tutte le attività automatiche di gestione del sistema di temporizzazione e di aggiornamento dello schermo grazie a classi di temporizzazione che consentono di concentrarsi sugli effetti da creare anziché sulle operazioni per ottenerli. Esponendo le classi di base di animazione da cui le classi dell'utente possono ereditare, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplifica anche la creazione di animazioni personalizzate che sfruttano molti vantaggi in termini di prestazioni delle classi di animazione standard.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Sistema di animazione delle proprietà WPF

Se si conoscono alcuni concetti importanti sul sistema di temporizzazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazioni possono essere più facili da usare. L'aspetto più importante è che, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si animano gli oggetti applicando animazioni alle rispettive proprietà. Ad esempio, per aumentare le dimensioni di un elemento del Framework, si animano le relative <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà. Per rendere una dissolvenza dell'oggetto dalla visualizzazione, è necessario animare la relativa proprietà <xref:System.Windows.UIElement.Opacity%2A>.

Affinché una proprietà disponga di funzionalità di animazione, devono essere soddisfatti i tre requisiti seguenti:

- Deve essere una proprietà di dipendenza.

- Deve appartenere a una classe che eredita da <xref:System.Windows.DependencyObject> e implementa l'interfaccia <xref:System.Windows.Media.Animation.IAnimatable>.

- Deve essere disponibile un tipo di animazione compatibile. Se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non è disponibile, è possibile crearne uno personalizzato. Vedere [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md).

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene molti oggetti con proprietà <xref:System.Windows.Media.Animation.IAnimatable>. I controlli, ad esempio <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.TabControl>e gli oggetti di <xref:System.Windows.Controls.Panel> e <xref:System.Windows.Shapes.Shape> ereditano da <xref:System.Windows.DependencyObject>. La maggior parte delle proprietà di tali oggetti è rappresentata da proprietà di dipendenza.

È possibile usare le animazioni quasi ovunque, ad esempio in stili e modelli del controllo. Le animazioni non devono necessariamente essere oggetti visivi ed è possibile animare oggetti che non appartengono all'interfaccia utente se soddisfano i criteri descritti in questa sezione.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Esempio - Applicare a un elemento una dissolvenza in entrata e in uscita

Questo esempio illustra come usare un'animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per animare il valore di una proprietà di dipendenza. Usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, ovvero un tipo di animazione che genera valori <xref:System.Double>, per animare la proprietà <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Shapes.Rectangle>. Di conseguenza, il <xref:System.Windows.Shapes.Rectangle> si dissolve in visualizzazione.

Nella prima parte dell'esempio viene creato un elemento <xref:System.Windows.Shapes.Rectangle>. I passaggi seguenti illustrano come creare un'animazione e applicarla alla proprietà <xref:System.Windows.UIElement.Opacity%2A> del rettangolo.

Di seguito viene illustrato come creare un elemento <xref:System.Windows.Shapes.Rectangle> in un <xref:System.Windows.Controls.StackPanel> in XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Nell'esempio seguente viene illustrato come creare un elemento <xref:System.Windows.Shapes.Rectangle> in una <xref:System.Windows.Controls.StackPanel> nel codice.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Parte 1 - Creare un oggetto DoubleAnimation

Un modo per rendere una dissolvenza dell'elemento in entrata e in uscita è l'animazione della relativa proprietà <xref:System.Windows.UIElement.Opacity%2A>. Poiché la proprietà <xref:System.Windows.UIElement.Opacity%2A> è di tipo <xref:System.Double>, è necessaria un'animazione che produce valori Double. Una <xref:System.Windows.Media.Animation.DoubleAnimation> è un'animazione di questo tipo. Una <xref:System.Windows.Media.Animation.DoubleAnimation> crea una transizione tra due valori Double. Per specificare il valore iniziale, impostare la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>. Per specificare il valore finale, impostare la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.

1. Un valore di opacità di `1.0` rende completamente opaco l'oggetto e un valore di opacità di `0.0` lo rende completamente invisibile. Per eseguire la transizione dell'animazione da `1.0` a `0.0` impostare la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> su `1.0` e la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> su `0.0`. Di seguito viene illustrato come creare un <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Di seguito viene illustrato come creare un <xref:System.Windows.Media.Animation.DoubleAnimation> nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Successivamente, è necessario specificare un <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di un'animazione specifica il tempo necessario per passare dal valore iniziale al valore di destinazione. Di seguito viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su cinque secondi in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Di seguito viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su cinque secondi nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Nel codice precedente è stata mostrata un'animazione che esegue la transizione da `1.0` a `0.0`, che determina la dissolvenza dell'elemento di destinazione da completamente opaco a completamente invisibile. Per fare in modo che l'elemento venga nuovamente visualizzato dopo la scomparsa, impostare la proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> dell'animazione su `true`. Per fare in modo che l'animazione venga ripetuta per un periodo illimitato, impostare la relativa proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Di seguito viene illustrato come impostare le proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Di seguito viene illustrato come impostare le proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Parte 2 - Creare uno storyboard

Per applicare un'animazione a un oggetto, è necessario creare un <xref:System.Windows.Media.Animation.Storyboard> e utilizzare le proprietà <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> associate per specificare l'oggetto e la proprietà a cui aggiungere un'animazione.

1. Creare il <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio. Di seguito viene illustrato come creare il <xref:System.Windows.Media.Animation.Storyboard> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Per creare il <xref:System.Windows.Media.Animation.Storyboard> nel codice, dichiarare una variabile <xref:System.Windows.Media.Animation.Storyboard> a livello di classe.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Inizializzare quindi il <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. Il <xref:System.Windows.Media.Animation.Storyboard> deve stabilire dove applicare l'animazione. Utilizzare la proprietà associata <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> per specificare l'oggetto a cui aggiungere un'animazione. Di seguito viene illustrato come impostare il nome di destinazione del <xref:System.Windows.Media.Animation.DoubleAnimation> su `MyRectangle` in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Di seguito viene illustrato come impostare il nome di destinazione del <xref:System.Windows.Media.Animation.DoubleAnimation> per `MyRectangle` nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Utilizzare la proprietà associata <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> per specificare la proprietà a cui aggiungere un'animazione. Di seguito viene illustrato il modo in cui l'animazione viene configurata per la destinazione della proprietà <xref:System.Windows.UIElement.Opacity%2A> della <xref:System.Windows.Shapes.Rectangle> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Di seguito viene illustrato il modo in cui l'animazione viene configurata per la destinazione della proprietà <xref:System.Windows.UIElement.Opacity%2A> della <xref:System.Windows.Shapes.Rectangle> nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Per ulteriori informazioni sulla sintassi <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> e per altri esempi, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML) - Associare lo storyboard a un trigger

Il modo più semplice per applicare e avviare un <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nell'usare un trigger di evento. In questa sezione viene illustrato come associare il <xref:System.Windows.Media.Animation.Storyboard> a un trigger in XAML.

1. Creare un oggetto <xref:System.Windows.Media.Animation.BeginStoryboard> e associarvi lo storyboard. Un <xref:System.Windows.Media.Animation.BeginStoryboard> è un tipo di <xref:System.Windows.TriggerAction> che si applica e avvia un <xref:System.Windows.Media.Animation.Storyboard>.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Creare una <xref:System.Windows.EventTrigger> e aggiungere il <xref:System.Windows.Media.Animation.BeginStoryboard> alla raccolta di <xref:System.Windows.EventTrigger.Actions%2A>. Impostare la proprietà <xref:System.Windows.EventTrigger.RoutedEvent%2A> della <xref:System.Windows.EventTrigger> sull'evento indirizzato per il quale si desidera avviare il <xref:System.Windows.Media.Animation.Storyboard>. Per ulteriori informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md).

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Aggiungere la <xref:System.Windows.EventTrigger> alla raccolta <xref:System.Windows.FrameworkElement.Triggers%2A> del rettangolo.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (codice) - Associare lo storyboard a un gestore eventi

Il modo più semplice per applicare e avviare una <xref:System.Windows.Media.Animation.Storyboard> nel codice consiste nell'usare un gestore eventi. In questa sezione viene illustrato come associare il <xref:System.Windows.Media.Animation.Storyboard> a un gestore eventi nel codice.

1. Eseguire la registrazione per l'evento <xref:System.Windows.FrameworkElement.Loaded> del rettangolo.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Dichiarare il gestore eventi. Nel gestore dell'evento usare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> per applicare lo storyboard.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]

### <a name="complete-example"></a>Esempio completo

Nell'esempio seguente viene illustrato come creare un rettangolo che si dissolve in entrata e in uscita in XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]

L'esempio seguente illustra come creare un rettangolo a cui viene applicata la dissolvenza in entrata e in uscita nel codice.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]

<a name="animationtypes"></a>

## <a name="animation-types"></a>Tipi di animazione

Poiché le animazioni generano valori di proprietà, per i diversi tipi di proprietà esistono tipi di animazione differenti. Per animare una proprietà che accetta un <xref:System.Double>, ad esempio la proprietà <xref:System.Windows.FrameworkElement.Width%2A> di un elemento, usare un'animazione che produce valori di <xref:System.Double>. Per animare una proprietà che accetta una <xref:System.Windows.Point>, utilizzare un'animazione che produce valori <xref:System.Windows.Point> e così via. A causa del numero di tipi di proprietà diversi, nello spazio dei nomi <xref:System.Windows.Media.Animation> sono presenti diverse classi di animazione. che fortunatamente seguono una convenzione di denominazione rigorosa che ne facilita la differenziazione:

- \<*Tipo*>Animation

  Nota come animazione "From/To/By" o "di base", viene applicata tra un valore iniziale e un valore di destinazione o con l'aggiunta di un valore di offset al valore iniziale.

  - Per specificare un valore iniziale, impostare la proprietà From dell'animazione.

  - Per specificare un valore finale, impostare la proprietà To dell'animazione.

  - Per specificare un valore di offset, impostare la proprietà By dell'animazione.

  Gli esempi del presente documento usano queste animazioni perché sono le più semplici. Le animazioni from/to/by sono descritte in dettaglio in Cenni preliminari sulle animazioni from/to/by.

- \<*Tipo*>AnimationUsingKeyFrames

  Le animazioni basate su fotogrammi chiave sono più efficaci delle animazioni From/To/By perché è possibile specificare un numero qualsiasi di valori di destinazione e controllarne il metodo di interpolazione. Alcuni tipi possono essere animati solo con animazioni basate su fotogrammi chiave. Le animazioni con fotogramma chiave sono descritte in dettaglio nella [Panoramica delle animazioni con fotogrammi chiave](key-frame-animations-overview.md).

- \<*Tipo*>AnimationUsingPath

  Le animazioni basate su tracciato consentono di usare un tracciato geometrico per produrre valori animati.

- \<*Tipo*>AnimationBase

  Classe astratta che, quando implementata, anima un valore \<*Type*>. Questa classe funge da classe di base per le classi \<*Tipo*>Animation e \<*Type*>AnimationUsingKeyFrames. È necessario gestire direttamente queste classi solo se si vuole creare animazioni personalizzate. In caso contrario, usare una classe \<*Tipo*>Animation o KeyFrame\<*Tipo*>Animation.

Nella maggior parte dei casi, è consigliabile usare il *tipo*di \<> classi di animazione, ad esempio <xref:System.Windows.Media.Animation.DoubleAnimation> e <xref:System.Windows.Media.Animation.ColorAnimation>.

La tabella seguente illustra diversi tipi di animazione comuni e alcune proprietà con cui vengono usati.

|Tipo di proprietà|Animazione (From/To/By) di base corrispondente|Animazione basata su fotogrammi chiave corrispondente|Animazione basata su tracciato corrispondente|Esempio di uso|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|nessuna|Animare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> o di un <xref:System.Windows.Media.GradientStop>.|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animare il <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Controls.DockPanel> o il <xref:System.Windows.FrameworkElement.Height%2A> di una <xref:System.Windows.Controls.Button>.|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animare la posizione del <xref:System.Windows.Media.EllipseGeometry.Center%2A> di un <xref:System.Windows.Media.EllipseGeometry>.|
|<xref:System.String>|nessuna|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|nessuna|Animare il <xref:System.Windows.Controls.TextBlock.Text%2A> di un <xref:System.Windows.Controls.TextBlock> o il <xref:System.Windows.Controls.ContentControl.Content%2A> di una <xref:System.Windows.Controls.Button>.|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Animazioni come sequenze temporali

Tutti i tipi di animazione ereditano dalla classe <xref:System.Windows.Media.Animation.Timeline>; tutte le animazioni sono pertanto tipi specializzati di sequenze temporali. Una <xref:System.Windows.Media.Animation.Timeline> definisce un intervallo di tempo. È possibile specificare i *comportamenti temporali* di una sequenza temporale: la relativa <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, il numero di volte che viene ripetuto e anche il tempo di avanzamento del tempo.

Poiché un'animazione è un <xref:System.Windows.Media.Animation.Timeline>, rappresenta anche un intervallo di tempo. Un'animazione calcola inoltre i valori di output durante l'avanzamento del periodo di tempo specificato (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Con l'avanzamento, ovvero la riproduzione, dell'animazione, viene aggiornata la proprietà associata.

Tre proprietà temporali utilizzate di frequente sono <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.

#### <a name="the-duration-property"></a>Proprietà Duration

Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza di tale segmento è determinata dalla <xref:System.Windows.Media.Animation.Timeline.Duration%2A> della sequenza temporale, che viene in genere specificata utilizzando un valore <xref:System.Windows.Duration.TimeSpan%2A>. Quando una sequenza temporale raggiunge il termine della durata, ha completato un'iterazione.

Un'animazione usa la proprietà <xref:System.Windows.Media.Animation.Timeline.Duration%2A> per determinare il valore corrente. Se non si specifica un valore <xref:System.Windows.Media.Animation.Timeline.Duration%2A> per un'animazione, viene utilizzato 1 secondo, ovvero l'impostazione predefinita.

Nella sintassi seguente viene illustrata una versione semplificata della sintassi dell'attributo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per la proprietà <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.

*ore* `:` *minuti* `:` *secondi*

Nella tabella seguente vengono illustrate diverse impostazioni <xref:System.Windows.Duration> e i valori risultanti.

|Impostazione di|Valore risultante|
|-------------|---------------------|
|0:0:5.5|5,5 secondi.|
|0:30:5.5|30 minuti e 5,5 secondi.|
|1:30:5.5|1 ora, 30 minuti e 5,5 secondi.|

Un modo per specificare una <xref:System.Windows.Duration> nel codice consiste nell'usare il metodo <xref:System.TimeSpan.FromSeconds%2A> per creare un <xref:System.TimeSpan>, quindi dichiarare una nuova struttura <xref:System.Windows.Duration> usando tale <xref:System.TimeSpan>.

Per ulteriori informazioni sui valori <xref:System.Windows.Duration> e sulla sintassi completa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vedere la struttura <xref:System.Windows.Duration>.

#### <a name="autoreverse"></a>Proprietà AutoReverse

La proprietà <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> specifica se una sequenza temporale viene riprodotta indietro dopo che ha raggiunto la fine del relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Se si imposta questa proprietà di animazione su `true`, un'animazione viene invertita dopo che raggiunge la fine del relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, riproducendo il valore iniziale del valore finale. Per impostazione predefinita, questa proprietà è `false`.

#### <a name="repeatbehavior"></a>RepeatBehavior

La proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> specifica il numero di volte in cui viene riprodotta una sequenza temporale. Per impostazione predefinita, le sequenze temporali hanno un conteggio delle iterazioni di `1.0`, il che significa che vengono riprodotte una sola volta e non vengono ripetute.

Per ulteriori informazioni su queste proprietà e altre, vedere [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Applicazione di un'animazione a una proprietà

Le sezioni precedenti descrivono i diversi tipi di animazioni e le relative proprietà temporali, mentre questa sezione illustra come applicare l'animazione alla proprietà da animare. gli oggetti <xref:System.Windows.Media.Animation.Storyboard> offrono un modo per applicare animazioni alle proprietà. Una <xref:System.Windows.Media.Animation.Storyboard> è una *sequenza temporale del contenitore* che fornisce informazioni di destinazione per le animazioni in esso contenute.

### <a name="targeting-objects-and-properties"></a>Oggetti di destinazione e proprietà

La classe <xref:System.Windows.Media.Animation.Storyboard> fornisce le proprietà <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> associate. Se si impostano tali proprietà in un'animazione, si indica l'oggetto da animare. Affinché un oggetto possa diventare la destinazione di un'animazione, è tuttavia necessario assegnargli un nome.

L'assegnazione di un nome a una <xref:System.Windows.FrameworkElement> è diversa dall'assegnazione di un nome a un oggetto <xref:System.Windows.Freezable>. La maggior parte dei controlli e dei pannelli sono elementi del framework, mentre gli oggetti più strettamente grafici, ad esempio pennelli, trasformazioni e geometrie, sono bloccabili. Se non si è certi che un tipo sia un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.Freezable>, vedere la sezione **gerarchia di ereditarietà** della documentazione di riferimento.

- Per creare un <xref:System.Windows.FrameworkElement> una destinazione di animazione, assegnargli un nome impostando la relativa proprietà <xref:System.Windows.FrameworkElement.Name%2A>. Nel codice è anche necessario usare il metodo <xref:System.Windows.FrameworkElement.RegisterName%2A> per registrare il nome dell'elemento con la pagina a cui appartiene.

- Per rendere un <xref:System.Windows.Freezable> oggetto una destinazione dell'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare la [direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) per assegnarle un nome. Nel codice è sufficiente usare il metodo <xref:System.Windows.FrameworkElement.RegisterName%2A> per registrare l'oggetto con la pagina a cui appartiene.

Nelle sezioni seguenti viene fornito un esempio di denominazione di un elemento in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e codice. Per informazioni più dettagliate sulla denominazione e la destinazione, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Applicazione e avvio di storyboard

Per avviare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], associarlo a una <xref:System.Windows.EventTrigger>. Un <xref:System.Windows.EventTrigger> è un oggetto che descrive le azioni da intraprendere quando si verifica un evento specificato. Una di queste azioni può essere un'azione <xref:System.Windows.Media.Animation.BeginStoryboard>, che viene usata per avviare lo storyboard. I trigger di evento sono concettualmente analoghi ai gestori eventi poiché consentono di specificare il modo in cui l'applicazione risponde a un determinato evento. A differenza dei gestori eventi, i trigger di evento possono essere descritti completamente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; non è necessario altro codice.

Per avviare una <xref:System.Windows.Media.Animation.Storyboard> nel codice, è possibile usare un <xref:System.Windows.EventTrigger> o usare il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> della classe <xref:System.Windows.Media.Animation.Storyboard>.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Controllo interattivo di uno storyboard

Nell'esempio precedente è stato illustrato come avviare un <xref:System.Windows.Media.Animation.Storyboard> quando si verifica un evento. È anche possibile controllare in modo interattivo un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio: è possibile sospendere, riprendere, arrestare, spostarlo al periodo di riempimento, cercare e rimuovere il <xref:System.Windows.Media.Animation.Storyboard>. Per ulteriori informazioni e un esempio che illustra come controllare in modo interattivo un <xref:System.Windows.Media.Animation.Storyboard>, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Effetti del termine di un'animazione

La proprietà <xref:System.Windows.Media.Animation.FillBehavior> specifica il comportamento di una sequenza temporale al termine di. Per impostazione predefinita, una sequenza temporale inizia <xref:System.Windows.Media.Animation.ClockState.Filling> al termine. Un'animazione <xref:System.Windows.Media.Animation.ClockState.Filling> include il valore di output finale.

Il <xref:System.Windows.Media.Animation.DoubleAnimation> nell'esempio precedente non termina perché la relativa proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> è impostata su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. L'esempio seguente anima un rettangolo usando un'animazione analoga. A differenza dell'esempio precedente, le proprietà <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> e <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> di questa animazione restano sui valori predefiniti. e di conseguenza l'animazione avanza da 1 a 0 in un intervallo di cinque secondi per poi arrestarsi.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Poiché il <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> non è stato modificato rispetto al valore predefinito, che è <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, l'animazione deve contenere il valore finale, 0, al termine dell'operazione. Di conseguenza, il <xref:System.Windows.UIElement.Opacity%2A> del rettangolo rimane a 0 al termine dell'animazione. Se si imposta la <xref:System.Windows.UIElement.Opacity%2A> del rettangolo su un altro valore, il codice sembra non avere alcun effetto, perché l'animazione continua a influire sulla proprietà <xref:System.Windows.UIElement.Opacity%2A>.

Un modo per ottenere nuovamente il controllo di una proprietà animata nel codice consiste nell'usare il metodo <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> e specificare null per il parametro <xref:System.Windows.Media.Animation.AnimationTimeline>. Per ulteriori informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Si noti che, anche se l'impostazione di un valore della proprietà con un'animazione <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> non ha alcun effetto, il valore della proprietà viene modificato. Per ulteriori informazioni, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Data binding e animazione di animazioni

La maggior parte delle proprietà di animazione può essere associata a dati o animata; ad esempio, è possibile aggiungere un'animazione alla proprietà <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di un <xref:System.Windows.Media.Animation.DoubleAnimation>. A causa della modalità di funzionamento del sistema di temporizzazione, tuttavia, le animazioni associate a dati o animate si comportano in modo diverso rispetto ad altri oggetti associati a dati o animati. Per comprendere questo comportamento, è opportuno capire il significato dell'applicazione di un'animazione a una proprietà.

Vedere l'esempio nella sezione precedente che ha illustrato come animare il <xref:System.Windows.UIElement.Opacity%2A> di un rettangolo. Quando viene caricato il rettangolo nell'esempio precedente, il trigger di evento applica la <xref:System.Windows.Media.Animation.Storyboard>. Il sistema di temporizzazione crea una copia della <xref:System.Windows.Media.Animation.Storyboard> e della relativa animazione. Queste copie sono bloccate (rese di sola lettura) e <xref:System.Windows.Media.Animation.Clock> vengono creati oggetti. che animano effettivamente le proprietà di destinazione.

Il sistema di temporizzazione crea un clock per il <xref:System.Windows.Media.Animation.DoubleAnimation> e lo applica all'oggetto e alla proprietà specificati dall'<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> della <xref:System.Windows.Media.Animation.DoubleAnimation>. In questo caso, il sistema di temporizzazione applica l'orologio alla proprietà <xref:System.Windows.UIElement.Opacity%2A> dell'oggetto denominato "derectangle".

Sebbene venga creato anche un clock per la <xref:System.Windows.Media.Animation.Storyboard>, l'orologio non viene applicato alle proprietà. Lo scopo è quello di controllare il clock figlio, l'orologio creato per il <xref:System.Windows.Media.Animation.DoubleAnimation>.

Affinché un'animazione rifletta le modifiche di data binding, è necessario rigenerarne l'orologio. Gli orologi non vengono rigenerati automaticamente. Per fare in modo che un'animazione rifletta le modifiche, riapplicarne lo storyboard usando un <xref:System.Windows.Media.Animation.BeginStoryboard> o il metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>. Quando si usa uno di questi metodi, l'animazione viene riavviata. Nel codice è possibile usare il metodo <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> per spostare nuovamente lo storyboard nella posizione precedente.

Per un esempio di animazione con associazione a dati, vedere [esempio di animazione key spline](https://go.microsoft.com/fwlink/?LinkID=160011). Per ulteriori informazioni sul funzionamento del sistema di animazione e temporizzazione, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Altri modi per applicare un'animazione

Gli esempi del presente documento illustrano come applicare animazioni tramite storyboard. Quando si usa il codice, è possibile eseguire questa operazione in diversi altri modi. Per ulteriori informazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Esempi di animazione

Gli esempi seguenti consentono di iniziare ad aggiungere animazione alle applicazioni.

- [Esempio di valori di destinazione dell'animazione From/To/By](https://go.microsoft.com/fwlink/?LinkID=159988)

  Descrive le diverse impostazioni From/To/By.

- [Esempio di comportamento temporale di un'animazione](https://go.microsoft.com/fwlink/?LinkID=159970)

  Illustra le diverse modalità per controllare il comportamento temporale di un'animazione. Questo esempio illustra anche come associare a dati il valore di destinazione di un'animazione.

<a name="related_topics"></a>

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)|Viene descritto il modo in cui il sistema di temporizzazione usa le classi <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock>, che consentono di creare animazioni.|
|[Suggerimenti sulle animazioni](animation-tips-and-tricks.md)|Contiene suggerimenti utili per la risoluzione di problemi relativi alle animazioni, ad esempio problemi di prestazioni.|
|[Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md)|Descrive come estendere il sistema dell'animazione con fotogrammi chiave, classi di animazione o callback per fotogramma.|
|[Panoramica sulle animazioni From/To/By](from-to-by-animations-overview.md)|Descrive come creare un'animazione che effettua la transizione tra due valori.|
|[Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)|Descrive come creare un'animazione con più valori di destinazione, inclusa la possibilità di controllare il metodo di interpolazione.|
|[Funzioni di interpolazione](easing-functions.md)|Descrive come applicare formule matematiche alle animazioni per ottenere un comportamento realistico, ad esempio un effetto di rimbalzo.|
|[Panoramica sulle animazioni tracciato](path-animations-overview.md)|Descrive come spostare o ruotare un oggetto lungo un tracciato complesso.|
|[Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)|Descrive le animazioni di proprietà in cui si usano storyboard, animazioni locali, orologi e animazioni per fotogramma.|
|[Cenni preliminari sugli storyboard](storyboards-overview.md)|Descrive come usare gli storyboard con più sequenze temporali per creare animazioni complesse.|
|[Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)|Vengono descritti i tipi e le proprietà <xref:System.Windows.Media.Animation.Timeline> utilizzati nelle animazioni.|
|[Cenni preliminari sugli eventi di tempo](timing-events-overview.md)|Vengono descritti gli eventi disponibili nell'<xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock> oggetti per l'esecuzione di codice nei punti della sequenza temporale, ad esempio Begin, pause, Resume, Skip o stop.|
|[Procedure relative alle proprietà](animation-and-timing-how-to-topics.md)|Contiene esempi di codice per usare animazioni e sequenze temporali in un'applicazione.|
|[Procedure relative a oggetti Clock](clocks-how-to-topics.md)|Contiene esempi di codice per l'utilizzo dell'oggetto <xref:System.Windows.Media.Animation.Clock> nell'applicazione.|
|[Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni con fotogrammi chiave in un'applicazione.|
|[Procedure relative all'animazione percorso](path-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni basate su tracciato in un'applicazione.|

<a name="reference"></a>

## <a name="reference"></a>Riferimenti

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
