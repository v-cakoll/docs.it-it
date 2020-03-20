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
ms.openlocfilehash: 7810bfbf4f5bedf51e0797a4b9017f589e0b0a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187584"
---
# <a name="panels-overview"></a>Cenni preliminari sugli elementi Panel
<xref:System.Windows.Controls.Panel>Gli elementi sono componenti che controllano il rendering degli elementi, ovvero le dimensioni, la posizione e la disposizione del contenuto figlio. L'oggetto [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un <xref:System.Windows.Controls.Panel> numero di elementi predefiniti, <xref:System.Windows.Controls.Panel> nonché la possibilità di costruire elementi personalizzati.  
  
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
 <xref:System.Windows.Controls.Panel>è la classe base per tutti [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]gli elementi che forniscono supporto di layout in . Gli <xref:System.Windows.Controls.Panel> elementi derivati vengono utilizzati per posizionare e disporre gli elementi e il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite completa di implementazioni di elementi Panel derivati che abilitano numerosi layout complessi. Tali classi derivate espongono proprietà e metodi che consentono di implementare la maggior parte degli scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] standard. Gli sviluppatori che non sono in grado di trovare un comportamento di <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> disposizione figlio che soddisfi le proprie esigenze possono creare nuovi layout eseguendo l'override dei metodi e <xref:System.Windows.FrameworkElement.MeasureOverride%2A> . Per altre informazioni sui comportamenti di layout personalizzati, vedere [Elementi Panel personalizzati](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Membri comuni degli elementi Panel  
 Tutti <xref:System.Windows.Controls.Panel> gli elementi supportano le proprietà <xref:System.Windows.FrameworkElement>di <xref:System.Windows.FrameworkElement.Height%2A>ridimensionamento e posizionamento di base definite da <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, , , <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>e <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Per ulteriori informazioni sul posizionamento delle proprietà definite da <xref:System.Windows.FrameworkElement>, vedere [Alignment, Margins, and Padding Overview](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>espone proprietà aggiuntive di importanza critica per la comprensione e l'utilizzo del layout. La <xref:System.Windows.Controls.Panel.Background%2A> proprietà viene utilizzata per riempire l'area tra i <xref:System.Windows.Media.Brush>bordi di un elemento del pannello derivato con un oggetto . <xref:System.Windows.Controls.Panel.Children%2A>rappresenta la raccolta figlio <xref:System.Windows.Controls.Panel> di elementi di cui è costituito l'oggetto . <xref:System.Windows.Controls.Panel.InternalChildren%2A>rappresenta il contenuto <xref:System.Windows.Controls.Panel.Children%2A> della raccolta più i membri generati dall'associazione dati. Entrambi sono <xref:System.Windows.Controls.UIElementCollection> costituiti da un elemento <xref:System.Windows.Controls.Panel>figlio ospitato all'interno dell'elemento padre .  
  
 Panel espone anche <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> una proprietà associata che può essere utilizzata <xref:System.Windows.Controls.Panel>per ottenere un ordine a più livelli in un oggetto derivato. I membri della <xref:System.Windows.Controls.Panel.Children%2A> collezione di <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> un pannello con un valore <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> più alto appaiono davanti a quelli con un valore inferiore. Ciò è particolarmente utile <xref:System.Windows.Controls.Canvas> per <xref:System.Windows.Controls.Grid> i pannelli come e che consentono agli elementi figlio di condividere lo stesso spazio di coordinate.  
  
 <xref:System.Windows.Controls.Panel>definisce inoltre <xref:System.Windows.Controls.Panel.OnRender%2A> il metodo , che può essere utilizzato <xref:System.Windows.Controls.Panel>per eseguire l'override del comportamento di presentazione predefinito di un oggetto .  
  
#### <a name="attached-properties"></a>Proprietà associate  
 Gli elementi Panel derivati usano ampiamente le proprietà associate. Una proprietà associata è una forma specializzata di proprietà di dipendenza che non dispone della proprietà "wrapper" di Common Language Runtime (CLR) convenzionale. Le proprietà associate presentano una sintassi specializzata in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], illustrata in molti esempi seguenti.  
  
 Uno degli scopi di una proprietà associata è quello di consentire agli elementi figlio di archiviare valori univoci di una proprietà effettivamente definita da un elemento padre. Questa funzionalità, molto utile per il layout dell'applicazione, consente agli elementi figlio di comunicare all'elemento padre il modo in cui devono essere presentati in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Elementi Panel derivati  
 Molti oggetti <xref:System.Windows.Controls.Panel>derivano da , ma non tutti sono destinati all'utilizzo come provider di layout radice. Esistono sei classi di<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.DockPanel>pannello <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.StackPanel>definite <xref:System.Windows.Controls.VirtualizingStackPanel>( <xref:System.Windows.Controls.WrapPanel>, , , , [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], e ) progettate specificamente per la creazione di applicazioni .  
  
 Ogni elemento Panel incapsula la propria funzionalità speciale, come illustrato nella tabella seguente.  
  
|Nome dell'elemento|Elemento Panel dell'interfaccia utente?|Descrizione|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sì|Definisce un'area all'interno della quale è <xref:System.Windows.Controls.Canvas> possibile posizionare in modo esplicito gli elementi figlio in base alle coordinate rispetto all'area.|  
|<xref:System.Windows.Controls.DockPanel>|Sì|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|  
|<xref:System.Windows.Controls.Grid>|Sì|Definisce un'area flessibile della griglia costituita da righe e colonne. Gli elementi <xref:System.Windows.Controls.Grid> figlio di un oggetto <xref:System.Windows.FrameworkElement.Margin%2A> possono essere posizionati con precisione utilizzando la proprietà .|  
|<xref:System.Windows.Controls.StackPanel>|Sì|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Gestisce il layout dei <xref:System.Windows.Controls.TabControl>pulsanti di tabulazione in un oggetto .|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Dispone il contenuto <xref:System.Windows.Controls.ToolBar> all'interno di un controllo.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid>viene utilizzato per disporre gli elementi figlio in una griglia con tutte le dimensioni di cella uguali.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Implementa una classe di base per i pannelli in grado di virtualizzare la raccolta di elementi figlio relativa.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sì|Dispone e virtualizza il contenuto su una singola riga orientato orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sì|<xref:System.Windows.Controls.WrapPanel>posiziona gli elementi figlio in posizione sequenziale da sinistra a destra, suddividendo il contenuto alla riga successiva sul bordo della casella contenitore. L'ordinamento successivo viene eseguito in sequenza dall'alto <xref:System.Windows.Controls.WrapPanel.Orientation%2A> verso il basso o da destra verso sinistra, a seconda del valore della proprietà.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Elementi Panel dell'interfaccia utente  
 Sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] disponibili sei classi di pannello che [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sono <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.DockPanel>ottimizzate per supportare scenari: , <xref:System.Windows.Controls.Grid>, , <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, e <xref:System.Windows.Controls.WrapPanel>. Tali elementi Panel sono facili da usare, versatili ed estendibili per la maggior parte delle applicazioni.  
  
 Ogni <xref:System.Windows.Controls.Panel> elemento derivato considera i vincoli di ridimensionamento in modo diverso. Comprendere come <xref:System.Windows.Controls.Panel> una maniglia vincoli in direzione orizzontale o verticale può rendere il layout più prevedibile.  
  
|**Nome pannello**|**Dimensione x**|**Dimensione y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Vincolato al contenuto|Vincolato al contenuto|  
|<xref:System.Windows.Controls.DockPanel>|Vincolato|Vincolato|  
|<xref:System.Windows.Controls.StackPanel>(Orientamento verticale)|Vincolato|Vincolato al contenuto|  
|<xref:System.Windows.Controls.StackPanel>(Orientamento orizzontale)|Vincolato al contenuto|Vincolato|  
|<xref:System.Windows.Controls.Grid>|Vincolato|Vincolato, tranne <xref:System.Windows.GridUnitType.Auto> nei casi in cui si applicano a righe e colonne|  
|<xref:System.Windows.Controls.WrapPanel>|Vincolato al contenuto|Vincolato al contenuto|  
  
 Di seguito sono disponibili descrizioni più dettagliate ed esempi di uso di ogni elemento.  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>Canvas  
 L'elemento <xref:System.Windows.Controls.Canvas> consente il posizionamento del contenuto in base alle coordinate *x* e *y* assolute. Gli elementi possono essere disegnati in una posizione univoca. Se gli elementi occupano le stesse coordinate, l'ordine in cui vengono disegnati è determinato dall'ordine di visualizzazione nel markup.  
  
 <xref:System.Windows.Controls.Canvas>fornisce il supporto di <xref:System.Windows.Controls.Panel>layout più flessibile di qualsiasi . Le proprietà Height e Width vengono utilizzate per definire l'area dell'area di <xref:System.Windows.Controls.Canvas>disegno e agli elementi all'interno vengono assegnate coordinate assolute rispetto all'area dell'oggetto padre. Quattro <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>proprietà associate, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, e , consentono <xref:System.Windows.Controls.Canvas>un controllo preciso del posizionamento degli oggetti all'interno di un oggetto , consentendo allo sviluppatore di posizionare e disporre gli elementi con precisione sullo schermo.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Proprietà ClipToBounds in un elemento Canvas  
 <xref:System.Windows.Controls.Canvas>può posizionare gli elementi figlio in qualsiasi posizione sullo schermo, <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A>anche in corrispondenza di coordinate esterne a quella definita e . Inoltre, <xref:System.Windows.Controls.Canvas> non è influenzato dalle dimensioni dei suoi figli. Di conseguenza, è possibile che un elemento figlio sovradisegni altri elementi <xref:System.Windows.Controls.Canvas>all'esterno del rettangolo di delimitazione dell'elemento padre. Il comportamento predefinito <xref:System.Windows.Controls.Canvas> di un oggetto consiste nel consentire ai figli di essere disegnati all'esterno dei limiti dell'oggetto padre. <xref:System.Windows.Controls.Canvas> Se questo comportamento non <xref:System.Windows.UIElement.ClipToBounds%2A> è auspicabile, `true`la proprietà può essere impostata su . In <xref:System.Windows.Controls.Canvas> questo modo ritagliare alle proprie dimensioni. <xref:System.Windows.Controls.Canvas>è l'unico elemento di layout che consente di disegnare elementi figlio all'esterno dei limiti.  
  
 Questo comportamento viene illustrato graficamente in [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties) (Esempio di confronto di proprietà Width).  
  
#### <a name="defining-and-using-a-canvas"></a>Definizione e uso di un elemento Canvas  
 È <xref:System.Windows.Controls.Canvas> possibile creare un'istanza di Un semplicemente utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o codice. Nell'esempio seguente viene <xref:System.Windows.Controls.Canvas> illustrato come utilizzare per posizionare in modo assoluto il contenuto. Questo codice produce tre quadrati di 100 pixel. Il primo quadrato è rosso e la posizione del relativo angolo superiore sinistro (*x, y*) è specificata come (0, 0). Il secondo quadrato è verde e la posizione dell'angolo superiore sinistro è impostata su (100, 100), sotto e a destra rispetto al primo quadrato. Il terzo quadrato è blu, con la posizione dell'angolo superiore sinistro impostata su (50, 50). Il quadrato ingloba pertanto il quadrante inferiore destro del primo quadrato e quello superiore sinistro del secondo. Poiché il terzo quadrato è stato disposto per ultimo, sembra posizionato sopra agli altri due e di conseguenza le porzioni sovrapposte ne assumono il colore.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento Canvas](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 L'elemento <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> utilizza la proprietà associata come impostata negli elementi di contenuto figlio per posizionare il contenuto lungo i bordi di un contenitore. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è <xref:System.Windows.Controls.Dock.Top> impostato <xref:System.Windows.Controls.Dock.Bottom>su o , posiziona gli elementi figlio sopra o sotto l'altro. Quando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è <xref:System.Windows.Controls.Dock.Left> impostato <xref:System.Windows.Controls.Dock.Right>su o , posiziona gli elementi figlio a sinistra o a destra l'uno dell'altro. La <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà determina la posizione dell'elemento finale <xref:System.Windows.Controls.DockPanel>aggiunto come figlio di un oggetto .  
  
 È possibile <xref:System.Windows.Controls.DockPanel> utilizzare per posizionare un gruppo di controlli correlati, ad esempio un set di pulsanti. In alternativa, è possibile utilizzarlo per [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]creare un "paned", simile a quello trovato in Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Se <xref:System.Windows.FrameworkElement.Height%2A> le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.Controls.DockPanel> le proprietà non sono specificate, le dimensioni del relativo contenuto. Le dimensioni possono aumentare o diminuire a seconda delle dimensioni degli elementi figlio. Tuttavia, quando queste proprietà vengono specificate e non vi <xref:System.Windows.Controls.DockPanel> è più spazio per il successivo elemento figlio specificato, non visualizza tale elemento figlio o gli elementi figlio successivi e non misura gli elementi figlio successivi.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Per impostazione predefinita, <xref:System.Windows.Controls.DockPanel> l'ultimo elemento figlio di un elemento "riempirà" lo spazio rimanente non allocato. Se questo comportamento non è <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> desiderato, impostare la proprietà su `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definizione e uso di un elemento DockPanel  
 Nell'esempio riportato di seguito <xref:System.Windows.Controls.DockPanel>viene illustrato come partizionare lo spazio utilizzando un oggetto . Vengono <xref:System.Windows.Controls.Border> aggiunti cinque elementi come <xref:System.Windows.Controls.DockPanel>elementi figlio di un elemento padre . Ognuno utilizza una proprietà <xref:System.Windows.Controls.DockPanel> di posizionamento diversa di un spazio di partizione. L'elemento finale riempie lo spazio rimanente non allocato.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipo scenario DockPanel](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Griglia  
 L'elemento <xref:System.Windows.Controls.Grid> unisce la funzionalità di un controllo dati tabulare e di posizionamento assoluto. R <xref:System.Windows.Controls.Grid> consente di posizionare e applicare uno stile facilmente agli elementi. <xref:System.Windows.Controls.Grid>consente di definire raggruppamenti di righe e colonne flessibili e fornisce <xref:System.Windows.Controls.Grid> anche un meccanismo per condividere le informazioni di ridimensionamento tra più elementi.  
  
#### <a name="how-is-grid-different-from-table"></a>Differenza tra gli elementi Grid e Table  
 <xref:System.Windows.Documents.Table>e <xref:System.Windows.Controls.Grid> condividere alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi. A <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto del flusso (vedere [Panoramica del documento](../advanced/flow-document-overview.md) di flusso per altre informazioni sul contenuto del flusso). Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument>oggetto , <xref:System.Windows.Documents.Table> supporta i comportamenti del contenuto del <xref:System.Windows.Controls.Grid> flusso, ad esempio l'impaginazione, la ridisposizione delle colonne e la selezione del contenuto, mentre a non lo fa. Un <xref:System.Windows.Controls.Grid> altro d'altra parte è <xref:System.Windows.Documents.FlowDocument> meglio utilizzato <xref:System.Windows.Controls.Grid> al di fuori di un <xref:System.Windows.Documents.Table> per molti motivi, tra cui aggiunge elementi in base a un indice di riga e colonna, non. L'elemento <xref:System.Windows.Controls.Grid> consente la stratificazione del contenuto figlio, consentendo l'esistenza di più elementi all'interno di una singola "cella". <xref:System.Windows.Documents.Table>non supporta la stratificazione. Gli elementi <xref:System.Windows.Controls.Grid> figlio di un oggetto possono essere posizionati in modo assoluto rispetto all'area dei relativi limiti di "cella". <xref:System.Windows.Documents.Table>non supporta questa funzione. Infine, <xref:System.Windows.Controls.Grid> un è più <xref:System.Windows.Documents.Table>leggero di un .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamento di ridimensionamento di righe e colonne  
 Le colonne e <xref:System.Windows.Controls.Grid> le righe <xref:System.Windows.GridUnitType.Star> definite all'interno di un oggetto possono sfruttare il ridimensionamento per distribuire lo spazio rimanente in modo proporzionale. Quando <xref:System.Windows.GridUnitType.Star> viene selezionata come Altezza o Larghezza di una riga o di una colonna, tale colonna o riga riceve una proporzione ponderata dello spazio disponibile rimanente. Ciò è <xref:System.Windows.GridUnitType.Auto>in contrasto con , che distribuirà lo spazio in modo uniforme in base alle dimensioni del contenuto all'interno di una colonna o di una riga. Questo valore viene espresso come `*` o come `2*` quando si usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Nel primo caso la riga o la colonna riceverebbe una volta lo spazio disponibile, nel secondo caso lo riceverebbe due volte e così via. Combinando questa tecnica per distribuire proporzionalmente <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> lo `Stretch` spazio con un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e il valore di esso è possibile partizionare lo spazio di layout per percentuale di spazio sullo schermo. <xref:System.Windows.Controls.Grid>è l'unico pannello di layout in grado di distribuire lo spazio in questo modo.  
  
#### <a name="defining-and-using-a-grid"></a>Definizione e uso di un elemento Grid  
 Nell'esempio seguente viene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] illustrato come compilare un elemento simile a quello disponibile nella finestra di dialogo Esegui disponibile nel menu Start di Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento Grid](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 Oggetto <xref:System.Windows.Controls.StackPanel> consente di "impilare" gli elementi in una direzione assegnata. La direzione predefinita dello stack è verticale. La <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà può essere utilizzata per controllare il flusso del contenuto.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel e DockPanel  
 Anche <xref:System.Windows.Controls.DockPanel> se può anche "impilare" gli elementi figlio <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel> non produrre risultati analoghi in alcuni scenari di utilizzo. Ad esempio, l'ordine degli elementi figlio <xref:System.Windows.Controls.DockPanel> può influire <xref:System.Windows.Controls.StackPanel>sulle dimensioni in un oggetto ma non in un oggetto . Questo perché <xref:System.Windows.Controls.StackPanel> misura nella direzione <xref:System.Double.PositiveInfinity>dell'impilamento a , mentre <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.  
  
 L'esempio seguente illustra questa differenza fondamentale.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La differenza nel comportamento di rendering viene illustrata in questa immagine.  
  
 ![Schermata: StackPanel e DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definizione e uso di un elemento StackPanel  
 Nell'esempio seguente viene <xref:System.Windows.Controls.StackPanel> illustrato come utilizzare un per creare un set di pulsanti posizionati verticalmente. Per il posizionamento <xref:System.Windows.Controls.StackPanel.Orientation%2A> orizzontale, impostare la proprietà su <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento StackPanel](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce inoltre una <xref:System.Windows.Controls.StackPanel> variante dell'elemento che "virtualizza" automaticamente il contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dei dati, viene generato un subset di elementi in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel>(tramite la <xref:System.Windows.Controls.VirtualizingPanel>funzionalità fornita da ) <xref:System.Windows.Controls.ItemContainerGenerator> calcola <xref:System.Windows.Controls.ItemsControl> gli <xref:System.Windows.Controls.ListBox> elementi <xref:System.Windows.Controls.ListView>visibili e utilizza l'oggetto da un (ad esempio o ) per creare elementi solo per gli elementi visibili.  
  
 L'elemento <xref:System.Windows.Controls.VirtualizingStackPanel> viene impostato automaticamente come host <xref:System.Windows.Controls.ListBox>degli elementi per controlli quali l'oggetto . Quando si ospita una raccolta con associazione a dati, il contenuto viene <xref:System.Windows.Controls.ScrollViewer>virtualizzato automaticamente, purché il contenuto si riperleghi entro i limiti di un oggetto . In questo modo le prestazioni ottenute nell'hosting di molti elementi figlio vengono significativamente migliorate.  
  
 Nel markup seguente viene <xref:System.Windows.Controls.VirtualizingStackPanel> illustrato come utilizzare un come host di elementi. La <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> proprietà associata deve `true` essere impostata su (impostazione predefinita) affinché si verifichi la virtualizzazione.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>viene utilizzato per posizionare gli elementi figlio in posizione sequenziale da sinistra a destra, suddividendo il contenuto alla riga successiva quando raggiunge il bordo del relativo contenitore padre. Il contenuto può essere orientato orizzontalmente o verticalmente. <xref:System.Windows.Controls.WrapPanel>è utile per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari di flusso semplice. e consente anche di applicare un ridimensionamento uniforme a tutti i propri elementi figlio.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.WrapPanel> illustrato <xref:System.Windows.Controls.Button> come creare un per visualizzare i controlli che eseguono il wrapping quando raggiungono il bordo del relativo contenitore.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Tipico elemento WrapPanel](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Elementi Panel annidati  
 <xref:System.Windows.Controls.Panel>gli elementi possono essere nidificati l'uno all'interno dell'altro per produrre layout complessi. Questo può rivelarsi molto <xref:System.Windows.Controls.Panel> utile in situazioni in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]cui si è ideali per una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]parte di un , ma non può soddisfare le esigenze di una parte diversa del .  
  
 Non esiste alcun limite concreto al livello di annidamento che l'applicazione può supportare, ma è preferibile limitare l'uso dei pannelli a quelli effettivamente necessari per il layout desiderato. In molti casi, un <xref:System.Windows.Controls.Grid> elemento può essere utilizzato al posto dei pannelli annidati a causa della sua flessibilità come contenitore di layout. In questo modo le prestazioni dell'applicazione possono aumentare, grazie all'assenza di elementi non necessari nell'albero.  
  
 Nell'esempio seguente viene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] illustrato come creare <xref:System.Windows.Controls.Panel> un che sfrutta gli elementi annidati per ottenere un layout specifico. In questo caso <xref:System.Windows.Controls.DockPanel> particolare, un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento viene <xref:System.Windows.Controls.StackPanel> utilizzato per <xref:System.Windows.Controls.Grid>fornire <xref:System.Windows.Controls.Canvas> la struttura e gli elementi <xref:System.Windows.Controls.DockPanel>annidati, a e a , vengono utilizzati per posizionare gli elementi figlio esattamente all'interno dell'elemento padre.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 L'applicazione compilata crea una nuova [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] analoga alla seguente.  
  
 ![Interfaccia utente che utilizza panelli annidati](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Elementi Panel personalizzati  
 Mentre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una matrice di controlli di layout flessibili, i <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> comportamenti <xref:System.Windows.FrameworkElement.MeasureOverride%2A> di layout personalizzati possono essere ottenuti anche eseguendo l'override di e metodi. Il ridimensionamento e il posizionamento personalizzati possono essere eseguiti definendo nuovi comportamenti di posizionamento in tali metodi di override.  
  
 Analogamente, i comportamenti di layout personalizzati <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Grid>basati su classi derivate (ad esempio o ) possono essere definiti eseguendo l'override dei relativi <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi e <xref:System.Windows.FrameworkElement.MeasureOverride%2A> .  
  
 Nel markup seguente viene illustrato <xref:System.Windows.Controls.Panel> come creare un elemento personalizzato. Questo <xref:System.Windows.Controls.Panel>nuovo , `PlotPanel`definito come , supporta il posizionamento degli elementi figlio tramite l'utilizzo di coordinate *x e* *y* hardcoded. In questo esempio, un <xref:System.Windows.Shapes.Rectangle> elemento (non mostrato) viene posizionato in corrispondenza dei punti di stampa 50 (*x*) e 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Per visualizzare un'implementazione di elementi Panel più complessi, vedere [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Supporto per la globalizzazione o la localizzazione  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta un insieme di funzionalità che facilitano la creazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizzabili.  
  
 Tutti gli elementi del <xref:System.Windows.FrameworkElement.FlowDirection%2A> pannello supportano a livello nativo la proprietà, che può essere utilizzata per ridisporre dinamicamente il contenuto in base alle impostazioni locali o della lingua dell'utente. Per altre informazioni, vedere <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La <xref:System.Windows.Window.SizeToContent%2A> proprietà fornisce un meccanismo che consente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]agli sviluppatori di applicazioni di anticipare le esigenze di localized . Utilizzando <xref:System.Windows.SizeToContent.WidthAndHeight> il valore di questa <xref:System.Windows.Window> proprietà, un elemento padre viene sempre ridimensionato in modo dinamico per adattarsi al contenuto e non è vincolato da restrizioni artificiali di altezza o larghezza.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel> e sono tutte buone scelte per localizzabile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas>non è una buona scelta, tuttavia, perché posiziona il contenuto in modo assoluto, rendendo difficile la localizzazione.  
  
 Per ulteriori informazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sulla creazione di applicazioni con interfacce utente localizzabili, vedere La sezione Utilizzo di [Cenni](../advanced/use-automatic-layout-overview.md)preliminari sul layout automatico .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Layout](../advanced/layout.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
- [Panoramica su allineamento, margini e spaziatura interna](../advanced/alignment-margins-and-padding-overview.md)
- [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979) (Esempio di creazione di un elemento Panel personalizzato con ritorno a capo del contenuto)
- [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md)
- [Cenni preliminari sull'utilizzo del layout automatico](../advanced/use-automatic-layout-overview.md)
- [Layout e progettazione](../advanced/optimizing-performance-layout-and-design.md)
