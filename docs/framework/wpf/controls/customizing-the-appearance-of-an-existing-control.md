---
title: Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
ms.date: 03/30/2017
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
ms.openlocfilehash: 435789e0d1bc601a9eb51488254407fefd334e05
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706145"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
<a name="introduction"></a> Oggetto <xref:System.Windows.Controls.ControlTemplate> specifica la struttura visiva e il comportamento di un controllo. È possibile personalizzare l'aspetto di un controllo assegnando una nuova <xref:System.Windows.Controls.ControlTemplate>. Quando si crea un <xref:System.Windows.Controls.ControlTemplate>, si sostituisce l'aspetto di un controllo esistente senza modificarne la funzionalità. Ad esempio, è possibile rendere i pulsanti nell'applicazione forma rotonda invece della forma quadrata predefinita, ma il pulsante genererà comunque il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
 Questo argomento illustra le varie parti di un <xref:System.Windows.Controls.ControlTemplate>, viene illustrato come creare una semplice <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>e spiega come comprendere il contratto di controllo di un controllo in modo che sia possibile personalizzare l'aspetto del controllo. Poiché si crea una <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile modificare l'aspetto del controllo senza scrivere alcun codice. È anche possibile usare una finestra di progettazione, ad esempio Microsoft Expression Blend, per creare modelli di controlli personalizzati. Questo argomento viene illustrato negli esempi il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che consentono di personalizzare l'aspetto di un <xref:System.Windows.Controls.Button> ed elenca l'esempio completo alla fine dell'argomento. Per altre informazioni sull'uso di Expression Blend, vedere [Applicazione di stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Le illustrazioni seguenti viene illustrato un <xref:System.Windows.Controls.Button> che usa il <xref:System.Windows.Controls.ControlTemplate> che viene creato in questo argomento.  
  
 ![Pulsante con un modello del controllo personalizzato. ](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato  
  
 ![Pulsante con un bordo rosso. ](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato e su cui è posizionato il puntatore del mouse  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si basa sul presupposto che si sappiano creare e usare i controlli e gli stili come descritto in [Controlli](../../../../docs/framework/wpf/controls/index.md). I concetti illustrati in questo argomento si applicano agli elementi che ereditano dal <xref:System.Windows.Controls.Control> (classe), tranne per il <xref:System.Windows.Controls.UserControl>. Non è possibile applicare una <xref:System.Windows.Controls.ControlTemplate> a un <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Quando creare un oggetto ControlTemplate  
 Controlli presentano molte proprietà, ad esempio <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>, che è possibile impostare per specificare diversi aspetti dell'aspetto del controllo, ma le modifiche che è possibile configurare queste proprietà sono limitate. Ad esempio, è possibile impostare il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà impostandolo sul blu e <xref:System.Windows.Controls.Control.FontStyle%2A> su corsivo in un <xref:System.Windows.Controls.CheckBox>.  
  
 Senza la possibilità di creare una nuova <xref:System.Windows.Controls.ControlTemplate> per i controlli, tutti i controlli in ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su avrebbe lo stesso aspetto generale, limitando così la possibilità di creare un'applicazione con un aspetto personalizzato. Per impostazione predefinita, ogni <xref:System.Windows.Controls.CheckBox> presenta caratteristiche simili. Ad esempio, il contenuto del <xref:System.Windows.Controls.CheckBox> è sempre a destra dell'indicatore di selezione, e il segno di spunta viene sempre utilizzato per indicare che il <xref:System.Windows.Controls.CheckBox> sia selezionata.  
  
 Si crea un <xref:System.Windows.Controls.ControlTemplate> quando si desidera personalizzare l'aspetto del controllo oltre che dall'impostazione delle altre proprietà nel controllo. Nell'esempio del <xref:System.Windows.Controls.CheckBox>, si supponga che il contenuto della casella di controllo di sopra dell'indicatore di selezione e si desidera una X per indicare che il <xref:System.Windows.Controls.CheckBox> sia selezionata. È possibile specificare queste modifiche nel <xref:System.Windows.Controls.ControlTemplate> del <xref:System.Windows.Controls.CheckBox>.  
  
 La figura seguente mostra una <xref:System.Windows.Controls.CheckBox> che usa un valore predefinito <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Casella di controllo con il modello di controllo predefinito. ](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Oggetto CheckBox che usa il modello del controllo predefinito  
  
 La figura seguente mostra una <xref:System.Windows.Controls.CheckBox> che usa un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> per posizionare il contenuto del <xref:System.Windows.Controls.CheckBox> sopra l'indicatore di selezione e visualizza una X quando il <xref:System.Windows.Controls.CheckBox> sia selezionata.  
  
 ![Casella di controllo con un modello del controllo personalizzato. ](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Oggetto CheckBox che usa un modello del controllo personalizzato  
  
 Il <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.CheckBox> in questo esempio è abbastanza complesso, pertanto questo argomento viene utilizzato un semplice esempio di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Modifica della struttura visiva di un controllo  
 Nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un controllo è spesso un composto <xref:System.Windows.FrameworkElement> oggetti. Quando si crea una <xref:System.Windows.Controls.ControlTemplate>, si combinano <xref:System.Windows.FrameworkElement> oggetti per compilare un singolo controllo. Oggetto <xref:System.Windows.Controls.ControlTemplate> deve avere un solo <xref:System.Windows.FrameworkElement> come elemento radice. L'elemento radice contiene in genere altri <xref:System.Windows.FrameworkElement> oggetti. La combinazione degli oggetti costituisce la struttura visiva del controllo.  
  
 L'esempio seguente crea un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Button>. Il <xref:System.Windows.Controls.ControlTemplate> crea la struttura visiva del <xref:System.Windows.Controls.Button>. In questo esempio, l'aspetto del pulsante non cambia quando si sposta il puntatore del mouse o si fa clic su di esso. La procedura per modificare l'aspetto del pulsante quando è in uno stato diverso viene descritta più avanti in questo argomento.  
  
 In questo esempio, la struttura visiva è costituita dalle parti seguenti:  
  
-   Oggetto <xref:System.Windows.Controls.Border> denominate `RootElement` che funge da radice del modello <xref:System.Windows.FrameworkElement>.  
  
-   Oggetto <xref:System.Windows.Controls.Grid> che è un figlio del `RootElement`.  
  
-   Oggetto <xref:System.Windows.Controls.ContentPresenter> che consente di visualizzare il contenuto del pulsante. Il <xref:System.Windows.Controls.ContentPresenter> consente a qualsiasi tipo di oggetto da visualizzare.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Mantenimento della funzionalità delle proprietà di un controllo tramite TemplateBinding  
 Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate>, è comunque possibile usare le proprietà pubbliche per modificare l'aspetto del controllo. Il [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup associa una proprietà di un elemento che si trova nel <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica definita dal controllo. Quando si usa [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), si consente alle proprietà del controllo di fungere da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 Nell'esempio seguente viene ripetuta la parte dell'esempio precedente che usa il [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup per associare le proprietà degli elementi inclusi nel <xref:System.Windows.Controls.ControlTemplate> a proprietà pubbliche definite dal pulsante.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In questo esempio, il <xref:System.Windows.Controls.Grid> ha relativi <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> modello di proprietà associato a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. In quanto <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> è associato al modello, è possibile creare più pulsanti che utilizzano la stessa <xref:System.Windows.Controls.ControlTemplate> e impostare il <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> su valori diversi per ogni pulsante. Se <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> è stata non modello associata a una proprietà di un elemento nel <xref:System.Windows.Controls.ControlTemplate>, impostando il <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> di un pulsante avrebbe alcun effetto sull'aspetto del pulsante.  
  
 Tenere presente che i nomi delle due proprietà non devono necessariamente essere identici. Nell'esempio precedente, il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> proprietà del <xref:System.Windows.Controls.Button> modello associato ai <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> proprietà del <xref:System.Windows.Controls.ContentPresenter>. In questo modo il contenuto del pulsante può essere posizionato orizzontalmente. <xref:System.Windows.Controls.ContentPresenter> non ha una proprietà denominata `HorizontalContentAlignment`, ma <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> può essere associato a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Quando si associa al modello una proprietà, accertarsi che le proprietà di origine e destinazione siano dello stesso tipo.  
  
 Il <xref:System.Windows.Controls.Control> classe definisce diverse proprietà che deve essere utilizzata dal modello del controllo per avere effetto sul controllo quando vengono impostate. Come il <xref:System.Windows.Controls.ControlTemplate> Usa la proprietà dipende dalla proprietà. Il <xref:System.Windows.Controls.ControlTemplate> deve usare la proprietà in uno dei modi seguenti:  
  
-   Un elemento di <xref:System.Windows.Controls.ControlTemplate> modello associato alla proprietà.  
  
-   Un elemento di <xref:System.Windows.Controls.ControlTemplate> eredita la proprietà da un oggetto padre <xref:System.Windows.FrameworkElement>.  
  
 La tabella seguente elenca le proprietà visive ereditate da un controllo dal <xref:System.Windows.Controls.Control> classe. Indica anche se il modello del controllo predefinito di un controllo usa il valore della proprietà ereditato o se deve essere associato al modello.  
  
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
  
 La tabella elenca solo le proprietà visive ereditate dal <xref:System.Windows.Controls.Control> classe. Oltre alle proprietà elencate nella tabella, un controllo può anche ereditare le <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, e <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> proprietà dall'elemento framework padre.  
  
 Inoltre, se il <xref:System.Windows.Controls.ContentPresenter> è nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ContentControl>, il <xref:System.Windows.Controls.ContentPresenter> verrà automaticamente associato al <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà. Allo stesso modo, un' <xref:System.Windows.Controls.ItemsPresenter> che si trova nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ItemsControl> verrà automaticamente associato al <xref:System.Windows.Controls.ItemsControl.Items%2A> e <xref:System.Windows.Controls.ItemsPresenter> proprietà.  
  
 L'esempio seguente crea due pulsanti che utilizzano il <xref:System.Windows.Controls.ControlTemplate> definito nell'esempio precedente. Nell'esempio viene impostata la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontSize%2A> proprietà per ogni pulsante. Impostando il <xref:System.Windows.Controls.Control.Background%2A> proprietà ha effetto perché è associata al modello nel <xref:System.Windows.Controls.ControlTemplate>. Anche se il <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.FontSize%2A> vlastnosti nejsou associato al modello, la loro impostazione ha effetto poiché i relativi valori vengono ereditati.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Nell'esempio precedente viene generato un output simile alla figura seguente.  
  
 ![Due pulsanti, uno blu e uno viola. ](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
Due pulsanti con diversi colori di sfondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Modifica dell'aspetto di un controllo in base allo stato  
 La differenza tra un pulsante con l'aspetto predefinito e il pulsante dell'esempio precedente è che il pulsante predefinito cambia leggermente in relazione allo stato. Ad esempio, l'aspetto del pulsante predefinito cambia quando viene premuto o quando il puntatore del mouse viene spostato sul pulsante. Sebbene il <xref:System.Windows.Controls.ControlTemplate> non modifica la funzionalità di un controllo, viene modificato il comportamento visivo del controllo. Il comportamento visivo descrive l'aspetto del controllo quando è in un determinato stato. Per comprendere la differenza tra la funzionalità e il comportamento visivo di un controllo, si consideri l'esempio del pulsante. La funzionalità del pulsante consiste nel generare il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento quando viene fatto clic, ma il comportamento visivo del pulsante consiste nel modificare l'aspetto del controllo quando viene puntato o premuto.  
  
 Si utilizza <xref:System.Windows.VisualState> oggetti per specificare l'aspetto di un controllo quando è in un determinato stato. Oggetto <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> che modifica l'aspetto degli elementi che sono nel <xref:System.Windows.Controls.ControlTemplate>. Non devi scrivere codice per ottenere questo risultato perché per la logica del controllo cambia stato usando il <xref:System.Windows.VisualStateManager>. Quando il controllo passa allo stato specificato per il <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> proprietà, il <xref:System.Windows.Media.Animation.Storyboard> inizia. Quando il controllo esce dallo stato, il <xref:System.Windows.Media.Animation.Storyboard> si arresta.  
  
 L'esempio seguente mostra le <xref:System.Windows.VisualState> che modifica l'aspetto di un <xref:System.Windows.Controls.Button> quando il puntatore del mouse è posizionato sopra di essa. Il <xref:System.Windows.Media.Animation.Storyboard> modificando il colore del colore del bordo del pulsante viene modificato il `BorderBrush`. Se si fa riferimento il <xref:System.Windows.Controls.ControlTemplate> riportato all'inizio di questo argomento, si ricorderà che `BorderBrush` è il nome del <xref:System.Windows.Media.SolidColorBrush> che viene assegnato al <xref:System.Windows.Controls.Border.Background%2A> del <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Il controllo è responsabile della definizione degli stati come parte del relativo contratto e questo aspetto verrà, esaminato in dettaglio nella sezione [Personalizzazione di altri controlli sulla base del contratto di controllo](#customizing_other_controls_by_understanding_the_control_contract) più avanti in questo argomento. La tabella seguente elenca gli stati specificati per il <xref:System.Windows.Controls.Button>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
  
 Il <xref:System.Windows.Controls.Button> definisce due gruppi di stati: il `CommonStates` gruppo che contiene il `Normal`, `MouseOver`, `Pressed`, e `Disabled` stati. Mentre il gruppo `FocusStates` contiene gli stati `Focused` e `Unfocused`. Gli stati nello stesso gruppo si escludono a vicenda. Il controllo è sempre in uno stato specifico per ogni gruppo. Ad esempio, un <xref:System.Windows.Controls.Button> può avere lo stato attivo anche quando il puntatore del mouse non è posizionato sopra di essa, quindi, un <xref:System.Windows.Controls.Button> nel `Focused` lo stato può essere nel `MouseOver`, `Pressed`, o `Normal` dello stato.  
  
 Si aggiungono <xref:System.Windows.VisualState> oggetti <xref:System.Windows.VisualStateGroup> oggetti. Si aggiungono <xref:System.Windows.VisualStateGroup> gli oggetti per il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà associata. L'esempio seguente definisce la <xref:System.Windows.VisualState> degli oggetti per il `Normal`, `MouseOver`, e `Pressed` stati, che fanno tutti il `CommonStates` gruppo. Il <xref:System.Windows.VisualState.Name%2A> della ognuno <xref:System.Windows.VisualState> corrisponde al nome nella tabella precedente. Lo stato `Disabled` e gli stati del gruppo `FocusStates` sono stati omessi per brevità, ma sono inclusi nell'esempio completo alla fine di questo argomento.  
  
> [!NOTE]
>  Assicurarsi di impostare il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà sulla directory radice associata <xref:System.Windows.FrameworkElement> del <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Nell'esempio precedente viene generato un output simile alle figure seguenti.  
  
 ![Pulsante con un modello del controllo personalizzato. ](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato nello stato normale  
  
 ![Pulsante con un bordo rosso. ](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato nello stato di passaggio del mouse  
  
 ![Il bordo è trasparente in un pulsante premuto. ](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Pulsante che usa un modello del controllo personalizzato nello stato premuto  
  
 Per trovare gli stati visivi dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Impostazione del comportamento di un controllo nella transizione tra stati  
 Nell'esempio precedente, l'aspetto del pulsante cambia anche quando viene selezionato dall'utente, ma se non viene premuto per almeno un secondo, l'utente non vede l'effetto. Per impostazione predefinita, l'animazione impiega un secondo per attivarsi. Poiché è probabile che gli utenti rilasciano un pulsante in molto meno tempo, il feedback visivo non sarà efficace se si lascia il <xref:System.Windows.Controls.ControlTemplate> nello stato predefinito.  
  
 È possibile specificare la quantità di tempo impiegato per eseguire la transizione senza problemi un controllo da uno stato a altro mediante l'aggiunta di un'animazione <xref:System.Windows.VisualTransition> gli oggetti per il <xref:System.Windows.Controls.ControlTemplate>. Quando si crea un <xref:System.Windows.VisualTransition>, si specifica uno o più delle operazioni seguenti:  
  
-   Il tempo necessario affinché si verifichi una transizione tra stati.  
  
-   Le modifiche aggiuntive nell'aspetto del controllo che si verificano al momento della transizione.  
  
-   Gli stati di <xref:System.Windows.VisualTransition> viene applicato a.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Impostazione della durata di una transizione  
 È possibile specificare il tempo necessario una transizione impostando il <xref:System.Windows.VisualTransition.GeneratedDuration%2A> proprietà. Nell'esempio precedente è presente un <xref:System.Windows.VisualState> che specifica che il bordo del pulsante diventa trasparente quando viene premuto il pulsante, ma l'animazione richiede troppo tempo per essere visualizzata se il pulsante viene premuto e rilasciato rapidamente. È possibile usare un <xref:System.Windows.VisualTransition> per specificare la quantità di tempo impiegato dal controllo per la transizione allo stato premuto. Nell'esempio seguente viene specificato che il controllo impiega un centesimo di secondo per passare allo stato di pressione.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Impostazione delle modifiche all'aspetto del controllo durante una transizione  
 Il <xref:System.Windows.VisualTransition> contiene un <xref:System.Windows.Media.Animation.Storyboard> che inizia quando il controllo esegue la transizione tra stati. Ad esempio, è possibile specificare che una determinata animazione si verifica quando il controllo passa dallo stato `MouseOver` allo stato `Normal`. L'esempio seguente crea un <xref:System.Windows.VisualTransition> che specifica che quando l'utente sposta il puntatore del mouse dal pulsante, il bordo del pulsante diventa blu, quindi giallo e infine nero in 1,5 secondi.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Impostazione dei casi in cui applicare un oggetto VisualTransition  
 Oggetto <xref:System.Windows.VisualTransition> possono essere limitate da applicare solo a determinati stati o applicarlo ogni volta che il controllo passa tra stati. Nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicata quando il controllo passa dal `MouseOver` torni allo stato di `Normal` stato; nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicata quando il controllo passa al `Pressed` dello stato. Per limitare l'una <xref:System.Windows.VisualTransition> viene applicata mediante l'impostazione di <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> proprietà. Nella tabella seguente vengono descritti i livelli di restrizione, in modo decrescente dal più restrittivo.  
  
|Tipo di restrizione|Valore di From|Valore di To|  
|-------------------------|-------------------|-----------------|  
|Da uno stato specifico un altro stato specifico|Il nome di un <xref:System.Windows.VisualState>|Il nome di un <xref:System.Windows.VisualState>|  
|Da qualsiasi stato a uno stato specifico|Non impostato|Il nome di un <xref:System.Windows.VisualState>|  
|Da uno stato specifico a qualsiasi stato|Il nome di un <xref:System.Windows.VisualState>|Non impostato|  
|Da qualsiasi stato a qualsiasi altro stato|Non impostato|Non impostato|  
  
 È possibile avere più <xref:System.Windows.VisualTransition> oggetti un <xref:System.Windows.VisualStateGroup> che fanno riferimento allo stesso stato, ma verranno usati nell'ordine specificato nella tabella precedente. Nell'esempio seguente, sono presenti due <xref:System.Windows.VisualTransition> oggetti. Quando il controllo passa dal `Pressed` torni allo stato il `MouseOver` lo stato, il <xref:System.Windows.VisualTransition> che ha entrambi <xref:System.Windows.VisualTransition.From%2A> e <xref:System.Windows.VisualTransition.To%2A> set viene utilizzato. Quando il controllo passa da uno stato diverso da `Pressed` allo stato `MouseOver`, viene usato l'altro stato.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Il <xref:System.Windows.VisualStateGroup> ha un <xref:System.Windows.VisualStateGroup.Transitions%2A> proprietà che contiene il <xref:System.Windows.VisualTransition> oggetti che si applicano al <xref:System.Windows.VisualState> gli oggetti nel <xref:System.Windows.VisualStateGroup>. Come le <xref:System.Windows.Controls.ControlTemplate> autore, si è liberi includere eventuali <xref:System.Windows.VisualTransition> desiderato. Tuttavia, se il <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> sono impostate su nomi di stato che non sono nel <xref:System.Windows.VisualStateGroup>, il <xref:System.Windows.VisualTransition> viene ignorato.  
  
 L'esempio seguente mostra le <xref:System.Windows.VisualStateGroup> per il `CommonStates`. L'esempio definisce un <xref:System.Windows.VisualTransition> per ognuno dei seguenti del pulsante esegue la transizione.  
  
-   Allo stato `Pressed`.  
  
-   Allo stato `MouseOver`.  
  
-   Dallo stato `Pressed` allo stato `MouseOver`.  
  
-   Dallo stato `MouseOver` allo stato `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalizzazione di altri controlli sulla base del contratto di controllo  
 Un controllo che usa un' <xref:System.Windows.Controls.ControlTemplate> per specificare la struttura visiva (usando <xref:System.Windows.FrameworkElement> oggetti) e il comportamento visivo (tramite <xref:System.Windows.VisualState> oggetti) usa il modello di controllo part. Molti dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usano questo modello. Le parti che un <xref:System.Windows.Controls.ControlTemplate> autore dovrà essere a conoscenza vengono comunicate tramite il contratto di controllo. Quando si conoscono le parti di un contratto di controllo, è possibile personalizzare l'aspetto di qualsiasi controllo che utilizza il modello di controllo part.  
  
 Un contratto di controllo include tre elementi:  
  
-   Gli elementi visivi usati dalla logica del controllo.  
  
-   Gli stati del controllo e il gruppo a cui appartiene ogni stato.  
  
-   Le proprietà pubbliche che influiscono visivamente sul controllo.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementi visivi nel contratto di controllo  
 In alcuni casi per la logica di un controllo interagisce con un <xref:System.Windows.FrameworkElement> che si trova nel <xref:System.Windows.Controls.ControlTemplate>. Ad esempio, il controllo può gestire un evento di uno dei relativi elementi. Quando un controllo si aspetta di trovare un determinato <xref:System.Windows.FrameworkElement> nella <xref:System.Windows.Controls.ControlTemplate>, deve fornire tali informazioni per il <xref:System.Windows.Controls.ControlTemplate> autore. Il controllo Usa il <xref:System.Windows.TemplatePartAttribute> per indicare il tipo di elemento previsto e quale deve essere il nome dell'elemento. Il <xref:System.Windows.Controls.Button> non ha <xref:System.Windows.FrameworkElement> parti nel relativo contratto di controllo, ma altri controlli, ad esempio il <xref:System.Windows.Controls.ComboBox>, eseguire operazioni.  
  
 L'esempio seguente mostra le <xref:System.Windows.TemplatePartAttribute> gli oggetti che vengono specificati nel <xref:System.Windows.Controls.ComboBox> classe. La logica del <xref:System.Windows.Controls.ComboBox> si aspetta di trovare un <xref:System.Windows.Controls.TextBox> denominata `PART_EditableTextBox` e un <xref:System.Windows.Controls.Primitives.Popup> denominato `PART_Popup` nel relativo <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 L'esempio seguente mostra una rappresentazione semplificata <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ComboBox> che include gli elementi specificati dalle <xref:System.Windows.TemplatePartAttribute> oggetti nel <xref:System.Windows.Controls.ComboBox> classe.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Stati nel contratto di controllo  
 Anche gli stati di un controllo fanno parte del contratto di controllo. L'esempio di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button> Mostra come specificare l'aspetto di un <xref:System.Windows.Controls.Button> a seconda dei suoi Stati. Si crea una <xref:System.Windows.VisualState> per ogni stato specificato e inserire tutti i <xref:System.Windows.VisualState> gli oggetti che condividono un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> in un <xref:System.Windows.VisualStateGroup>, come descritto in [modifica dell'aspetto di un controllo a seconda del relativo stato](#changing_the_appearance_of_a_control_depending_on_its_state) più indietro in questo argomento. I controlli di terze parti devono specificare gli stati tramite il <xref:System.Windows.TemplateVisualStateAttribute>, che consente di strumenti della finestra di progettazione, ad esempio Expression Blend, per esporre gli stati del controllo per la creazione di modelli di controllo.  
  
 Per trovare il contratto di controllo dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Proprietà nel contratto di controllo  
 Anche le proprietà pubbliche che influiscono visivamente sul controllo sono incluse nel contratto di controllo. È possibile impostare queste proprietà per modificare l'aspetto del controllo senza creare un nuovo <xref:System.Windows.Controls.ControlTemplate>. È anche possibile usare la [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup per associare le proprietà degli elementi inclusi nel <xref:System.Windows.Controls.ControlTemplate> alle proprietà pubbliche definite dal <xref:System.Windows.Controls.Button>.  
  
 L'esempio seguente illustra il contratto di controllo per il pulsante.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Quando si crea una <xref:System.Windows.Controls.ControlTemplate>, è spesso più semplice iniziare con un oggetto esistente <xref:System.Windows.Controls.ControlTemplate> e apportarvi modifiche. È possibile eseguire una delle seguenti opzioni per modificare un oggetto esistente <xref:System.Windows.Controls.ControlTemplate>:  
  
-   Utilizzare una finestra di progettazione, ad esempio Expression Blend, che fornisce un'interfaccia utente grafica per la creazione di modelli del controllo. Per altre informazioni, vedere [Applicazione di stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Ottenere il valore predefinito <xref:System.Windows.Controls.ControlTemplate> e modificarlo. Per trovare i modelli del controllo predefiniti che sono inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Temi WPF predefiniti](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Esempio completo  
 L'esempio seguente illustra l'intero <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> che è descritti in questo argomento.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
