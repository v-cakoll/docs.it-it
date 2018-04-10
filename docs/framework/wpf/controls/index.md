---
title: Controlli
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66c6cc58423a2af8d0fd6de93b8884918888fb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="controls"></a>Controlli
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]viene fornito con molti dei componenti dell'interfaccia utente comuni che vengono utilizzati in quasi tutte le applicazioni di Windows, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, e <xref:System.Windows.Controls.ListBox>. In passato, questi oggetti sono stati indicati come controlli. Mentre il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK viene utilizzato il termine "controllo" per indicare qualsiasi classe che rappresenta un oggetto visibile in un'applicazione, è importante notare che non necessita di una classe da cui ereditare la <xref:System.Windows.Controls.Control> classe disponga di una presenza visibile. Le classi che ereditano dal <xref:System.Windows.Controls.Control> classe contiene un <xref:System.Windows.Controls.ControlTemplate>, che consente al consumer di un controllo di modificarne radicalmente l'aspetto del controllo senza dover creare una nuova sottoclasse.  Questo argomento viene illustrato come controlli (quelli che ereditano dal <xref:System.Windows.Controls.Control> classe e quelli che non) vengono comunemente utilizzate [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creazione dell'istanza di un controllo  
 È possibile aggiungere un controllo a un'applicazione utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o codice.  L'esempio seguente illustra come creare una semplice applicazione che chiede all'utente di indicare nome e cognome.  Questo esempio vengono creati sei controlli: due etichette, due caselle di testo e due pulsanti, in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È possibile creare tutti i controlli in modo analogo.  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene creata la stessa applicazione nel codice. Per ragioni di brevità, la creazione del <xref:System.Windows.Controls.Grid>, `grid1`, è stata esclusa dall'esempio. `grid1`presenta le stesse definizioni di colonna e riga, come illustrato nel passaggio precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Modifica dell'aspetto di un controllo  
 È spesso necessario modificare l'aspetto di un controllo per adattarlo all'aspetto dell'applicazione. Per modificare l'aspetto di un controllo, è possibile adottare una delle procedure seguenti, a seconda del risultato che si intende ottenere:  
  
-   Modificare il valore di una proprietà del controllo.  
  
-   Creare un <xref:System.Windows.Style> per il controllo.  
  
-   Creare un nuovo <xref:System.Windows.Controls.ControlTemplate> per il controllo.  
  
### <a name="changing-a-controls-property-value"></a>Modifica di un valore della proprietà del controllo  
 Molti controlli presentano proprietà che consentono di modificare l'aspetto del controllo, ad esempio il <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button>. È possibile impostare le proprietà del valore in entrambi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e il codice. L'esempio seguente imposta il <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, e <xref:System.Windows.Controls.Control.FontWeight%2A> proprietà in un <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Nell'esempio seguente vengono impostate le stesse proprietà nel codice.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Creazione di uno stile per un controllo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]offre la possibilità di specificare l'aspetto dei controlli a livello globale, anziché impostare le proprietà di ogni istanza dell'applicazione, creando un <xref:System.Windows.Style>. Nell'esempio seguente viene creato un <xref:System.Windows.Style> che viene applicata a ogni <xref:System.Windows.Controls.Button> nell'applicazione. <xref:System.Windows.Style>le definizioni sono in genere definite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in un <xref:System.Windows.ResourceDictionary>, ad esempio il <xref:System.Windows.FrameworkElement.Resources%2A> proprietà del <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 È inoltre possibile applicare uno stile solo a determinati controlli di un tipo specifico assegnando una chiave per lo stile e specificando tale chiave nel `Style` proprietà del controllo.  Per ulteriori informazioni sugli stili, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creazione di un ControlTemplate  
 Oggetto <xref:System.Windows.Style> consente di impostare le proprietà su più controlli in un momento, ma in alcuni casi è consigliabile personalizzare l'aspetto di un <xref:System.Windows.Controls.Control> oltre operazioni creando un <xref:System.Windows.Style>. Le classi che ereditano dal <xref:System.Windows.Controls.Control> classe dispone di un <xref:System.Windows.Controls.ControlTemplate>, che definisce la struttura e l'aspetto di un <xref:System.Windows.Controls.Control>. Il <xref:System.Windows.Controls.Control.Template%2A> proprietà di un <xref:System.Windows.Controls.Control> è pubblico, pertanto è possibile assegnare un <xref:System.Windows.Controls.Control> un <xref:System.Windows.Controls.ControlTemplate> che è diverso da quello predefinito. Spesso è possibile specificare un nuovo <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Control> anziché ereditare da un controllo per personalizzare l'aspetto di un <xref:System.Windows.Controls.Control>.  
  
 Si consideri un controllo molto comune, <xref:System.Windows.Controls.Button>.  Il comportamento principale di un <xref:System.Windows.Controls.Button> consiste nell'abilitare un'applicazione eseguire azioni quando l'utente fa clic sopra.  Per impostazione predefinita, il <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene visualizzato come un rettangolo generato.  Durante lo sviluppo di un'applicazione, è possibile sfruttare i vantaggi offerti dal comportamento di un <xref:System.Windows.Controls.Button>, vale a dire, mediante la gestione del pulsante evento click, ma è possibile modificare l'aspetto del pulsante oltre operazioni modificando le proprietà del pulsante.  In questo caso, è possibile creare un nuovo <xref:System.Windows.Controls.ControlTemplate>.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>.  Il <xref:System.Windows.Controls.ControlTemplate> crea un <xref:System.Windows.Controls.Button> con angoli arrotondati e uno sfondo sfumato.  Il <xref:System.Windows.Controls.ControlTemplate> contiene un <xref:System.Windows.Controls.Border> cui <xref:System.Windows.Controls.Border.Background%2A> è un <xref:System.Windows.Media.LinearGradientBrush> con due <xref:System.Windows.Media.GradientStop> oggetti.  Il primo <xref:System.Windows.Media.GradientStop> utilizza l'associazione dati per associare il <xref:System.Windows.Media.GradientStop.Color%2A> proprietà del <xref:System.Windows.Media.GradientStop> per il colore di sfondo del pulsante.  Quando si imposta la <xref:System.Windows.Controls.Control.Background%2A> proprietà del <xref:System.Windows.Controls.Button>, il colore di tale valore verrà utilizzato come primo <xref:System.Windows.Media.GradientStop>. Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md). Nell'esempio viene creato anche un <xref:System.Windows.Trigger> che modifica l'aspetto del <xref:System.Windows.Controls.Button> quando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> è `true`.  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.Control.Background%2A> proprietà del <xref:System.Windows.Controls.Button> deve essere impostata su un <xref:System.Windows.Media.SolidColorBrush> per il funzionamento dell'esempio.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 È possibile sottoscrivere un evento del controllo utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o codice, ma è possibile gestire solo un evento nel codice.  Nell'esempio seguente viene illustrato come sottoscrivere il `Click` evento di un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 L'esempio seguente viene gestito il `Click` evento di un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenuto avanzato dei controlli  
 La maggior parte delle classi che ereditano dalla <xref:System.Windows.Controls.Control> classe dispone di capacità sufficiente per contenere contenuto dettagliato. Ad esempio, un <xref:System.Windows.Controls.Label> può contenere qualsiasi oggetto, ad esempio una stringa, un <xref:System.Windows.Controls.Image>, o un <xref:System.Windows.Controls.Panel>.  Le classi seguenti forniscono il supporto per contenuto dettagliato e agire come classi di base per la maggior parte dei controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>-- Alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, e <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>-- Alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, e <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>-- Alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, e <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>-- Alcuni esempi di classi che ereditano da questa classe sono <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, e <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Per ulteriori informazioni su queste classi base, vedere [modello di contenuto WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Controlli per categoria](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [Libreria di controlli](../../../../docs/framework/wpf/controls/control-library.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Input](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [Attivare un comando](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [Procedure dettagliate: creazione di un pulsante personalizzato a cui è stata aggiunta un'animazione](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)
