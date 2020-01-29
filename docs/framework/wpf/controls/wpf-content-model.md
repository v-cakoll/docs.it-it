---
title: Modello di contenuto
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
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738278"
---
# <a name="wpf-content-model"></a>Modello di contenuto WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è una piattaforma di presentazione che offre numerosi controlli e tipi simili a controlli il cui scopo principale consiste nel visualizzare tipi di contenuto diversi. Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.  
  
 Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il modello di contenuto descrive il contenuto che può essere usato in un controllo. Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto. Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Classi con contenuto arbitrario  
 Alcuni controlli possono contenere un oggetto di qualsiasi tipo, ad esempio una stringa, un oggetto <xref:System.DateTime> o un <xref:System.Windows.UIElement> contenitore per elementi aggiuntivi. Ad esempio, un <xref:System.Windows.Controls.Button> può contenere un'immagine e un testo; oppure un <xref:System.Windows.Controls.CheckBox> può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre quattro classi in grado di includere contenuto arbitrario. Nella tabella seguente sono elencate le classi che ereditano da <xref:System.Windows.Controls.Control>.  
  
|Classe con contenuto arbitrario|Contenuto|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un singolo oggetto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.|  
|<xref:System.Windows.Controls.ItemsControl>|Una raccolta di oggetti arbitrari.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.|  
  
 I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo. Nella figura seguente viene illustrato un controllo di ogni modello di contenuto che contiene un'immagine e del testo:  
  
 ![Screenshot che mostra quattro controlli diversi, uno per ogni modello di contenuto.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Controlli che contengono un singolo oggetto arbitrario  
 La classe <xref:System.Windows.Controls.ContentControl> contiene una singola parte di contenuto arbitrario. La relativa proprietà Content è <xref:System.Windows.Controls.ContentControl.Content%2A>. I controlli seguenti ereditano da <xref:System.Windows.Controls.ContentControl> e usano il modello di contenuto:  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 Nella figura seguente sono illustrati quattro pulsanti il cui <xref:System.Windows.Controls.ContentControl.Content%2A> è impostato su una stringa, un oggetto <xref:System.DateTime>, un <xref:System.Windows.Shapes.Rectangle>e un <xref:System.Windows.Controls.Panel> contenente un <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>:  
  
 ![Screenshot che mostra quattro pulsanti con tipi di contenuto diversi.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Per un esempio di come impostare la proprietà <xref:System.Windows.Controls.ContentControl.Content%2A>, vedere <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Controlli che contengono un'intestazione e un singolo oggetto arbitrario  
 La classe <xref:System.Windows.Controls.HeaderedContentControl> eredita da <xref:System.Windows.Controls.ContentControl> e visualizza il contenuto con un'intestazione. Eredita la proprietà Content, <xref:System.Windows.Controls.ContentControl.Content%2A>, da <xref:System.Windows.Controls.ContentControl> e definisce la proprietà <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di tipo <xref:System.Object>; Pertanto, entrambi possono essere un oggetto arbitrario.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedContentControl> e usano il modello di contenuto:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 Nella figura seguente vengono illustrati due oggetti <xref:System.Windows.Controls.TabItem>. Il primo <xref:System.Windows.Controls.TabItem> ha <xref:System.Windows.UIElement> oggetti come <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e la <xref:System.Windows.Controls.ContentControl.Content%2A>. Il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> è impostato su un <xref:System.Windows.Controls.StackPanel> che contiene un <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>. Il <xref:System.Windows.Controls.ContentControl.Content%2A> è impostato su un <xref:System.Windows.Controls.StackPanel> che contiene una <xref:System.Windows.Controls.TextBlock> e una <xref:System.Windows.Controls.Label>. Il secondo <xref:System.Windows.Controls.TabItem> dispone di una stringa nel <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e di un <xref:System.Windows.Controls.TextBlock> nel <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl che usa tipi diversi nella proprietà dell'intestazione.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Per un esempio di come creare oggetti <xref:System.Windows.Controls.TabItem>, vedere <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Controlli che contengono una raccolta di oggetti arbitrari  
 La classe <xref:System.Windows.Controls.ItemsControl> eredita da <xref:System.Windows.Controls.Control> e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi. Le proprietà di contenuto sono <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> viene in genere usato per popolare la <xref:System.Windows.Controls.ItemsControl> con una raccolta di dati. Se non si desidera utilizzare una raccolta per popolare il <xref:System.Windows.Controls.ItemsControl>, è possibile aggiungere elementi utilizzando la proprietà <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.ItemsControl> e usano il modello di contenuto:  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 Nella figura seguente viene illustrato un <xref:System.Windows.Controls.ListBox> che contiene questi tipi di elementi:  
  
- stringa.  
  
- Un oggetto <xref:System.DateTime>.  
  
- Oggetto <xref:System.Windows.UIElement>.  
  
- <xref:System.Windows.Controls.Panel> contenente una <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>.  
  
 ![Screenshot che mostra una casella di riepilogo con quattro tipi di contenuto.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari  
 La classe <xref:System.Windows.Controls.HeaderedItemsControl> eredita da <xref:System.Windows.Controls.ItemsControl> e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi e un'intestazione. Eredita le proprietà del contenuto <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>e <xref:System.Windows.Controls.ItemsControl.Items%2A>e definisce la proprietà <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> che può essere un oggetto arbitrario.  
  
 I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedItemsControl> e usano il modello di contenuto:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Classi che contengono una raccolta di oggetti UIElement  
 La classe <xref:System.Windows.Controls.Panel> posiziona e dispone gli oggetti <xref:System.Windows.UIElement> figlio. La relativa proprietà Content è <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Le classi seguenti ereditano dalla classe <xref:System.Windows.Controls.Panel> e usano il relativo modello di contenuto:  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Classi che influiscono sull'aspetto di un oggetto UIElement  
 La classe <xref:System.Windows.Controls.Decorator> applica effetti visivi a un singolo <xref:System.Windows.UIElement>figlio. La relativa proprietà Content è <xref:System.Windows.Controls.Decorator.Child%2A>. Le classi seguenti ereditano da <xref:System.Windows.Controls.Decorator> e usano il relativo modello di contenuto:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 Nella figura seguente viene illustrato un <xref:System.Windows.Controls.TextBox> che ha (è decorato con) un <xref:System.Windows.Controls.Border> intorno.  
  
 ![TextBox con bordo nero](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
TextBlock con bordo nero  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Classi che forniscono feedback visivo su un oggetto UIElement  
 La classe <xref:System.Windows.Documents.Adorner> fornisce indicazioni visive a un utente. Ad esempio, usare un <xref:System.Windows.Documents.Adorner> per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo. La classe <xref:System.Windows.Documents.Adorner> fornisce un Framework in cui è possibile creare strumenti decorativi personalizzati. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati. Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](adorners-overview.md).  
  
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
 Per la visualizzazione di testo normale o formattato sono disponibili numerose classi. È possibile utilizzare <xref:System.Windows.Controls.TextBlock> per visualizzare piccole quantità di testo. Se si desidera visualizzare grandi quantità di testo, utilizzare i controlli <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Il <xref:System.Windows.Controls.TextBlock> dispone di due proprietà di contenuto: <xref:System.Windows.Controls.TextBlock.Text%2A> e <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Quando si desidera visualizzare il testo che utilizza la formattazione coerente, la proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> è spesso la scelta migliore. Se si prevede di usare una formattazione diversa per tutto il testo, usare la proprietà <xref:System.Windows.Controls.TextBlock.Inlines%2A>. La proprietà <xref:System.Windows.Controls.TextBlock.Inlines%2A> è una raccolta di oggetti <xref:System.Windows.Documents.Inline>, che specificano la modalità di formattazione del testo.  
  
 La tabella seguente elenca la proprietà Content per le classi <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>e <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
|Control|Proprietà di contenuto|Tipo proprietà di contenuto|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Documento|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
  
 Il <xref:System.Windows.Documents.FlowDocument> implementa l'interfaccia <xref:System.Windows.Documents.IDocumentPaginatorSource>; Pertanto, tutte e tre le classi possono assumere un <xref:System.Windows.Documents.FlowDocument> come contenuto.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Classi che consentono di formattare il testo dell'utente  
 <xref:System.Windows.Documents.TextElement> e le classi correlate consentono di formattare il testo. gli oggetti <xref:System.Windows.Documents.TextElement> contengono e formattano il testo negli oggetti <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument>. I due tipi principali di oggetti <xref:System.Windows.Documents.TextElement> sono elementi <xref:System.Windows.Documents.Block> ed elementi <xref:System.Windows.Documents.Inline>. Un elemento <xref:System.Windows.Documents.Block> rappresenta un blocco di testo, ad esempio un paragrafo o un elenco. Un elemento <xref:System.Windows.Documents.Inline> rappresenta una parte di testo in un blocco. Molte <xref:System.Windows.Documents.Inline> classi specificano la formattazione per il testo a cui vengono applicate. Ogni <xref:System.Windows.Documents.TextElement> dispone di un proprio modello di contenuto. Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Avanzate](../advanced/index.md)
