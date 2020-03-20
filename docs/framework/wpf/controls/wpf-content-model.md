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
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187397"
---
# <a name="wpf-content-model"></a>Modello di contenuto WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è una piattaforma di presentazione che offre numerosi controlli e tipi simili a controlli il cui scopo principale consiste nel visualizzare tipi di contenuto diversi. Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.  
  
 Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il modello di contenuto descrive il contenuto che può essere usato in un controllo. Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto. Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a>Classi con contenuto arbitrario  
 Alcuni controlli possono contenere un oggetto di qualsiasi <xref:System.DateTime> tipo, <xref:System.Windows.UIElement> ad esempio una stringa, un oggetto o un oggetto che è un contenitore per gli elementi aggiuntivi. Ad esempio, <xref:System.Windows.Controls.Button> un può contenere un'immagine e del testo; o <xref:System.Windows.Controls.CheckBox> un può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre quattro classi in grado di includere contenuto arbitrario. Nella tabella seguente sono elencate <xref:System.Windows.Controls.Control>le classi , che ereditano da .  
  
|Classe con contenuto arbitrario|Contenuto|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un singolo oggetto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.|  
|<xref:System.Windows.Controls.ItemsControl>|Una raccolta di oggetti arbitrari.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.|  
  
 I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo. Nella figura seguente viene illustrato un controllo da ogni modello di contenuto che contiene un'immagine e del testo:The following illustration shows one control from each content model that contains an image and some text:  
  
 ![Screenshot che mostra quattro controlli diversi, uno per ogni modello di contenuto.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Controlli che contengono un singolo oggetto arbitrario  
 La <xref:System.Windows.Controls.ContentControl> classe contiene una singola parte di contenuto arbitrario. La proprietà <xref:System.Windows.Controls.ContentControl.Content%2A>content è . I controlli seguenti <xref:System.Windows.Controls.ContentControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:  
  
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
  
 Nella figura seguente vengono <xref:System.Windows.Controls.ContentControl.Content%2A> illustrati quattro pulsanti <xref:System.DateTime> il <xref:System.Windows.Shapes.Rectangle>cui è <xref:System.Windows.Controls.Panel> impostato <xref:System.Windows.Shapes.Ellipse> su <xref:System.Windows.Controls.TextBlock>una stringa, un oggetto, un oggetto e un che contiene un oggetto e un :  
  
 ![Screenshot che mostra quattro pulsanti con tipi di contenuto diversi.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Per un esempio di <xref:System.Windows.Controls.ContentControl.Content%2A> impostazione <xref:System.Windows.Controls.ContentControl>della proprietà, vedere .  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Controlli che contengono un'intestazione e un singolo oggetto arbitrario  
 La <xref:System.Windows.Controls.HeaderedContentControl> classe eredita <xref:System.Windows.Controls.ContentControl> da e visualizza il contenuto con un'intestazione. Eredita <xref:System.Windows.Controls.ContentControl.Content%2A>la proprietà content, <xref:System.Windows.Controls.ContentControl> , da <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e definisce <xref:System.Object>la proprietà di tipo ; pertanto, entrambi possono essere un oggetto arbitrario.  
  
 I controlli seguenti <xref:System.Windows.Controls.HeaderedContentControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 Nella figura seguente <xref:System.Windows.Controls.TabItem> vengono illustrati due oggetti. Il <xref:System.Windows.Controls.TabItem> primo <xref:System.Windows.UIElement> dispone <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di <xref:System.Windows.Controls.ContentControl.Content%2A>oggetti come il e il . <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> L'oggetto è <xref:System.Windows.Controls.StackPanel> impostato <xref:System.Windows.Shapes.Ellipse> su <xref:System.Windows.Controls.TextBlock>a che contiene un e un oggetto . <xref:System.Windows.Controls.ContentControl.Content%2A> L'oggetto è <xref:System.Windows.Controls.StackPanel> impostato <xref:System.Windows.Controls.TextBlock> su <xref:System.Windows.Controls.Label>a che contiene a e un oggetto . Il <xref:System.Windows.Controls.TabItem> secondo ha una <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> stringa <xref:System.Windows.Controls.TextBlock> in <xref:System.Windows.Controls.ContentControl.Content%2A>e a nel file .  
  
 ![TabControl che utilizza tipi diversi nel Header proprietà.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Per un esempio di <xref:System.Windows.Controls.TabItem> creazione <xref:System.Windows.Controls.HeaderedContentControl>di oggetti, vedere .  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Controlli che contengono una raccolta di oggetti arbitrari  
 La <xref:System.Windows.Controls.ItemsControl> classe eredita <xref:System.Windows.Controls.Control> da e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi. Le proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> di <xref:System.Windows.Controls.ItemsControl.Items%2A>contenuto sono e . <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>viene in genere <xref:System.Windows.Controls.ItemsControl> utilizzato per popolare l'oggetto con una raccolta di dati. Se non si desidera utilizzare un <xref:System.Windows.Controls.ItemsControl>insieme per popolare l'oggetto , è possibile aggiungere elementi utilizzando la <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà .  
  
 I controlli seguenti <xref:System.Windows.Controls.ItemsControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:  
  
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
  
 Nella figura seguente <xref:System.Windows.Controls.ListBox> viene illustrato un che contiene questi tipi di elementi:  
  
- Stringa.  
  
- Oggetto <xref:System.DateTime> .  
  
- <xref:System.Windows.UIElement>.  
  
- Oggetto <xref:System.Windows.Controls.Panel> che <xref:System.Windows.Shapes.Ellipse> contiene <xref:System.Windows.Controls.TextBlock>un e un oggetto .  
  
 ![Screenshot che mostra un controllo ListBox con quattro tipi di contenuto.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari  
 La <xref:System.Windows.Controls.HeaderedItemsControl> classe eredita <xref:System.Windows.Controls.ItemsControl> da e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi e un'intestazione. Eredita le <xref:System.Windows.Controls.ItemsControl> proprietà di <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>contenuto, , e <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> , e definisce la proprietà che può essere un oggetto arbitrario.  
  
 I controlli seguenti <xref:System.Windows.Controls.HeaderedItemsControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Classi che contengono una raccolta di oggetti UIElement  
 La <xref:System.Windows.Controls.Panel> classe posiziona e <xref:System.Windows.UIElement> dispone gli oggetti figlio. La proprietà <xref:System.Windows.Controls.Panel.Children%2A>content è .  
  
 Le classi seguenti <xref:System.Windows.Controls.Panel> ereditano dalla classe e utilizzano il relativo modello di contenuto:The following classes inherit from the class and use its content model:  
  
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
 La <xref:System.Windows.Controls.Decorator> classe applica effetti visivi su <xref:System.Windows.UIElement>o intorno a un singolo figlio . La proprietà <xref:System.Windows.Controls.Decorator.Child%2A>content è . Le classi seguenti <xref:System.Windows.Controls.Decorator> ereditano da e utilizzano il relativo modello di contenuto:The following classes inherit from and use its content model:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 Nella figura seguente <xref:System.Windows.Controls.TextBox> viene illustrato un che <xref:System.Windows.Controls.Border> ha (è decorato con) un intorno ad esso.  
  
 ![TextBox con bordo nero](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
TextBlock con bordo nero  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Classi che forniscono feedback visivo su un oggetto UIElement  
 La <xref:System.Windows.Documents.Adorner> classe fornisce segnali visivi a un utente. Ad esempio, <xref:System.Windows.Documents.Adorner> utilizzare un oggetto per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato di un controllo. La <xref:System.Windows.Documents.Adorner> classe fornisce un framework in modo che è possibile creare strumenti decorativi visuali personalizzati. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati. Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a>Classi che consentono agli utenti di immettere testo  
 In WPF sono disponibili tre controlli primari che consentono agli utenti di immettere testo. Ogni controllo determina una visualizzazione diversa del testo. La tabella seguente elenca questi tre controlli correlati al testo, le relative funzionalità per la visualizzazione di testo, nonché le relative proprietà contenenti il testo del controllo.  
  
|Controllo|Il testo viene visualizzato come|Proprietà di contenuto|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|Testo normale|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Testo formattato|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Testo nascosto (i caratteri sono mascherati)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a>Classi che consentono di visualizzare il testo dell'utente  
 Per la visualizzazione di testo normale o formattato sono disponibili numerose classi. È possibile <xref:System.Windows.Controls.TextBlock> utilizzare per visualizzare piccole quantità di testo. Se si desidera visualizzare grandi quantità di <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>testo, <xref:System.Windows.Controls.FlowDocumentScrollViewer> utilizzare i controlli , o .  
  
 Il <xref:System.Windows.Controls.TextBlock> dispone di <xref:System.Windows.Controls.TextBlock.Text%2A> due <xref:System.Windows.Controls.TextBlock.Inlines%2A>proprietà di contenuto: e . Quando si desidera visualizzare testo che <xref:System.Windows.Controls.TextBlock.Text%2A> utilizza una formattazione coerente, la proprietà è spesso la scelta migliore. Se si prevede di utilizzare una formattazione diversa in tutto il testo, utilizzare la <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà . La <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà è <xref:System.Windows.Documents.Inline> una raccolta di oggetti che specificano come formattare il testo.  
  
 Nella tabella seguente sono <xref:System.Windows.Controls.FlowDocumentReader>elencate <xref:System.Windows.Controls.FlowDocumentPageViewer>le <xref:System.Windows.Controls.FlowDocumentScrollViewer> proprietà di contenuto per le classi , e .  
  
|Controllo|Proprietà di contenuto|Tipo proprietà di contenuto|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Document|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Document|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Document|<xref:System.Windows.Documents.FlowDocument>|  
  
 Implementa <xref:System.Windows.Documents.FlowDocument> l'interfaccia; <xref:System.Windows.Documents.IDocumentPaginatorSource> pertanto, tutte e <xref:System.Windows.Documents.FlowDocument> tre le classi possono prendere un come contenuto.  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a>Classi che consentono di formattare il testo dell'utente  
 <xref:System.Windows.Documents.TextElement>e le classi correlate consentono di formattare il testo. <xref:System.Windows.Documents.TextElement>oggetti contengono e <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Documents.FlowDocument> formattano il testo e gli oggetti. I due tipi <xref:System.Windows.Documents.TextElement> principali <xref:System.Windows.Documents.Block> di <xref:System.Windows.Documents.Inline> oggetti sono elementi ed elementi. Un <xref:System.Windows.Documents.Block> elemento rappresenta un blocco di testo, ad esempio un paragrafo o un elenco. Un <xref:System.Windows.Documents.Inline> elemento rappresenta una parte di testo in un blocco. Molte <xref:System.Windows.Documents.Inline> classi specificano la formattazione per il testo a cui vengono applicate. Ognuno <xref:System.Windows.Documents.TextElement> ha il proprio modello di contenuto. Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Avanzate](../advanced/index.md)
