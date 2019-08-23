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
ms.openlocfilehash: 5fe464f2b79fa1f7b0674c049110d32f2ad32335
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944815"
---
# <a name="panels-overview"></a>Cenni preliminari sugli elementi Panel
<xref:System.Windows.Controls.Panel>gli elementi sono componenti che controllano il rendering degli elementi, ovvero le dimensioni e le dimensioni, la posizione e la disposizione del contenuto figlio. Fornisce una serie di elementi predefiniti <xref:System.Windows.Controls.Panel> , nonché la possibilità di creare elementi personalizzati <xref:System.Windows.Controls.Panel>. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Classe Panel](#Panels_view_from_10000_feet)  
  
- [Membri comuni degli elementi Panel](#Panels_declared_members)  
  
- [Elementi Panel derivati](#Panels_derived_elements)  
  
- [Elementi Panel dell'interfaccia utente](#Panels_main_UI_elements)  
  
- [Elementi Panel annidati](#Panels_nested_panel_elements)  
  
- [Elementi Panel personalizzati](#Panels_custom_panel_elements)  
  
- [Supporto per la globalizzazione o la localizzazione](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Classe Panel  
 <xref:System.Windows.Controls.Panel>è la classe base per tutti gli elementi che forniscono supporto per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]il layout in. Gli <xref:System.Windows.Controls.Panel> elementi derivati vengono utilizzati per posizionare e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] disporre gli elementi nel codice e.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite completa di implementazioni di elementi Panel derivati che abilitano numerosi layout complessi. Tali classi derivate espongono proprietà e metodi che consentono di implementare la maggior parte degli scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] standard. Gli sviluppatori che non riescono a trovare un comportamento di disposizione figlio che soddisfi le proprie esigenze possono creare nuovi layout <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> eseguendo <xref:System.Windows.FrameworkElement.MeasureOverride%2A> l'override dei metodi e. Per altre informazioni sui comportamenti di layout personalizzati, vedere [Elementi Panel personalizzati](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Membri comuni degli elementi Panel  
 Tutti <xref:System.Windows.Controls.Panel> gli elementi supportano le proprietà di ridimensionamento e posizionamento <xref:System.Windows.FrameworkElement>di base definite da <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>tra <xref:System.Windows.FrameworkElement.Margin%2A>cui <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A> <xref:System.Windows.FrameworkElement.Width%2A>,,, e. Per ulteriori informazioni sulle proprietà di posizionamento definite <xref:System.Windows.FrameworkElement>da, vedere [Cenni preliminari su allineamento, margini e spaziatura interna](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>espone proprietà aggiuntive di importanza critica per la comprensione e l'utilizzo del layout. La <xref:System.Windows.Controls.Panel.Background%2A> proprietà viene utilizzata per riempire l'area tra i limiti di un elemento Panel derivato con un <xref:System.Windows.Media.Brush>oggetto. <xref:System.Windows.Controls.Panel.Children%2A>rappresenta la raccolta figlio di elementi di cui <xref:System.Windows.Controls.Panel> l'oggetto è costituito. <xref:System.Windows.Controls.Panel.InternalChildren%2A>rappresenta il contenuto della <xref:System.Windows.Controls.Panel.Children%2A> raccolta e i membri generati da Data Binding. Entrambi sono costituiti <xref:System.Windows.Controls.UIElementCollection> da un di elementi figlio ospitati <xref:System.Windows.Controls.Panel>all'interno dell'elemento padre.  
  
 Il pannello espone anche <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> una proprietà associata che può essere usata per ottenere un ordine a più livelli <xref:System.Windows.Controls.Panel>in un oggetto derivato. I membri della <xref:System.Windows.Controls.Panel.Children%2A> raccolta di un pannello con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore superiore vengono visualizzati davanti a quelli con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore più basso. Questa operazione è particolarmente utile per i pannelli <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.Grid> ad esempio e, che consentono agli elementi figlio di condividere lo stesso spazio delle coordinate.  
  
 <xref:System.Windows.Controls.Panel>definisce anche il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo, che può essere usato per eseguire l'override del comportamento di presentazione <xref:System.Windows.Controls.Panel>predefinito di un oggetto.  
  
#### <a name="attached-properties"></a>Proprietà associate  
 Gli elementi Panel derivati usano ampiamente le proprietà associate. Una proprietà associata è un tipo specializzato di proprietà di dipendenza che non dispone della proprietà di Common Language Runtime (CLR) convenzionale "wrapper". Le proprietà associate presentano una sintassi specializzata in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], illustrata in molti esempi seguenti.  
  
 Uno degli scopi di una proprietà associata è quello di consentire agli elementi figlio di archiviare valori univoci di una proprietà effettivamente definita da un elemento padre. Questa funzionalità, molto utile per il layout dell'applicazione, consente agli elementi figlio di comunicare all'elemento padre il modo in cui devono essere presentati in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Elementi Panel derivati  
 Molti oggetti derivano <xref:System.Windows.Controls.Panel>da, ma non tutti devono essere usati come provider di layout radice. Sono disponibili sei classi Panel definite (<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.DockPanel>,, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>e <xref:System.Windows.Controls.WrapPanel>) progettate specificamente per la creazione dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Ogni elemento Panel incapsula la propria funzionalità speciale, come illustrato nella tabella seguente.  
  
|Nome elemento|Elemento Panel dell'interfaccia utente?|Descrizione|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sì|Definisce un'area all'interno della <xref:System.Windows.Controls.Canvas> quale è possibile posizionare in modo esplicito gli elementi figlio in base alle coordinate relative all'area.|  
|<xref:System.Windows.Controls.DockPanel>|Yes|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|  
|<xref:System.Windows.Controls.Grid>|Sì|Definisce un'area flessibile della griglia costituita da righe e colonne. Gli elementi figlio di <xref:System.Windows.Controls.Grid> un oggetto possono essere posizionati <xref:System.Windows.FrameworkElement.Margin%2A> con precisione utilizzando la proprietà.|  
|<xref:System.Windows.Controls.StackPanel>|Sì|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Gestisce il layout dei pulsanti di tabulazione <xref:System.Windows.Controls.TabControl>in un oggetto.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Dispone il contenuto all'interno <xref:System.Windows.Controls.ToolBar> di un controllo.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid>viene utilizzato per disporre gli elementi figlio in una griglia con tutte le dimensioni delle celle uguali.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Implementa una classe di base per i pannelli in grado di virtualizzare la raccolta di elementi figlio relativa.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sì|Dispone e virtualizza il contenuto su una singola riga orientato orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sì|<xref:System.Windows.Controls.WrapPanel>posiziona gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto sulla riga successiva al bordo della casella contenitore. L'ordinamento successivo avviene in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore <xref:System.Windows.Controls.WrapPanel.Orientation%2A> della proprietà.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Elementi Panel dell'interfaccia utente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] In sono disponibili sei classi di pannelli ottimizzate per supportare <xref:System.Windows.Controls.VirtualizingStackPanel> <xref:System.Windows.Controls.WrapPanel> <xref:System.Windows.Controls.Grid> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenari: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>,, <xref:System.Windows.Controls.StackPanel>, e. Tali elementi Panel sono facili da usare, versatili ed estendibili per la maggior parte delle applicazioni.  
  
 Ogni elemento <xref:System.Windows.Controls.Panel> derivato considera i vincoli di ridimensionamento in modo diverso. Comprendere il modo <xref:System.Windows.Controls.Panel> in cui un oggetto gestisce i vincoli nella direzione orizzontale o verticale può rendere il layout più prevedibile.  
  
|**Nome dell'elemento Panel**|**Dimensione x**|**Dimensione y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Vincolato al contenuto|Vincolato al contenuto|  
|<xref:System.Windows.Controls.DockPanel>|Vincolato|Vincolato|  
|<xref:System.Windows.Controls.StackPanel>(Orientamento verticale)|Vincolato|Vincolato al contenuto|  
|<xref:System.Windows.Controls.StackPanel>(Orientamento orizzontale)|Vincolato al contenuto|Vincolato|  
|<xref:System.Windows.Controls.Grid>|Vincolato|Vincolato, tranne nei casi in cui <xref:System.Windows.GridUnitType.Auto> si applica a righe e colonne|  
|<xref:System.Windows.Controls.WrapPanel>|Vincolato al contenuto|Vincolato al contenuto|  
  
 Di seguito sono disponibili descrizioni più dettagliate ed esempi di uso di ogni elemento.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 L' <xref:System.Windows.Controls.Canvas> elemento consente il posizionamento del contenuto in base alle coordinate assolute *x* e *y*. Gli elementi possono essere disegnati in una posizione univoca. Se gli elementi occupano le stesse coordinate, l'ordine in cui vengono disegnati è determinato dall'ordine di visualizzazione nel markup.  
  
 <xref:System.Windows.Controls.Canvas>offre il supporto di layout più flessibile di <xref:System.Windows.Controls.Panel>qualsiasi. Le proprietà Height e Width vengono usate per definire l'area dell'area di disegno e gli elementi all'interno di vengono assegnati coordinate assolute rispetto all' <xref:System.Windows.Controls.Canvas>area dell'elemento padre. Quattro proprietà associate, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas>, e ,<xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>consentono un controllo accurato della posizione dell'oggetto all'interno di un, consentendo allo sviluppatore di posizionare e disporre gli elementi esattamente sullo schermo. <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType>  
  
#### <a name="cliptobounds-within-a-canvas"></a>Proprietà ClipToBounds in un elemento Canvas  
 <xref:System.Windows.Controls.Canvas>consente di posizionare gli elementi figlio in qualsiasi posizione sullo schermo, anche in corrispondenza di coordinate esterne ai propri e <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A>definiti. Inoltre, <xref:System.Windows.Controls.Canvas> non è influenzato dalle dimensioni dei relativi elementi figlio. Di conseguenza, è possibile che un elemento figlio sovradisegni altri elementi all'esterno del rettangolo delimitatore dell'elemento padre <xref:System.Windows.Controls.Canvas>. Il comportamento predefinito di un <xref:System.Windows.Controls.Canvas> oggetto consiste nel consentire il disegno di elementi figlio all'esterno dei limiti dell' <xref:System.Windows.Controls.Canvas>elemento padre. Se questo comportamento è indesiderato <xref:System.Windows.UIElement.ClipToBounds%2A> , la proprietà può essere `true`impostata su. Questo consente <xref:System.Windows.Controls.Canvas> di ritagliare le proprie dimensioni. <xref:System.Windows.Controls.Canvas>è l'unico elemento di layout che consente di disegnare elementi figlio al di fuori dei relativi limiti.  
  
 Questo comportamento viene illustrato graficamente in [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050) (Esempio di confronto di proprietà Width).  
  
#### <a name="defining-and-using-a-canvas"></a>Definizione e uso di un elemento Canvas  
 È <xref:System.Windows.Controls.Canvas> possibile creare un'istanza di un oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] semplicemente utilizzando o il codice. Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Controls.Canvas> per posizionare in modo assoluto il contenuto. Questo codice produce tre quadrati di 100 pixel. Il primo quadrato è rosso e la posizione del relativo angolo superiore sinistro (*x, y*) è specificata come (0, 0). Il secondo quadrato è verde e la posizione dell'angolo superiore sinistro è impostata su (100, 100), sotto e a destra rispetto al primo quadrato. Il terzo quadrato è blu, con la posizione dell'angolo superiore sinistro impostata su (50, 50). Il quadrato ingloba pertanto il quadrante inferiore destro del primo quadrato e quello superiore sinistro del secondo. Poiché il terzo quadrato è stato disposto per ultimo, sembra posizionato sopra agli altri due e di conseguenza le porzioni sovrapposte ne assumono il colore.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento Canvas tipico.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 L' <xref:System.Windows.Controls.DockPanel> elemento usa la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata come set negli elementi di contenuto figlio per posizionare il contenuto lungo i bordi di un contenitore. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostato su <xref:System.Windows.Controls.Dock.Top> o <xref:System.Windows.Controls.Dock.Bottom>, posiziona gli elementi figlio sopra o sotto l'uno all'altro. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostato su <xref:System.Windows.Controls.Dock.Left> o <xref:System.Windows.Controls.Dock.Right>, posiziona gli elementi figlio a sinistra o a destra. La <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà determina la posizione dell'elemento finale aggiunto come figlio di un oggetto <xref:System.Windows.Controls.DockPanel>.  
  
 È possibile utilizzare <xref:System.Windows.Controls.DockPanel> per posizionare un gruppo di controlli correlati, ad esempio un set di pulsanti. In alternativa, è possibile usarlo per creare un "riquadri" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], simile a quello disponibile in Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Se le <xref:System.Windows.FrameworkElement.Height%2A> proprietà <xref:System.Windows.FrameworkElement.Width%2A> e non vengono specificate, <xref:System.Windows.Controls.DockPanel> il relativo contenuto viene ridimensionato. Le dimensioni possono aumentare o diminuire a seconda delle dimensioni degli elementi figlio. Tuttavia, quando queste proprietà vengono specificate e non è più disponibile spazio per il successivo elemento figlio specificato, <xref:System.Windows.Controls.DockPanel> non visualizza tale elemento figlio né gli elementi figlio successivi e non misura gli elementi figlio successivi.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Per impostazione predefinita, l'ultimo elemento figlio <xref:System.Windows.Controls.DockPanel> di un elemento compilerà lo spazio rimanente e non allocato. Se questo comportamento non è desiderato, impostare la <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà su `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definizione e uso di un elemento DockPanel  
 Nell'esempio seguente viene illustrato come partizionare lo spazio <xref:System.Windows.Controls.DockPanel>utilizzando un oggetto. Cinque <xref:System.Windows.Controls.Border> elementi vengono aggiunti come elementi figlio di un <xref:System.Windows.Controls.DockPanel>elemento padre. Ogni utilizza una proprietà di posizionamento diversa di <xref:System.Windows.Controls.DockPanel> un oggetto per partizionare lo spazio. L'elemento finale riempie lo spazio rimanente non allocato.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Scenario DockPanel tipico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 L' <xref:System.Windows.Controls.Grid> elemento unisce la funzionalità di un controllo del posizionamento assoluto e dei dati tabulari. Un <xref:System.Windows.Controls.Grid> oggetto consente di posizionare e applicare in modo semplice gli elementi. <xref:System.Windows.Controls.Grid>consente di definire raggruppamenti flessibili di righe e colonne e fornisce anche un meccanismo per condividere le informazioni sul dimensionamento <xref:System.Windows.Controls.Grid> tra più elementi.  
  
#### <a name="how-is-grid-different-from-table"></a>Differenza tra gli elementi Grid e Table  
 <xref:System.Windows.Documents.Table>e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi. Un <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto di flusso. per altre informazioni sul contenuto dinamico, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md) . Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno <xref:System.Windows.Documents.FlowDocument>di <xref:System.Windows.Documents.Table> un, supporta i comportamenti del contenuto di flusso come paginazione, riflusso di colonne <xref:System.Windows.Controls.Grid> e selezione di contenuto, mentre a non lo è. È <xref:System.Windows.Controls.Grid> invece consigliabile usare un oggetto <xref:System.Windows.Documents.FlowDocument> per molti motivi, <xref:System.Windows.Documents.Table> tra cui <xref:System.Windows.Controls.Grid> l'aggiunta di elementi in base a un indice di riga e colonna. L' <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione di contenuto figlio, consentendo l'esistenza di più di un elemento all'interno di una singola "cella". <xref:System.Windows.Documents.Table>non supporta la sovrapposizione. Gli elementi figlio di <xref:System.Windows.Controls.Grid> un oggetto possono essere posizionati in modo assoluto rispetto all'area dei limiti "Cell". <xref:System.Windows.Documents.Table>non supporta questa funzionalità. Infine, un <xref:System.Windows.Controls.Grid> valore è più chiaro di un <xref:System.Windows.Documents.Table>oggetto.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamento di ridimensionamento di righe e colonne  
 <xref:System.Windows.Controls.Grid> Le<xref:System.Windows.GridUnitType.Star> colonne e le righe definite all'interno di un possono sfruttare il dimensionamento per distribuire lo spazio rimanente in modo proporzionale. Quando <xref:System.Windows.GridUnitType.Star> si seleziona l'altezza o la larghezza di una riga o di una colonna, tale colonna o riga riceve una proporzione ponderata dello spazio disponibile rimanente. Si tratta di un contrasto <xref:System.Windows.GridUnitType.Auto>rispetto a, che consente di distribuire lo spazio in modo uniforme in base alle dimensioni del contenuto all'interno di una colonna o di una riga. Questo valore viene espresso come `*` o come `2*` quando si usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Nel primo caso la riga o la colonna riceverebbe una volta lo spazio disponibile, nel secondo caso lo riceverebbe due volte e così via. Combinando questa tecnica per la distribuzione proporzionale <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> dello <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> spazio con `Stretch` un valore e, è possibile partizionare lo spazio del layout in base alla percentuale dello spazio dello schermo. <xref:System.Windows.Controls.Grid>è l'unico pannello di layout in grado di distribuire lo spazio in questo modo.  
  
#### <a name="defining-and-using-a-grid"></a>Definizione e uso di un elemento Grid  
 Nell'esempio seguente viene illustrato come creare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] oggetto simile a quello presente nella finestra di dialogo Esegui disponibile nel menu Start di Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento Grid tipico.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Un <xref:System.Windows.Controls.StackPanel> oggetto consente di "stack" elementi in una direzione assegnata. La direzione predefinita dello stack è verticale. La <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà può essere usata per controllare il flusso di contenuto.  
  
#### <a name="stackpanel-vs-dockpanel"></a>Confronto tra gli elementi StackPanel e DockPanel  
 Sebbene <xref:System.Windows.Controls.DockPanel> possa anche "stack" <xref:System.Windows.Controls.DockPanel> elementi figlio e <xref:System.Windows.Controls.StackPanel> non producono risultati analoghi in alcuni scenari di utilizzo. Ad esempio, l'ordine degli elementi figlio può influire sulle dimensioni in <xref:System.Windows.Controls.DockPanel> un oggetto ma non <xref:System.Windows.Controls.StackPanel>in un oggetto. Ciò è dovuto <xref:System.Windows.Controls.StackPanel> al fatto che le misure nella direzione dello <xref:System.Double.PositiveInfinity>stack in <xref:System.Windows.Controls.DockPanel> , mentre misura solo le dimensioni disponibili.  
  
 L'esempio seguente illustra questa differenza fondamentale.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La differenza nel comportamento di rendering viene illustrata in questa immagine.  
  
 ![Screenshot Confronto tra gli elementi StackPanel e e DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definizione e uso di un elemento StackPanel  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.StackPanel> oggetto per creare un set di pulsanti posizionati verticalmente. Per il posizionamento orizzontale, impostare <xref:System.Windows.Controls.StackPanel.Orientation%2A> la proprietà <xref:System.Windows.Controls.Orientation.Horizontal>su.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento StackPanel tipico.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce inoltre una variante dell'elemento <xref:System.Windows.Controls.StackPanel> che "virtualizza" automaticamente il contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dei dati, viene generato un subset di elementi in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel>(tramite la <xref:System.Windows.Controls.ItemContainerGenerator> funzionalità fornita <xref:System.Windows.Controls.VirtualizingPanel>da) calcola gli elementi visibili e <xref:System.Windows.Controls.ListBox> utilizza da un oggetto <xref:System.Windows.Controls.ItemsControl> (ad esempio o <xref:System.Windows.Controls.ListView>) per creare solo elementi per gli elementi visibili.  
  
 L' <xref:System.Windows.Controls.VirtualizingStackPanel> elemento viene impostato automaticamente come host degli elementi per i <xref:System.Windows.Controls.ListBox>controlli, ad esempio. Quando si ospita una raccolta con associazione a dati, il contenuto viene automaticamente virtualizzato, purché il contenuto sia entro i limiti di <xref:System.Windows.Controls.ScrollViewer>un. In questo modo le prestazioni ottenute nell'hosting di molti elementi figlio vengono significativamente migliorate.  
  
 Il markup seguente illustra come usare un oggetto <xref:System.Windows.Controls.VirtualizingStackPanel> come host di elementi. Per <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> eseguire la virtualizzazione, è `true` necessario impostare la proprietà associata su (impostazione predefinita).  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>viene utilizzato per posizionare gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto alla riga successiva quando raggiunge il bordo del contenitore padre. Il contenuto può essere orientato orizzontalmente o verticalmente. <xref:System.Windows.Controls.WrapPanel>è utile per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari con flussi semplici. e consente anche di applicare un ridimensionamento uniforme a tutti i propri elementi figlio.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.WrapPanel> oggetto per <xref:System.Windows.Controls.Button> visualizzare i controlli che vengono a capo quando raggiungono il bordo del relativo contenitore.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Elemento WrapPanel tipico.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Elementi Panel annidati  
 <xref:System.Windows.Controls.Panel>gli elementi possono essere annidati l'uno all'interno dell'altro per produrre layout complessi. Questo può risultare molto utile nelle situazioni in cui <xref:System.Windows.Controls.Panel> uno è ideale per una parte di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]un, ma potrebbe non soddisfare le esigenze di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]una parte diversa del.  
  
 Non esiste alcun limite concreto al livello di annidamento che l'applicazione può supportare, ma è preferibile limitare l'uso dei pannelli a quelli effettivamente necessari per il layout desiderato. In molti casi, è <xref:System.Windows.Controls.Grid> possibile utilizzare un elemento anziché i pannelli annidati a causa della relativa flessibilità come contenitore di layout. In questo modo le prestazioni dell'applicazione possono aumentare, grazie all'assenza di elementi non necessari nell'albero.  
  
 Nell'esempio seguente viene illustrato come creare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] oggetto che sfrutta i vantaggi <xref:System.Windows.Controls.Panel> degli elementi annidati per ottenere un layout specifico. In questo caso particolare, viene <xref:System.Windows.Controls.DockPanel> usato un elemento per fornire [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] la struttura, gli <xref:System.Windows.Controls.StackPanel> elementi annidati <xref:System.Windows.Controls.Grid>, un oggetto <xref:System.Windows.Controls.Canvas> e un oggetto per posizionare gli elementi figlio esattamente all' <xref:System.Windows.Controls.DockPanel>interno dell'elemento padre.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Interfaccia utente in cui vengono usati elementi Panel annidati.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Elementi Panel personalizzati  
 Sebbene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisca una matrice di controlli di layout flessibili, è possibile ottenere comportamenti di layout personalizzati anche eseguendo l'override <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> dei <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi e. Il ridimensionamento e il posizionamento personalizzati possono essere eseguiti definendo nuovi comportamenti di posizionamento in tali metodi di override.  
  
 Analogamente, è possibile definire comportamenti di layout personalizzati basati su classi <xref:System.Windows.Controls.Canvas> derivate, ad esempio o <xref:System.Windows.Controls.Grid>, eseguendo <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> l' <xref:System.Windows.FrameworkElement.MeasureOverride%2A> override dei relativi metodi e.  
  
 Nel markup seguente viene illustrato come creare un elemento <xref:System.Windows.Controls.Panel> personalizzato. Questo nuovo <xref:System.Windows.Controls.Panel>, definito come `PlotPanel`, supporta il posizionamento di elementi figlio tramite l'utilizzo di coordinate *x* e *y*hardcoded. In questo esempio, un <xref:System.Windows.Shapes.Rectangle> elemento (non mostrato) viene posizionato in corrispondenza del punto del tracciato 50 (*x*) e 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Per visualizzare un'implementazione di elementi Panel più complessi, vedere [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Supporto per la globalizzazione o la localizzazione  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta un insieme di funzionalità che facilitano la creazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizzabili.  
  
 Tutti gli elementi Panel supportano in modo <xref:System.Windows.FrameworkElement.FlowDirection%2A> nativo la proprietà, che può essere usata per riattivare dinamicamente il contenuto in base alle impostazioni locali o della lingua di un utente. Per altre informazioni, vedere <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La <xref:System.Windows.Window.SizeToContent%2A> proprietà fornisce un meccanismo che consente agli sviluppatori di applicazioni di prevedere le esigenze di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]localizzate. Usando il <xref:System.Windows.SizeToContent.WidthAndHeight> valore di questa proprietà, un elemento <xref:System.Windows.Window> padre viene sempre dimensionato in modo dinamico per adattarsi al contenuto e non è vincolato da restrizioni di altezza o larghezza artificiali.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]e <xref:System.Windows.Controls.StackPanel> sono tutte scelte valide per la localizzabilità. <xref:System.Windows.Controls.Canvas>non è una scelta ottimale, tuttavia, perché posiziona il contenuto in modo assoluto, rendendolo difficile da localizzare.  
  
 Per altre informazioni sulla creazione di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] localizzabili, vedere [Use Automatic Layout Overview](../advanced/use-automatic-layout-overview.md) (Cenni preliminari sull'uso del layout automatico).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Layout](../advanced/layout.md)
- [Esempio di raccolta di controlli WPF](https://go.microsoft.com/fwlink/?LinkID=160053)
- [Panoramica su allineamento, margini e spaziatura interna](../advanced/alignment-margins-and-padding-overview.md)
- [Esempio di creare un pannello di contenuto personalizzato per il wrapping](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md)
- [Cenni preliminari sull'utilizzo del layout automatico](../advanced/use-automatic-layout-overview.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](../advanced/optimizing-performance-layout-and-design.md)
