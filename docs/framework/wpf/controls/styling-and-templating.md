---
title: Applicazione di stili e modelli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- triggers [WPF]
- styles [WPF], referencing
- event triggers [WPF]
- styles [WPF], prerequisites
- styles [WPF], declaring
- styles [WPF], overview
- styles [WPF], extending
- styles [WPF], triggers
- styles [WPF], event triggers
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
ms.openlocfilehash: 580eb2c7efd00382f7fff24984f0ce6f6d8fa027
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370722"
---
# <a name="styling-and-templating"></a>Applicazione di stili e modelli
Gli stili e i modelli di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono un insieme di funzionalità (stili, modelli, trigger e storyboard) che gli sviluppatori e i progettisti usano per creare effetti visivamente accattivanti e per conferire al prodotto un aspetto coerente. Gli sviluppatori e i progettisti possono personalizzare ampiamente l'aspetto a livello di applicazione, ma l'uso di un modello di stili e modelli definito è fondamentale per consentire la manutenzione e la condivisione dell'aspetto all'interno di un'applicazione e tra più applicazioni. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre questo modello.  
  
 Un'altra caratteristica del modello di stili di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è la separazione tra presentazione e logica. In pratica, mentre gli sviluppatori lavorano sulla logica di programmazione usando C# o Visual Basic, i progettisti possono lavorare sull'aspetto di un'applicazione usando solo il linguaggio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Questa panoramica è incentrata sugli aspetti legati agli stili e ai modelli dell'applicazione e non tratta i concetti relativi al data binding. Per informazioni sul data binding, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).  
  
 È inoltre importante conoscere le risorse, che consentono il riutilizzo dei modelli e degli stili. Per altre informazioni sulle risorse, vedere [Risorse XAML](../advanced/xaml-resources.md).

<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Esempio di applicazione di stili e modelli  
 Gli esempi di codice usati in questa panoramica sono basati su un esempio di foto semplice mostrato nella figura seguente:  
  
 ![ListView con stile](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 Questo esempio usa stili e modelli per creare un'esperienza utente visivamente accattivante. L'esempio ha due <xref:System.Windows.Controls.TextBlock> elementi e un <xref:System.Windows.Controls.ListBox> controllo associato a un elenco di immagini. Per l'esempio completo, vedere [Introduzione a un esempio di applicazione di stili e di modelli](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Nozioni di base sugli stili  
 È possibile considerare un <xref:System.Windows.Style> come un modo pratico per applicare un set di valori di proprietà per più di un elemento. Ad esempio, tenere presente quanto segue <xref:System.Windows.Controls.TextBlock> elementi e il relativo aspetto predefinito:  
  
 [!code-xaml[StylingIntroSample_snippet#TextBlocks](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Screenshot di esempio di applicazione di uno stile](./media/stylingintro-textblocksbefore.PNG "StylingIntro_TextBlocksBefore")  
  
 È possibile modificare l'aspetto predefinito impostando le proprietà, ad esempio <xref:System.Windows.Controls.Control.FontSize%2A> e <xref:System.Windows.Controls.Control.FontFamily%2A>, su ogni <xref:System.Windows.Controls.TextBlock> elemento direttamente. Tuttavia, se si desidera che il <xref:System.Windows.Controls.TextBlock> elementi condividere alcune proprietà, è possibile creare un <xref:System.Windows.Style> nel `Resources` sezione del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, come illustrato di seguito:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb1](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Quando si imposta la <xref:System.Windows.Style.TargetType%2A> dello stile per il <xref:System.Windows.Controls.TextBlock> tipo, lo stile applicato a tutti i <xref:System.Windows.Controls.TextBlock> elementi nella finestra.  
  
 A questo punto il <xref:System.Windows.Controls.TextBlock> gli elementi vengono visualizzati come indicato di seguito:  
  
 ![Screenshot di esempio di applicazione di uno stile](./media/stylingintro-textblocksbasestyle.PNG "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Estensione degli stili  
 Probabilmente si desidera che i due <xref:System.Windows.Controls.TextBlock> elementi condividono alcuni valori delle proprietà, ad esempio il <xref:System.Windows.Controls.Control.FontFamily%2A> e il centrato <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, ma opportuno anche il testo "My Pictures" hanno alcune proprietà aggiuntive. Creare a tal fine un nuovo stile basato sul primo stile, come illustrato di seguito:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Si noti che allo stile precedente è assegnato un attributo `x:Key`. Per applicare lo stile, impostare il <xref:System.Windows.FrameworkElement.Style%2A> proprietà di <xref:System.Windows.Controls.TextBlock> per il `x:Key` valore, come illustrato di seguito:  
  
 [!code-xaml[StylingIntroSnippet#UIText](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Ciò <xref:System.Windows.Controls.TextBlock> stile include ora una <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> pari a <xref:System.Windows.HorizontalAlignment.Center>, un <xref:System.Windows.Controls.TextBlock.FontFamily%2A> pari a `Comic Sans MS`, un <xref:System.Windows.Controls.TextBlock.FontSize%2A> valore pari a 26 e un <xref:System.Windows.Controls.TextBlock.Foreground%2A> valore impostato sul <xref:System.Windows.Media.LinearGradientBrush> illustrato nell'esempio. Si noti che viene eseguito l'override di <xref:System.Windows.Controls.Control.FontSize%2A> valore dello stile di base. Se è presente più di un <xref:System.Windows.Setter> impostano la stessa proprietà un <xref:System.Windows.Style>, il <xref:System.Windows.Setter> vale a dire dichiarato ultima ha la precedenza.  
  
 Di seguito viene illustrato ciò che il <xref:System.Windows.Controls.TextBlock> elementi essere simile a:  
  
 ![TextBlock con stile](./media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Ciò `TitleText` stile di visualizzazione estende lo stile che è stato creato per il <xref:System.Windows.Controls.TextBlock> tipo. È anche possibile estendere uno stile con attributo `x:Key` usando il valore di `x:Key`. Per un esempio, vedere l'esempio fornito per il <xref:System.Windows.Style.BasedOn%2A> proprietà.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relazione tra la proprietà TargetType e l'attributo x:Key  
 Come illustrato nel primo esempio, impostando il <xref:System.Windows.Style.TargetType%2A> proprietà `TextBlock` senza l'assegnazione un' `x:Key` fa sì che lo stile da applicare a tutti i <xref:System.Windows.Controls.TextBlock> elementi. In questo caso, l'attributo `x:Key` è impostato in modo implicito su `{x:Type TextBlock}`. Ciò significa che se si imposta in modo esplicito il `x:Key` su un valore diverso da `{x:Type TextBlock}`, il <xref:System.Windows.Style> non viene applicato a tutti <xref:System.Windows.Controls.TextBlock> elementi automaticamente. In alternativa, è necessario applicare lo stile (usando il `x:Key` valore) per il <xref:System.Windows.Controls.TextBlock> elementi in modo esplicito. Se lo stile si trova nella sezione delle risorse e non si impostano i <xref:System.Windows.Style.TargetType%2A> proprietà di stile, quindi è necessario fornire un `x:Key`.  
  
 Oltre a fornire un valore predefinito per il `x:Key`, il <xref:System.Windows.Style.TargetType%2A> proprietà specifica il tipo a cui si applicano le proprietà del setter. Se non si specifica un <xref:System.Windows.Style.TargetType%2A>, è necessario qualificare la proprietà di <xref:System.Windows.Setter> gli oggetti con il nome di una classe usando la sintassi `Property="ClassName.Property"`. Ad esempio, anziché impostare `Property="FontSize"`, è necessario impostare <xref:System.Windows.Setter.Property%2A> al `"TextBlock.FontSize"` o `"Control.FontSize"`.  
  
 Si noti inoltre che molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono costituiti da una combinazione di altri controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se si crea uno stile che si applica a tutti i controlli di un tipo, è possibile che si ottengano risultati imprevisti. Ad esempio, se si crea uno stile destinato il <xref:System.Windows.Controls.TextBlock> digitare un <xref:System.Windows.Window>, lo stile applicato a tutti <xref:System.Windows.Controls.TextBlock> controlli nella finestra anche se il <xref:System.Windows.Controls.TextBlock> fa parte di un altro controllo, ad esempio un <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Stili e risorse  
 È possibile usare uno stile in qualsiasi elemento da cui deriva <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Il modo più comune di dichiarare uno stile è come risorsa nella sezione `Resources` di un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come illustrato negli esempi precedenti. Poiché gli stili sono risorse, obbediscono alle stesse regole di ambito che si applicano a tutte le risorse. Il punto in cui si dichiara uno stile influisce sugli elementi a cui lo stile può essere applicato. Se, ad esempio, si dichiara lo stile nell'elemento radice del file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di definizione dell'applicazione, lo stile può essere usato ovunque nell'applicazione. Se si crea un'applicazione di navigazione e si dichiara lo stile in uno dei file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dell'applicazione, lo stile può essere usato solo in quel file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per altre informazioni sulle regole di ambito delle risorse, vedere [Risorse XAML](../advanced/xaml-resources.md).  
  
 Altre informazioni sugli stili e le risorse sono disponibili nella sezione [Risorse e temi condivisi](#styling_themes) più avanti in questa panoramica.  
  
### <a name="setting-styles-programmatically"></a>Impostazione degli stili a livello di codice  
 Per assegnare uno stile denominato a un elemento a livello di codice, ottenere lo stile dalla raccolta di risorse e assegnarlo alla proprietà dell'elemento <xref:System.Windows.FrameworkElement.Style%2A> proprietà. Si noti che gli elementi in una raccolta di risorse sono di tipo <xref:System.Object>. Pertanto, è necessario eseguire il cast lo stile recuperato a un <xref:System.Windows.Style> prima di assegnarlo al <xref:System.Windows.FrameworkElement.Style%2A> proprietà. Ad esempio, per impostare l'oggetto definito `TitleText` applicare uno stile in un <xref:System.Windows.Controls.TextBlock> denominata `textblock1`, eseguire le operazioni seguenti:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Si noti che quando si applica uno stile, questo viene bloccato e non è più possibile modificarlo. Se si intende modificarlo in modo dinamico, è necessario crearne uno nuovo in sostituzione di quello esistente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Style.IsSealed%2A>.  
  
 È possibile creare un oggetto che sceglie uno stile da applicare in base alla logica personalizzata. Per un esempio, vedere l'esempio fornito per il <xref:System.Windows.Controls.StyleSelector> classe.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Associazioni, risorse dinamiche e gestori eventi  
 Si noti che è possibile usare la proprietà `Setter.Value` per specificare una [estensione di markup di associazione](../advanced/binding-markup-extension.md) o una [estensione di markup DynamicResource](../advanced/dynamicresource-markup-extension.md). Per altre informazioni, vedere gli esempi forniti per il <xref:System.Windows.Setter.Value%2A?displayProperty=nameWithType> proprietà.  
  
 Questa panoramica si limita a illustrare l'uso dei setter per impostare il valore delle proprietà. In uno stile è possibile specificare anche i gestori eventi. Per altre informazioni, vedere <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Modelli di dati  
 In questa applicazione di esempio è presente un <xref:System.Windows.Controls.ListBox> controllo associato a un elenco di foto:  
  
 [!code-xaml[StylingIntroSnippet#UIListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Ciò <xref:System.Windows.Controls.ListBox> attualmente simile al seguente:  
  
 ![ListBox prima dell'applicazione del modello](./media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 La maggior parte dei controlli include un tipo di contenuto che spesso deriva da dati che si sceglie di associare. In questo esempio i dati sono l'elenco di foto. Nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si utilizza un <xref:System.Windows.DataTemplate> per definire la rappresentazione visiva dei dati. In sostanza, gli elementi da inserire in un <xref:System.Windows.DataTemplate> determina l'aspetto dei dati nell'applicazione sottoposta a rendering.  
  
 Nell'applicazione di esempio ogni oggetto `Photo` personalizzato dispone di una proprietà `Source` di tipo stringa che specifica il percorso file dell'immagine. Gli oggetti foto in questo momento appaiono come percorsi file.  
  
 Per le foto vengano visualizzate come immagini, si crea un <xref:System.Windows.DataTemplate> come risorsa:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#DataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Si noti che il <xref:System.Windows.DataTemplate.DataType%2A> proprietà è molto simile al <xref:System.Windows.Style.TargetType%2A> proprietà del <xref:System.Windows.Style>. Se il <xref:System.Windows.DataTemplate> si trova nella sezione delle risorse, quando si specifica il <xref:System.Windows.DataTemplate.DataType%2A> proprietà a un tipo e non le si assegna un `x:Key`, il <xref:System.Windows.DataTemplate> viene applicato ogni volta che appare tale tipo. Avere sempre la possibilità di assegnare il <xref:System.Windows.DataTemplate> con un `x:Key` e quindi impostarla come un `StaticResource` per le proprietà che accettano <xref:System.Windows.DataTemplate> tipi, ad esempio il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà o il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.  
  
 In pratica, il <xref:System.Windows.DataTemplate> nell'esempio precedente definisce che ogni volta che è presente una `Photo` dell'oggetto, questo deve apparire come un <xref:System.Windows.Controls.Image> all'interno di un <xref:System.Windows.Controls.Border>. Con questo <xref:System.Windows.DataTemplate>, l'applicazione appare ora simile al seguente:  
  
 ![Immagine foto](./media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 Il modello di applicazione di modelli di dati fornisce altre funzionalità. Ad esempio, se si visualizzano i dati di raccolta che contiene altre raccolte che usano un <xref:System.Windows.Controls.HeaderedItemsControl> digitare, ad esempio un <xref:System.Windows.Controls.Menu> o una <xref:System.Windows.Controls.TreeView>, è presente il <xref:System.Windows.HierarchicalDataTemplate>. Un'altra funzionalità di creazione di modelli di dati è il <xref:System.Windows.Controls.DataTemplateSelector>, che consente di scegliere un <xref:System.Windows.DataTemplate> da usare in base alla logica personalizzata. Per altre informazioni, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md), in cui vengono discusse più dettagliatamente le diverse caratteristiche dei modelli di dati.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Modelli di controllo  
 Nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il <xref:System.Windows.Controls.ControlTemplate> di un controllo definisce l'aspetto del controllo. È possibile modificare la struttura e l'aspetto di un controllo definendo un nuovo <xref:System.Windows.Controls.ControlTemplate> per il controllo. In molti casi, la flessibilità offerta da questo oggetto è sufficiente a evitare di dover scrivere dei controlli personalizzati. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Trigger  
 Un trigger imposta proprietà o avvia azioni, ad esempio un'animazione, quando un valore di proprietà cambia o quando viene generato un evento. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, e <xref:System.Windows.DataTemplate> dotati di un `Triggers` proprietà che può contenere un set di trigger. Sono disponibili diversi tipi di trigger.  
  
### <a name="property-triggers"></a>Trigger di proprietà  
 Oggetto <xref:System.Windows.Trigger> che valori di set di proprietà o avvia azioni in base al valore di una proprietà viene chiamato un trigger di proprietà.  
  
 Per illustrare come usare i trigger di proprietà, è possibile rendere ogni <xref:System.Windows.Controls.ListBoxItem> parzialmente trasparente a meno che non è selezionata. Il seguente stile imposta la <xref:System.Windows.UIElement.Opacity%2A> pari a un <xref:System.Windows.Controls.ListBoxItem> a `0.5`. Quando la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> proprietà viene `true`, tuttavia, il <xref:System.Windows.UIElement.Opacity%2A> è impostata su `1.0`:  
  
 [!code-xaml[StylingIntroSample_snippet#Triggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xaml[StylingIntroSample_snippet#EndTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 Questo esempio Usa un <xref:System.Windows.Trigger> per impostare un valore della proprietà, ma si noti che il <xref:System.Windows.Trigger> classe include anche le <xref:System.Windows.TriggerBase.EnterActions%2A> e <xref:System.Windows.TriggerBase.ExitActions%2A> proprietà che consentono a un trigger eseguire azioni.  
  
 Si noti che il <xref:System.Windows.FrameworkElement.MaxHeight%2A> proprietà del <xref:System.Windows.Controls.ListBoxItem> è impostata su `75`. Nella figura seguente il terzo elemento è l'elemento selezionato:  
  
 ![ListView con stile](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTrigger e storyboard  
 Un altro tipo di trigger è il <xref:System.Windows.EventTrigger>, che avvia una serie di azioni in base all'occorrenza di un evento. Seguente, ad esempio, <xref:System.Windows.EventTrigger> oggetti specificano che quando il puntatore del mouse entra la <xref:System.Windows.Controls.ListBoxItem>, il <xref:System.Windows.FrameworkElement.MaxHeight%2A> proprietà aggiunge un'animazione al valore `90` su un `0.2` secondo periodo. Quando il puntatore del mouse viene spostato dall'elemento, la proprietà torna al valore originale in un `1` secondo. Si noti come non sia necessario specificare una <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valore per il <xref:System.Windows.ContentElement.MouseLeave> animazione. L'animazione è infatti in grado di tenere traccia del valore originale.  
  
 [!code-xaml[StylingIntroSample_snippet#EventTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Per altre informazioni, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).  
  
 Nella figura seguente il mouse punta sul terzo elemento:  
  
 ![Screenshot di esempio di applicazione di uno stile](./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger e MultiDataTrigger  
 Oltre a <xref:System.Windows.Trigger> e <xref:System.Windows.EventTrigger>, esistono altri tipi di trigger. <xref:System.Windows.MultiTrigger> Consente di impostare i valori delle proprietà in base a più condizioni. Si utilizza <xref:System.Windows.DataTrigger> e <xref:System.Windows.MultiDataTrigger> quando la proprietà della condizione è associato a dati.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Risorse e temi condivisi  
 Una tipica applicazione Windows Presentation Foundation (WPF) potrebbe essere più le risorse dell'interfaccia utente che vengono applicate in tutta l'applicazione. Nel suo complesso, questo set di risorse può essere considerato il tema dell'applicazione. Windows Presentation Foundation (WPF) fornisce supporto per l'assemblaggio delle risorse di interfaccia utente come un tema usando un dizionario risorse incapsulato come il <xref:System.Windows.ResourceDictionary> classe.  
  
 I temi di Windows Presentation Foundation (WPF) vengono definiti tramite il meccanismo di creazione di modelli che espone Windows Presentation Foundation (WPF) e applicazione di stili per personalizzare gli oggetti visivi di qualsiasi elemento.  
  
 Le risorse del tema Windows Presentation Foundation (WPF) vengono archiviate in dizionari risorse incorporati. Questi dizionari risorse devono essere incorporati all'interno di un assembly firmato e possono essere incorporati nello stesso assembly come codice o in un assembly affiancato. Nel caso di PresentationFramework. dll, l'assembly che contiene i controlli Windows Presentation Foundation (WPF), le risorse del tema sono in una serie di assembly side-by-side.  
  
 Il tema diventa l'ultimo posto in cui cercare lo stile di un elemento. In genere, si inizia a cercare la risorsa appropriata nell'albero degli elementi, quindi si cerca nella raccolta delle risorse dell'applicazione e infine si esegue una query nel sistema. Ciò consente agli sviluppatori di applicazioni di ridefinire lo stile per qualsiasi oggetto a livello di albero o di applicazione prima di raggiungere il tema.  
  
 È possibile definire i dizionari risorse come file singoli che consentono di riusare un tema in più applicazioni. È inoltre possibile creare temi scambiabili definendo più dizionari risorse che forniscono gli stessi tipi di risorse ma con valori diversi. La ridefinizione di questi stili o di altre risorse a livello di applicazione è l'approccio consigliato per definire l'interfaccia di un'applicazione.  
  
 Per condividere un set di risorse, inclusi gli stili e modelli, tutte le applicazioni, è possibile creare un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file e definire un <xref:System.Windows.ResourceDictionary>. Si esamini ad esempio la figura seguente che mostra parte dell'[Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating):

![Esempi di modelli di controlli](./media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Se si osservano i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nell'esempio, si noterà che tutti i file includono l'elemento seguente:  
  
 [!code-xaml[ControlTemplateExamples#MergedDictionaries](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 È la condivisione delle `shared.xaml`, che definisce un <xref:System.Windows.ResourceDictionary> che contiene un set di risorse di stile e il pennello che consente i controlli nell'esempio di conferire un aspetto coerente.  
  
 Per altre informazioni, vedere [Dizionari risorse uniti](../advanced/merged-resource-dictionaries.md).  
  
 Se si intende creare un tema per il controllo personalizzato, vedere la sezione relativa alla libreria di controlli esterni in [Cenni preliminari sulla modifica di controlli](control-authoring-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md)
- [Procedura: Trovare elementi generati da un oggetto ControlTemplate](how-to-find-controltemplate-generated-elements.md)
- [Procedura: trovare elementi generati da un oggetto DataTemplate](../data/how-to-find-datatemplate-generated-elements.md)
