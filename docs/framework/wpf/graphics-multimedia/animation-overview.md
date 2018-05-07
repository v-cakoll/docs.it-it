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
ms.openlocfilehash: 5fb9550ddce4ead900206c2ece2f976ab8b42c4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="animation-overview"></a>Cenni preliminari sull'animazione
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un potente set di elementi grafici e layout funzionalità che consentono di creare interfacce utente accattivanti e documenti accattivanti. L'animazione può migliorare ulteriormente l'aspetto e la facilità di uso dell'interfaccia utente. Applicando semplicemente animare un colore di sfondo oppure utilizzando un oggetto animato <xref:System.Windows.Media.Transform>, è possibile creare transizioni schermata significativo o fornire utili segnali visivi.  
  
 Questa panoramica fornisce un'introduzione al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di animazione e temporizzazione. Si concentra sull'animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti tramite storyboard.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Introduzione alle animazioni  
 L'animazione è un'illusione ottica creata scorrendo rapidamente una serie di immagini, ognuna leggermente diversa dall'ultima. Il cervello percepisce il gruppo di immagini come un'unica scena che si modifica. Nei film questa illusione viene creata usando fotocamere che registrano molte fotografie (fotogrammi) al secondo. Quando i fotogrammi vengono riprodotti con un proiettore, il pubblico vede un'immagine in movimento.  
  
 L'animazione in un computer è simile. Un programma che applica una dissolvenza in uscita al disegno di un rettangolo funziona ad esempio nel modo indicato di seguito.  
  
-   Il programma crea un timer.  
  
-   Il programma controlla il timer a intervalli stabiliti per rilevare la quantità di tempo trascorso.  
  
-   Ogni volta che il programma controlla il timer, calcola anche il valore di opacità per il rettangolo in base al tempo trascorso.  
  
-   Il programma aggiorna quindi il rettangolo in base al nuovo valore e lo ridisegna.  
  
 Prima di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] gli sviluppatori dovevano creare e gestire i propri sistemi di temporizzazione oppure utilizzare speciali librerie personalizzate. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include un efficiente sistema di temporizzazione viene esposta tramite codice gestito e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e che è perfettamente integrato nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework. Le funzionalità disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplificano l'applicazione di animazioni ai controlli e ad altri oggetti grafici.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue in modo efficiente tutte le attività automatiche di gestione del sistema di temporizzazione e di aggiornamento dello schermo grazie a classi di temporizzazione che consentono di concentrarsi sugli effetti da creare anziché sulle operazioni per ottenerli. Esponendo le classi di base di animazione da cui le classi dell'utente possono ereditare, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] semplifica anche la creazione di animazioni personalizzate che sfruttano molti vantaggi in termini di prestazioni delle classi di animazione standard.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Sistema di animazione delle proprietà WPF  
 Se si comprende alcuni concetti importanti sul sistema di temporizzazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazioni possono essere più facile da utilizzare. Più importante è che, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si aggiunge un'animazione oggetti applicando l'animazione alle relative proprietà. Ad esempio, per ingrandire un elemento del framework, si aggiunge un'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà. Per fare un oggetto dalla visualizzazione, si aggiunge un'animazione relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà.  
  
 Affinché una proprietà disponga di funzionalità di animazione, devono essere soddisfatti i tre requisiti seguenti:  
  
-   Deve essere una proprietà di dipendenza.  
  
-   Deve appartenere a una classe che eredita da <xref:System.Windows.DependencyObject> e implementa il <xref:System.Windows.Media.Animation.IAnimatable> interfaccia.  
  
-   Deve essere disponibile un tipo di animazione compatibile. (Se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non ne fornisce uno, è possibile creare. Vedere il [panoramica delle animazioni personalizzate](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene molti oggetti con <xref:System.Windows.Media.Animation.IAnimatable> proprietà. I controlli come <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.TabControl>, nonché <xref:System.Windows.Controls.Panel> e <xref:System.Windows.Shapes.Shape> oggetti ereditano da <xref:System.Windows.DependencyObject>. La maggior parte delle proprietà di tali oggetti è rappresentata da proprietà di dipendenza.  
  
 È possibile usare le animazioni quasi ovunque, ad esempio in stili e modelli del controllo. Le animazioni non devono necessariamente essere oggetti visivi ed è possibile animare oggetti che non appartengono all'interfaccia utente se soddisfano i criteri descritti in questa sezione.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Esempio - Applicare a un elemento una dissolvenza in entrata e in uscita  
 In questo esempio viene illustrato come utilizzare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animazione per animare il valore di una proprietà di dipendenza. Usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, che è un tipo di animazione che genera l'errore <xref:System.Double> valori, da cui iniziare l'animazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà di un <xref:System.Windows.Shapes.Rectangle>. Di conseguenza, il <xref:System.Windows.Shapes.Rectangle> dissolvenza rimosso dalla visualizzazione.  
  
 Nella prima parte dell'esempio creato un <xref:System.Windows.Shapes.Rectangle> elemento. I passaggi che seguono viene illustrato come creare un'animazione e applicarla al rettangolo <xref:System.Windows.UIElement.Opacity%2A> proprietà.
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Shapes.Rectangle> elemento in un <xref:System.Windows.Controls.StackPanel> in XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Shapes.Rectangle> elemento in un <xref:System.Windows.Controls.StackPanel> nel codice.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Parte 1 - Creare un oggetto DoubleAnimation  
 Per fare un elemento rimosso dalla visualizzazione, è possibile animare la <xref:System.Windows.UIElement.Opacity%2A> proprietà. Poiché il <xref:System.Windows.UIElement.Opacity%2A> proprietà è di tipo <xref:System.Double>, è necessaria un'animazione che produce valori double. Oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> è un'animazione di questo tipo. Oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> crea una transizione tra due valori double. Per specificare il valore iniziale, impostare il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà. Per specificare il valore finale, impostare il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.  
  
1.  Un valore di opacità `1.0` rende l'oggetto completamente opaco e un valore di opacità `0.0` rende completamente invisibile. Per eseguire la transizione di animazione da `1.0` per `0.0` impostare relativo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà `1.0` e il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà `0.0`. Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Animation.DoubleAnimation> nel codice.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  Successivamente, è necessario specificare un <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di un'animazione specifica il tempo impiegato per passare dal valore iniziale al valore di destinazione. Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> a cinque secondi in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> a cinque secondi nel codice.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  Il codice precedente ha mostrato un'animazione che esegue la transizione da `1.0` a `0.0`, che fa sì che l'elemento destinazione gradualmente da completamente opaco completamente invisibile. Per fare l'elemento in visualizzazione dopo torni, impostare il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà dell'animazione per `true`. Affinché l'animazione ripetere all'infinito, impostare il relativo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà nel codice.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Parte 2 - Creare uno storyboard  
 Per applicare un'animazione a un oggetto, si crea un <xref:System.Windows.Media.Animation.Storyboard> e utilizzare il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> allegati proprietà per specificare l'oggetto e proprietà da animare.  
  
1.  Creare il <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio. Nell'esempio seguente viene illustrato come creare il <xref:System.Windows.Media.Animation.Storyboard> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     Per creare il <xref:System.Windows.Media.Animation.Storyboard> nel codice, dichiarare un <xref:System.Windows.Media.Animation.Storyboard> variabile a livello di classe.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Quindi inizializzare la <xref:System.Windows.Media.Animation.Storyboard> e aggiungere l'animazione come figlio.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  Il <xref:System.Windows.Media.Animation.Storyboard> deve conoscere la posizione in cui applicare l'animazione. Utilizzare il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà associata per specificare l'oggetto da cui iniziare l'animazione. Nell'esempio seguente viene illustrato come impostare il nome di destinazione di <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Nell'esempio seguente viene illustrato come impostare il nome di destinazione di <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` nel codice.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Utilizzare il <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> proprietà associata per specificare la proprietà da animare. Nell'esempio seguente viene illustrato come configurare l'animazione di destinazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà del <xref:System.Windows.Shapes.Rectangle> in XAML.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Nell'esempio seguente viene illustrato come configurare l'animazione di destinazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà del <xref:System.Windows.Shapes.Rectangle> nel codice.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> sintassi e per altri esempi, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML) - Associare lo storyboard a un trigger  
 Il modo più semplice per applicare e avviare un <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nell'utilizzare un trigger di evento. In questa sezione viene illustrato come associare il <xref:System.Windows.Media.Animation.Storyboard> con un trigger in XAML.  
  
1.  Creare un <xref:System.Windows.Media.Animation.BeginStoryboard> dell'oggetto e associare lo storyboard. Oggetto <xref:System.Windows.Media.Animation.BeginStoryboard> è un tipo di <xref:System.Windows.TriggerAction> che applica e avvia un <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Creare un <xref:System.Windows.EventTrigger> e aggiungere il <xref:System.Windows.Media.Animation.BeginStoryboard> al relativo <xref:System.Windows.EventTrigger.Actions%2A> insieme. Impostare il <xref:System.Windows.EventTrigger.RoutedEvent%2A> proprietà del <xref:System.Windows.EventTrigger> per l'evento indirizzato che si desidera avviare il <xref:System.Windows.Media.Animation.Storyboard>. (Per ulteriori informazioni sugli eventi indirizzati, vedere il [indirizzato Cenni preliminari sugli eventi](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Aggiungere il <xref:System.Windows.EventTrigger> per il <xref:System.Windows.FrameworkElement.Triggers%2A> insieme del rettangolo.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (codice) - Associare lo storyboard a un gestore eventi  
 Il modo più semplice per applicare e avviare un <xref:System.Windows.Media.Animation.Storyboard> nel codice consiste nell'utilizzare un gestore eventi. In questa sezione viene illustrato come associare il <xref:System.Windows.Media.Animation.Storyboard> con un gestore eventi nel codice.  
  
1.  Eseguire la registrazione per il <xref:System.Windows.FrameworkElement.Loaded> evento del rettangolo.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Dichiarare il gestore eventi. Nel gestore eventi, utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per applicare lo storyboard.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Esempio completo  
 Di seguito viene illustrato come creare un rettangolo che si visualizza in XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 L'esempio seguente illustra come creare un rettangolo a cui viene applicata la dissolvenza in entrata e in uscita nel codice.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Tipi di animazione  
 Poiché le animazioni generano valori di proprietà, per i diversi tipi di proprietà esistono tipi di animazione differenti. Per aggiungere un'animazione a una proprietà che accetta un <xref:System.Double>, ad esempio il <xref:System.Windows.FrameworkElement.Width%2A> proprietà di un elemento, utilizzare un'animazione che produce <xref:System.Double> valori. Per aggiungere un'animazione a una proprietà che accetta un <xref:System.Windows.Point>, utilizzare un'animazione che produce <xref:System.Windows.Point> valori e così via. A causa del numero di diversi tipi di proprietà, sono disponibili diverse classi di <xref:System.Windows.Media.Animation> dello spazio dei nomi. che fortunatamente seguono una convenzione di denominazione rigorosa che ne facilita la differenziazione:  
  
-   \<*Tipo*> animazione  
  
     Nota come animazione "From/To/By" o "di base", viene applicata tra un valore iniziale e un valore di destinazione o con l'aggiunta di un valore di offset al valore iniziale.  
  
    -   Per specificare un valore iniziale, impostare la proprietà From dell'animazione.  
  
    -   Per specificare un valore finale, impostare la proprietà To dell'animazione.  
  
    -   Per specificare un valore di offset, impostare la proprietà By dell'animazione.  
  
     Gli esempi del presente documento usano queste animazioni perché sono le più semplici. Da/a/da animazioni sono descritti in dettaglio nella panoramica From/To/By animazioni.  
  
-   \<*Tipo*> AnimationUsingKeyFrames  
  
     Le animazioni basate su fotogrammi chiave sono più efficaci delle animazioni From/To/By perché è possibile specificare un numero qualsiasi di valori di destinazione e controllarne il metodo di interpolazione. Alcuni tipi possono essere animati solo con animazioni basate su fotogrammi chiave. Le animazioni di fotogrammi chiave vengono descritte dettagliatamente nel [Cenni preliminari sulle animazioni di fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   \<*Tipo*> AnimationUsingPath  
  
     Le animazioni basate su tracciato consentono di usare un tracciato geometrico per produrre valori animati.  
  
-   \<*Tipo*> AnimationBase  
  
     Classe astratta che, quando viene implementata, aggiunge un'animazione un \< *tipo*> valore. Questa classe funge da classe base per \< *tipo*> animazione e \< *tipo*> AnimationUsingKeyFrames classi. È necessario gestire direttamente queste classi solo se si vuole creare animazioni personalizzate. In caso contrario, utilizzare un \< *tipo*> animazione o un fotogramma chiave\<*tipo*> animazione.  
  
 Nella maggior parte dei casi, è consigliabile usare il \< *tipo*> classi di animazione, ad esempio <xref:System.Windows.Media.Animation.DoubleAnimation> e <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 La tabella seguente illustra diversi tipi di animazione comuni e alcune proprietà con cui vengono usati.  
  
|Tipo di proprietà|Animazione (From/To/By) di base corrispondente|Animazione basata su fotogrammi chiave corrispondente|Animazione basata su tracciato corrispondente|Esempio di uso|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Nessuno|Animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> o <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animare la <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.FrameworkElement.Height%2A> di un <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> posizione di un <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Nessuno|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Nessuno|Animare la <xref:System.Windows.Controls.TextBlock.Text%2A> di un <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Animazioni come sequenze temporali  
 Tutti i tipi di animazione ereditano la <xref:System.Windows.Media.Animation.Timeline> classe; pertanto, tutte le animazioni sono tipi speciali di sequenze temporali. Oggetto <xref:System.Windows.Media.Animation.Timeline> definisce un segmento di tempo. È possibile specificare il *comportamenti di temporizzazione* di una sequenza temporale: relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, quante volte è ripetuto e tempo la velocità di avanzamento del.  
  
 Poiché un'animazione è un <xref:System.Windows.Media.Animation.Timeline>, rappresenta inoltre un intervallo di tempo. Un'animazione calcola anche i valori di output man mano che passa nell'intervallo di tempo specificato (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Con l'avanzamento, ovvero la riproduzione, dell'animazione, viene aggiornata la proprietà associata.  
  
 Sono tre proprietà temporali utilizzate più frequentemente <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, e <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Proprietà Duration  
 Come accennato in precedenza, una sequenza temporale rappresenta un intervallo di tempo. La lunghezza del segmento è il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> della sequenza temporale, a cui è in genere specificata usando un <xref:System.Windows.Duration.TimeSpan%2A> valore. Quando una sequenza temporale raggiunge il termine della durata, ha completato un'iterazione.  
  
 Utilizza un'animazione relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per determinare il valore corrente. Se non si specifica un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valore per un'animazione, viene utilizzato il valore predefinito di 1 secondo.  
  
 La sintassi seguente viene illustrata una versione semplificata del [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attributo sintassi per la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà.  
  
*ore* `:` *minuti* `:` *secondi*
  
 Nella tabella seguente vengono mostrate diverse <xref:System.Windows.Duration> impostazioni e i relativi valori risultante.  
  
|Impostazione|Valore risultante|  
|-------------|---------------------|  
|0:0:5.5|5,5 secondi.|  
|0:30:5.5|30 minuti e 5,5 secondi.|  
|1:30:5.5|1 ora, 30 minuti e 5,5 secondi.|  
  
 Un modo per specificare un <xref:System.Windows.Duration> nel codice consiste nell'utilizzare il <xref:System.TimeSpan.FromSeconds%2A> metodo per creare un <xref:System.TimeSpan>, quindi dichiarare una nuova <xref:System.Windows.Duration> struttura utilizzando tale <xref:System.TimeSpan>.  
  
 Per ulteriori informazioni su <xref:System.Windows.Duration> valori e completa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintassi, vedere il <xref:System.Windows.Duration> struttura.  
  
#### <a name="autoreverse"></a>Proprietà AutoReverse  
 Il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà specifica se una sequenza temporale viene riprodotta con le versioni precedenti, dopo aver raggiunto la fine del relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Se si imposta questa proprietà di animazione `true`, un'animazione viene riprodotta una volta raggiunta la fine del relativo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, ossia dal valore iniziale al valore iniziale. Per impostazione predefinita, questa proprietà è `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 Il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà specifica quante volte viene riprodotto una sequenza temporale. Per impostazione predefinita, le sequenze temporali hanno un conteggio di iterazioni di `1.0`, vale a dire che vengono riprodotti una sola volta e non vengono ripetuti.  
  
 Per ulteriori informazioni su queste e altre proprietà, vedere il [Timing Behaviors Overview](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Applicazione di un'animazione a una proprietà  
 Le sezioni precedenti descrivono i diversi tipi di animazioni e le relative proprietà temporali, mentre questa sezione illustra come applicare l'animazione alla proprietà da animare. <xref:System.Windows.Media.Animation.Storyboard> gli oggetti forniscono un modo per applicare le animazioni a proprietà. Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un *sequenza temporale contenitore* che fornisce informazioni per le animazioni che contiene.  
  
### <a name="targeting-objects-and-properties"></a>Oggetti di destinazione e proprietà  
 Il <xref:System.Windows.Media.Animation.Storyboard> classe fornisce il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> le proprietà associate. Se si impostano tali proprietà in un'animazione, si indica l'oggetto da animare. Affinché un oggetto possa diventare la destinazione di un'animazione, è tuttavia necessario assegnargli un nome.  
  
 Assegnazione di un nome di un <xref:System.Windows.FrameworkElement> rispetto all'assegnazione di un nome di un <xref:System.Windows.Freezable> oggetto. La maggior parte dei controlli e dei pannelli sono elementi del framework, mentre gli oggetti più strettamente grafici, ad esempio pennelli, trasformazioni e geometrie, sono bloccabili. Se non si è certi che un tipo sia un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.Freezable>, consultare il **gerarchia di ereditarietà** sezione della documentazione di riferimento.  
  
-   Per rendere un <xref:System.Windows.FrameworkElement> la destinazione di un'animazione, si assegnargli un nome impostando il relativo <xref:System.Windows.FrameworkElement.Name%2A> proprietà. Nel codice, è necessario utilizzare anche il <xref:System.Windows.FrameworkElement.RegisterName%2A> metodo per registrare il nome dell'elemento con la pagina a cui appartiene.  
  
-   Per rendere un <xref:System.Windows.Freezable> oggetto di destinazione di un'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], si utilizza il [direttiva X:Name](../../../../docs/framework/xaml-services/x-name-directive.md) per assegnare un nome. Nel codice, è sufficiente utilizzare il <xref:System.Windows.FrameworkElement.RegisterName%2A> metodo per registrare l'oggetto con la pagina a cui appartiene.  
  
 Le sezioni seguenti viene fornito un esempio di un elemento nella denominazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e il codice. Per informazioni più dettagliate sulla denominazione e di destinazione, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Applicazione e avvio di storyboard  
 Per avviare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], associarlo a un <xref:System.Windows.EventTrigger>. Un <xref:System.Windows.EventTrigger> è un oggetto che descrive le azioni da intraprendere quando si verifica un evento specificato. Può essere uno di tali azioni un <xref:System.Windows.Media.Animation.BeginStoryboard> azione, che consente di avviare lo storyboard. I trigger di evento sono concettualmente analoghi ai gestori eventi poiché consentono di specificare il modo in cui l'applicazione risponde a un determinato evento. A differenza dei gestori eventi, i trigger di evento possono essere descritti dettagliatamente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; nessun altro codice è obbligatorio.  
  
 Per avviare un <xref:System.Windows.Media.Animation.Storyboard> nel codice, è possibile utilizzare un <xref:System.Windows.EventTrigger> o utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo la <xref:System.Windows.Media.Animation.Storyboard> classe.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Controllo interattivo di uno storyboard  
 L'esempio precedente illustra come avviare un <xref:System.Windows.Media.Animation.Storyboard> quando si verifica un evento. È possibile controllare anche in modo interattivo un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio: è possibile sospendere, riprendere, arrestare, spostarlo al periodo di riempimento, ricerca e rimuovere il <xref:System.Windows.Media.Animation.Storyboard>. Per ulteriori informazioni e un esempio che illustra come controllare in modo interattivo un <xref:System.Windows.Media.Animation.Storyboard>, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Effetti del termine di un'animazione  
 Il <xref:System.Windows.Media.Animation.FillBehavior> proprietà specifica il comportamento di una sequenza temporale quando termina. Per impostazione predefinita, viene avviata una sequenza temporale <xref:System.Windows.Media.Animation.ClockState.Filling> alla data di fine. Un'animazione che <xref:System.Windows.Media.Animation.ClockState.Filling> contiene il valore di output finale.  
  
 Il <xref:System.Windows.Media.Animation.DoubleAnimation> nell'esempio precedente non termina perché il relativo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> è impostata su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. L'esempio seguente anima un rettangolo usando un'animazione analoga. A differenza dell'esempio precedente, il <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> e <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> le proprietà di questa animazione vengono lasciate sui rispettivi valori predefiniti. e di conseguenza l'animazione avanza da 1 a 0 in un intervallo di cinque secondi per poi arrestarsi.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Poiché il relativo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> non è stato modificato rispetto al valore predefinito, ovvero <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, l'animazione mantiene il valore finale, 0, la fine. Pertanto, il <xref:System.Windows.UIElement.Opacity%2A> del rettangolo rimane impostata su 0 al termine dell'animazione termina. Se si imposta la <xref:System.Windows.UIElement.Opacity%2A> del rettangolo da un altro valore, il codice sembra non hanno alcun effetto, poiché l'animazione è ancora che interessano la <xref:System.Windows.UIElement.Opacity%2A> proprietà.  
  
 Un modo per ottenere nuovamente il controllo di una proprietà animata nel codice consiste nell'utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> (metodo) e specificare null per il <xref:System.Windows.Media.Animation.AnimationTimeline> parametro. Per ulteriori informazioni e un esempio, vedere [impostarla una proprietà dopo l'animazione di uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Si noti che, sebbene l'impostazione di un valore della proprietà che ha un <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> sembra non hanno alcun effetto animazione, modificare il valore della proprietà. Per ulteriori informazioni, vedere il [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Data binding e animazione di animazioni  
 La maggior parte delle proprietà di animazione può essere associata a dati o animata; ad esempio, è possibile animare la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà di un <xref:System.Windows.Media.Animation.DoubleAnimation>. A causa della modalità di funzionamento del sistema di temporizzazione, tuttavia, le animazioni associate a dati o animate si comportano in modo diverso rispetto ad altri oggetti associati a dati o animati. Per comprendere questo comportamento, è opportuno capire il significato dell'applicazione di un'animazione a una proprietà.  
  
 Fare riferimento all'esempio nella sezione precedente che è stato illustrato come aggiungere un'animazione di <xref:System.Windows.UIElement.Opacity%2A> di un rettangolo. Quando viene caricato il rettangolo nell'esempio precedente, il trigger di evento si applica il <xref:System.Windows.Media.Animation.Storyboard>. Il sistema di temporizzazione crea una copia del <xref:System.Windows.Media.Animation.Storyboard> e l'animazione. Queste copie sono bloccate (resa di sola lettura) e <xref:System.Windows.Media.Animation.Clock> vengono creati oggetti da esse. che animano effettivamente le proprietà di destinazione.  
  
 Il sistema di temporizzazione crea un orologio per il <xref:System.Windows.Media.Animation.DoubleAnimation> e viene applicato all'oggetto e la proprietà specificata per il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation>. In questo caso, il sistema di temporizzazione applica l'orologio per il <xref:System.Windows.UIElement.Opacity%2A> proprietà dell'oggetto denominato "MyRectangle".  
  
 Anche se viene creato un orologio anche per il <xref:System.Windows.Media.Animation.Storyboard>, l'orologio non viene applicato a qualsiasi proprietà. Il suo scopo è controllare figlio il proprio orologio, ossia che viene creato per il <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Affinché un'animazione rifletta le modifiche di data binding, è necessario rigenerarne l'orologio. Gli orologi non vengono rigenerati automaticamente. Per creare un'animazione a riflettere le modifiche, riapplicare dello storyboard, utilizzando un <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo. Quando si usa uno di questi metodi, l'animazione viene riavviata. Nel codice, è possibile utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> eseguire il metodo per spostare lo storyboard nella posizione precedente.  
  
 Per un esempio di un tipo di dati animazione associata, vedere [chiave Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011). Per ulteriori informazioni sul funzionamento del sistema di animazione e temporizzazione, vedere [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Altri modi per applicare un'animazione  
 Gli esempi del presente documento illustrano come applicare animazioni tramite storyboard. Quando si usa il codice, è possibile eseguire questa operazione in diversi altri modi. Per ulteriori informazioni, vedere il [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Esempi di animazione  
 Gli esempi seguenti consentono di iniziare ad aggiungere animazione alle applicazioni.  
  
-   [Esempio di valori di destinazione dell'animazione From/To/By](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Descrive le diverse impostazioni From/To/By.  
  
-   [Esempio di comportamento temporale di un'animazione](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Illustra le diverse modalità per controllare il comportamento temporale di un'animazione. Questo esempio illustra anche come associare a dati il valore di destinazione di un'animazione.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Cenni preliminari sull'animazione e sul sistema di temporizzazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Viene descritto come il sistema di temporizzazione utilizza il <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock> classi, che consentono di creare animazioni.|  
|[Suggerimenti sulle animazioni](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Contiene suggerimenti utili per la risoluzione di problemi relativi alle animazioni, ad esempio problemi di prestazioni.|  
|[Cenni preliminari sulle animazioni personalizzate](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Descrive come estendere il sistema dell'animazione con fotogrammi chiave, classi di animazione o callback per fotogramma.|  
|Cenni preliminari sulle animazioni From/To/By|Descrive come creare un'animazione che effettua la transizione tra due valori.|  
|[Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Descrive come creare un'animazione con più valori di destinazione, inclusa la possibilità di controllare il metodo di interpolazione.|  
|[Funzioni di interpolazione](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Descrive come applicare formule matematiche alle animazioni per ottenere un comportamento realistico, ad esempio un effetto di rimbalzo.|  
|[Panoramica sulle animazioni tracciato](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Descrive come spostare o ruotare un oggetto lungo un tracciato complesso.|  
|[Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Descrive le animazioni di proprietà in cui si usano storyboard, animazioni locali, orologi e animazioni per fotogramma.|  
|[Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Descrive come usare gli storyboard con più sequenze temporali per creare animazioni complesse.|  
|[Cenni preliminari sui comportamenti temporali](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Viene descritto il <xref:System.Windows.Media.Animation.Timeline> tipi e le proprietà utilizzati nelle animazioni.|  
|[Cenni preliminari sugli eventi di tempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Vengono descritti gli eventi disponibili sul <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock> oggetti per l'esecuzione di codice in punti nella sequenza temporale, ad esempio avviare, sospendere, riprendere, ignorare o arrestare.|  
|[Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Contiene esempi di codice per usare animazioni e sequenze temporali in un'applicazione.|  
|[Procedure relative a oggetti Clock](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Contiene esempi di codice per l'utilizzo di <xref:System.Windows.Media.Animation.Clock> oggetto nell'applicazione.|  
|[Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni con fotogrammi chiave in un'applicazione.|  
|[Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Contiene esempi di codice per l'uso di animazioni basate su tracciato in un'applicazione.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
