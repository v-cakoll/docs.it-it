---
title: Cenni preliminari sugli elementi Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: f8fd3237d71bc1960678565192c7ef9ddcb2c366
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674754"
---
# <a name="panels-overview"></a>Cenni preliminari sugli elementi Panel
<xref:System.Windows.Controls.Panel> gli elementi sono componenti che consentono di controllare il rendering degli elementi, ovvero le dimensioni e le dimensioni, la posizione e la disposizione del contenuto figlio. Il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce una serie di predefinite <xref:System.Windows.Controls.Panel> elementi, nonché la possibilità di costruire custom <xref:System.Windows.Controls.Panel> elementi.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Classe Panel](#Panels_view_from_10000_feet)  
  
-   [Membri comuni degli elementi Panel](#Panels_declared_members)  
  
-   [Elementi Panel derivati](#Panels_derived_elements)  
  
-   [Elementi Panel dell'interfaccia utente](#Panels_main_UI_elements)  
  
-   [Elementi Panel annidati](#Panels_nested_panel_elements)  
  
-   [Elementi Panel personalizzati](#Panels_custom_panel_elements)  
  
-   [Supporto per la globalizzazione o la localizzazione](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Classe Panel  
 <xref:System.Windows.Controls.Panel> è la classe base per tutti gli elementi che forniscono un layout di supporto [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Derivato <xref:System.Windows.Controls.Panel> gli elementi vengono usati per posizionare e disporre gli elementi in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e codice.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite completa di implementazioni di elementi Panel derivati che abilitano numerosi layout complessi. Tali classi derivate espongono proprietà e metodi che consentono di implementare la maggior parte degli scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] standard. Gli sviluppatori che non riescono a trovare un comportamento di disposizione degli elementi figlio che soddisfa le proprie esigenze è possibile creare nuovi layout eseguendo l'override di <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> e <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi. Per altre informazioni sui comportamenti di layout personalizzati, vedere [Elementi Panel personalizzati](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Membri comuni degli elementi Panel  
 Tutti i <xref:System.Windows.Controls.Panel> elementi supportano la base di ridimensionamento e posizionamento di proprietà definite dal <xref:System.Windows.FrameworkElement>, tra cui <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, e <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Per ulteriori informazioni sulle proprietà definite dal posizionamento <xref:System.Windows.FrameworkElement>, vedere [allineamento, margini e spaziatura interna Panoramica](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> espone le proprietà aggiuntive che sono di importanza fondamentale per comprendere e usare layout. Il <xref:System.Windows.Controls.Panel.Background%2A> proprietà viene utilizzata per riempire l'area compresa nei limiti di un elemento panel derivato con un <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A> rappresenta la raccolta di elementi figlio che la <xref:System.Windows.Controls.Panel> è costituito. <xref:System.Windows.Controls.Panel.InternalChildren%2A> rappresenta il contenuto del <xref:System.Windows.Controls.Panel.Children%2A> insieme più i membri generati dal data binding. Entrambi sono costituiti una <xref:System.Windows.Controls.UIElementCollection> degli elementi figlio ospitati nel controllo padre <xref:System.Windows.Controls.Panel>.  
  
 Panel espone inoltre un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> proprietà che può essere utilizzato per ottenere un ordine a più livelli in un oggetto derivato associata <xref:System.Windows.Controls.Panel>. I membri di un pannello <xref:System.Windows.Controls.Panel.Children%2A> insieme con un livello più elevato <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore vengono visualizzate prima di quelli con un basso <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore. Ciò è particolarmente utile per i pannelli, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.Grid> che consentono agli elementi figlio di condividere lo stesso spazio delle coordinate.  
  
 <xref:System.Windows.Controls.Panel> definisce anche il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo, che può essere utilizzato per eseguire l'override del comportamento di presentazione predefinito un <xref:System.Windows.Controls.Panel>.  
  
#### <a name="attached-properties"></a>Proprietà associate  
 Gli elementi Panel derivati usano ampiamente le proprietà associate. Una proprietà associata è un tipo specializzato di proprietà di dipendenza che non dispone della proprietà "wrapper" di [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] convenzionale. Le proprietà associate presentano una sintassi specializzata in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], illustrata in molti esempi seguenti.  
  
 Uno degli scopi di una proprietà associata è quello di consentire agli elementi figlio di archiviare valori univoci di una proprietà effettivamente definita da un elemento padre. Questa funzionalità, molto utile per il layout dell'applicazione, consente agli elementi figlio di comunicare all'elemento padre il modo in cui devono essere presentati in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Elementi Panel derivati  
 Molti oggetti derivano dalla <xref:System.Windows.Controls.Panel>, ma non tutte sono destinate all'utilizzo come provider di layout radice. Esistono sei classi panel definite (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, e <xref:System.Windows.Controls.WrapPanel>) che sono progettate specificamente per la creazione di applicazioni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Ogni elemento Panel incapsula la propria funzionalità speciale, come illustrato nella tabella seguente.  
  
|Nome elemento|Elemento Panel dell'interfaccia utente?|Descrizione|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Yes|Definisce un'area all'interno del quale è possibile posizionare in modo esplicito elementi figlio tramite coordinate relative al <xref:System.Windows.Controls.Canvas> area.|  
|<xref:System.Windows.Controls.DockPanel>|Yes|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|  
|<xref:System.Windows.Controls.Grid>|Yes|Definisce un'area flessibile della griglia costituita da righe e colonne. Gli elementi figlio di un <xref:System.Windows.Controls.Grid> possono essere posizionati con precisione usando la <xref:System.Windows.FrameworkElement.Margin%2A> proprietà.|  
|<xref:System.Windows.Controls.StackPanel>|Yes|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Gestisce il layout dei pulsanti della scheda in un <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Dispone il contenuto all'interno di un <xref:System.Windows.Controls.ToolBar> controllo.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid> Consente di disporre gli elementi figlio in una griglia con tutte le celle di uguali dimensioni.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Implementa una classe di base per i pannelli in grado di virtualizzare la raccolta di elementi figlio relativa.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Yes|Dispone e virtualizza il contenuto su una singola riga orientato orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Yes|<xref:System.Windows.Controls.WrapPanel> Posiziona gli elementi figlio in sequenza da sinistra a destra, contenuto di rilievo alla riga successiva sul bordo della casella contenitore. Ordinamento successivo procede in sequenza dall'alto verso il basso o da destra a sinistra, in base al valore di <xref:System.Windows.Controls.WrapPanel.Orientation%2A> proprietà.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Elementi Panel dell'interfaccia utente  
 In sono disponibili sei classi panel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che sono ottimizzati per supportare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenari: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, e <xref:System.Windows.Controls.WrapPanel>. Tali elementi Panel sono facili da usare, versatili ed estendibili per la maggior parte delle applicazioni.  
  
 Ogni derivato <xref:System.Windows.Controls.Panel> considera i vincoli di ridimensionamento in modo diverso. Comprendere come un <xref:System.Windows.Controls.Panel> gestisce i vincoli in direzione orizzontale o verticale possono rendere layout più prevedibile.  
  
|**Nome dell'elemento Panel**|**Dimensione x**|**Dimensione y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Vincolato al contenuto|Vincolato al contenuto|  
|<xref:System.Windows.Controls.DockPanel>|Vincolato|Vincolato|  
|<xref:System.Windows.Controls.StackPanel> (Con orientamento verticale)|Vincolato|Vincolato al contenuto|  
|<xref:System.Windows.Controls.StackPanel> (Con orientamento orizzontale)|Vincolato al contenuto|Vincolato|  
|<xref:System.Windows.Controls.Grid>|Vincolato|Vincolato, tranne nei casi in cui <xref:System.Windows.GridUnitType.Auto> si applicano alle righe e colonne|  
|<xref:System.Windows.Controls.WrapPanel>|Vincolato al contenuto|Vincolato al contenuto|  
  
 Di seguito sono disponibili descrizioni più dettagliate ed esempi di uso di ogni elemento.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 Il <xref:System.Windows.Controls.Canvas> elemento consente di posizionare il contenuto in base a assoluto *x -* e *y -* coordinate. Gli elementi possono essere disegnati in una posizione univoca. Se gli elementi occupano le stesse coordinate, l'ordine in cui vengono disegnati è determinato dall'ordine di visualizzazione nel markup.  
  
 <xref:System.Windows.Controls.Canvas> fornisce il supporto di layout più flessibile di qualsiasi <xref:System.Windows.Controls.Panel>. Proprietà Height e Width vengono usate per definire l'area dell'area di disegno e gli elementi all'interno vengono assegnati coordinate assolute relative all'area dell'elemento padre <xref:System.Windows.Controls.Canvas>. Quattro proprietà, associate <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, consente un controllo accurato del posizionamento di un oggetto all'interno di un <xref:System.Windows.Controls.Canvas>, che consente allo sviluppatore di posizionare e disporre gli elementi in modo preciso sullo schermo.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Proprietà ClipToBounds in un elemento Canvas  
 <xref:System.Windows.Controls.Canvas> possibile posizionare gli elementi figlio in qualsiasi posizione sullo schermo, anche in corrispondenza delle coordinate che sono di fuori di un proprio definita <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A>. Inoltre, <xref:System.Windows.Controls.Canvas> non dipende dalle dimensioni dei relativi elementi figlio. Di conseguenza, è possibile che un elemento figlio estenda altri elementi all'esterno del rettangolo di delimitazione dell'elemento padre <xref:System.Windows.Controls.Canvas>. Il comportamento predefinito di un <xref:System.Windows.Controls.Canvas> consiste nel consentire agli elementi figlio di essere disegnati esternamente ai limiti dell'elemento padre <xref:System.Windows.Controls.Canvas>. Se questo comportamento è indesiderato, il <xref:System.Windows.UIElement.ClipToBounds%2A> può essere impostata su `true`. In questo modo, <xref:System.Windows.Controls.Canvas> di clip in base alle proprie dimensioni. <xref:System.Windows.Controls.Canvas> è l'unico elemento di layout che consente agli elementi figlio di essere disegnate di fuori dei limiti.  
  
 Questo comportamento viene illustrato graficamente in [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050) (Esempio di confronto di proprietà Width).  
  
#### <a name="defining-and-using-a-canvas"></a>Definizione e uso di un elemento Canvas  
 Oggetto <xref:System.Windows.Controls.Canvas> è possibile creare istanze usando semplicemente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o code. Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Controls.Canvas> al posizionamento assoluto del contenuto. Questo codice produce tre quadrati di 100 pixel. Il primo quadrato è rosso e la posizione del relativo angolo superiore sinistro (*x, y*) è specificata come (0, 0). Il secondo quadrato è verde e la posizione dell'angolo superiore sinistro è impostata su (100, 100), sotto e a destra rispetto al primo quadrato. Il terzo quadrato è blu, con la posizione dell'angolo superiore sinistro impostata su (50, 50). Il quadrato ingloba pertanto il quadrante inferiore destro del primo quadrato e quello superiore sinistro del secondo. Poiché il terzo quadrato è stato disposto per ultimo, sembra posizionato sopra agli altri due e di conseguenza le porzioni sovrapposte ne assumono il colore.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento Canvas tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 Il <xref:System.Windows.Controls.DockPanel> elemento utilizza il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata come set di elementi di contenuto figlio per posizionare il contenuto lungo i bordi di un contenitore. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.Dock.Top> o <xref:System.Windows.Controls.Dock.Bottom>, gli elementi figlio di sopra o sotto l'altro. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.Dock.Left> o <xref:System.Windows.Controls.Dock.Right>, gli elementi figlio a sinistra o destra di loro. Il <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà determina la posizione dell'elemento finale aggiunto come figlio di un <xref:System.Windows.Controls.DockPanel>.  
  
 È possibile usare <xref:System.Windows.Controls.DockPanel> per posizionare un gruppo di controlli correlati, ad esempio un set di pulsanti. In alternativa, è possibile usarlo per creare una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con riquadri, analoga a quella disponibile in [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Se relativo <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> non siano specificate proprietà, <xref:System.Windows.Controls.DockPanel> dimensioni in base al contenuto. Le dimensioni possono aumentare o diminuire a seconda delle dimensioni degli elementi figlio. Tuttavia, quando queste proprietà sono specificate e non è più disponibile spazio per il successivo elemento figlio specificato, <xref:System.Windows.Controls.DockPanel> tale elemento figlio o gli elementi figlio successivi non vengono visualizzati e non misura gli elementi figlio successivi.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento "riempirà" il rimanente spazio non allocato. Se non si desidera questo comportamento, impostare il <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definizione e uso di un elemento DockPanel  
 L'esempio seguente illustra come partizionare lo spazio utilizzando un <xref:System.Windows.Controls.DockPanel>. Cinque <xref:System.Windows.Controls.Border> gli elementi vengono aggiunti come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel>. Ciascuno utilizza una diversa proprietà di posizionamento di un <xref:System.Windows.Controls.DockPanel> nello spazio di partizione. L'elemento finale riempie lo spazio rimanente non allocato.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Scenario DockPanel tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 Il <xref:System.Windows.Controls.Grid> elemento unisce le funzionalità di posizionamento assoluto e controllo dei dati tabulari. Oggetto <xref:System.Windows.Controls.Grid> consente di eseguire facilmente gli elementi di stile e posizione. <xref:System.Windows.Controls.Grid> è possibile definire raggruppamenti flessibili righe e colonne e fornisce anche un meccanismo per condividere le informazioni di ridimensionamento tra più <xref:System.Windows.Controls.Grid> elementi.  
  
#### <a name="how-is-grid-different-from-table"></a>Differenza tra gli elementi Grid e Table  
 <xref:System.Windows.Documents.Table> e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuno è adatto per scenari diversi. Oggetto <xref:System.Windows.Documents.Table> progettato per l'uso in contenuto dinamico (vedere [Cenni preliminari sui documenti dinamici](../../../../docs/framework/wpf/advanced/flow-document-overview.md) per altre informazioni sul contenuto di flusso). Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supporta contenuti comportamenti flusso come paginazione, riflusso di colonne e selezione di contenuto durante una <xref:System.Windows.Controls.Grid> non esiste. Oggetto <xref:System.Windows.Controls.Grid> d'altro canto è particolarmente utile di fuori di un <xref:System.Windows.Documents.FlowDocument> per diversi motivi, tra cui <xref:System.Windows.Controls.Grid> aggiunge gli elementi in base a un indice di riga e colonna, <xref:System.Windows.Documents.Table> non esiste. Il <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione di contenuto figlio, che consente più di un elemento esistente all'interno di un singolo "cella". <xref:System.Windows.Documents.Table> non supporta la sovrapposizione. Gli elementi figlio di un <xref:System.Windows.Controls.Grid> possono essere posizionati in modo assoluto rispetto all'area della relativa "cella". <xref:System.Windows.Documents.Table> non supporta questa funzionalità. Infine, un <xref:System.Windows.Controls.Grid> leggero rispetto a un <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamento di ridimensionamento di righe e colonne  
 Le colonne e righe definite in un <xref:System.Windows.Controls.Grid> possono sfruttare <xref:System.Windows.GridUnitType.Star> ridimensionamento per poter distribuire proporzionalmente lo spazio rimanente. Quando <xref:System.Windows.GridUnitType.Star> sia selezionata l'altezza o larghezza di una riga o colonna, tale colonna o riga riceve una proporzione ponderata dello spazio disponibile rimanente. È in contrasto con <xref:System.Windows.GridUnitType.Auto>, che distribuirà spazio in modo uniforme in base alla dimensione del contenuto all'interno di una colonna o riga. Questo valore viene espresso come `*` o come `2*` quando si usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Nel primo caso la riga o la colonna riceverebbe una volta lo spazio disponibile, nel secondo caso lo riceverebbe due volte e così via. Combinando questa tecnica per distribuire proporzionalmente lo spazio con un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> pari a `Stretch` è possibile suddividere lo spazio di layout con la percentuale di spazio sullo schermo. <xref:System.Windows.Controls.Grid> è l'unico pannello di layout che è possibile distribuire lo spazio in questo modo.  
  
#### <a name="defining-and-using-a-grid"></a>Definizione e uso di un elemento Grid  
 L'esempio seguente illustra come creare una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga a quella presente nella finestra Esegui disponibile nel menu Start di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento Grid tipico.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Oggetto <xref:System.Windows.Controls.StackPanel> consente di "stack" gli elementi in una direzione assegnata. La direzione predefinita dello stack è verticale. Il <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà può essere utilizzata per controllare il flusso del contenuto.  
  
#### <a name="stackpanel-vs-dockpanel"></a>Confronto tra gli elementi StackPanel e DockPanel  
 Sebbene <xref:System.Windows.Controls.DockPanel> possono anche "stack" gli elementi figlio <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel> non producono risultati analoghi negli stessi scenari d'uso. Ad esempio, l'ordine degli elementi figlio possa influire sulle relative dimensioni in un <xref:System.Windows.Controls.DockPanel> ma non in un <xref:System.Windows.Controls.StackPanel>. Infatti <xref:System.Windows.Controls.StackPanel> misure nella direzione dello stack in corrispondenza <xref:System.Double.PositiveInfinity>, mentre <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.  
  
 L'esempio seguente illustra questa differenza fondamentale.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La differenza nel comportamento di rendering viene illustrata in questa immagine.  
  
 ![Screenshot: confronto tra gli elementi StackPanel e DockPanel](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definizione e uso di un elemento StackPanel  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.StackPanel> per creare un set di pulsanti posizionati verticalmente. Per il posizionamento orizzontale, impostare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento StackPanel tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce inoltre una variazione del <xref:System.Windows.Controls.StackPanel> elemento che virtualizza automaticamente "il" contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dei dati, viene generato un subset di elementi in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel> (tramite la funzionalità fornita da <xref:System.Windows.Controls.VirtualizingPanel>) calcola gli elementi visibili e funziona con il <xref:System.Windows.Controls.ItemContainerGenerator> da un <xref:System.Windows.Controls.ItemsControl> (ad esempio <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) soltanto di creare gli elementi per gli elementi visibili.  
  
 Il <xref:System.Windows.Controls.VirtualizingStackPanel> elemento viene impostato automaticamente come host degli elementi per i controlli, ad esempio il <xref:System.Windows.Controls.ListBox>. Quando insieme con associazione a una data di hosting, il contenuto viene virtualizzato automaticamente, purché il contenuto sia all'interno di un <xref:System.Windows.Controls.ScrollViewer>. In questo modo le prestazioni ottenute nell'hosting di molti elementi figlio vengono significativamente migliorate.  
  
 Il markup seguente illustra come usare un <xref:System.Windows.Controls.VirtualizingStackPanel> come host di elementi. Il <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> proprietà associata deve essere impostata su `true` (predefinito) per eseguire la virtualizzazione.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> viene utilizzato per posizionare gli elementi figlio in sequenza da sinistra a destra, interrompendo il contenuto nella riga successiva quando raggiunge il bordo del contenitore padre. Il contenuto può essere orientato orizzontalmente o verticalmente. <xref:System.Windows.Controls.WrapPanel> è utile per il flusso semplice [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari. e consente anche di applicare un ridimensionamento uniforme a tutti i propri elementi figlio.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.WrapPanel> per visualizzare <xref:System.Windows.Controls.Button> controlli che va a capo quando raggiungono il bordo del relativo contenitore.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento WrapPanel tipico.](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Elementi Panel annidati  
 <xref:System.Windows.Controls.Panel> gli elementi possono essere annidati all'interno di altro per creare layout complessi. Ciò può rivelarsi particolarmente utile nelle situazioni in cui uno <xref:System.Windows.Controls.Panel> è ideale per una parte di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ma potrebbe non soddisfare le esigenze di un'altra porzione del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Non esiste alcun limite concreto al livello di annidamento che l'applicazione può supportare, ma è preferibile limitare l'uso dei pannelli a quelli effettivamente necessari per il layout desiderato. In molti casi, un <xref:System.Windows.Controls.Grid> elemento può essere usato invece di Panel annidati relativa flessibilità come contenitore di layout. In questo modo le prestazioni dell'applicazione possono aumentare, grazie all'assenza di elementi non necessari nell'albero.  
  
 Nell'esempio seguente viene illustrato come creare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che sfrutta i vantaggi di annidate <xref:System.Windows.Controls.Panel> elementi per ottenere un layout specifico. In questo caso specifico, un <xref:System.Windows.Controls.DockPanel> elemento viene usato per fornire [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] strutturare e annidate <xref:System.Windows.Controls.StackPanel> elementi, una <xref:System.Windows.Controls.Grid>e un <xref:System.Windows.Controls.Canvas> vengono usati per posizionare elementi figlio con precisione nel controllo padre <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Interfaccia utente in cui vengono usati elementi Panel annidati.](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Elementi Panel personalizzati  
 Anche se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una matrice di controlli di layout flessibile, il layout personalizzato comportamenti possono essere ottenuti anche eseguendo l'override di <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> e <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi. Il ridimensionamento e il posizionamento personalizzati possono essere eseguiti definendo nuovi comportamenti di posizionamento in tali metodi di override.  
  
 Allo stesso modo, i comportamenti di layout personalizzati in base alle classi derivate (ad esempio <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.Grid>) possono essere definiti eseguendo l'override loro <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> e <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi.  
  
 Il markup seguente viene illustrato come creare un oggetto personalizzato <xref:System.Windows.Controls.Panel> elemento. Questa nuova <xref:System.Windows.Controls.Panel>, definita come `PlotPanel`, supporta il posizionamento degli elementi figlio tramite l'utilizzo a livello di codice *x -* e *y -* coordinate. In questo esempio, un <xref:System.Windows.Shapes.Rectangle> elemento (non mostrato) viene posizionato in corrispondenza di punti del tracciato 50 (*x*) e 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Per visualizzare un'implementazione di elementi Panel più complessi, vedere [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Supporto per la globalizzazione o la localizzazione  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta un insieme di funzionalità che facilitano la creazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizzabili.  
  
 Tutti gli elementi panel supportano in modo nativo il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà, che può essere utilizzata per un nuovo flusso dinamico del contenuto in base alle impostazioni locali o dalla lingua dell'utente. Per altre informazioni, vedere <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Il <xref:System.Windows.Window.SizeToContent%2A> proprietà fornisce un meccanismo che consente agli sviluppatori di applicazioni per prevedere le esigenze di localizzate [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Usando il <xref:System.Windows.SizeToContent.WidthAndHeight> valore di questa proprietà, un elemento padre <xref:System.Windows.Window> sempre ridimensionato in modo dinamico per adattarsi al contenuto e non è vincolato da restrizioni artificiali di altezza o larghezza.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, e <xref:System.Windows.Controls.StackPanel> sono tutte opzioni appropriate per localizzabili [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas> è, tuttavia, non una scelta appropriata perché posiziona il contenuto in modo assoluto, rendendolo difficile da localizzare.  
  
 Per altre informazioni sulla creazione di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] localizzabili, vedere [Use Automatic Layout Overview](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md) (Cenni preliminari sull'uso del layout automatico).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Esempio di raccolta di controlli WPF](https://go.microsoft.com/fwlink/?LinkID=160053)  
 [Panoramica su allineamento, margini e spaziatura interna](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Creare un contenuto-Wrapping Panel Sample personalizzato](https://go.microsoft.com/fwlink/?LinkID=159979)  
 [Cenni preliminari sulle proprietà associate](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [Cenni preliminari sull'utilizzo del layout automatico](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
