---
title: Cenni preliminari sull'animazione
description: Rendere un'interfaccia utente accattivante ancora più spettacolare con transizioni di schermo drammatiche o segnali visivi vividi in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: d761be0c95fb8aa7eb39cb26b57979185226b8fb
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853869"
---
# <a name="animation-overview"></a>Cenni preliminari sull'animazione

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre un set potente di funzionalità di grafica e layout che consentono di creare interfacce utente di forte impatto e documenti accattivanti. L'animazione può migliorare ulteriormente l'aspetto e la facilità di uso dell'interfaccia utente. Semplicemente animando un colore di sfondo o applicando un'animazione <xref:System.Windows.Media.Transform> , è possibile creare transizioni di schermo drammatiche o fornire segnali visivi utili.

Questa panoramica offre un'introduzione al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di animazione e temporizzazione. Si concentra sull'animazione degli oggetti tramite gli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] storyboard.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Introduzione alle animazioni

L'animazione è un'illusione ottica creata scorrendo rapidamente una serie di immagini, ognuna leggermente diversa dall'ultima. Il cervello percepisce il gruppo di immagini come un'unica scena che si modifica. Nei film questa illusione viene creata usando fotocamere che registrano molte fotografie (fotogrammi) al secondo. Quando i fotogrammi vengono riprodotti con un proiettore, il pubblico vede un'immagine in movimento.

L'animazione in un computer è simile. Un programma che applica una dissolvenza in uscita al disegno di un rettangolo funziona ad esempio nel modo indicato di seguito.

- Il programma crea un timer.

- Il programma controlla il timer a intervalli stabiliti per rilevare la quantità di tempo trascorso.

- Ogni volta che il programma controlla il timer, calcola anche il valore di opacità per il rettangolo in base al tempo trascorso.

- Il programma aggiorna quindi il rettangolo in base al nuovo valore e lo ridisegna.

Prima di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , gli sviluppatori di Microsoft Windows dovevano creare e gestire i propri sistemi temporali o usare librerie personalizzate speciali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]include un sistema di temporizzazione efficiente esposto tramite codice gestito e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] integrato in modo approfondito nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework. Le funzionalità disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplificano l'applicazione di animazioni ai controlli e ad altri oggetti grafici.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue in modo efficiente tutte le attività automatiche di gestione del sistema di temporizzazione e di aggiornamento dello schermo grazie a classi di temporizzazione che consentono di concentrarsi sugli effetti da creare anziché sulle operazioni per ottenerli. Esponendo le classi di base di animazione da cui le classi dell'utente possono ereditare, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplifica anche la creazione di animazioni personalizzate che sfruttano molti vantaggi in termini di prestazioni delle classi di animazione standard.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Sistema di animazione delle proprietà WPF

Se si conoscono alcuni concetti importanti sul sistema di temporizzazione, le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazioni possono essere più facili da usare. L'aspetto più importante è che, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , si animano gli oggetti applicando animazioni alle rispettive proprietà. Ad esempio, per aumentare le dimensioni di un elemento del Framework, si animano le relative <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e. Per fare in modo che un oggetto venga sfumato dalla visualizzazione, animarne la <xref:System.Windows.UIElement.Opacity%2A> Proprietà.

Affinché una proprietà disponga di funzionalità di animazione, devono essere soddisfatti i tre requisiti seguenti:

- Deve essere una proprietà di dipendenza.

- Deve appartenere a una classe che eredita da <xref:System.Windows.DependencyObject> e implementa l' <xref:System.Windows.Media.Animation.IAnimatable> interfaccia.

- Deve essere disponibile un tipo di animazione compatibile. Se non [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è disponibile, è possibile crearne uno personalizzato. Vedere [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md).

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]contiene molti oggetti con <xref:System.Windows.Media.Animation.IAnimatable> Proprietà. Controlli quali <xref:System.Windows.Controls.Button> e e <xref:System.Windows.Controls.TabControl> anche <xref:System.Windows.Controls.Panel> <xref:System.Windows.Shapes.Shape> gli oggetti e ereditano da <xref:System.Windows.DependencyObject> . La maggior parte delle proprietà di tali oggetti è rappresentata da proprietà di dipendenza.

È possibile usare le animazioni quasi ovunque, ad esempio in stili e modelli del controllo. Le animazioni non devono necessariamente essere oggetti visivi ed è possibile animare oggetti che non appartengono all'interfaccia utente se soddisfano i criteri descritti in questa sezione.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Esempio - Applicare a un elemento una dissolvenza in entrata e in uscita

Questo esempio illustra come usare un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazione per animare il valore di una proprietà di dipendenza. USA <xref:System.Windows.Media.Animation.DoubleAnimation> , che è un tipo di animazione che genera <xref:System.Double> valori, per animare la <xref:System.Windows.UIElement.Opacity%2A> proprietà di un oggetto <xref:System.Windows.Shapes.Rectangle> . Di conseguenza, la <xref:System.Windows.Shapes.Rectangle> dissolvenza in entrata e in uscita.

Nella prima parte dell'esempio viene creato un <xref:System.Windows.Shapes.Rectangle> elemento. I passaggi seguenti illustrano come creare un'animazione e applicarla alla proprietà del rettangolo <xref:System.Windows.UIElement.Opacity%2A> .

Di seguito viene illustrato come creare un <xref:System.Windows.Shapes.Rectangle> elemento in un oggetto <xref:System.Windows.Controls.StackPanel> in XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Shapes.Rectangle> elemento in un oggetto <xref:System.Windows.Controls.StackPanel> nel codice.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Parte 1 - Creare un oggetto DoubleAnimation

Un modo per rendere una dissolvenza dell'elemento in entrata e in uscita è l'animazione della relativa <xref:System.Windows.UIElement.Opacity%2A> Proprietà. Poiché la <xref:System.Windows.UIElement.Opacity%2A> proprietà è di tipo <xref:System.Double> , è necessaria un'animazione che produce valori Double. Una <xref:System.Windows.Media.Animation.DoubleAnimation> è un'animazione di questo tipo. Una <xref:System.Windows.Media.Animation.DoubleAnimation> Crea una transizione tra due valori Double. Per specificare il valore iniziale, impostarne la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Proprietà. Per specificare il valore finale, impostarne la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Proprietà.

1. Un valore di opacità di `1.0` rende l'oggetto completamente opaco e un valore di opacità lo `0.0` rende completamente invisibile. Per eseguire la transizione dell'animazione da `1.0` a `0.0` , impostare la relativa <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà su `1.0` e la relativa <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà su `0.0` . Di seguito viene illustrato come creare un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Di seguito viene illustrato come creare un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Successivamente, è necessario specificare un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . L'oggetto <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di un'animazione specifica il tempo necessario per passare dal valore iniziale al valore di destinazione. Di seguito viene illustrato come impostare <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su cinque secondi in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Di seguito viene illustrato come impostare <xref:System.Windows.Media.Animation.Timeline.Duration%2A> su cinque secondi nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Nel codice precedente è stata mostrata un'animazione che esegue la transizione da `1.0` a `0.0` , che determina la dissolvenza dell'elemento di destinazione da completamente opaco a completamente invisibile. Per fare in modo che l'elemento venga nuovamente visualizzato dopo la scomparsa, impostare la <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà dell'animazione su `true` . Per fare in modo che l'animazione venga ripetuta per un periodo illimitato, impostare la relativa <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . Di seguito viene illustrato come impostare le <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà e in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Di seguito viene illustrato come impostare le <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà e nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Parte 2 - Creare uno storyboard

Per applicare un'animazione a un oggetto, creare un oggetto <xref:System.Windows.Media.Animation.Storyboard> e usare le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà associate e per specificare l'oggetto e la proprietà a cui aggiungere un'animazione.

1. Creare <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio. Di seguito viene illustrato come creare <xref:System.Windows.Media.Animation.Storyboard> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Per creare il <xref:System.Windows.Media.Animation.Storyboard> nel codice, dichiarare una <xref:System.Windows.Media.Animation.Storyboard> variabile a livello di classe.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Inizializzare quindi l'oggetto <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. <xref:System.Windows.Media.Animation.Storyboard>Deve stabilire dove applicare l'animazione. Usare la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà associata per specificare l'oggetto a cui aggiungere un'animazione. Nell'esempio seguente viene illustrato come impostare il nome di destinazione di <xref:System.Windows.Media.Animation.DoubleAnimation> su `MyRectangle` in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Nell'esempio seguente viene illustrato come impostare il nome di destinazione dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> su `MyRectangle` nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Usare la <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà associata per specificare la proprietà a cui aggiungere un'animazione. Di seguito viene illustrato il modo in cui l'animazione viene configurata per la destinazione della <xref:System.Windows.UIElement.Opacity%2A> proprietà di <xref:System.Windows.Shapes.Rectangle> in XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Di seguito viene illustrato il modo in cui l'animazione viene configurata per la destinazione della <xref:System.Windows.UIElement.Opacity%2A> proprietà di <xref:System.Windows.Shapes.Rectangle> nel codice.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Per ulteriori informazioni sulla <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> sintassi e per altri esempi, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML) - Associare lo storyboard a un trigger

Il modo più semplice per applicare e avviare una <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nell'usare un trigger di evento. In questa sezione viene illustrato come associare l'oggetto a <xref:System.Windows.Media.Animation.Storyboard> un trigger in XAML.

1. Creare un <xref:System.Windows.Media.Animation.BeginStoryboard> oggetto e associarvi lo storyboard. Un <xref:System.Windows.Media.Animation.BeginStoryboard> è un tipo di <xref:System.Windows.TriggerAction> che si applica e avvia un oggetto <xref:System.Windows.Media.Animation.Storyboard> .

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Creare un oggetto <xref:System.Windows.EventTrigger> e aggiungere alla <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger.Actions%2A> raccolta. Impostare la <xref:System.Windows.EventTrigger.RoutedEvent%2A> proprietà dell'oggetto sull' <xref:System.Windows.EventTrigger> evento indirizzato che si desidera avviare <xref:System.Windows.Media.Animation.Storyboard> . Per ulteriori informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md).

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Aggiungere alla <xref:System.Windows.EventTrigger> <xref:System.Windows.FrameworkElement.Triggers%2A> raccolta del rettangolo.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (codice) - Associare lo storyboard a un gestore eventi

Il modo più semplice per applicare e avviare un <xref:System.Windows.Media.Animation.Storyboard> nel codice consiste nell'usare un gestore eventi. In questa sezione viene illustrato come associare l'oggetto a <xref:System.Windows.Media.Animation.Storyboard> un gestore eventi nel codice.

1. Eseguire la registrazione per l' <xref:System.Windows.FrameworkElement.Loaded> evento del rettangolo.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Dichiarare il gestore eventi. Nel gestore dell'evento usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per applicare lo storyboard.

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

Poiché le animazioni generano valori di proprietà, per i diversi tipi di proprietà esistono tipi di animazione differenti. Per animare una proprietà che accetta un oggetto <xref:System.Double> , ad esempio la <xref:System.Windows.FrameworkElement.Width%2A> proprietà di un elemento, usare un'animazione che produce <xref:System.Double> valori. Per animare una proprietà che accetta un oggetto <xref:System.Windows.Point> , usare un'animazione che produce <xref:System.Windows.Point> valori e così via. A causa del numero di tipi di proprietà diversi, nello spazio dei nomi sono presenti diverse classi di animazione <xref:System.Windows.Media.Animation> . che fortunatamente seguono una convenzione di denominazione rigorosa che ne facilita la differenziazione:

- \<*Type*>Animazione

  Nota come animazione "From/To/By" o "di base", viene applicata tra un valore iniziale e un valore di destinazione o con l'aggiunta di un valore di offset al valore iniziale.

  - Per specificare un valore iniziale, impostare la proprietà From dell'animazione.

  - Per specificare un valore finale, impostare la proprietà To dell'animazione.

  - Per specificare un valore di offset, impostare la proprietà By dell'animazione.

  Gli esempi del presente documento usano queste animazioni perché sono le più semplici. Le animazioni from/to/by sono descritte in dettaglio in Cenni preliminari sulle animazioni from/to/by.

- \<*Type*>AnimationUsingKeyFrames

  Le animazioni basate su fotogrammi chiave sono più efficaci delle animazioni From/To/By perché è possibile specificare un numero qualsiasi di valori di destinazione e controllarne il metodo di interpolazione. Alcuni tipi possono essere animati solo con animazioni basate su fotogrammi chiave. Le animazioni con fotogramma chiave sono descritte in dettaglio nella [Panoramica delle animazioni con fotogrammi chiave](key-frame-animations-overview.md).

- \<*Type*>AnimationUsingPath

  Le animazioni basate su tracciato consentono di usare un tracciato geometrico per produrre valori animati.

- \<*Type*>AnimationBase

  Classe astratta che, quando viene implementata, aggiunge un'animazione a un \<*Type*> valore. Questa classe funge da classe base per \<*Type*> \<*Type*> le classi Animation e AnimationUsingKeyFrames. È necessario gestire direttamente queste classi solo se si vuole creare animazioni personalizzate. In caso contrario, utilizzare un'animazione \<*Type*> o un'animazione del fotogramma chiave \<*Type*> .

Nella maggior parte dei casi, è consigliabile usare le \<*Type*> classi di animazione, ad esempio <xref:System.Windows.Media.Animation.DoubleAnimation> e <xref:System.Windows.Media.Animation.ColorAnimation> .

La tabella seguente illustra diversi tipi di animazione comuni e alcune proprietà con cui vengono usati.

|Tipo di proprietà|Animazione (From/To/By) di base corrispondente|Animazione basata su fotogrammi chiave corrispondente|Animazione basata su tracciato corrispondente|Esempio di utilizzo|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|nessuno|Animare l'oggetto <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> o un oggetto <xref:System.Windows.Media.GradientStop> .|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animare l'oggetto <xref:System.Windows.FrameworkElement.Width%2A> di un oggetto <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.FrameworkElement.Height%2A> di un oggetto <xref:System.Windows.Controls.Button> .|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> posizione di un oggetto <xref:System.Windows.Media.EllipseGeometry> .|
|<xref:System.String>|nessuno|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|nessuno|Animare l'oggetto <xref:System.Windows.Controls.TextBlock.Text%2A> di un oggetto <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.Button> .|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Animazioni come sequenze temporali

Tutti i tipi di animazione ereditano dalla <xref:System.Windows.Media.Animation.Timeline> classe; pertanto, tutte le animazioni sono tipi specializzati di sequenze temporali. Un oggetto <xref:System.Windows.Media.Animation.Timeline> definisce un intervallo di tempo. È possibile specificare i *comportamenti temporali* di una sequenza temporale: la relativa <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , il numero di volte che viene ripetuta e la velocità di avanzamento del tempo.

Poiché un'animazione è un <xref:System.Windows.Media.Animation.Timeline> , rappresenta anche un intervallo di tempo. Un'animazione calcola inoltre i valori di output durante l'avanzamento nel segmento di tempo specificato (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ). Con l'avanzamento, ovvero la riproduzione, dell'animazione, viene aggiornata la proprietà associata.

Tre proprietà temporali utilizzate di frequente sono <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> .

#### <a name="the-duration-property"></a>Proprietà Duration

Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza di tale segmento è determinata dall'oggetto <xref:System.Windows.Media.Animation.Timeline.Duration%2A> della sequenza temporale, che viene in genere specificato utilizzando un <xref:System.Windows.Duration.TimeSpan%2A> valore. Quando una sequenza temporale raggiunge il termine della durata, ha completato un'iterazione.

Un'animazione usa la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per determinare il valore corrente. Se non si specifica un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valore per un'animazione, viene utilizzato 1 secondo, che corrisponde all'impostazione predefinita.

Nella sintassi seguente viene illustrata una versione semplificata della [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi degli attributi per la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Proprietà.

*ore* `:` *minuti* `:` *secondi*

Nella tabella seguente vengono illustrate diverse <xref:System.Windows.Duration> Impostazioni e i valori risultanti.

|Impostazione|Valore risultante|
|-------------|---------------------|
|0:0:5.5|5,5 secondi.|
|0:30:5.5|30 minuti e 5,5 secondi.|
|1:30:5.5|1 ora, 30 minuti e 5,5 secondi.|

Un modo per specificare un <xref:System.Windows.Duration> nel codice consiste nell'usare il <xref:System.TimeSpan.FromSeconds%2A> metodo per creare un oggetto <xref:System.TimeSpan> , quindi dichiarare una nuova <xref:System.Windows.Duration> struttura usando tale metodo <xref:System.TimeSpan> .

Per ulteriori informazioni sui <xref:System.Windows.Duration> valori e sulla [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi completa, vedere la <xref:System.Windows.Duration> struttura.

#### <a name="autoreverse"></a>Proprietà AutoReverse

La <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà specifica se una sequenza temporale viene riprodotta indietro dopo che ha raggiunto la fine del relativo oggetto <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Se si imposta questa proprietà di animazione su `true` , un'animazione viene invertita dopo il raggiungimento della fine del relativo oggetto <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , risalendo al valore iniziale del relativo valore finale. Per impostazione predefinita, questa proprietà è `false` .

#### <a name="repeatbehavior"></a>RepeatBehavior

La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà specifica il numero di volte in cui viene riprodotta una sequenza temporale. Per impostazione predefinita, le sequenze temporali hanno un numero di iterazioni pari `1.0` a, che significa che vengono riprodotte una sola volta e non vengono ripetute.

Per ulteriori informazioni su queste proprietà e altre, vedere [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Applicazione di un'animazione a una proprietà

Le sezioni precedenti descrivono i diversi tipi di animazioni e le relative proprietà temporali, mentre questa sezione illustra come applicare l'animazione alla proprietà da animare. <xref:System.Windows.Media.Animation.Storyboard>gli oggetti forniscono un modo per applicare animazioni alle proprietà. Un <xref:System.Windows.Media.Animation.Storyboard> è una *sequenza temporale del contenitore* che fornisce informazioni sulla destinazione per le animazioni in esso contenute.

### <a name="targeting-objects-and-properties"></a>Oggetti di destinazione e proprietà

La <xref:System.Windows.Media.Animation.Storyboard> classe fornisce le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà associate e. Se si impostano tali proprietà in un'animazione, si indica l'oggetto da animare. Affinché un oggetto possa diventare la destinazione di un'animazione, è tuttavia necessario assegnargli un nome.

L'assegnazione di un nome a un <xref:System.Windows.FrameworkElement> oggetto differisce dall'assegnazione di un nome a un <xref:System.Windows.Freezable> oggetto. La maggior parte dei controlli e dei pannelli sono elementi del framework, mentre gli oggetti più strettamente grafici, ad esempio pennelli, trasformazioni e geometrie, sono bloccabili. Se non si è certi che un tipo sia <xref:System.Windows.FrameworkElement> o <xref:System.Windows.Freezable> , fare riferimento alla sezione **gerarchia di ereditarietà** della relativa documentazione di riferimento.

- Per creare una <xref:System.Windows.FrameworkElement> destinazione di animazione, assegnarle un nome impostando la <xref:System.Windows.FrameworkElement.Name%2A> Proprietà. Nel codice, è necessario usare anche il <xref:System.Windows.FrameworkElement.RegisterName%2A> metodo per registrare il nome dell'elemento con la pagina a cui appartiene.

- Per creare un <xref:System.Windows.Freezable> oggetto in una destinazione di animazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , utilizzare la [direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) per assegnarle un nome. Nel codice è sufficiente usare il <xref:System.Windows.FrameworkElement.RegisterName%2A> metodo per registrare l'oggetto con la pagina a cui appartiene.

Nelle sezioni seguenti viene fornito un esempio di denominazione di un elemento nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] codice e. Per informazioni più dettagliate sulla denominazione e la destinazione, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Applicazione e avvio di storyboard

Per avviare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , associarlo a un <xref:System.Windows.EventTrigger> . Un <xref:System.Windows.EventTrigger> oggetto è un oggetto che descrive le azioni da intraprendere quando si verifica un evento specificato. Una di queste azioni può essere un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione, che viene usata per avviare lo storyboard. I trigger di evento sono concettualmente analoghi ai gestori eventi poiché consentono di specificare il modo in cui l'applicazione risponde a un determinato evento. A differenza dei gestori eventi, i trigger di evento possono essere descritti in modo completo in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . non è necessario altro codice.

Per avviare un <xref:System.Windows.Media.Animation.Storyboard> nel codice, è possibile usare un oggetto <xref:System.Windows.EventTrigger> o usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo della <xref:System.Windows.Media.Animation.Storyboard> classe.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Controllo interattivo di uno storyboard

Nell'esempio precedente è stato illustrato come avviare un oggetto <xref:System.Windows.Media.Animation.Storyboard> quando si verifica un evento. È anche possibile controllare in modo interattivo un oggetto <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio: è possibile sospendere, riprendere, arrestare, avanzare al periodo di riempimento, cercare e rimuovere il <xref:System.Windows.Media.Animation.Storyboard> . Per ulteriori informazioni e un esempio che illustra come controllare in modo interattivo un oggetto <xref:System.Windows.Media.Animation.Storyboard> , vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Effetti del termine di un'animazione

La <xref:System.Windows.Media.Animation.FillBehavior> proprietà specifica il comportamento di una sequenza temporale al termine di. Per impostazione predefinita, una sequenza temporale inizia <xref:System.Windows.Media.Animation.ClockState.Filling> al termine di. Un'animazione che <xref:System.Windows.Media.Animation.ClockState.Filling> include il valore di output finale.

<xref:System.Windows.Media.Animation.DoubleAnimation>Nell'esempio precedente non termina perché la relativa <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà è impostata su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . L'esempio seguente anima un rettangolo usando un'animazione analoga. A differenza dell'esempio precedente, le <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà e di questa animazione rimangono i valori predefiniti. e di conseguenza l'animazione avanza da 1 a 0 in un intervallo di cinque secondi per poi arrestarsi.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Poiché la proprietà <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> non è stata modificata rispetto al valore predefinito, ovvero <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> l'animazione include il valore finale 0, al termine dell'operazione. Di conseguenza, l'oggetto <xref:System.Windows.UIElement.Opacity%2A> del rettangolo rimane a 0 dopo la fine dell'animazione. Se si imposta la <xref:System.Windows.UIElement.Opacity%2A> proprietà del rettangolo su un altro valore, il codice sembra non avere alcun effetto, perché l'animazione continua a influire sulla <xref:System.Windows.UIElement.Opacity%2A> Proprietà.

Un modo per ottenere nuovamente il controllo di una proprietà animata nel codice consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo e specificare null per il <xref:System.Windows.Media.Animation.AnimationTimeline> parametro. Per ulteriori informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Si noti che, anche se l'impostazione di un valore della proprietà con un' <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> animazione o sembra non avere alcun effetto, il valore della proprietà cambia. Per ulteriori informazioni, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Data binding e animazione di animazioni

La maggior parte delle proprietà di animazione può essere associata a dati o animata; ad esempio, è possibile aggiungere un'animazione alla <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà di un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> . A causa della modalità di funzionamento del sistema di temporizzazione, tuttavia, le animazioni associate a dati o animate si comportano in modo diverso rispetto ad altri oggetti associati a dati o animati. Per comprendere questo comportamento, è opportuno capire il significato dell'applicazione di un'animazione a una proprietà.

Vedere l'esempio nella sezione precedente che ha illustrato come animare l'oggetto <xref:System.Windows.UIElement.Opacity%2A> di un rettangolo. Quando il rettangolo nell'esempio precedente viene caricato, il trigger di evento applica <xref:System.Windows.Media.Animation.Storyboard> . Il sistema di temporizzazione crea una copia di <xref:System.Windows.Media.Animation.Storyboard> e della relativa animazione. Queste copie sono bloccate (rese di sola lettura) e <xref:System.Windows.Media.Animation.Clock> gli oggetti vengono creati da essi. che animano effettivamente le proprietà di destinazione.

Il sistema di temporizzazione crea un clock per <xref:System.Windows.Media.Animation.DoubleAnimation> e lo applica all'oggetto e alla proprietà specificati da <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> di <xref:System.Windows.Media.Animation.DoubleAnimation> . In questo caso, il sistema di temporizzazione applica l'orologio alla <xref:System.Windows.UIElement.Opacity%2A> proprietà dell'oggetto denominato "derectangle".

Sebbene venga creato anche un clock per <xref:System.Windows.Media.Animation.Storyboard> , l'orologio non viene applicato alle proprietà. Lo scopo è quello di controllare il clock figlio, l'orologio creato per <xref:System.Windows.Media.Animation.DoubleAnimation> .

Affinché un'animazione rifletta le modifiche di data binding, è necessario rigenerarne l'orologio. Gli orologi non vengono rigenerati automaticamente. Per fare in modo che un'animazione rifletta le modifiche, riapplicarne lo storyboard usando un <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo o. Quando si usa uno di questi metodi, l'animazione viene riavviata. Nel codice è possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo per spostare nuovamente lo storyboard nella posizione precedente.

Per un esempio di animazione con associazione a dati, vedere [esempio di animazione key spline](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations). Per ulteriori informazioni sul funzionamento del sistema di animazione e temporizzazione, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Altri modi per applicare un'animazione

Gli esempi del presente documento illustrano come applicare animazioni tramite storyboard. Quando si usa il codice, è possibile eseguire questa operazione in diversi altri modi. Per ulteriori informazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Esempi di animazione

Gli esempi seguenti consentono di iniziare ad aggiungere animazione alle applicazioni.

- [Esempio di valori di destinazione dell'animazione From/To/By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)

  Descrive le diverse impostazioni From/To/By.

- [Esempio di comportamento temporale di un'animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)

  Illustra le diverse modalità per controllare il comportamento temporale di un'animazione. Questo esempio illustra anche come associare a dati il valore di destinazione di un'animazione.

<a name="related_topics"></a>

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)|Viene descritto il modo in cui il sistema di temporizzazione usa le <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> classi e, che consentono di creare animazioni.|
|[Suggerimenti sulle animazioni](animation-tips-and-tricks.md)|Contiene suggerimenti utili per la risoluzione di problemi relativi alle animazioni, ad esempio problemi di prestazioni.|
|[Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md)|Descrive come estendere il sistema dell'animazione con fotogrammi chiave, classi di animazione o callback per fotogramma.|
|[Cenni preliminari sulle animazioni From/To/By](from-to-by-animations-overview.md)|Descrive come creare un'animazione che effettua la transizione tra due valori.|
|[Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)|Descrive come creare un'animazione con più valori di destinazione, inclusa la possibilità di controllare il metodo di interpolazione.|
|[Funzioni di interpolazione](easing-functions.md)|Descrive come applicare formule matematiche alle animazioni per ottenere un comportamento realistico, ad esempio un effetto di rimbalzo.|
|[Panoramica sulle animazioni tracciato](path-animations-overview.md)|Descrive come spostare o ruotare un oggetto lungo un tracciato complesso.|
|[Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)|Descrive le animazioni di proprietà in cui si usano storyboard, animazioni locali, orologi e animazioni per fotogramma.|
|[Cenni preliminari sugli storyboard](storyboards-overview.md)|Descrive come usare gli storyboard con più sequenze temporali per creare animazioni complesse.|
|[Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)|Descrive i <xref:System.Windows.Media.Animation.Timeline> tipi e le proprietà utilizzati nelle animazioni.|
|[Cenni preliminari sugli eventi di tempo](timing-events-overview.md)|Vengono descritti gli eventi disponibili negli <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> oggetti e per l'esecuzione di codice nei punti della sequenza temporale, ad esempio Begin, pause, Resume, Skip o stop.|
|[Procedure](animation-and-timing-how-to-topics.md)|Contiene esempi di codice per usare animazioni e sequenze temporali in un'applicazione.|
|[Procedure relative a oggetti Clock](clocks-how-to-topics.md)|Contiene esempi di codice per l'utilizzo dell' <xref:System.Windows.Media.Animation.Clock> oggetto nell'applicazione.|
|[Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni con fotogrammi chiave in un'applicazione.|
|[Procedure relative all'animazione percorso](path-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni basate su tracciato in un'applicazione.|

<a name="reference"></a>

## <a name="reference"></a>Riferimento

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
