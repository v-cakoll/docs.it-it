---
title: Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0019b739c794cbffa62b49749371c2a19f752267
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
<a name="introduction"></a>Oggetto <xref:System.Windows.Controls.ControlTemplate> specifica la struttura e il comportamento di un controllo visivo. È possibile personalizzare l'aspetto di un controllo assegnando a un nuovo <xref:System.Windows.Controls.ControlTemplate>. Quando si crea un <xref:System.Windows.Controls.ControlTemplate>, la sostituzione dell'aspetto di un controllo esistente senza modificarne la funzionalità. Ad esempio, è possibile creare i pulsanti nell'applicazione rotondi anziché la forma di quadrato predefinito, ma il pulsante genererà comunque il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
 In questo argomento illustra le varie parti di un <xref:System.Windows.Controls.ControlTemplate>, viene illustrato come creare un semplice <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>e viene spiegato come comprendere il contratto di un controllo in modo che sia possibile personalizzare l'aspetto. Poiché si crea un <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile modificare l'aspetto di un controllo senza scrivere alcun codice. È anche possibile usare una finestra di progettazione, ad esempio Microsoft Expression Blend, per creare modelli di controlli personalizzati. Questo argomento viene illustrato negli esempi di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che consentono di personalizzare l'aspetto di un <xref:System.Windows.Controls.Button> ed elenca l'esempio completo alla fine dell'argomento. Per altre informazioni sull'uso di Expression Blend, vedere [Applicazione di stili a un controllo che supporta modelli](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Nell'illustrazione seguente vengono mostrati un <xref:System.Windows.Controls.Button> che utilizza il <xref:System.Windows.Controls.ControlTemplate> che viene creato in questo argomento.  
  
 ![Pulsante con un modello di controllo personalizzato. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato  
  
 ![Pulsante con un bordo rosso. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato e su cui è posizionato il puntatore del mouse  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si basa sul presupposto che si sappiano creare e usare i controlli e gli stili come descritto in [Controlli](../../../../docs/framework/wpf/controls/index.md). I concetti illustrati in questo argomento si applicano agli elementi da cui ereditare il <xref:System.Windows.Controls.Control> (classe), tranne che per il <xref:System.Windows.Controls.UserControl>. Non è possibile applicare un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Quando creare un oggetto ControlTemplate  
 Controlli hanno molte proprietà, ad esempio <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>, che è possibile impostare per specificare diversi aspetti dell'aspetto del controllo, ma le modifiche apportate dall'impostazione di queste proprietà sono limitate. Ad esempio, è possibile impostare il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà impostandolo sul blu e <xref:System.Windows.Controls.Control.FontStyle%2A> su corsivo in un <xref:System.Windows.Controls.CheckBox>.  
  
 Senza la possibilità di creare un nuovo <xref:System.Windows.Controls.ControlTemplate> per i controlli, tutti i controlli ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su avrebbe lo stesso aspetto generale, che potrebbe limitare la possibilità di creare un'applicazione con un aspetto personalizzato. Per impostazione predefinita, ogni <xref:System.Windows.Controls.CheckBox> ha caratteristiche simili. Ad esempio, il contenuto del <xref:System.Windows.Controls.CheckBox> è sempre a destra dell'indicatore di selezione, e il segno di spunta viene sempre utilizzato per indicare che il <xref:System.Windows.Controls.CheckBox> è selezionata.  
  
 Si crea un <xref:System.Windows.Controls.ControlTemplate> quando si desidera personalizzare l'aspetto del controllo oltre le impostazione delle altre proprietà sul controllo. Nell'esempio del <xref:System.Windows.Controls.CheckBox>, si supponga che il contenuto della casella di controllo per sopra l'indicatore di selezione e si desidera una X per indicare che il <xref:System.Windows.Controls.CheckBox> è selezionata. È possibile specificare queste modifiche nel <xref:System.Windows.Controls.ControlTemplate> del <xref:System.Windows.Controls.CheckBox>.  
  
 La figura seguente mostra un <xref:System.Windows.Controls.CheckBox> che utilizza un valore predefinito <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Una casella di controllo con il modello di controllo predefinito. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Oggetto CheckBox che usa il modello del controllo predefinito  
  
 Nella figura seguente un <xref:System.Windows.Controls.CheckBox> che utilizza un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> per inserire il contenuto del <xref:System.Windows.Controls.CheckBox> sopra l'indicatore di selezione e consente di visualizzare una X quando il <xref:System.Windows.Controls.CheckBox> è selezionata.  
  
 ![Una casella di controllo con un modello di controllo personalizzato. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Oggetto CheckBox che usa un modello del controllo personalizzato  
  
 Il <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.CheckBox> in questo esempio è relativamente complessa, pertanto questo argomento viene utilizzato un semplice esempio di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Modifica della struttura visiva di un controllo  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un controllo è spesso un composito <xref:System.Windows.FrameworkElement> oggetti. Quando si crea un <xref:System.Windows.Controls.ControlTemplate>, combinare <xref:System.Windows.FrameworkElement> oggetti per compilare un singolo controllo. Oggetto <xref:System.Windows.Controls.ControlTemplate> deve avere un solo <xref:System.Windows.FrameworkElement> come elemento radice. L'elemento radice contiene in genere altri <xref:System.Windows.FrameworkElement> oggetti. La combinazione degli oggetti costituisce la struttura visiva del controllo.  
  
 Nell'esempio seguente viene creato un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Button>. Il <xref:System.Windows.Controls.ControlTemplate> crea la struttura visiva del <xref:System.Windows.Controls.Button>. In questo esempio, l'aspetto del pulsante non cambia quando si sposta il puntatore del mouse o si fa clic su di esso. La procedura per modificare l'aspetto del pulsante quando è in uno stato diverso viene descritta più avanti in questo argomento.  
  
 In questo esempio, la struttura visiva è costituita dalle parti seguenti:  
  
-   Oggetto <xref:System.Windows.Controls.Border> denominato `RootElement` che funge da radice del modello <xref:System.Windows.FrameworkElement>.  
  
-   Oggetto <xref:System.Windows.Controls.Grid> che rappresenta un elemento figlio di `RootElement`.  
  
-   Oggetto <xref:System.Windows.Controls.ContentPresenter> che consente di visualizzare il contenuto del pulsante. Il <xref:System.Windows.Controls.ContentPresenter> consente qualsiasi tipo di oggetto da visualizzare.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Mantenimento della funzionalità delle proprietà di un controllo tramite TemplateBinding  
 Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate>, è che si desideri continuare a utilizzare le proprietà pubbliche per modificare l'aspetto del controllo. Il [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup associa una proprietà di un elemento che è il <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica che viene definita dal controllo. Quando si usa [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), si consente alle proprietà del controllo di fungere da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 Nell'esempio seguente viene ripetuta la parte dell'esempio precedente che utilizza il [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup per associare le proprietà di elementi presenti il <xref:System.Windows.Controls.ControlTemplate> a proprietà pubbliche che sono definite dal pulsante.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In questo esempio, il <xref:System.Windows.Controls.Grid> è relativo <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà modello associato a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Poiché <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> è associata al modello, è possibile creare più pulsanti che utilizzano la stessa <xref:System.Windows.Controls.ControlTemplate> e impostare il <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> su valori diversi per ogni pulsante. Se <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> era non modello associato a una proprietà di un elemento nel <xref:System.Windows.Controls.ControlTemplate>, impostando il <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> di un pulsante avrebbe alcun effetto sull'aspetto del pulsante.  
  
 Tenere presente che i nomi delle due proprietà non devono necessariamente essere identici. Nell'esempio precedente, il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> proprietà del <xref:System.Windows.Controls.Button> è modello associato al <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> proprietà del <xref:System.Windows.Controls.ContentPresenter>. In questo modo il contenuto del pulsante può essere posizionato orizzontalmente. <xref:System.Windows.Controls.ContentPresenter>non dispone di una proprietà denominata `HorizontalContentAlignment`, ma <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> può essere associato a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Quando si associa al modello una proprietà, accertarsi che le proprietà di origine e destinazione siano dello stesso tipo.  
  
 La <xref:System.Windows.Controls.Control> classe definisce diverse proprietà che deve essere utilizzata dal modello di controllo ha un effetto sul controllo quando vengono impostate. Come il <xref:System.Windows.Controls.ControlTemplate> utilizza la proprietà dipende dalla proprietà. Il <xref:System.Windows.Controls.ControlTemplate> deve utilizzare la proprietà in uno dei modi seguenti:  
  
-   Un elemento di <xref:System.Windows.Controls.ControlTemplate> modello associato alla proprietà.  
  
-   Un elemento di <xref:System.Windows.Controls.ControlTemplate> eredita la proprietà da un padre <xref:System.Windows.FrameworkElement>.  
  
 Nella tabella seguente sono elencate le proprietà visive ereditate da un controllo dalla <xref:System.Windows.Controls.Control> classe. Indica anche se il modello del controllo predefinito di un controllo usa il valore della proprietà ereditato o se deve essere associato al modello.  
  
|Proprietà|Metodo di utilizzo|  
|--------------|------------------|  
|<xref:System.Windows.Controls.Control.Background%2A>|Associazione a modello|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Associazione a modello|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Associazione a modello|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Ereditarietà della proprietà o associazione a modello|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|Ereditarietà della proprietà o associazione a modello|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Ereditarietà della proprietà o associazione a modello|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Ereditarietà della proprietà o associazione a modello|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|Ereditarietà della proprietà o associazione a modello|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Associazione a modello|  
|<xref:System.Windows.Controls.Control.Padding%2A>|Associazione a modello|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Associazione a modello|  
  
 Nella tabella vengono elencate solo le proprietà visive ereditate dalla <xref:System.Windows.Controls.Control> classe. Oltre alle proprietà elencate nella tabella, un controllo può anche ereditare il <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, e <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> proprietà dall'elemento padre framework.  
  
 Inoltre, se il <xref:System.Windows.Controls.ContentPresenter> nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ContentControl>, il <xref:System.Windows.Controls.ContentPresenter> verrà automaticamente associato al <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà. Analogamente, un <xref:System.Windows.Controls.ItemsPresenter> che si trova nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ItemsControl> verrà automaticamente associato al <xref:System.Windows.Controls.ItemsControl.Items%2A> e <xref:System.Windows.Controls.ItemsPresenter> proprietà.  
  
 L'esempio seguente crea due pulsanti che utilizzano il <xref:System.Windows.Controls.ControlTemplate> definito nell'esempio precedente. Nell'esempio viene impostata la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontSize%2A> proprietà su ogni pulsante. L'impostazione di <xref:System.Windows.Controls.Control.Background%2A> proprietà ha effetto perché è associata al modello nel <xref:System.Windows.Controls.ControlTemplate>. Anche se il <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.FontSize%2A> proprietà non sono associate al modello, la loro impostazione ha effetto poiché i relativi valori vengono ereditati.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Nell'esempio precedente viene generato un output simile alla figura seguente.  
  
 ![Due pulsanti, uno blu e uno viola. ] (../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
Due pulsanti con diversi colori di sfondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Modifica dell'aspetto di un controllo in base allo stato  
 La differenza tra un pulsante con l'aspetto predefinito e il pulsante dell'esempio precedente è che il pulsante predefinito cambia leggermente in relazione allo stato. Ad esempio, l'aspetto del pulsante predefinito cambia quando viene premuto o quando il puntatore del mouse viene spostato sul pulsante. Sebbene il <xref:System.Windows.Controls.ControlTemplate> non modifica la funzionalità di un controllo viene modificato il comportamento del controllo visual. Il comportamento visivo descrive l'aspetto del controllo quando è in un determinato stato. Per comprendere la differenza tra la funzionalità e il comportamento visivo di un controllo, si consideri l'esempio del pulsante. La funzionalità del pulsante consiste nel generare le <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento quando viene selezionato, ma il comportamento del pulsante visual consiste nel modificare l'aspetto quando viene puntata o premuto.  
  
 Utilizzare <xref:System.Windows.VisualState> gli oggetti per specificare l'aspetto di un controllo quando è in un determinato stato. Oggetto <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> che modifica l'aspetto degli elementi presenti il <xref:System.Windows.Controls.ControlTemplate>. Non è necessario scrivere codice per ottenere questo risultato perché la logica del controllo modifica lo stato tramite il <xref:System.Windows.VisualStateManager>. Quando il controllo entra nello stato specificato per il <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> proprietà, il <xref:System.Windows.Media.Animation.Storyboard> inizia. Quando il controllo esce dallo stato, il <xref:System.Windows.Media.Animation.Storyboard> si arresta.  
  
 Nell'esempio seguente il <xref:System.Windows.VisualState> che modifica l'aspetto di un <xref:System.Windows.Controls.Button> quando il puntatore è su di esso. Il <xref:System.Windows.Media.Animation.Storyboard> cambia colore del bordo del pulsante modificando il colore del `BorderBrush`. Se si fa riferimento al <xref:System.Windows.Controls.ControlTemplate> riportato all'inizio di questo argomento, si ricorderà che `BorderBrush` è il nome del <xref:System.Windows.Media.SolidColorBrush> assegnato al <xref:System.Windows.Controls.Border.Background%2A> del <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Il controllo è responsabile della definizione degli stati come parte del relativo contratto e questo aspetto verrà, esaminato in dettaglio nella sezione [Personalizzazione di altri controlli sulla base del contratto di controllo](#customizing_other_controls_by_understanding_the_control_contract) più avanti in questo argomento. Nella tabella seguente sono elencati gli stati specificati per il <xref:System.Windows.Controls.Button>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
  
 Il <xref:System.Windows.Controls.Button> definisce due gruppi di stato: il `CommonStates` gruppo che contiene il `Normal`, `MouseOver`, `Pressed`, e `Disabled` stati. Mentre il gruppo `FocusStates` contiene gli stati `Focused` e `Unfocused`. Gli stati nello stesso gruppo si escludono a vicenda. Il controllo è sempre in uno stato specifico per ogni gruppo. Ad esempio, un <xref:System.Windows.Controls.Button> può diventare attivo, anche quando il puntatore del mouse viene spostato, pertanto un <xref:System.Windows.Controls.Button> nel `Focused` lo stato può essere nel `MouseOver`, `Pressed`, o `Normal` stato.  
  
 Aggiungere <xref:System.Windows.VisualState> oggetti <xref:System.Windows.VisualStateGroup> oggetti. Aggiungere <xref:System.Windows.VisualStateGroup> oggetti per il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà associata. L'esempio seguente definisce il <xref:System.Windows.VisualState> gli oggetti per il `Normal`, `MouseOver`, e `Pressed` stati, che sono tutti nel `CommonStates` gruppo. Il <xref:System.Windows.VisualState.Name%2A> di ogni <xref:System.Windows.VisualState> corrisponde al nome nella tabella precedente. Lo stato `Disabled` e gli stati del gruppo `FocusStates` sono stati omessi per brevità, ma sono inclusi nell'esempio completo alla fine di questo argomento.  
  
> [!NOTE]
>  Assicurarsi di impostare il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà nella directory principale associata <xref:System.Windows.FrameworkElement> del <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Nell'esempio precedente viene generato un output simile alle figure seguenti.  
  
 ![Pulsante con un modello di controllo personalizzato. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato nello stato normale  
  
 ![Pulsante con un bordo rosso. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato nello stato di passaggio del mouse  
  
 ![Il bordo è trasparente in un pulsante premuto. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Pulsante che usa un modello del controllo personalizzato nello stato premuto  
  
 Per trovare gli stati visivi dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Impostazione del comportamento di un controllo nella transizione tra stati  
 Nell'esempio precedente, l'aspetto del pulsante cambia anche quando viene selezionato dall'utente, ma se non viene premuto per almeno un secondo, l'utente non vede l'effetto. Per impostazione predefinita, l'animazione impiega un secondo per attivarsi. Poiché gli utenti possono fare clic su e rilascia un pulsante in molto meno tempo, il feedback visivo diventeranno effettivo se si lascia il <xref:System.Windows.Controls.ControlTemplate> nello stato predefinito.  
  
 È possibile specificare la quantità di tempo impiegata un'animazione di transizione graduale mediante l'aggiunta di un controllo da uno stato a un altro <xref:System.Windows.VisualTransition> oggetti per il <xref:System.Windows.Controls.ControlTemplate>. Quando si crea un <xref:System.Windows.VisualTransition>, si specifica uno o più delle operazioni seguenti:  
  
-   Il tempo necessario affinché si verifichi una transizione tra stati.  
  
-   Le modifiche aggiuntive nell'aspetto del controllo che si verificano al momento della transizione.  
  
-   Gli stati di <xref:System.Windows.VisualTransition> è collegato.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Impostazione della durata di una transizione  
 È possibile specificare la durata di una transizione impostando il <xref:System.Windows.VisualTransition.GeneratedDuration%2A> proprietà. Nell'esempio precedente è presente un <xref:System.Windows.VisualState> che specifica che il bordo del pulsante diventa trasparente quando viene premuto il pulsante, ma l'animazione è troppo lunga per essere visibile se il pulsante è premuto e rilasciato rapidamente. È possibile utilizzare un <xref:System.Windows.VisualTransition> per specificare la quantità di tempo impiegato il controllo per la transizione allo stato di pressione. Nell'esempio seguente viene specificato che il controllo impiega un centesimo di secondo per passare allo stato di pressione.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Impostazione delle modifiche all'aspetto del controllo durante una transizione  
 Il <xref:System.Windows.VisualTransition> contiene un <xref:System.Windows.Media.Animation.Storyboard> che inizia quando il controllo esegue la transizione tra stati. Ad esempio, è possibile specificare che una determinata animazione si verifica quando il controllo passa dallo stato `MouseOver` allo stato `Normal`. Nell'esempio seguente viene creato un <xref:System.Windows.VisualTransition> che specifica che quando l'utente sposta il puntatore del mouse dal pulsante, il bordo del pulsante diventa blu, quindi in giallo e infine su nero in 1,5 secondi.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Impostazione dei casi in cui applicare un oggetto VisualTransition  
 Oggetto <xref:System.Windows.VisualTransition> possono essere limitate da applicare solo a determinati stati o può essere applicato ogni volta che il controllo passa tra stati. Nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicata quando il controllo esce dal `MouseOver` allo stato di `Normal` stato; nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicata quando il controllo entra nel `Pressed` stato. Per limitare l'una <xref:System.Windows.VisualTransition> viene applicato dall'impostazione di <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> proprietà. Nella tabella seguente vengono descritti i livelli di restrizione, in modo decrescente dal più restrittivo.  
  
|Tipo di restrizione|Valore di From|Valore di To|  
|-------------------------|-------------------|-----------------|  
|Da uno stato specifico un altro stato specifico|Il nome di un<xref:System.Windows.VisualState>|Il nome di un<xref:System.Windows.VisualState>|  
|Da qualsiasi stato a uno stato specifico|Non impostato|Il nome di un<xref:System.Windows.VisualState>|  
|Da uno stato specifico a qualsiasi stato|Il nome di un<xref:System.Windows.VisualState>|Non impostato|  
|Da qualsiasi stato a qualsiasi altro stato|Non impostato|Non impostato|  
  
 È possibile avere più <xref:System.Windows.VisualTransition> gli oggetti in un <xref:System.Windows.VisualStateGroup> che fanno riferimento allo stesso stato, ma verranno utilizzati nell'ordine specificato nella tabella precedente. Nell'esempio seguente, sono disponibili due <xref:System.Windows.VisualTransition> oggetti. Quando il controllo passa dal `Pressed` allo stato di `MouseOver` stato, il <xref:System.Windows.VisualTransition> che contiene sia <xref:System.Windows.VisualTransition.From%2A> e <xref:System.Windows.VisualTransition.To%2A> set viene utilizzato. Quando il controllo passa da uno stato diverso da `Pressed` allo stato `MouseOver`, viene usato l'altro stato.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Il <xref:System.Windows.VisualStateGroup> ha un <xref:System.Windows.VisualStateGroup.Transitions%2A> proprietà che contiene il <xref:System.Windows.VisualTransition> gli oggetti che si applicano al <xref:System.Windows.VisualState> gli oggetti il <xref:System.Windows.VisualStateGroup>. Come il <xref:System.Windows.Controls.ControlTemplate> autore, si possono includere qualsiasi <xref:System.Windows.VisualTransition> desiderato. Tuttavia, se il <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> proprietà vengono impostate su nomi di stato che non sono nel <xref:System.Windows.VisualStateGroup>, <xref:System.Windows.VisualTransition> viene ignorato.  
  
 Nell'esempio seguente il <xref:System.Windows.VisualStateGroup> per il `CommonStates`. Nell'esempio viene definito un <xref:System.Windows.VisualTransition> per ognuno dei seguenti del pulsante esegue la transizione.  
  
-   Allo stato `Pressed`.  
  
-   Allo stato `MouseOver`.  
  
-   Dallo stato `Pressed` allo stato `MouseOver`.  
  
-   Dallo stato `MouseOver` allo stato `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalizzazione di altri controlli sulla base del contratto di controllo  
 Un controllo che utilizza un <xref:System.Windows.Controls.ControlTemplate> per specificare la struttura visual (tramite <xref:System.Windows.FrameworkElement> oggetti) e il comportamento di visual (tramite <xref:System.Windows.VisualState> oggetti) utilizza il modello di controllo di parti. Molti dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usano questo modello. Le parti che un <xref:System.Windows.Controls.ControlTemplate> autore deve essere comunicata vengono comunicati tramite il contratto di controllo. Quando si conoscono le parti di un contratto di controllo, è possibile personalizzare l'aspetto di qualsiasi controllo che utilizza il modello di controllo part.  
  
 Un contratto di controllo include tre elementi:  
  
-   Gli elementi visivi usati dalla logica del controllo.  
  
-   Gli stati del controllo e il gruppo a cui appartiene ogni stato.  
  
-   Le proprietà pubbliche che influiscono visivamente sul controllo.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementi visivi nel contratto di controllo  
 Talvolta una logica di controllo interagisce con un <xref:System.Windows.FrameworkElement> che si trova nel <xref:System.Windows.Controls.ControlTemplate>. Ad esempio, il controllo può gestire un evento di uno dei relativi elementi. Quando un controllo si aspetta di trovare un particolare <xref:System.Windows.FrameworkElement> nel <xref:System.Windows.Controls.ControlTemplate>, devono essere tali informazioni per il <xref:System.Windows.Controls.ControlTemplate> autore. Il controllo Usa il <xref:System.Windows.TemplatePartAttribute> per fornire il tipo di elemento previsto e quale deve essere il nome dell'elemento. Il <xref:System.Windows.Controls.Button> privo di <xref:System.Windows.FrameworkElement> parti nel relativo contratto, ma altri controlli, ad esempio il <xref:System.Windows.Controls.ComboBox>, eseguire.  
  
 Nell'esempio seguente il <xref:System.Windows.TemplatePartAttribute> gli oggetti specificati nella <xref:System.Windows.Controls.ComboBox> classe. La logica di <xref:System.Windows.Controls.ComboBox> prevede di trovare un <xref:System.Windows.Controls.TextBox> denominato `PART_EditableTextBox` e un <xref:System.Windows.Controls.Primitives.Popup> denominato `PART_Popup` nel relativo <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 L'esempio seguente mostra una rappresentazione semplificata <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ComboBox> che include gli elementi specificati dal <xref:System.Windows.TemplatePartAttribute> gli oggetti al <xref:System.Windows.Controls.ComboBox> classe.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Stati nel contratto di controllo  
 Anche gli stati di un controllo fanno parte del contratto di controllo. Nell'esempio di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button> viene illustrato come specificare l'aspetto di un <xref:System.Windows.Controls.Button> a seconda degli stati. Si crea un <xref:System.Windows.VisualState> per ogni stato specificato e inserire tutte <xref:System.Windows.VisualState> gli oggetti che condividono un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> in un <xref:System.Windows.VisualStateGroup>, come descritto in [modifica dell'aspetto di un controllo a seconda del relativo stato](#changing_the_appearance_of_a_control_depending_on_its_state) più indietro in questo argomento. Controlli di terze parti devono specificare gli stati tramite le <xref:System.Windows.TemplateVisualStateAttribute>, che consente gli strumenti di progettazione, ad esempio Expression Blend, per esporre gli stati del controllo per la creazione di modelli di controllo.  
  
 Per trovare il contratto di controllo dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Proprietà nel contratto di controllo  
 Anche le proprietà pubbliche che influiscono visivamente sul controllo sono incluse nel contratto di controllo. È possibile impostare queste proprietà per modificare l'aspetto del controllo senza creare un nuovo <xref:System.Windows.Controls.ControlTemplate>. È inoltre possibile utilizzare il [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup per associare le proprietà di elementi che sono nel <xref:System.Windows.Controls.ControlTemplate> a proprietà pubbliche definite per il <xref:System.Windows.Controls.Button>.  
  
 L'esempio seguente illustra il contratto di controllo per il pulsante.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate>, è spesso più semplice iniziare con un oggetto esistente <xref:System.Windows.Controls.ControlTemplate> e apportarvi modifiche. È possibile eseguire una delle operazioni seguenti per modificare un oggetto esistente <xref:System.Windows.Controls.ControlTemplate>:  
  
-   Utilizzare una finestra di progettazione, ad esempio Expression Blend, che fornisce un'interfaccia utente grafica per la creazione di modelli del controllo. Per altre informazioni, vedere [Applicazione di stili a un controllo che supporta modelli](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Ottenere il valore predefinito <xref:System.Windows.Controls.ControlTemplate> e modificarlo. Per trovare i modelli del controllo predefiniti che sono inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Temi WPF predefiniti](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Esempio completo  
 Nell'esempio seguente viene illustrato l'intero <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> che è descritto in questo argomento.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
