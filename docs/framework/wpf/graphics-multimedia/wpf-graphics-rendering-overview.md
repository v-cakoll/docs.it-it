---
title: Cenni preliminari sul rendering della grafica WPF
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
helpviewer_keywords:
- graphics [WPF], rendering
- rendering graphics [WPF]
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: "51"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfb9a546ca33b848fbbcbd114951eddc5b000663
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-graphics-rendering-overview"></a>Cenni preliminari sul rendering della grafica WPF
Questo argomento offre una panoramica del livello visivo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Viene analizzato il ruolo del <xref:System.Windows.Media.Visual> classe per il rendering di supporto nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello.  
  
  
<a name="role_of_visual_object"></a>   
## <a name="role-of-the-visual-object"></a>Ruolo dell'oggetto visivo  
 Il <xref:System.Windows.Media.Visual> classe è l'astrazione di base da cui ogni <xref:System.Windows.FrameworkElement> oggetto deriva. Viene anche usata come punto di ingresso per la scrittura di nuovi controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e in molti casi può essere considerata come l'handle di finestra (HWND) nel modello di applicazione Win32.  
  
 Il <xref:System.Windows.Media.Visual> oggetto è un core [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto, il cui ruolo primario è di fornire supporto per il rendering. Controlli dell'interfaccia utente, ad esempio <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.TextBox>, derivare la <xref:System.Windows.Media.Visual> e come utilizzarla per mantenere i dati di rendering. Il <xref:System.Windows.Media.Visual> oggetto fornisce supporto per:  
  
-   Visualizzazione dell'output: eseguire il rendering del contenuto del disegno serializzato e salvato in modo permanente di un oggetto visivo.  
  
-   Trasformazioni: eseguire trasformazioni su un oggetto visivo.  
  
-   Ritaglio: offrire supporto dell'area di ritaglio per un oggetto visivo.  
  
-   Hit testing: determinare se una coordinata o una geometria è contenuta all'interno di un oggetto visivo.  
  
-   Calcoli relativi al rettangolo di selezione: determinare il rettangolo delimitatore di un oggetto visivo.  
  
 Tuttavia, il <xref:System.Windows.Media.Visual> oggetto non include il supporto per funzionalità non per il rendering, ad esempio:  
  
-   Gestione di eventi  
  
-   Layout  
  
-   Stili  
  
-   Associazione dati  
  
-   Globalizzazione  
  
 <xref:System.Windows.Media.Visual>viene esposto come classe astratta da cui devono essere derivate classi figlie pubblica. La figura seguente illustra la gerarchia degli oggetti visivi esposti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 ![Diagramma delle classi derivate dall'oggetto Visual](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
Gerarchia delle classi visive  
  
### <a name="drawingvisual-class"></a>Classe DrawingVisual  
 Il <xref:System.Windows.Media.DrawingVisual> è una classe utilizzata per eseguire il rendering di testo, immagini o forme di disegno semplificata. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, che migliora le prestazioni di runtime. Per questo motivo, i disegni sono ideali per sfondi e ClipArt. Il <xref:System.Windows.Media.DrawingVisual> può essere utilizzato per creare un oggetto visivo personalizzato. Per altre informazioni, vedere [Uso degli oggetti DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
### <a name="viewport3dvisual-class"></a>Classe Viewport3DVisual  
 Il <xref:System.Windows.Media.Media3D.Viewport3DVisual> offre un bridge tra 2D <xref:System.Windows.Media.Visual> e <xref:System.Windows.Media.Media3D.Visual3D> oggetti. La <xref:System.Windows.Media.Media3D.Visual3D> classe è la classe base per tutti gli elementi visivi 3D. Il <xref:System.Windows.Media.Media3D.Viewport3DVisual> che è necessario definire un <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> valore e un <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> valore. La camera consente di visualizzare la scena. Il viewport stabilisce dove viene eseguito il mapping della proiezione sulla superficie 2D. Per altre informazioni sul 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Cenni preliminari sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  
  
### <a name="containervisual-class"></a>Classe ContainerVisual  
 Il <xref:System.Windows.Media.ContainerVisual> classe viene utilizzata come un contenitore per una raccolta di <xref:System.Windows.Media.Visual> oggetti. Il <xref:System.Windows.Media.DrawingVisual> deriva dalla classe di <xref:System.Windows.Media.ContainerVisual> (classe), in modo che possa contenere una raccolta di oggetti visivi.  
  
### <a name="drawing-content-in-visual-objects"></a>Contenuto del disegno in oggetti visivi  
 Oggetto <xref:System.Windows.Media.Visual> oggetto archivia i dati di rendering come un **elenco di istruzioni di grafica vettoriale**. Ogni elemento nell'elenco di istruzioni rappresenta un set di dati grafici di basso livello e risorse associate in un formato serializzato. Esistono quattro diversi tipi di dati di rendering che possono contenere il contenuto del disegno.  
  
|Tipo di contenuto del disegno|Descrizione|  
|--------------------------|-----------------|  
|Grafica vettoriale|Rappresenta vector dati grafici e i relativi <xref:System.Windows.Media.Brush> e <xref:System.Windows.Media.Pen> informazioni.|  
|Image|Rappresenta un'immagine all'interno di un'area definita da un <xref:System.Windows.Rect>.|  
|Icona|Rappresenta un disegno che esegue il rendering di un <xref:System.Windows.Media.GlyphRun>, che è una sequenza di glifi da una risorsa di tipo di carattere specificata. Ecco come viene rappresentato il testo.|  
|Video|Rappresenta un disegno che esegue il rendering di video.|  
  
 Il <xref:System.Windows.Media.DrawingContext> consente di inserire un <xref:System.Windows.Media.Visual> con contenuto visivo. Quando si utilizza un <xref:System.Windows.Media.DrawingContext> comandi di disegno dell'oggetto, si archivia un set di dati di rendering che verranno successivamente utilizzati dal sistema di grafica; non si disegna sullo schermo in tempo reale.  
  
 Quando si crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di controllo, ad esempio un <xref:System.Windows.Controls.Button>, il controllo genera in modo implicito i dati di rendering per il disegno stesso. Ad esempio, impostando il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà del <xref:System.Windows.Controls.Button> , il controllo archiviare una rappresentazione per il rendering di un glifo.  
  
 Oggetto <xref:System.Windows.Media.Visual> descrive il proprio contenuto come uno o più <xref:System.Windows.Media.Drawing> gli oggetti contenuti all'interno di un <xref:System.Windows.Media.DrawingGroup>. Oggetto <xref:System.Windows.Media.DrawingGroup> descrive inoltre le maschere di opacità, trasformazioni, gli effetti bitmap e altre operazioni che vengono applicate al relativo contenuto. <xref:System.Windows.Media.DrawingGroup>le operazioni vengono applicate nell'ordine seguente quando viene eseguito il rendering di contenuto: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>e quindi <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Nella figura seguente viene illustrato l'ordine in cui <xref:System.Windows.Media.DrawingGroup> le operazioni vengono applicate durante la sequenza di rendering.  
  
 ![Ordine delle operazioni DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Ordine delle operazioni DrawingGroup  
  
 Per altre informazioni, vedere [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
#### <a name="drawing-content-at-the-visual-layer"></a>Contenuto del disegno a livello visivo  
 Non creare direttamente un'istanza un <xref:System.Windows.Media.DrawingContext>; tuttavia, è possibile, acquisire un contesto di disegno da determinati metodi, ad esempio <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>. Nell'esempio seguente viene recuperato un <xref:System.Windows.Media.DrawingContext> da un <xref:System.Windows.Media.DrawingVisual> e viene utilizzato per disegnare un rettangolo.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### <a name="enumerating-drawing-content-at-the-visual-layer"></a>Enumerazione del contenuto del disegno a livello visivo  
 Oltre agli altri utilizzi <xref:System.Windows.Media.Drawing> oggetti forniscono anche un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.  
  
> [!NOTE]
>  Quando si sta enumerando il contenuto dell'oggetto visivo, vengono recuperati <xref:System.Windows.Media.Drawing> oggetti e non la rappresentazione sottostante dei dati di rendering come un elenco di istruzioni di grafica vettoriale.  
  
 L'esempio seguente usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> valore di un <xref:System.Windows.Media.Visual> e di eseguirne l'enumerazione.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## <a name="how-visual-objects-are-used-to-build-controls"></a>Uso degli oggetti visivi per la compilazione di controlli  
 Molti degli oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono costituiti da altri oggetti visivi, cioè possono contenere gerarchie variabili di oggetti discendenti. Molti degli elementi dell'interfaccia utente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ad esempio i controlli, sono composti da più oggetti visivi che rappresentano tipi diversi di elementi di rendering. Ad esempio, il <xref:System.Windows.Controls.Button> controllo può contenere un numero di altri oggetti, inclusi <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter>, e <xref:System.Windows.Controls.TextBlock>.  
  
 Il codice seguente illustra un <xref:System.Windows.Controls.Button> controllo definita nel markup.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Se decide di enumerare gli oggetti visivi che costituiscono il valore predefinito <xref:System.Windows.Controls.Button> controllo, si otterrebbe la gerarchia degli oggetti visivi illustrata di seguito:  
  
 ![Diagramma della gerarchia struttura ad albero visuale](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.gif "VisualLayerOverview03")  
Diagramma della gerarchia di una struttura ad albero visuale  
  
 Il <xref:System.Windows.Controls.Button> controllo contiene un <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> elemento, che a sua volta, contiene un <xref:System.Windows.Controls.ContentPresenter> elemento. Il <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> elemento è responsabile della creazione di un bordo e uno sfondo per il <xref:System.Windows.Controls.Button>. Il <xref:System.Windows.Controls.ContentPresenter> è responsabile della visualizzazione del contenuto dell'elemento di <xref:System.Windows.Controls.Button>. In questo caso, poiché viene visualizzato il testo, il <xref:System.Windows.Controls.ContentPresenter> elemento contiene un <xref:System.Windows.Controls.TextBlock> elemento. Il fatto che il <xref:System.Windows.Controls.Button> controlli utilizza una <xref:System.Windows.Controls.ContentPresenter> indica che il contenuto potrebbe essere rappresentato da altri elementi, ad esempio un <xref:System.Windows.Controls.Image> o una geometria, ad esempio un <xref:System.Windows.Media.EllipseGeometry>.  
  
### <a name="control-templates"></a>Modelli di controllo  
 La chiave per l'espansione di un controllo in una gerarchia dei controlli è il <xref:System.Windows.Controls.ControlTemplate>. Un modello di controllo specifica la gerarchia visiva predefinita per un controllo. Quando si fa riferimento in modo esplicito a un controllo, si fa riferimento in modo implicito alla relativa gerarchia visiva. È possibile eseguire l'override dei valori predefiniti di un modello di controllo per creare un aspetto visivo personalizzato per un controllo. Ad esempio, è possibile modificare il valore del colore di sfondo di <xref:System.Windows.Controls.Button> controllare in modo che utilizzi un valore di colore sfumato lineare anziché un valore di colore a tinta unita. Per altre informazioni, vedere [Stili e modelli di Button](../../../../docs/framework/wpf/controls/button-styles-and-templates.md).  
  
 Un elemento dell'interfaccia utente, ad esempio un <xref:System.Windows.Controls.Button> di controllo, contiene numerosi elenchi di istruzione grafica vettoriale che descrivono la definizione di tutto il rendering di un controllo. Il codice seguente illustra un <xref:System.Windows.Controls.Button> controllo definita nel markup.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Se si esegue l'enumerazione degli oggetti visivi e vettoriale elenchi di istruzioni di grafica che costituiscono il <xref:System.Windows.Controls.Button> controllo, si otterrebbe la gerarchia di oggetti illustrata di seguito:  
  
 ![Diagramma della struttura ad albero visuale e dati di rendering](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
Diagramma della struttura ad albero e dei dati di rendering  
  
 Il <xref:System.Windows.Controls.Button> controllo contiene un <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> elemento, che a sua volta, contiene un <xref:System.Windows.Controls.ContentPresenter> elemento. Il <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> elemento è responsabile della creazione di tutti gli elementi grafici discreti che costituiscono il bordo e lo sfondo di un pulsante. Il <xref:System.Windows.Controls.ContentPresenter> è responsabile della visualizzazione del contenuto dell'elemento di <xref:System.Windows.Controls.Button>. In questo caso, poiché viene visualizzata un'immagine, il <xref:System.Windows.Controls.ContentPresenter> elemento contiene un <xref:System.Windows.Controls.Image> elemento.  
  
 Tenere in considerazione alcuni punti sulla gerarchia degli oggetti visivi e sugli elenchi di istruzioni di grafica vettoriale:  
  
-   L'ordinamento nella gerarchia rappresenta l'ordine di rendering delle informazioni di disegno. A partire dall'elemento visivo radice, gli elementi figlio vengono attraversati da sinistra a destra e dall'alto verso il basso. Se un elemento contiene elementi visivi figlio, essi vengono attraversati prima degli elementi di pari livello.  
  
-   Gli elementi dei nodi non foglia nella gerarchia, ad esempio <xref:System.Windows.Controls.ContentPresenter>, vengono utilizzati per contenere gli elementi figlio, non contengono elenchi di istruzioni.  
  
-   Se un elemento visivo contiene sia un elenco di istruzioni di grafica vettoriale che oggetti visivi figlio, viene eseguito il rendering dell'elenco di istruzioni nell'elemento visivo padre prima dei disegni in uno qualsiasi degli oggetti visivi figlio.  
  
-   Il rendering degli elementi nell'elenco di istruzioni di grafica vettoriale viene eseguito da sinistra a destra.  
  
<a name="visual_tree"></a>   
## <a name="visual-tree"></a>Struttura ad albero visuale  
 La struttura ad albero visuale contiene tutti gli elementi visivi usati nell'interfaccia utente di un'applicazione. Poiché un elemento visivo contiene informazioni sul disegno salvate in modo permanente, la struttura ad albero visuale può essere considerata come un grafico della scena, contenente tutte le informazioni di rendering necessarie per comporre l'output verso il dispositivo di visualizzazione. Questo albero è costituito da tutti gli elementi visivi creati direttamente dall'applicazione, nel codice o nel markup. La struttura ad albero visuale contiene anche tutti gli elementi visivi creati dall'espansione del modello di elementi quali controlli e oggetti dati.  
  
 Il codice seguente illustra un <xref:System.Windows.Controls.StackPanel> elemento definito nel markup.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Se decide di enumerare gli oggetti visivi che costituiscono il <xref:System.Windows.Controls.StackPanel> elemento dell'esempio di codice, si otterrebbe la gerarchia di oggetti visivi illustrata di seguito:  
  
 ![Diagramma della gerarchia struttura ad albero visuale](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.gif "VisualLayerOverview05")  
Diagramma della gerarchia di una struttura ad albero visuale  
  
### <a name="rendering-order"></a>Ordine di rendering  
 La struttura ad albero visuale determina l'ordine di rendering degli oggetti visivi e di disegno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'ordine di attraversamento inizia con l'oggetto visivo radice, ovvero il nodo superiore nella struttura ad albero visuale. Gli elementi figlio dell'oggetto visivo radice vengono quindi attraversati, da sinistra a destra. Se un oggetto visivo ha elementi figlio, questi ultimi vengono attraversati prima degli elementi di pari livello. Ciò significa che viene eseguito il rendering del contenuto di un oggetto visivo figlio prima del contenuto dell'oggetto visivo stesso.  
  
 ![Diagramma dell'ordine di rendering della struttura ad albero visuale](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.gif "VisualLayerOverview06")  
Diagramma dell'ordine di rendering della struttura ad albero visuale  
  
### <a name="root-visual"></a>Oggetto visivo radice  
 L'**oggetto visivo radice** è l'elemento di primo livello di una gerarchia struttura ad albero visuale. Nella maggior parte delle applicazioni, la classe base dell'elemento visivo radice è <xref:System.Windows.Window> o <xref:System.Windows.Navigation.NavigationWindow>. Se venissero tuttavia ospitati oggetti visivi in un'applicazione Win32, l'oggetto visivo radice sarebbe l'oggetto visivo di primo livello ospitato nella finestra Win32. Per altre informazioni, vedere [Esercitazione: hosting di oggetti visivi in un'applicazione Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### <a name="relationship-to-the-logical-tree"></a>Relazione con l'albero logico  
 L'albero logico in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rappresenta gli elementi di un'applicazione in fase di esecuzione. Sebbene questo albero non venga modificato direttamente, la visualizzazione dell'applicazione è utile per comprendere l'ereditarietà delle proprietà e il routing degli eventi. A differenza di struttura ad albero visuale, l'albero logico può rappresentare oggetti di dati non visivi, ad esempio <xref:System.Windows.Documents.ListItem>. In molti casi, l'albero logico corrisponde strettamente alle definizioni di markup dell'applicazione. Il codice seguente illustra un <xref:System.Windows.Controls.DockPanel> elemento definito nel markup.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Se si esegue l'enumerazione degli oggetti logici che costituiscono il <xref:System.Windows.Controls.DockPanel> elemento dell'esempio di codice, si otterrebbe la gerarchia degli oggetti logici illustrata di seguito:  
  
 ![Diagramma dell'albero](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.gif "Tree1_wcp")  
Diagramma dell'albero logico  
  
 La struttura ad albero visuale e l'albero logico sono sincronizzati con il set corrente di elementi dell'applicazione che riflette qualsiasi aggiunta, eliminazione o modifica di elementi. Presentano tuttavia visualizzazioni diverse dell'applicazione. A differenza di struttura ad albero visuale, l'albero logico non espande un controllo <xref:System.Windows.Controls.ContentPresenter> elemento. Ciò significa che non vi è una corrispondenza diretta tra un albero logico e una struttura ad albero visuale per lo stesso set di oggetti. Infatti, richiamando il **vengono restituiti** dell'oggetto <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> (metodo) e **VisualTreeHelper** dell'oggetto <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> con lo stesso elemento come un parametro produce risultati diversi (metodo) .  
  
 Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
### <a name="viewing-the-visual-tree-with-xamlpad"></a>Visualizzazione della struttura ad albero visuale con XamlPad  
 Lo strumento XamlPad di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un'opzione per visualizzare ed esplorare la struttura ad albero visuale che corrisponde al contenuto di [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] attualmente definito. Fare clic sul pulsante **Show Visual Tree** (Mostra struttura ad albero visuale) sulla barra dei menu per visualizzare la struttura ad albero visuale. Di seguito viene illustrata l'espansione del contenuto [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] in nodi di struttura ad albero visuale nel pannello **Visual Tree Explorer** di XamlPad:  
  
 ![Pannello Visual Tree Explorer in XamlPad](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
Pannello Visual Tree Explorer in XamlPad  
  
 Si noti come <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, e <xref:System.Windows.Controls.Button> visualizzano entrambi una gerarchia di oggetti visivi separata nel **Visual Tree Explorer** Pannello di XamlPad. In questo modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli hanno un <xref:System.Windows.Controls.ControlTemplate> che contiene la struttura ad albero visuale del controllo. Quando si fa riferimento in modo esplicito a un controllo, si fa riferimento in modo implicito alla relativa gerarchia visiva.  
  
### <a name="profiling-visual-performance"></a>Profilatura delle prestazioni visive  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite di strumenti per la profilatura delle prestazioni che consentono di analizzare il comportamento dell'applicazione in fase di esecuzione e di determinare i tipi di ottimizzazioni delle prestazioni che è possibile applicare. Lo strumento Visual Profiler offre una visualizzazione grafica completa dei dati sulle prestazioni eseguendo il mapping direttamente alla struttura ad albero visuale dell'applicazione. In questa schermata, la sezione **Utilizzo della CPU** di Visual Profiler fornisce un'indicazione dettagliata dell'uso dei servizi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da parte di un oggetto, ad esempio il layout e il rendering.  
  
 ![Visual Profiler Visualizza output](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf_VisualProfiler_04")  
Output di Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## <a name="visual-rendering-behavior"></a>Comportamento di rendering visivo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] introduce numerose funzionalità che influiscono sul comportamento di rendering degli oggetti visivi: grafica in modalità differita, grafica vettoriale e grafica indipendente dal dispositivo.  
  
### <a name="retained-mode-graphics"></a>Grafica in modalità differita  
 Uno dei fattori chiave per comprendere il ruolo dell'oggetto visivo consiste nel comprendere la differenza tra i sistemi di grafica in **modalità immediata** e in **modalità differita**. Un'applicazione Win32 standard basata su GDI o GDI+ usa un sistema di grafica in modalità immediata. Ciò significa che l'applicazione è responsabile dell'aggiornamento della porzione dell'area client invalidata, a causa di un'azione, ad esempio il ridimensionamento di una finestra o la modifica dell'aspetto visivo di un oggetto.  
  
 ![Diagramma della sequenza di rendering Win32](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
Diagramma della sequenza di rendering Win32  
  
 Al contrario, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un sistema in modalità differita. Questo significa che gli oggetti applicazione che hanno un aspetto visivo definiscono un set di dati di disegno serializzato. Dopo aver definito i dati di disegno, il sistema è responsabile della successiva risposta a tutte le richieste di aggiornamento per il rendering degli oggetti applicazione. Anche in fase di esecuzione, è possibile modificare o creare oggetti applicazione e affidarsi al sistema per rispondere alle richieste di aggiornamento. Il punto forte di un sistema di grafica in modalità differita è che le informazioni sul disegno vengono sempre salvate in modo permanente in uno stato serializzato dall'applicazione, ma la responsabilità del rendering viene lasciata al sistema. Il diagramma seguente mostra come l'applicazione si basa su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per rispondere alle richieste di aggiornamento.  
  
 ![Diagramma della sequenza di rendering WPF](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
Diagramma della sequenza di rendering WPF  
  
#### <a name="intelligent-redrawing"></a>Ridisegno intelligente  
 Uno dei maggiori vantaggi nell'uso della grafica in modalità differita è che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può ottimizzare in modo efficace ciò che deve essere ridisegnato nell'applicazione. Anche se si ha a che fare con una scena complessa con livelli di opacità variabili, in genere non è necessario scrivere un codice specifico per ottimizzare il ridisegno. Confrontare questo aspetto con la programmazione Win32 in cui può succedere di dedicare un notevole impegno per ottimizzare l'applicazione riducendo al minimo la quantità di ridisegno nell'area di aggiornamento. Vedere [Ridisegno nell'area di aggiornamento](https://msdn.microsoft.com/library/dd162909.aspx) per un esempio del tipo di complessità inclusa nell'ottimizzazione del ridisegno nelle applicazioni Win32.  
  
### <a name="vector-graphics"></a>Grafica vettoriale  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa la **grafica vettoriale** come formato per i dati di rendering. Le immagini vettoriali, che includono Scalable Vector Graphics (con estensione svg), Windows Metafile (con estensione wmf) e i tipi di carattere TrueType, archiviano i dati di rendering e li trasmettono come un elenco di istruzioni che descrivono come ricreare un'immagine mediante primitive grafiche. I tipi di carattere TrueType sono ad esempio caratteri vettoriali che descrivono un set di linee, curve e comandi, anziché una matrice di pixel. Uno dei principali vantaggi della grafica vettoriale è la possibilità di adattarsi a qualsiasi dimensione e risoluzione.  
  
 A differenza delle immagini vettoriali, le immagini bitmap archiviano i dati di rendering come rappresentazione pixel per pixel di un'immagine, di cui è stato eseguito il pre-rendering per una risoluzione specifica. Una delle differenze principali tra i formati di immagini bitmap e vettoriali è la fedeltà all'immagine originale. Quando ad esempio viene modificata la dimensione di un'immagine di origine, i sistemi di grafica bitmap allungano l'immagine, mentre i sistemi di grafica vettoriale la ridimensionano, conservandone la fedeltà.  
  
 La figura seguente illustra un'immagine di origine che è stata ridimensionata del 300%. Si notino le distorsioni visualizzate quando l'immagine di origine viene allungata come immagine bitmap anziché ridimensionata come immagine vettoriale.  
  
 ![Differenze tra grafica raster e vettoriale](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
Differenze tra grafica raster e vettoriale  
  
 Il markup seguente vengono illustrati due <xref:System.Windows.Shapes.Path> gli elementi definiti. Il secondo elemento viene utilizzato un <xref:System.Windows.Media.ScaleTransform> per ridimensionare le istruzioni di disegno del primo elemento da 300%. Si noti che le istruzioni di disegno nel <xref:System.Windows.Shapes.Path> elementi rimangono invariati.  
  
 [!code-xaml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### <a name="about-resolution-and-device-independent-graphics"></a>Informazioni sulla grafica indipendente dalla risoluzione e dal dispositivo  
 Esistono due fattori di sistema che determinano la dimensione del testo e della grafica sullo schermo: risoluzione e DPI. La risoluzione indica il numero di pixel visualizzati sullo schermo. Con l'aumento della risoluzione i pixel vengono rimpiccioliti, con la conseguente riduzione della dimensione di grafica e testo. Un'immagine visualizzata su un monitor impostato su 1024 x 768 apparirà molto più piccola quando viene modificata la risoluzione in 1600 x 1200.  
  
 L'altra impostazione di sistema, DPI, descrive le dimensioni di un pollice di schermo in pixel. La maggior parte dei sistemi [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ha un valore DPI di 96 che indica che un pollice di schermo è pari a 96 pixel. Se si aumenta l'impostazione DPI il pollice di schermo diventa più grande; se si diminuisce, il pollice di schermo diventa più piccolo. Ciò significa che, nella maggior parte dei sistemi, un pollice di schermo non ha le stesse dimensioni di un pollice reale. Quando si aumenta il valore DPI, il testo e la grafica compatibili con DPI diventano più grandi poiché viene aumentata la dimensione del pollice di schermo. L'aumento del valore DPI può rendere il testo più leggibile, soprattutto a risoluzioni elevate.  
  
 Non tutte le applicazioni sono compatibili con il valore DPI: alcune usano i pixel hardware come unità di misura primaria. La modifica del valore DPI di sistema non ha alcun effetto su tali applicazioni. Molte altre applicazioni usano unità compatibili con DPI per descrivere le dimensioni dei tipi di carattere, ma usano i pixel per descrivere tutto il resto. L'eccessiva riduzione o l'eccessivo aumento del valore DPI può causare problemi di layout per queste applicazioni, poiché il testo delle applicazioni viene ridimensionato con l'impostazione DPI del sistema, ma non l'interfaccia utente. Questo problema è stato eliminato per le applicazioni sviluppate usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta il ridimensionamento automatico usando il pixel indipendente dal dispositivo come unità di misura primaria, anziché i pixel hardware. La grafica e il testo vengono ridimensionati correttamente senza operazioni aggiuntive da parte dello sviluppatore dell'applicazione. La figura seguente illustra un esempio di come vengono visualizzati la grafica e il testo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con impostazioni DPI diverse.  
  
 ![Grafica e testo con impostazioni DPI diverse](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm_dpi_setting_examples")  
Grafica e testo con impostazioni DPI diverse  
  
<a name="visualtreehelper_class"></a>   
## <a name="visualtreehelper-class"></a>Classe VisualTreeHelper  
 La <xref:System.Windows.Media.VisualTreeHelper> classe è una classe helper statica che fornisce funzionalità di basso livello di programmazione a livello di oggetto visivo, è utile in scenari molto specifici, ad esempio lo sviluppo di controlli personalizzati a prestazioni elevate. Nella maggior parte dei casi, il livello più alto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti framework, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.TextBlock>, offrono una maggiore flessibilità e facilità di utilizzo.  
  
### <a name="hit-testing"></a>Hit Testing  
 La <xref:System.Windows.Media.VisualTreeHelper> classe fornisce metodi per l'hit testing su oggetti visivi quando il valore predefinito supporto di hit test non soddisfa le proprie esigenze. È possibile utilizzare il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodi di <xref:System.Windows.Media.VisualTreeHelper> classe per determinare se un valore della coordinata geometria o un punto è all'interno del limite di un oggetto specifico, ad esempio un controllo o un elemento grafico. È ad esempio possibile usare l'hit testing per stabilire se un clic del mouse all'interno del rettangolo delimitatore di un oggetto rientra nella geometria di un cerchio. È anche possibile scegliere di eseguire l'override dell'implementazione predefinita dell'hit testing per eseguire calcoli di hit testing personalizzati.  
  
 Per altre informazioni sull'hit testing, vedere [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
### <a name="enumerating-the-visual-tree"></a>Enumerazione della struttura ad albero visuale  
 La <xref:System.Windows.Media.VisualTreeHelper> classe fornisce funzionalità per l'enumerazione i membri di un struttura ad albero visuale. Per recuperare un elemento padre, chiamare il <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A> metodo. Per recuperare un elemento figlio o discendente diretto, di un oggetto visivo, chiamare il <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> metodo. Questo metodo restituisce un elemento figlio <xref:System.Windows.Media.Visual> dell'elemento padre in corrispondenza dell'indice specificato.  
  
 L'esempio seguente illustra come enumerare tutti i discendenti di un oggetto visivo. Si tratta di una tecnica da usare se si desidera serializzare tutte le informazioni di rendering di una gerarchia di oggetti visivi.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 Nella maggior parte dei casi, l'albero logico è una rappresentazione più utile degli elementi di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Sebbene l'albero logico non venga modificato direttamente, la visualizzazione dell'applicazione è utile per comprendere l'ereditarietà delle proprietà e il routing degli eventi. A differenza di struttura ad albero visuale, l'albero logico può rappresentare oggetti di dati non visivi, ad esempio <xref:System.Windows.Documents.ListItem>. Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 La <xref:System.Windows.Media.VisualTreeHelper> classe fornisce metodi per la restituzione del rettangolo di delimitazione degli oggetti visivi. È possibile restituire il rettangolo di delimitazione di un oggetto visivo chiamando <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>. È possibile restituire il rettangolo di delimitazione di tutti i discendenti di un oggetto visivo, inclusi l'oggetto visivo stesso, chiamando <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>. Il codice seguente illustra come calcolare il rettangolo delimitatore di un oggetto visivo e di tutti i relativi discendenti.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 <xref:System.Windows.Media.DrawingVisual>  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Uso degli oggetti DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [Esercitazione: hosting di oggetti visivi in un'applicazione Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
