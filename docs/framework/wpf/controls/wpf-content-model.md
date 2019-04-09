---
title: Modello di contenuto WPF
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 4f866e0366a7781c287b3ebae7b668c2b296a5cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134607"
---
# <a name="wpf-content-model"></a>Modello di contenuto WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è una piattaforma di presentazione che offre numerosi controlli e tipi simili di controllo con lo scopo principale consiste nel visualizzare tipi diversi di contenuto. Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.  
  
 Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il modello di contenuto descrive il contenuto che può essere usato in un controllo. Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto. Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Classi con contenuto arbitrario  
 Alcuni controlli possono contenere un oggetto di qualsiasi tipo, ad esempio una stringa, un <xref:System.DateTime> oggetto, o un <xref:System.Windows.UIElement> vale a dire un contenitore per altri elementi. Ad esempio, un <xref:System.Windows.Controls.Button> può contenere un'immagine e del testo, o un <xref:System.Windows.Controls.CheckBox> può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono disponibili quattro classi che possono contenere contenuto arbitrario. La tabella seguente elenca le classi che ereditano da <xref:System.Windows.Controls.Control>.  
  
|Classe con contenuto arbitrario|Content|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un singolo oggetto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.|  
|<xref:System.Windows.Controls.ItemsControl>|Una raccolta di oggetti arbitrari.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.|  
  
 I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo. Nella figura seguente illustra un controllo di ogni modello di contenuto che contiene un'immagine e testo:  
  
 ![Screenshot che mostra quattro diversi controlli, uno da ogni modello di contenuto.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Controlli che contengono un singolo oggetto arbitrario  
 Il <xref:System.Windows.Controls.ContentControl> classe contiene un singolo elemento di contenuto arbitrario. Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.ContentControl.Content%2A>. I controlli seguenti ereditano da <xref:System.Windows.Controls.ContentControl> e usano il corrispondente modello di contenuto:  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 La figura seguente illustra quattro pulsanti la cui <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su una stringa, un <xref:System.DateTime> oggetto, un <xref:System.Windows.Shapes.Rectangle>e un <xref:System.Windows.Controls.Panel> che contiene un' <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>:  
  
 ![Screenshot che mostra quattro pulsanti con diversi tipi di contenuto.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Per un esempio di come impostare il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà, vedere <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Controlli che contengono un'intestazione e un singolo oggetto arbitrario  
 Il <xref:System.Windows.Controls.HeaderedContentControl> classe eredita da <xref:System.Windows.Controls.ContentControl> e visualizza il contenuto con un'intestazione. Eredita la proprietà di contenuto <xref:System.Windows.Controls.ContentControl.Content%2A>, dal <xref:System.Windows.Controls.ContentControl> e definisce il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> proprietà che è di tipo <xref:System.Object>; pertanto, entrambi possono essere un oggetto arbitrario.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedContentControl> e usano il corrispondente modello di contenuto:  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 La figura seguente mostra due <xref:System.Windows.Controls.TabItem> oggetti. Il primo <xref:System.Windows.Controls.TabItem> ha <xref:System.Windows.UIElement> oggetti come i <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il <xref:System.Windows.Controls.ContentControl.Content%2A>. Il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> è impostata su una <xref:System.Windows.Controls.StackPanel> che contiene un' <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>. Il <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su una <xref:System.Windows.Controls.StackPanel> che contiene un <xref:System.Windows.Controls.TextBlock> e un <xref:System.Windows.Controls.Label>. La seconda <xref:System.Windows.Controls.TabItem> dispone di una stringa nel <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e una <xref:System.Windows.Controls.TextBlock> nel <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl con tipi diversi di proprietà dell'intestazione.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Per un esempio di come creare <xref:System.Windows.Controls.TabItem> oggetti, vedere <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Controlli che contengono una raccolta di oggetti arbitrari  
 Il <xref:System.Windows.Controls.ItemsControl> classe eredita da <xref:System.Windows.Controls.Control> e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi. Le proprietà di contenuto vengono <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> in genere viene utilizzato per popolare il <xref:System.Windows.Controls.ItemsControl> con una raccolta di dati. Se non si desidera usare una raccolta per popolare la <xref:System.Windows.Controls.ItemsControl>, è possibile aggiungere elementi usando il <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.ItemsControl> e usano il corrispondente modello di contenuto:  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 La figura seguente mostra un <xref:System.Windows.Controls.ListBox> che contiene i tipi di elementi:  
  
-   Stringa.  
  
-   Oggetto <xref:System.DateTime>.  
  
-   Oggetto <xref:System.Windows.UIElement>.  
  
-   Oggetto <xref:System.Windows.Controls.Panel> che contiene un <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>.  
  
 ![Screenshot che mostra un controllo ListBox con quattro tipi di contenuto.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari  
 Il <xref:System.Windows.Controls.HeaderedItemsControl> classe eredita da <xref:System.Windows.Controls.ItemsControl> e può contenere più elementi, ad esempio stringhe, oggetti, o altri elementi e un'intestazione. Eredita le <xref:System.Windows.Controls.ItemsControl> proprietà, del contenuto <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, e <xref:System.Windows.Controls.ItemsControl.Items%2A>, e definisce il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà che può essere un oggetto arbitrario.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedItemsControl> e usano il corrispondente modello di contenuto:  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Classi che contengono una raccolta di oggetti UIElement  
 Il <xref:System.Windows.Controls.Panel> classe di posizionare e disporre figlio <xref:System.Windows.UIElement> oggetti. Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Le classi seguenti ereditano dal <xref:System.Windows.Controls.Panel> classe e usare il modello di contenuto:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Classi che influiscono sull'aspetto di un oggetto UIElement  
 Il <xref:System.Windows.Controls.Decorator> classe applica effetti visivi a o attorno a un singolo elemento figlio <xref:System.Windows.UIElement>. Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.Decorator.Child%2A>. Le classi seguenti ereditano da <xref:System.Windows.Controls.Decorator> e usano il corrispondente modello di contenuto:  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 La figura seguente mostra una <xref:System.Windows.Controls.TextBox> che ha (è decorato con) un <xref:System.Windows.Controls.Border> intorno a esso.  
  
 ![TextBox con bordo nero](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
TextBlock con bordo nero  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Classi che forniscono feedback visivo su un oggetto UIElement  
 Il <xref:System.Windows.Documents.Adorner> classe offre indicazioni visive a un utente. Ad esempio, usare un <xref:System.Windows.Documents.Adorner> per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo. Il <xref:System.Windows.Documents.Adorner> classe fornisce un framework in modo che sia possibile creare strumenti decorativi personalizzati. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati. Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>Classi che consentono agli utenti di immettere testo  
 In WPF sono disponibili tre controlli primari che consentono agli utenti di immettere testo. Ogni controllo determina una visualizzazione diversa del testo. La tabella seguente elenca questi tre controlli correlati al testo, le relative funzionalità per la visualizzazione di testo, nonché le relative proprietà contenenti il testo del controllo.  
  
|Control|Il testo viene visualizzato come|Proprietà di contenuto|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|Testo normale|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Testo formattato|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Testo nascosto (i caratteri sono mascherati)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>Classi che consentono di visualizzare il testo dell'utente  
 Per la visualizzazione di testo normale o formattato sono disponibili numerose classi. È possibile usare <xref:System.Windows.Controls.TextBlock> visualizzare piccole quantità di testo. Se si desidera visualizzare grandi quantità di testo, usare il <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, o <xref:System.Windows.Controls.FlowDocumentScrollViewer> controlli.  
  
 Il <xref:System.Windows.Controls.TextBlock> ha due proprietà di contenuto: <xref:System.Windows.Controls.TextBlock.Text%2A> e <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Quando si desidera visualizzare il testo che usa una formattazione coerente, di <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà è spesso la scelta migliore. Se si prevede di usare una formattazione diversa in tutto il testo, usare il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà. Il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà è una raccolta di <xref:System.Windows.Documents.Inline> oggetti, che specificano la modalità di formattazione del testo.  
  
 Nella tabella seguente elenca le proprietà per <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer> classi.  
  
|Control|Proprietà di contenuto|Tipo proprietà di contenuto|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Document|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Document|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Document|<xref:System.Windows.Documents.FlowDocument>|  
  
 Il <xref:System.Windows.Documents.FlowDocument> implementa la <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaccia; pertanto, tutte le tre classi possono adottare un <xref:System.Windows.Documents.FlowDocument> come contenuto.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Classi che consentono di formattare il testo dell'utente  
 <xref:System.Windows.Documents.TextElement> e le relative classi consentono di formattare il testo. <xref:System.Windows.Documents.TextElement> gli oggetti contengono e formattare il testo nei <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti. I due tipi principali di <xref:System.Windows.Documents.TextElement> gli oggetti vengono <xref:System.Windows.Documents.Block> gli elementi e <xref:System.Windows.Documents.Inline> elementi. Oggetto <xref:System.Windows.Documents.Block> elemento rappresenta un blocco di testo, ad esempio un paragrafo o un elenco. Un <xref:System.Windows.Documents.Inline> elemento rappresenta una porzione di testo in un blocco. Molti <xref:System.Windows.Documents.Inline> classi specificano la formattazione per il testo a cui sono applicati. Ogni <xref:System.Windows.Documents.TextElement> ha un proprio modello di contenuto. Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Avanzate](../advanced/index.md)
