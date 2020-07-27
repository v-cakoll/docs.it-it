---
title: Cenni preliminari sugli elementi Panel
description: Windows Presentation Foundation fornisce elementi Panel predefiniti che controllano il rendering degli elementi. Informazioni su come creare elementi Panel personalizzati.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 7f3f6948de28f50dc6470a7dfc1a5bad67e57c79
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167775"
---
# <a name="panels-overview"></a>Cenni preliminari sugli elementi Panel
<xref:System.Windows.Controls.Panel>gli elementi sono componenti che controllano il rendering degli elementi, ovvero le dimensioni e le dimensioni, la posizione e la disposizione del contenuto figlio. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Fornisce una serie di <xref:System.Windows.Controls.Panel> elementi predefiniti, nonché la possibilità di creare elementi personalizzati <xref:System.Windows.Controls.Panel> .  
  
 In questo argomento sono contenute le sezioni seguenti.  
  
- [Classe Panel](#Panels_view_from_10000_feet)  
  
- [Membri comuni degli elementi Panel](#Panels_declared_members)  
  
- [Elementi Panel derivati](#Panels_derived_elements)  
  
- [Elementi Panel dell'interfaccia utente](#Panels_main_UI_elements)  
  
- [Elementi Panel annidati](#Panels_nested_panel_elements)  
  
- [Elementi Panel personalizzati](#Panels_custom_panel_elements)  
  
- [Supporto per la globalizzazione o la localizzazione](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>
## <a name="the-panel-class"></a>Classe Panel  
 <xref:System.Windows.Controls.Panel>è la classe base per tutti gli elementi che forniscono supporto per il layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . Gli elementi derivati <xref:System.Windows.Controls.Panel> vengono utilizzati per posizionare e disporre gli elementi nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice e.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite completa di implementazioni di elementi Panel derivati che abilitano numerosi layout complessi. Tali classi derivate espongono proprietà e metodi che consentono di implementare la maggior parte degli scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] standard. Gli sviluppatori che non riescono a trovare un comportamento di disposizione figlio che soddisfi le proprie esigenze possono creare nuovi layout eseguendo l'override dei <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi e. Per altre informazioni sui comportamenti di layout personalizzati, vedere [Elementi Panel personalizzati](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Membri comuni degli elementi Panel  
 Tutti <xref:System.Windows.Controls.Panel> gli elementi supportano le proprietà di ridimensionamento e posizionamento di base definite da <xref:System.Windows.FrameworkElement> , tra cui <xref:System.Windows.FrameworkElement.Height%2A> ,, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> , <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.LayoutTransform%2A> . Per ulteriori informazioni sulle proprietà di posizionamento definite da <xref:System.Windows.FrameworkElement> , vedere [Cenni preliminari su allineamento, margini e spaziatura interna](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>espone proprietà aggiuntive di importanza critica per la comprensione e l'utilizzo del layout. La <xref:System.Windows.Controls.Panel.Background%2A> proprietà viene utilizzata per riempire l'area tra i limiti di un elemento Panel derivato con un oggetto <xref:System.Windows.Media.Brush> . <xref:System.Windows.Controls.Panel.Children%2A>rappresenta la raccolta figlio di elementi di cui l'oggetto <xref:System.Windows.Controls.Panel> è costituito. <xref:System.Windows.Controls.Panel.InternalChildren%2A>rappresenta il contenuto della <xref:System.Windows.Controls.Panel.Children%2A> raccolta e i membri generati da Data Binding. Entrambi sono costituiti da un <xref:System.Windows.Controls.UIElementCollection> di elementi figlio ospitati all'interno dell'elemento padre <xref:System.Windows.Controls.Panel> .  
  
 Il pannello espone anche una <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> proprietà associata che può essere usata per ottenere un ordine a più livelli in un oggetto derivato <xref:System.Windows.Controls.Panel> . I membri della raccolta di un pannello <xref:System.Windows.Controls.Panel.Children%2A> con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore superiore vengono visualizzati davanti a quelli con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valore più basso. Questa operazione è particolarmente utile per i pannelli, ad esempio <xref:System.Windows.Controls.Canvas> e, <xref:System.Windows.Controls.Grid> che consentono agli elementi figlio di condividere lo stesso spazio delle coordinate.  
  
 <xref:System.Windows.Controls.Panel>definisce anche il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo, che può essere usato per eseguire l'override del comportamento di presentazione predefinito di un oggetto <xref:System.Windows.Controls.Panel> .  
  
#### <a name="attached-properties"></a>Proprietà associate  
 Gli elementi Panel derivati usano ampiamente le proprietà associate. Una proprietà associata è un tipo specializzato di proprietà di dipendenza che non dispone della proprietà di Common Language Runtime (CLR) convenzionale "wrapper". Le proprietà associate presentano una sintassi specializzata in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], illustrata in molti esempi seguenti.  
  
 Uno degli scopi di una proprietà associata è quello di consentire agli elementi figlio di archiviare valori univoci di una proprietà effettivamente definita da un elemento padre. Questa funzionalità, molto utile per il layout dell'applicazione, consente agli elementi figlio di comunicare all'elemento padre il modo in cui devono essere presentati in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Elementi Panel derivati  
 Molti oggetti derivano da <xref:System.Windows.Controls.Panel> , ma non tutti devono essere usati come provider di layout radice. Sono disponibili sei classi Panel definite ( <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.DockPanel> , <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.VirtualizingStackPanel> e <xref:System.Windows.Controls.WrapPanel> ) progettate specificamente per la creazione dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .  
  
 Ogni elemento Panel incapsula la propria funzionalità speciale, come illustrato nella tabella seguente.  
  
|Nome dell'elemento|Elemento Panel dell'interfaccia utente?|Descrizione|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sì|Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio in base alle coordinate relative all' <xref:System.Windows.Controls.Canvas> area.|  
|<xref:System.Windows.Controls.DockPanel>|Sì|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|  
|<xref:System.Windows.Controls.Grid>|Sì|Definisce un'area flessibile della griglia costituita da righe e colonne. Gli elementi figlio di un oggetto <xref:System.Windows.Controls.Grid> possono essere posizionati con precisione utilizzando la <xref:System.Windows.FrameworkElement.Margin%2A> Proprietà.|  
|<xref:System.Windows.Controls.StackPanel>|Sì|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Gestisce il layout dei pulsanti di tabulazione in un oggetto <xref:System.Windows.Controls.TabControl> .|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Dispone il contenuto all'interno di un <xref:System.Windows.Controls.ToolBar> controllo.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid>viene utilizzato per disporre gli elementi figlio in una griglia con tutte le dimensioni delle celle uguali.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Implementa una classe di base per i pannelli in grado di virtualizzare la raccolta di elementi figlio relativa.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sì|Dispone e virtualizza il contenuto su una singola riga orientato orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sì|<xref:System.Windows.Controls.WrapPanel>posiziona gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto sulla riga successiva al bordo della casella contenitore. L'ordinamento successivo avviene in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Proprietà.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Elementi Panel dell'interfaccia utente  
 In sono disponibili sei classi di pannelli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ottimizzate per supportare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenari: <xref:System.Windows.Controls.Canvas> ,, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.VirtualizingStackPanel> e <xref:System.Windows.Controls.WrapPanel> . Tali elementi Panel sono facili da usare, versatili ed estendibili per la maggior parte delle applicazioni.  
  
 Ogni <xref:System.Windows.Controls.Panel> elemento derivato considera i vincoli di ridimensionamento in modo diverso. Comprendere il modo in cui un oggetto <xref:System.Windows.Controls.Panel> gestisce i vincoli nella direzione orizzontale o verticale può rendere il layout più prevedibile.  
  
|**Nome pannello**|**Dimensione x**|**Dimensione y**|  
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
 L' <xref:System.Windows.Controls.Canvas> elemento consente il posizionamento del contenuto in base alle coordinate assolute *x* e *y* . Gli elementi possono essere disegnati in una posizione univoca. Se gli elementi occupano le stesse coordinate, l'ordine in cui vengono disegnati è determinato dall'ordine di visualizzazione nel markup.  
  
 <xref:System.Windows.Controls.Canvas>offre il supporto di layout più flessibile di qualsiasi <xref:System.Windows.Controls.Panel> . Le proprietà Height e Width vengono usate per definire l'area dell'area di disegno e gli elementi all'interno di vengono assegnati coordinate assolute rispetto all'area dell'elemento padre <xref:System.Windows.Controls.Canvas> . Quattro proprietà associate, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType> , consentono un controllo accurato della posizione dell'oggetto all'interno di un <xref:System.Windows.Controls.Canvas> , consentendo allo sviluppatore di posizionare e disporre gli elementi esattamente sullo schermo.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Proprietà ClipToBounds in un elemento Canvas  
 <xref:System.Windows.Controls.Canvas>consente di posizionare gli elementi figlio in qualsiasi posizione sullo schermo, anche in corrispondenza di coordinate esterne ai propri <xref:System.Windows.FrameworkElement.Height%2A> e definiti <xref:System.Windows.FrameworkElement.Width%2A> . Inoltre, <xref:System.Windows.Controls.Canvas> non è influenzato dalle dimensioni dei relativi elementi figlio. Di conseguenza, è possibile che un elemento figlio sovradisegni altri elementi all'esterno del rettangolo delimitatore dell'elemento padre <xref:System.Windows.Controls.Canvas> . Il comportamento predefinito di un oggetto <xref:System.Windows.Controls.Canvas> consiste nel consentire il disegno di elementi figlio all'esterno dei limiti dell'elemento padre <xref:System.Windows.Controls.Canvas> . Se questo comportamento è indesiderato, la <xref:System.Windows.UIElement.ClipToBounds%2A> proprietà può essere impostata su `true` . Questo consente <xref:System.Windows.Controls.Canvas> di ritagliare le proprie dimensioni. <xref:System.Windows.Controls.Canvas>è l'unico elemento di layout che consente di disegnare elementi figlio al di fuori dei relativi limiti.  
  
 Questo comportamento viene illustrato graficamente in [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties) (Esempio di confronto di proprietà Width).  
  
#### <a name="defining-and-using-a-canvas"></a>Definizione e uso di un elemento Canvas  
 <xref:System.Windows.Controls.Canvas>È possibile creare un'istanza di un oggetto semplicemente utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o il codice. Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Controls.Canvas> per posizionare in modo assoluto il contenuto. Questo codice produce tre quadrati di 100 pixel. Il primo quadrato è rosso e la posizione del relativo angolo superiore sinistro (*x, y*) è specificata come (0, 0). Il secondo quadrato è verde e la posizione dell'angolo superiore sinistro è impostata su (100, 100), sotto e a destra rispetto al primo quadrato. Il terzo quadrato è blu, con la posizione dell'angolo superiore sinistro impostata su (50, 50). Il quadrato ingloba pertanto il quadrante inferiore destro del primo quadrato e quello superiore sinistro del secondo. Poiché il terzo quadrato è stato disposto per ultimo, sembra posizionato sopra agli altri due e di conseguenza le porzioni sovrapposte ne assumono il colore.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento Canvas](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 L' <xref:System.Windows.Controls.DockPanel> elemento usa la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata come set negli elementi di contenuto figlio per posizionare il contenuto lungo i bordi di un contenitore. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostato su <xref:System.Windows.Controls.Dock.Top> o <xref:System.Windows.Controls.Dock.Bottom> , posiziona gli elementi figlio sopra o sotto l'uno all'altro. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è impostato su <xref:System.Windows.Controls.Dock.Left> o <xref:System.Windows.Controls.Dock.Right> , posiziona gli elementi figlio a sinistra o a destra. La <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà determina la posizione dell'elemento finale aggiunto come figlio di un oggetto <xref:System.Windows.Controls.DockPanel> .  
  
 È possibile utilizzare <xref:System.Windows.Controls.DockPanel> per posizionare un gruppo di controlli correlati, ad esempio un set di pulsanti. In alternativa, è possibile usarlo per creare un "riquadri" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , simile a quello disponibile in Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Se le <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> proprietà e non vengono specificate, il <xref:System.Windows.Controls.DockPanel> relativo contenuto viene ridimensionato. Le dimensioni possono aumentare o diminuire a seconda delle dimensioni degli elementi figlio. Tuttavia, quando queste proprietà vengono specificate e non è più disponibile spazio per il successivo elemento figlio specificato, non <xref:System.Windows.Controls.DockPanel> Visualizza tale elemento figlio né gli elementi figlio successivi e non misura gli elementi figlio successivi.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento compilerà lo spazio rimanente e non allocato. Se questo comportamento non è desiderato, impostare la <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà su `false` .  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definizione e uso di un elemento DockPanel  
 Nell'esempio seguente viene illustrato come partizionare lo spazio utilizzando un oggetto <xref:System.Windows.Controls.DockPanel> . Cinque <xref:System.Windows.Controls.Border> elementi vengono aggiunti come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel> . Ogni utilizza una proprietà di posizionamento diversa di un oggetto <xref:System.Windows.Controls.DockPanel> per partizionare lo spazio. L'elemento finale riempie lo spazio rimanente non allocato.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipo scenario DockPanel](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Grid  
 L' <xref:System.Windows.Controls.Grid> elemento unisce la funzionalità di un controllo del posizionamento assoluto e dei dati tabulari. Un oggetto <xref:System.Windows.Controls.Grid> consente di posizionare e applicare in modo semplice gli elementi. <xref:System.Windows.Controls.Grid>consente di definire raggruppamenti flessibili di righe e colonne e fornisce anche un meccanismo per condividere le informazioni sul dimensionamento tra più <xref:System.Windows.Controls.Grid> elementi.  
  
#### <a name="how-is-grid-different-from-table"></a>Differenza tra gli elementi Grid e Table  
 <xref:System.Windows.Documents.Table>e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi. Un <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto di flusso. per altre informazioni sul contenuto dinamico, vedere [Cenni preliminari sui documenti dinamici](../advanced/flow-document-overview.md) . Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument> , <xref:System.Windows.Documents.Table> supporta i comportamenti del contenuto di flusso come paginazione, riflusso di colonne e selezione di contenuto, mentre a non <xref:System.Windows.Controls.Grid> lo è. <xref:System.Windows.Controls.Grid>È invece consigliabile usare un oggetto <xref:System.Windows.Documents.FlowDocument> per molti motivi, tra cui l'aggiunta di <xref:System.Windows.Controls.Grid> elementi in base a un indice di riga e colonna <xref:System.Windows.Documents.Table> . L' <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione di contenuto figlio, consentendo l'esistenza di più di un elemento all'interno di una singola "cella". <xref:System.Windows.Documents.Table>non supporta la sovrapposizione. Gli elementi figlio di un oggetto <xref:System.Windows.Controls.Grid> possono essere posizionati in modo assoluto rispetto all'area dei limiti "Cell". <xref:System.Windows.Documents.Table>non supporta questa funzionalità. Infine, un valore <xref:System.Windows.Controls.Grid> è più chiaro di un oggetto <xref:System.Windows.Documents.Table> .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamento di ridimensionamento di righe e colonne  
 Le colonne e le righe definite all'interno di un possono sfruttare il <xref:System.Windows.Controls.Grid> <xref:System.Windows.GridUnitType.Star> dimensionamento per distribuire lo spazio rimanente in modo proporzionale. Quando <xref:System.Windows.GridUnitType.Star> si seleziona l'altezza o la larghezza di una riga o di una colonna, tale colonna o riga riceve una proporzione ponderata dello spazio disponibile rimanente. Si tratta di un contrasto rispetto a <xref:System.Windows.GridUnitType.Auto> , che consente di distribuire lo spazio in modo uniforme in base alle dimensioni del contenuto all'interno di una colonna o di una riga. Questo valore viene espresso come `*` o come `2*` quando si usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Nel primo caso la riga o la colonna riceverebbe una volta lo spazio disponibile, nel secondo caso lo riceverebbe due volte e così via. Combinando questa tecnica per la distribuzione proporzionale dello spazio con un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore e, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> `Stretch` è possibile partizionare lo spazio del layout in base alla percentuale dello spazio dello schermo. <xref:System.Windows.Controls.Grid>è l'unico pannello di layout in grado di distribuire lo spazio in questo modo.  
  
#### <a name="defining-and-using-a-grid"></a>Definizione e uso di un elemento Grid  
 Nell'esempio seguente viene illustrato come creare un oggetto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] simile a quello presente nella finestra di dialogo Esegui disponibile nel menu Start di Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento Grid](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 Un oggetto <xref:System.Windows.Controls.StackPanel> consente di "stack" elementi in una direzione assegnata. La direzione predefinita dello stack è verticale. La <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà può essere usata per controllare il flusso di contenuto.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel rispetto a DockPanel  
 Sebbene <xref:System.Windows.Controls.DockPanel> possa anche "stack" elementi figlio <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel> non producono risultati analoghi in alcuni scenari di utilizzo. Ad esempio, l'ordine degli elementi figlio può influire sulle dimensioni in un oggetto <xref:System.Windows.Controls.DockPanel> ma non in un oggetto <xref:System.Windows.Controls.StackPanel> . Ciò è dovuto al fatto <xref:System.Windows.Controls.StackPanel> che le misure nella direzione dello stack in <xref:System.Double.PositiveInfinity> , mentre <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.  
  
 L'esempio seguente illustra questa differenza fondamentale.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La differenza nel comportamento di rendering viene illustrata in questa immagine.  
  
 ![Schermata: StackPanel e DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definizione e uso di un elemento StackPanel  
 Nell'esempio seguente viene illustrato come utilizzare un oggetto <xref:System.Windows.Controls.StackPanel> per creare un set di pulsanti posizionati verticalmente. Per il posizionamento orizzontale, impostare la <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà su <xref:System.Windows.Controls.Orientation.Horizontal> .  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento StackPanel](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce inoltre una variante dell' <xref:System.Windows.Controls.StackPanel> elemento che "virtualizza" automaticamente il contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dei dati, viene generato un subset di elementi in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel>(tramite la funzionalità fornita da <xref:System.Windows.Controls.VirtualizingPanel> ) calcola gli elementi visibili e utilizza <xref:System.Windows.Controls.ItemContainerGenerator> da un oggetto <xref:System.Windows.Controls.ItemsControl> (ad esempio <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView> ) per creare solo elementi per gli elementi visibili.  
  
 L' <xref:System.Windows.Controls.VirtualizingStackPanel> elemento viene impostato automaticamente come host degli elementi per i controlli, ad esempio <xref:System.Windows.Controls.ListBox> . Quando si ospita una raccolta con associazione a dati, il contenuto viene automaticamente virtualizzato, purché il contenuto sia entro i limiti di un <xref:System.Windows.Controls.ScrollViewer> . In questo modo le prestazioni ottenute nell'hosting di molti elementi figlio vengono significativamente migliorate.  
  
 Il markup seguente illustra come usare un oggetto <xref:System.Windows.Controls.VirtualizingStackPanel> come host di elementi. Per <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> eseguire la virtualizzazione, è necessario impostare la proprietà associata su `true` (impostazione predefinita).  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>viene utilizzato per posizionare gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto alla riga successiva quando raggiunge il bordo del contenitore padre. Il contenuto può essere orientato orizzontalmente o verticalmente. <xref:System.Windows.Controls.WrapPanel>è utile per scenari con flussi semplici [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . e consente anche di applicare un ridimensionamento uniforme a tutti i propri elementi figlio.  
  
 Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.WrapPanel> per visualizzare <xref:System.Windows.Controls.Button> i controlli che vengono a capo quando raggiungono il bordo del relativo contenitore.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento WrapPanel](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Elementi Panel annidati  
 <xref:System.Windows.Controls.Panel>gli elementi possono essere annidati l'uno all'interno dell'altro per produrre layout complessi. Questo può risultare molto utile nelle situazioni in cui uno <xref:System.Windows.Controls.Panel> è ideale per una parte di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , ma potrebbe non soddisfare le esigenze di una parte diversa del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .  
  
 Non esiste alcun limite concreto al livello di annidamento che l'applicazione può supportare, ma è preferibile limitare l'uso dei pannelli a quelli effettivamente necessari per il layout desiderato. In molti casi, <xref:System.Windows.Controls.Grid> è possibile utilizzare un elemento anziché i pannelli annidati a causa della relativa flessibilità come contenitore di layout. In questo modo le prestazioni dell'applicazione possono aumentare, grazie all'assenza di elementi non necessari nell'albero.  
  
 Nell'esempio seguente viene illustrato come creare un oggetto che sfrutta i [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vantaggi degli elementi annidati per <xref:System.Windows.Controls.Panel> ottenere un layout specifico. In questo caso particolare, <xref:System.Windows.Controls.DockPanel> viene usato un elemento per fornire la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] struttura, <xref:System.Windows.Controls.StackPanel> gli elementi annidati, un oggetto <xref:System.Windows.Controls.Grid> e un oggetto <xref:System.Windows.Controls.Canvas> per posizionare gli elementi figlio esattamente all'interno dell'elemento padre <xref:System.Windows.Controls.DockPanel> .  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Interfaccia utente che utilizza panelli annidati](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Elementi Panel personalizzati  
 Sebbene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisca una matrice di controlli di layout flessibili, è possibile ottenere comportamenti di layout personalizzati anche eseguendo l'override <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> dei <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi e. Il ridimensionamento e il posizionamento personalizzati possono essere eseguiti definendo nuovi comportamenti di posizionamento in tali metodi di override.  
  
 Analogamente, è possibile definire comportamenti di layout personalizzati basati su classi derivate, ad esempio <xref:System.Windows.Controls.Canvas> o, <xref:System.Windows.Controls.Grid> eseguendo l'override dei relativi <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodi e.  
  
 Nel markup seguente viene illustrato come creare un <xref:System.Windows.Controls.Panel> elemento personalizzato. Questo nuovo <xref:System.Windows.Controls.Panel> , definito come `PlotPanel` , supporta il posizionamento di elementi figlio tramite l'utilizzo di coordinate *x* e *y* hardcoded. In questo esempio, un <xref:System.Windows.Shapes.Rectangle> elemento (non mostrato) viene posizionato in corrispondenza del punto del tracciato 50 (*x*) e 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Per visualizzare un'implementazione di elementi Panel più complessi, vedere [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Supporto per la globalizzazione o la localizzazione  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta un insieme di funzionalità che facilitano la creazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizzabili.  
  
 Tutti gli elementi Panel supportano <xref:System.Windows.FrameworkElement.FlowDirection%2A> in modo nativo la proprietà, che può essere usata per riattivare dinamicamente il contenuto in base alle impostazioni locali o della lingua di un utente. Per altre informazioni, vedere <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La <xref:System.Windows.Window.SizeToContent%2A> proprietà fornisce un meccanismo che consente agli sviluppatori di applicazioni di prevedere le esigenze di localizzate [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Usando il <xref:System.Windows.SizeToContent.WidthAndHeight> valore di questa proprietà, un elemento padre <xref:System.Windows.Window> viene sempre dimensionato in modo dinamico per adattarsi al contenuto e non è vincolato da restrizioni di altezza o larghezza artificiali.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.StackPanel> sono tutte scelte valide per la localizzabilità [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . <xref:System.Windows.Controls.Canvas>non è una scelta ottimale, tuttavia, perché posiziona il contenuto in modo assoluto, rendendolo difficile da localizzare.  
  
 Per ulteriori informazioni sulla creazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di applicazioni con interfacce utente localizzabili (UI) s, vedere la [Panoramica sull'utilizzo del layout automatico](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Compilare una prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Layout](../advanced/layout.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
- [Panoramica su allineamento, margini e spaziatura interna](../advanced/alignment-margins-and-padding-overview.md)
- [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto)
- [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md)
- [Cenni preliminari sull'utilizzo del layout automatico](../advanced/use-automatic-layout-overview.md)
- [Layout e progettazione](../advanced/optimizing-performance-layout-and-design.md)
