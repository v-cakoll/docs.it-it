---
title: Controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2ec8c0a99f4e2431aed0d8c24168b7329de669f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187525"
---
# <a name="controls"></a>Controlli
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]con molti dei componenti dell'interfaccia utente comuni utilizzati <xref:System.Windows.Controls.Button>in <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox>quasi <xref:System.Windows.Controls.Menu>tutte <xref:System.Windows.Controls.ListBox>le applicazioni Windows, ad esempio , , , e . In passato, questi oggetti sono stati indicati come controlli. Mentre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'SDK continua a utilizzare il termine "controllo" per indicare vagamente qualsiasi classe che rappresenta un oggetto visibile <xref:System.Windows.Controls.Control> in un'applicazione, è importante notare che una classe non deve ereditare dalla classe per avere una presenza visibile. Le classi che <xref:System.Windows.Controls.Control> ereditano <xref:System.Windows.Controls.ControlTemplate>dalla classe contengono un oggetto , che consente al consumer di un controllo di modificare radicalmente l'aspetto del controllo senza dover creare una nuova sottoclasse.  In questo argomento viene illustrato come i <xref:System.Windows.Controls.Control> controlli (sia quelli che ereditano dalla classe che quelli che non lo fanno) vengono comunemente utilizzati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Creazione dell'istanza di un controllo  
 È possibile aggiungere un controllo a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] un'applicazione utilizzando uno o più codice.  L'esempio seguente illustra come creare una semplice applicazione che chiede all'utente di indicare nome e cognome.  In questo esempio vengono creati sei controlli: due etichette, due caselle di testo e due pulsanti, in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È possibile creare tutti i controlli in modo analogo.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene creata la stessa applicazione nel codice. Per brevità, la <xref:System.Windows.Controls.Grid>creazione `grid1`di , , è stata esclusa dal campione. `grid1`ha le stesse definizioni di colonna [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e riga come illustrato nell'esempio precedente.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Modifica dell'aspetto di un controllo  
 È spesso necessario modificare l'aspetto di un controllo per adattarlo all'aspetto dell'applicazione. Per modificare l'aspetto di un controllo, è possibile adottare una delle procedure seguenti, a seconda del risultato che si intende ottenere:  
  
- Modificare il valore di una proprietà del controllo.  
  
- Creare <xref:System.Windows.Style> un per il controllo.  
  
- Creare una <xref:System.Windows.Controls.ControlTemplate> nuova per il controllo.  
  
### <a name="changing-a-controls-property-value"></a>Modifica di un valore della proprietà del controllo  
 Molti controlli dispongono di proprietà che consentono di <xref:System.Windows.Controls.Control.Background%2A> modificare <xref:System.Windows.Controls.Button>la modalità di visualizzazione del controllo, ad esempio l'oggetto . È possibile impostare le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] proprietà del valore in entrambi i codici. Nell'esempio riportato <xref:System.Windows.Controls.Control.FontSize%2A>di <xref:System.Windows.Controls.Control.FontWeight%2A> seguito <xref:System.Windows.Controls.Button> vengono [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]impostate le <xref:System.Windows.Controls.Control.Background%2A>proprietà , e su un oggetto in .  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Nell'esempio seguente vengono impostate le stesse proprietà nel codice.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Creazione di uno stile per un controllo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]consente di specificare l'aspetto dei controlli all'ingrosso, anziché impostare <xref:System.Windows.Style>proprietà su ogni istanza dell'applicazione, creando un oggetto . Nell'esempio seguente <xref:System.Windows.Style> viene creato <xref:System.Windows.Controls.Button> un oggetto che viene applicato a ciascuno nell'applicazione. <xref:System.Windows.Style>le definizioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sono <xref:System.Windows.ResourceDictionary>in genere <xref:System.Windows.FrameworkElement.Resources%2A> definite in <xref:System.Windows.FrameworkElement>un oggetto , ad esempio la proprietà dell'oggetto .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 È inoltre possibile applicare uno stile solo a determinati controlli di un tipo specifico assegnando un tasto allo stile e specificando tale chiave nella `Style` proprietà del controllo.  Per ulteriori informazioni sugli stili, consultate [Applicazione di stili e modelli.](styling-and-templating.md)  
  
### <a name="creating-a-controltemplate"></a>Creazione di un ControlTemplate  
 A <xref:System.Windows.Style> consente di impostare le proprietà su più controlli alla volta, <xref:System.Windows.Controls.Control> ma a volte è <xref:System.Windows.Style>possibile personalizzare l'aspetto di un oltre le operazioni che è possibile eseguire creando un oggetto . Le classi che <xref:System.Windows.Controls.Control> ereditano <xref:System.Windows.Controls.ControlTemplate>dalla classe dispongono di <xref:System.Windows.Controls.Control>un oggetto , che definisce la struttura e l'aspetto di un oggetto . La <xref:System.Windows.Controls.Control.Template%2A> proprietà <xref:System.Windows.Controls.Control> di un è public, <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> in modo da poter dare un che è diverso da quello predefinito. È spesso possibile <xref:System.Windows.Controls.ControlTemplate> specificare <xref:System.Windows.Controls.Control> un nuovo oggetto anziché ereditare <xref:System.Windows.Controls.Control>da un controllo per personalizzare l'aspetto di un oggetto .  
  
 Si consideri il <xref:System.Windows.Controls.Button>controllo molto comune, .  Il comportamento principale <xref:System.Windows.Controls.Button> di un oggetto consiste nell'abilitare un'applicazione per eseguire un'azione quando l'utente fa clic su di esso.  Per impostazione <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinita, l'in viene visualizzato come rettangolo in rilievo.  Durante lo sviluppo di un'applicazione, è possibile <xref:System.Windows.Controls.Button>sfruttare il comportamento di un, ovvero la gestione dell'evento Click del pulsante, ma è possibile modificare l'aspetto del pulsante oltre a quanto è possibile fare modificando le proprietà del pulsante.  In questo caso, è <xref:System.Windows.Controls.ControlTemplate>possibile creare un nuovo file .  
  
 Nell'esempio riportato di seguito viene creato un <xref:System.Windows.Controls.ControlTemplate> oggetto per un oggetto <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> L'oggetto <xref:System.Windows.Controls.Button> crea un con angoli arrotondati e uno sfondo sfumato.  Il <xref:System.Windows.Controls.ControlTemplate> contiene <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> un <xref:System.Windows.Media.LinearGradientBrush> whose <xref:System.Windows.Media.GradientStop> è un con due oggetti.  Il <xref:System.Windows.Media.GradientStop> primo utilizza l'associazione dati per associare la <xref:System.Windows.Media.GradientStop.Color%2A> proprietà dell'oggetto <xref:System.Windows.Media.GradientStop> al colore dello sfondo del pulsante.  Quando si <xref:System.Windows.Controls.Control.Background%2A> imposta la <xref:System.Windows.Controls.Button>proprietà di , il colore di <xref:System.Windows.Media.GradientStop>tale valore verrà utilizzato come primo oggetto . Per ulteriori informazioni sull'associazione dati, vedere [Cenni preliminari sull'associazione dati.](../../../desktop-wpf/data/data-binding-overview.md) Nell'esempio viene <xref:System.Windows.Trigger> inoltre creato un <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> oggetto `true`che modifica l'aspetto di when is .  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Per <xref:System.Windows.Controls.Control.Background%2A> il <xref:System.Windows.Controls.Button> corretto funzionamento dell'esempio, è necessario impostare <xref:System.Windows.Media.SolidColorBrush> la proprietà dell'oggetto .  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 È possibile sottoscrivere l'evento di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un controllo usando uno o più codice, ma è possibile gestire solo un evento nel codice.  Nell'esempio riportato di `Click` seguito viene <xref:System.Windows.Controls.Button>illustrato come sottoscrivere l'evento di un oggetto .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Nell'esempio riportato di seguito viene gestita l'evento `Click` di un oggetto . <xref:System.Windows.Controls.Button>  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Contenuto avanzato dei controlli  
 La maggior parte <xref:System.Windows.Controls.Control> delle classi che ereditano dalla classe hanno la capacità di includere contenuto avanzato. Ad esempio, <xref:System.Windows.Controls.Label> un oggetto può contenere qualsiasi <xref:System.Windows.Controls.Image>oggetto, <xref:System.Windows.Controls.Panel>ad esempio una stringa, un oggetto , o un oggetto .  Le classi seguenti forniscono il supporto per il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]avanzato e fungono da classi base per la maggior parte dei controlli in .  
  
- <xref:System.Windows.Controls.ContentControl>-- Alcuni esempi di classi che <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button>ereditano <xref:System.Windows.Controls.ToolTip>da questa classe sono , , e .  
  
- <xref:System.Windows.Controls.ItemsControl>-- Alcuni esempi di classi che <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.Menu>ereditano <xref:System.Windows.Controls.Primitives.StatusBar>da questa classe sono , , e .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- Alcuni esempi di classi che <xref:System.Windows.Controls.TabItem> <xref:System.Windows.Controls.GroupBox>ereditano <xref:System.Windows.Controls.Expander>da questa classe sono , , e .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Alcuni esempi di classi che <xref:System.Windows.Controls.MenuItem>ereditano da questa classe sono , <xref:System.Windows.Controls.TreeViewItem>, e <xref:System.Windows.Controls.ToolBar>.  

 Per altre informazioni su queste classi di base, vedere Modello di [contenuto WPF.](wpf-content-model.md)  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
- [Controlli per categoria](controls-by-category.md)
- [Libreria di controlli](control-library.md)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Input](../advanced/input-wpf.md)
- [Attivare un comando](../advanced/how-to-enable-a-command.md)
- [Procedure dettagliate: creazione di un pulsante personalizzato a cui è stata aggiunta un'animazione](walkthroughs-create-a-custom-animated-button.md)
- [Personalizzazione dei controlli](control-customization.md)
