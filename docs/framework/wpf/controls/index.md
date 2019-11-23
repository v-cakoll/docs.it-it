---
title: Controls
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 42596c8adf1b8b27f250fa7a3cf6cc173a63e2eb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459442"
---
# <a name="controls"></a>Controls
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] viene fornito con molti componenti dell'interfaccia utente comuni utilizzati in quasi tutte le applicazioni Windows, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>e <xref:System.Windows.Controls.ListBox>. In passato, questi oggetti sono stati indicati come controlli. Mentre il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK continua a usare il termine "controllo" per indicare in modo generico qualsiasi classe che rappresenta un oggetto visibile in un'applicazione, è importante notare che una classe non deve ereditare dalla classe <xref:System.Windows.Controls.Control> per avere una presenza visibile. Le classi che ereditano dalla classe <xref:System.Windows.Controls.Control> contengono una <xref:System.Windows.Controls.ControlTemplate>, che consente al consumer di un controllo di modificare radicalmente l'aspetto del controllo senza dover creare una nuova sottoclasse.  In questo argomento viene illustrato il modo in cui i controlli (sia quelli che ereditano dalla classe <xref:System.Windows.Controls.Control> che quelli che non lo hanno) vengono comunemente usati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creazione dell'istanza di un controllo  
 È possibile aggiungere un controllo a un'applicazione utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o codice.  L'esempio seguente illustra come creare una semplice applicazione che chiede all'utente di indicare nome e cognome.  Questo esempio crea sei controlli: due etichette, due caselle di testo e due pulsanti, in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È possibile creare tutti i controlli in modo analogo.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene creata la stessa applicazione nel codice. Per brevità, la creazione di <xref:System.Windows.Controls.Grid>, `grid1`, è stata esclusa dall'esempio. `grid1` presenta le stesse definizioni di colonna e di riga, come illustrato nell'esempio di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Modifica dell'aspetto di un controllo  
 È spesso necessario modificare l'aspetto di un controllo per adattarlo all'aspetto dell'applicazione. Per modificare l'aspetto di un controllo, è possibile adottare una delle procedure seguenti, a seconda del risultato che si intende ottenere:  
  
- Modificare il valore di una proprietà del controllo.  
  
- Creare una <xref:System.Windows.Style> per il controllo.  
  
- Creare una nuova <xref:System.Windows.Controls.ControlTemplate> per il controllo.  
  
### <a name="changing-a-controls-property-value"></a>Modifica di un valore della proprietà del controllo  
 Molti controlli hanno proprietà che consentono di modificare la modalità di visualizzazione del controllo, ad esempio la <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button>. È possibile impostare le proprietà del valore sia in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che nel codice. Nell'esempio seguente vengono impostate le proprietà <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>e <xref:System.Windows.Controls.Control.FontWeight%2A> in un <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Nell'esempio seguente vengono impostate le stesse proprietà nel codice.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Creazione di uno stile per un controllo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre la possibilità di specificare l'aspetto dei controlli all'ingrosso, anziché impostare le proprietà per ogni istanza dell'applicazione, creando una <xref:System.Windows.Style>. Nell'esempio seguente viene creato un <xref:System.Windows.Style> applicato a ogni <xref:System.Windows.Controls.Button> nell'applicazione. le definizioni di <xref:System.Windows.Style> vengono in genere definite in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in un <xref:System.Windows.ResourceDictionary>, ad esempio la proprietà <xref:System.Windows.FrameworkElement.Resources%2A> del <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 È anche possibile applicare uno stile solo a determinati controlli di un tipo specifico assegnando una chiave allo stile e specificando tale chiave nella proprietà `Style` del controllo.  Per altre informazioni sugli stili, vedere applicazione di stili [e modelli](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creazione di un ControlTemplate  
 Un <xref:System.Windows.Style> consente di impostare le proprietà per più controlli contemporaneamente, ma a volte può essere necessario personalizzare l'aspetto di un <xref:System.Windows.Controls.Control> oltre a ciò che è possibile eseguire creando un <xref:System.Windows.Style>. Le classi che ereditano dalla classe <xref:System.Windows.Controls.Control> hanno una <xref:System.Windows.Controls.ControlTemplate>, che definisce la struttura e l'aspetto di un <xref:System.Windows.Controls.Control>. Il <xref:System.Windows.Controls.Control.Template%2A> proprietà di un <xref:System.Windows.Controls.Control> è pubblico, quindi è possibile assegnare a un <xref:System.Windows.Controls.Control> un <xref:System.Windows.Controls.ControlTemplate> diverso da quello predefinito. Spesso è possibile specificare un nuovo <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Control> anziché ereditare da un controllo per personalizzare l'aspetto di un <xref:System.Windows.Controls.Control>.  
  
 Si consideri il controllo molto comune, <xref:System.Windows.Controls.Button>.  Il comportamento principale di un <xref:System.Windows.Controls.Button> consiste nel consentire a un'applicazione di eseguire un'azione quando l'utente fa clic su di essa.  Per impostazione predefinita, il <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene visualizzato come rettangolo in rilievo.  Durante lo sviluppo di un'applicazione, può essere utile sfruttare il comportamento di un <xref:System.Windows.Controls.Button>, ovvero gestendo l'evento click del pulsante, ma è possibile modificare l'aspetto del pulsante oltre a ciò che è possibile apportare modificando le proprietà del pulsante.  In questo caso, è possibile creare una nuova <xref:System.Windows.Controls.ControlTemplate>.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>.  Il <xref:System.Windows.Controls.ControlTemplate> crea una <xref:System.Windows.Controls.Button> con angoli arrotondati e uno sfondo sfumato.  Il <xref:System.Windows.Controls.ControlTemplate> contiene una <xref:System.Windows.Controls.Border> il cui <xref:System.Windows.Controls.Border.Background%2A> è un <xref:System.Windows.Media.LinearGradientBrush> con due oggetti <xref:System.Windows.Media.GradientStop>.  Il primo <xref:System.Windows.Media.GradientStop> utilizza data binding per associare la proprietà <xref:System.Windows.Media.GradientStop.Color%2A> della <xref:System.Windows.Media.GradientStop> al colore dello sfondo del pulsante.  Quando si imposta la proprietà <xref:System.Windows.Controls.Control.Background%2A> della <xref:System.Windows.Controls.Button>, il colore di tale valore verrà usato come primo <xref:System.Windows.Media.GradientStop>. Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md). Nell'esempio viene inoltre creato un <xref:System.Windows.Trigger> che modifica l'aspetto del <xref:System.Windows.Controls.Button> quando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> è `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Per il corretto funzionamento dell'esempio, è necessario impostare la proprietà <xref:System.Windows.Controls.Control.Background%2A> della <xref:System.Windows.Controls.Button> su un <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 È possibile sottoscrivere l'evento di un controllo utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o codice, ma è possibile gestire solo un evento nel codice.  Nell'esempio seguente viene illustrato come sottoscrivere l'evento `Click` di un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Nell'esempio seguente viene gestito l'evento `Click` di un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenuto avanzato dei controlli  
 La maggior parte delle classi che ereditano dalla classe <xref:System.Windows.Controls.Control> ha la capacità di contenere contenuti avanzati. Ad esempio, un <xref:System.Windows.Controls.Label> può contenere qualsiasi oggetto, ad esempio una stringa, un <xref:System.Windows.Controls.Image>o un <xref:System.Windows.Controls.Panel>.  Le classi seguenti forniscono supporto per contenuti avanzati e fungono da classi di base per la maggior parte dei controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>: alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>e <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>: alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>e <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>: alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>e <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>: alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>e <xref:System.Windows.Controls.ToolBar>.  

 Per ulteriori informazioni su queste classi di base, vedere [modello di contenuto WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
- [Controlli per categoria](controls-by-category.md)
- [Libreria di controlli](control-library.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Input](../advanced/input-wpf.md)
- [Attivare un comando](../advanced/how-to-enable-a-command.md)
- [Procedure dettagliate: creazione di un pulsante personalizzato a cui è stata aggiunta un'animazione](walkthroughs-create-a-custom-animated-button.md)
- [Personalizzazione dei controlli](control-customization.md)
