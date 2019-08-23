---
title: Controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: faa1fbad85acf5788c10de7750c6a7c32b535bf5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957039"
---
# <a name="controls"></a>Controlli
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]viene fornito con molti dei componenti dell'interfaccia utente comuni utilizzati in quasi tutte le applicazioni Windows, ad <xref:System.Windows.Controls.Button>esempio <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox>,, <xref:System.Windows.Controls.Menu>, e <xref:System.Windows.Controls.ListBox>. In passato, questi oggetti sono stati indicati come controlli. Mentre l' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK continua a usare il termine "controllo" per indicare in modo generico qualsiasi classe che rappresenta un oggetto visibile in un'applicazione, è importante notare che una classe non deve necessariamente ereditare <xref:System.Windows.Controls.Control> dalla classe per avere una presenza visibile. Le classi che ereditano <xref:System.Windows.Controls.Control> dalla classe <xref:System.Windows.Controls.ControlTemplate>contengono, che consente al consumer di un controllo di modificare radicalmente l'aspetto del controllo senza dover creare una nuova sottoclasse.  In questo argomento viene illustrato il modo in cui i controlli (sia <xref:System.Windows.Controls.Control> quelli che ereditano dalla classe che quelli che non lo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]sono) sono comunemente utilizzati in.  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creazione dell'istanza di un controllo  
 È possibile aggiungere un controllo a un'applicazione usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o il codice.  L'esempio seguente illustra come creare una semplice applicazione che chiede all'utente di indicare nome e cognome.  Questo esempio crea sei controlli: due etichette, due caselle di testo e due pulsanti in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È possibile creare tutti i controlli in modo analogo.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene creata la stessa applicazione nel codice. Per brevità, la creazione di <xref:System.Windows.Controls.Grid>, `grid1`, è stata esclusa dall'esempio. `grid1`ha le stesse definizioni di colonna e di riga, come illustrato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nell'esempio precedente.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Modifica dell'aspetto di un controllo  
 È spesso necessario modificare l'aspetto di un controllo per adattarlo all'aspetto dell'applicazione. Per modificare l'aspetto di un controllo, è possibile adottare una delle procedure seguenti, a seconda del risultato che si intende ottenere:  
  
- Modificare il valore di una proprietà del controllo.  
  
- Creare un <xref:System.Windows.Style> oggetto per il controllo.  
  
- Creare un nuovo <xref:System.Windows.Controls.ControlTemplate> oggetto per il controllo.  
  
### <a name="changing-a-controls-property-value"></a>Modifica di un valore della proprietà del controllo  
 Molti controlli hanno proprietà che consentono di modificare la modalità <xref:System.Windows.Controls.Control.Background%2A> di visualizzazione del controllo, ad esempio di un oggetto. <xref:System.Windows.Controls.Button> È possibile impostare le proprietà del valore sia [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in che nel codice. Nell'esempio seguente vengono impostate <xref:System.Windows.Controls.Control.Background%2A>le <xref:System.Windows.Controls.Control.FontSize%2A>proprietà, <xref:System.Windows.Controls.Control.FontWeight%2A> e in un <xref:System.Windows.Controls.Button> oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]in.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Nell'esempio seguente vengono impostate le stesse proprietà nel codice.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Creazione di uno stile per un controllo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]consente di specificare l'aspetto dei controlli all'ingrosso, anziché impostare le proprietà per ogni istanza dell'applicazione, creando un oggetto <xref:System.Windows.Style>. Nell'esempio seguente viene creato <xref:System.Windows.Style> un oggetto applicato a ogni <xref:System.Windows.Controls.Button> nell'applicazione. <xref:System.Windows.Style>le definizioni vengono in genere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definite in <xref:System.Windows.ResourceDictionary>in un, ad <xref:System.Windows.FrameworkElement.Resources%2A> esempio la proprietà <xref:System.Windows.FrameworkElement>di.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 È anche possibile applicare uno stile solo a determinati controlli di un tipo specifico assegnando una chiave allo stile e specificando tale chiave nella `Style` proprietà del controllo.  Per altre informazioni sugli stili, vedere applicazione di stili [e modelli](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creazione di un ControlTemplate  
 Un <xref:System.Windows.Style> oggetto consente di impostare le proprietà per più controlli contemporaneamente, ma a volte può essere necessario personalizzare l'aspetto di un <xref:System.Windows.Controls.Control> elemento oltre a ciò che è possibile eseguire creando <xref:System.Windows.Style>un oggetto. Le classi che ereditano <xref:System.Windows.Controls.Control> dalla classe hanno <xref:System.Windows.Controls.ControlTemplate>un oggetto, che definisce la struttura e l' <xref:System.Windows.Controls.Control>aspetto di un oggetto. La <xref:System.Windows.Controls.Control.Template%2A> proprietà di un <xref:System.Windows.Controls.Control> oggetto è pubblica, pertanto è possibile assegnare <xref:System.Windows.Controls.Control> a <xref:System.Windows.Controls.ControlTemplate> un oggetto diverso da quello predefinito. Spesso è possibile specificare un nuovo <xref:System.Windows.Controls.ControlTemplate> oggetto per <xref:System.Windows.Controls.Control> un oggetto anziché ereditare da un controllo per personalizzare l'aspetto di <xref:System.Windows.Controls.Control>un oggetto.  
  
 Si consideri il controllo <xref:System.Windows.Controls.Button>molto comune, ovvero.  Il comportamento principale di un <xref:System.Windows.Controls.Button> consiste nel consentire a un'applicazione di eseguire un'azione quando l'utente fa clic su di essa.  Per impostazione predefinita, <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene visualizzato come un rettangolo in rilievo.  Durante lo sviluppo di un'applicazione, è possibile sfruttare il comportamento di un <xref:System.Windows.Controls.Button>, ovvero gestendo l'evento click del pulsante, ma è possibile modificare l'aspetto del pulsante oltre a ciò che si può fare modificando le proprietà del pulsante.  In questo caso, è possibile creare un nuovo <xref:System.Windows.Controls.ControlTemplate>.  
  
 Nell'esempio seguente viene creato <xref:System.Windows.Controls.ControlTemplate> un oggetto <xref:System.Windows.Controls.Button>per un oggetto.  Crea un oggetto <xref:System.Windows.Controls.Button> con angoli arrotondati e uno sfondo sfumato. <xref:System.Windows.Controls.ControlTemplate>  Contiene <xref:System.Windows.Controls.ControlTemplate> un oggetto <xref:System.Windows.Controls.Border> il <xref:System.Windows.Controls.Border.Background%2A> cui è <xref:System.Windows.Media.LinearGradientBrush> un oggetto <xref:System.Windows.Media.GradientStop> con due oggetti.  Il primo <xref:System.Windows.Media.GradientStop> USA Data Binding per associare la <xref:System.Windows.Media.GradientStop.Color%2A> proprietà dell'oggetto <xref:System.Windows.Media.GradientStop> al colore dello sfondo del pulsante.  Quando si imposta la <xref:System.Windows.Controls.Control.Background%2A> proprietà <xref:System.Windows.Controls.Button>di, il colore di tale valore verrà usato come primo <xref:System.Windows.Media.GradientStop>. Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../data/data-binding-overview.md). Nell'esempio viene inoltre creato <xref:System.Windows.Trigger> un oggetto che modifica l'aspetto <xref:System.Windows.Controls.Button> dell' <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> oggetto `true`quando è.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Per il corretto funzionamento <xref:System.Windows.Controls.Button> dell'esempio, la <xref:System.Windows.Controls.Control.Background%2A> proprietà di deve essere impostata su. <xref:System.Windows.Media.SolidColorBrush>  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 È possibile sottoscrivere l'evento di un controllo usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o il codice, ma è possibile gestire solo un evento nel codice.  Nell'esempio seguente viene illustrato come sottoscrivere l' `Click` evento di un <xref:System.Windows.Controls.Button>oggetto.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Nell'esempio seguente viene gestito `Click` l'evento di <xref:System.Windows.Controls.Button>un oggetto.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenuto avanzato dei controlli  
 La maggior parte delle classi che <xref:System.Windows.Controls.Control> ereditano dalla classe ha la capacità di contenere contenuti avanzati. Ad esempio, un <xref:System.Windows.Controls.Label> oggetto può contenere qualsiasi oggetto, ad esempio una stringa, <xref:System.Windows.Controls.Image>un oggetto o <xref:System.Windows.Controls.Panel>un oggetto.  Le classi seguenti forniscono supporto per contenuti avanzati e fungono da classi di base per la maggior parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dei controlli in.  
  
- <xref:System.Windows.Controls.ContentControl>--Alcuni esempi di classi che ereditano da questa classe <xref:System.Windows.Controls.Label>sono <xref:System.Windows.Controls.Button>, e <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>--Alcuni esempi di classi che ereditano da questa classe <xref:System.Windows.Controls.ListBox>sono <xref:System.Windows.Controls.Menu>, e <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--Alcuni esempi di classi che ereditano da questa classe <xref:System.Windows.Controls.TabItem>sono <xref:System.Windows.Controls.GroupBox>, e <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Alcuni esempi di classi che ereditano da questa classe <xref:System.Windows.Controls.MenuItem>sono <xref:System.Windows.Controls.TreeViewItem>, e <xref:System.Windows.Controls.ToolBar>.  

 Per ulteriori informazioni su queste classi di base, vedere [modello di contenuto WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
- [Controlli per categoria](controls-by-category.md)
- [Libreria di controlli](control-library.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Input](../advanced/input-wpf.md)
- [Attivare un comando](../advanced/how-to-enable-a-command.md)
- [Procedure dettagliate: Creare un pulsante animato personalizzato](walkthroughs-create-a-custom-animated-button.md)
- [Personalizzazione dei controlli](control-customization.md)
