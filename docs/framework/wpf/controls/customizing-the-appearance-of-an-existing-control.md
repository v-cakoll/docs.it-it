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
ms.openlocfilehash: 63a0b724b71c4a4901c2dedcf502045a75ec405c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933727"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
<a name="introduction"></a>Un <xref:System.Windows.Controls.ControlTemplate> oggetto specifica la struttura visiva e il comportamento visivo di un controllo. È possibile personalizzare l'aspetto di un controllo assegnando un nuovo <xref:System.Windows.Controls.ControlTemplate>oggetto. Quando si crea un <xref:System.Windows.Controls.ControlTemplate>oggetto, si sostituisce l'aspetto di un controllo esistente senza modificarne la funzionalità. Ad esempio, è possibile fare in modo che i pulsanti all'interno dell'applicazione si trovino invece della forma quadrata predefinita, ma <xref:System.Windows.Controls.Primitives.ButtonBase.Click> il pulsante genera comunque l'evento.  
  
 In questo argomento vengono illustrate le varie <xref:System.Windows.Controls.ControlTemplate>parti di un oggetto, <xref:System.Windows.Controls.ControlTemplate> viene illustrata la creazione di una semplice per un <xref:System.Windows.Controls.Button>e viene illustrato come comprendere il contratto di controllo di un controllo in modo che sia possibile personalizzarne l'aspetto. Poiché si crea un <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile modificare l'aspetto di un controllo senza scrivere alcun codice. È anche possibile usare una finestra di progettazione, ad esempio Microsoft Expression Blend, per creare modelli di controlli personalizzati. In questo argomento vengono illustrati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempi nell'oggetto che consente di <xref:System.Windows.Controls.Button> personalizzare l'aspetto di un oggetto ed elencare l'esempio completo alla fine dell'argomento. Per altre informazioni sull'uso di Expression Blend, vedere [Applicazione di stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Nelle illustrazioni seguenti viene illustrato <xref:System.Windows.Controls.Button> un oggetto che <xref:System.Windows.Controls.ControlTemplate> utilizza l'oggetto creato in questo argomento.  
  
 ![Un pulsante con un modello di controllo personalizzato.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato  
  
 ![Un pulsante con un bordo rosso.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato e su cui è posizionato il puntatore del mouse  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si basa sul presupposto che si sappiano creare e usare i controlli e gli stili come descritto in [Controlli](index.md). I concetti illustrati in questo argomento si applicano agli elementi che <xref:System.Windows.Controls.Control> ereditano dalla classe, <xref:System.Windows.Controls.UserControl>ad eccezione di. Non è possibile applicare <xref:System.Windows.Controls.ControlTemplate> un oggetto <xref:System.Windows.Controls.UserControl>a un oggetto.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Quando creare un oggetto ControlTemplate  
 I controlli hanno molte proprietà, ad <xref:System.Windows.Controls.Border.Background%2A>esempio <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>, che è possibile impostare per specificare diversi aspetti dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate. Ad esempio, è possibile impostare la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà su blu e <xref:System.Windows.Controls.Control.FontStyle%2A> su corsivo in un <xref:System.Windows.Controls.CheckBox>oggetto.  
  
 Senza la possibilità di creare un nuovo <xref:System.Windows.Controls.ControlTemplate> controllo per i controlli, tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]controlli in ogni applicazione basata su hanno lo stesso aspetto generale, in modo da limitare la possibilità di creare un'applicazione con un aspetto personalizzato. Per impostazione predefinita, <xref:System.Windows.Controls.CheckBox> ogni ha caratteristiche simili. Ad esempio, il contenuto di <xref:System.Windows.Controls.CheckBox> è sempre a destra dell'indicatore di selezione e il segno di spunta viene sempre usato per indicare che l'oggetto <xref:System.Windows.Controls.CheckBox> è selezionato.  
  
 Viene creato un <xref:System.Windows.Controls.ControlTemplate> oggetto quando si desidera personalizzare l'aspetto del controllo oltre a quello che l'impostazione delle altre proprietà del controllo. Nell'esempio di <xref:System.Windows.Controls.CheckBox>, si supponga che il contenuto della casella di controllo sia sopra l'indicatore di selezione e che si desideri una X per indicare che l'oggetto <xref:System.Windows.Controls.CheckBox> è selezionato. Queste modifiche vengono specificate nella <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>di.  
  
 Nella figura seguente viene illustrato <xref:System.Windows.Controls.CheckBox> un oggetto che utilizza <xref:System.Windows.Controls.ControlTemplate>un valore predefinito.  
  
 ![Casella di controllo con il modello di controllo predefinito.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Oggetto CheckBox che usa il modello del controllo predefinito  
  
 Nella figura seguente viene illustrato <xref:System.Windows.Controls.CheckBox> un oggetto che utilizza <xref:System.Windows.Controls.ControlTemplate> un oggetto personalizzato per <xref:System.Windows.Controls.CheckBox> inserire il contenuto di sopra l'indicatore di <xref:System.Windows.Controls.CheckBox> selezione e visualizza una X quando viene selezionato.  
  
 ![Casella di controllo con un modello di controllo personalizzato.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Oggetto CheckBox che usa un modello del controllo personalizzato  
  
 Per in questo esempio è relativamente complesso, quindi in questo argomento viene utilizzato un esempio più semplice di creazione di <xref:System.Windows.Controls.ControlTemplate> un oggetto per un oggetto. <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Modifica della struttura visiva di un controllo  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un controllo è spesso un oggetto <xref:System.Windows.FrameworkElement> composito. Quando si crea un <xref:System.Windows.Controls.ControlTemplate>oggetto, si <xref:System.Windows.FrameworkElement> combinano gli oggetti per compilare un unico controllo. Un <xref:System.Windows.Controls.ControlTemplate> oggetto deve avere un <xref:System.Windows.FrameworkElement> solo come elemento radice. L'elemento radice contiene in genere <xref:System.Windows.FrameworkElement> altri oggetti. La combinazione degli oggetti costituisce la struttura visiva del controllo.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ControlTemplate> oggetto personalizzato <xref:System.Windows.Controls.Button>per l'oggetto. Crea la struttura visiva dell'oggetto <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.ControlTemplate> In questo esempio, l'aspetto del pulsante non cambia quando si sposta il puntatore del mouse o si fa clic su di esso. La procedura per modificare l'aspetto del pulsante quando è in uno stato diverso viene descritta più avanti in questo argomento.  
  
 In questo esempio, la struttura visiva è costituita dalle parti seguenti:  
  
- Oggetto <xref:System.Windows.Controls.Border> <xref:System.Windows.FrameworkElement>denominato `RootElement` che funge da radice del modello.  
  
- Oggetto <xref:System.Windows.Controls.Grid> che è un elemento figlio `RootElement`di.  
  
- Oggetto <xref:System.Windows.Controls.ContentPresenter> che Visualizza il contenuto del pulsante. <xref:System.Windows.Controls.ContentPresenter> Consente di visualizzare qualsiasi tipo di oggetto.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Mantenimento della funzionalità delle proprietà di un controllo tramite TemplateBinding  
 Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate>, è comunque possibile usare le proprietà pubbliche per modificare l'aspetto del controllo. L'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) associa una proprietà di un elemento che si trova in <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica definita dal controllo. Quando si usa [TemplateBinding](../advanced/templatebinding-markup-extension.md), si consente alle proprietà del controllo di fungere da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../advanced/templatebinding-markup-extension.md).  
  
 Nell'esempio seguente viene ripetuta la parte dell'esempio precedente che usa l'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) per associare le proprietà degli elementi presenti in <xref:System.Windows.Controls.ControlTemplate> alle proprietà pubbliche definite dal pulsante.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In questo esempio il <xref:System.Windows.Controls.Grid> modello di <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà è associato a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Poiché <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> è associato <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> a un modello, è possibile creare più pulsanti che utilizzano <xref:System.Windows.Controls.ControlTemplate> lo stesso e impostare su valori diversi in ogni pulsante. Se <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> non è associato a un modello a una proprietà di un elemento <xref:System.Windows.Controls.ControlTemplate>in, l' <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> impostazione di di un pulsante non avrà alcun effetto sull'aspetto del pulsante.  
  
 Tenere presente che i nomi delle due proprietà non devono necessariamente essere identici. Nell'esempio precedente, <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> la proprietà <xref:System.Windows.Controls.Button> di <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> è un modello associato <xref:System.Windows.Controls.ContentPresenter>alla proprietà di. In questo modo il contenuto del pulsante può essere posizionato orizzontalmente. <xref:System.Windows.Controls.ContentPresenter>non dispone di una proprietà denominata `HorizontalContentAlignment`, ma <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> può essere associata a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Quando si associa al modello una proprietà, accertarsi che le proprietà di origine e destinazione siano dello stesso tipo.  
  
 La <xref:System.Windows.Controls.Control> classe definisce diverse proprietà che devono essere utilizzate dal modello di controllo per avere un effetto sul controllo quando vengono impostate. La modalità di utilizzo della proprietà dipende dalla proprietà. <xref:System.Windows.Controls.ControlTemplate> È <xref:System.Windows.Controls.ControlTemplate> necessario utilizzare la proprietà in uno dei modi seguenti:  
  
- Un elemento nel <xref:System.Windows.Controls.ControlTemplate> modello viene associato alla proprietà.  
  
- Un elemento in <xref:System.Windows.Controls.ControlTemplate> eredita la proprietà da un elemento padre <xref:System.Windows.FrameworkElement>.  
  
 Nella tabella seguente sono elencate le proprietà visive ereditate da un <xref:System.Windows.Controls.Control> controllo dalla classe. Indica anche se il modello del controllo predefinito di un controllo usa il valore della proprietà ereditato o se deve essere associato al modello.  
  
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
  
 La tabella elenca solo le proprietà visive ereditate <xref:System.Windows.Controls.Control> dalla classe. Oltre alle proprietà elencate nella tabella, un controllo può ereditare anche le <xref:System.Windows.FrameworkElement.DataContext%2A>proprietà, <xref:System.Windows.FrameworkElement.Language%2A>e <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> dall'elemento del framework padre.  
  
 Inoltre, se l' <xref:System.Windows.Controls.ContentPresenter> oggetto si trova <xref:System.Windows.Controls.ControlTemplate> nell'oggetto <xref:System.Windows.Controls.ContentControl>di un <xref:System.Windows.Controls.ContentPresenter> oggetto, l'oggetto verrà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> associato <xref:System.Windows.Controls.ContentControl.Content%2A> automaticamente alle proprietà e. Analogamente, <xref:System.Windows.Controls.ItemsPresenter> un oggetto che si <xref:System.Windows.Controls.ControlTemplate> trova in <xref:System.Windows.Controls.ItemsControl> di un oggetto verrà associato <xref:System.Windows.Controls.ItemsControl.Items%2A> automaticamente <xref:System.Windows.Controls.ItemsPresenter> alle proprietà e.  
  
 Nell'esempio seguente vengono creati due pulsanti che utilizzano <xref:System.Windows.Controls.ControlTemplate> l'oggetto definito nell'esempio precedente. Nell'esempio vengono impostate <xref:System.Windows.Controls.Control.Background%2A>le <xref:System.Windows.Controls.Control.Foreground%2A>proprietà, <xref:System.Windows.Controls.Control.FontSize%2A> e per ogni pulsante. L'impostazione <xref:System.Windows.Controls.Control.Background%2A> della proprietà ha effetto perché è associato <xref:System.Windows.Controls.ControlTemplate>a un modello in. Anche se le <xref:System.Windows.Controls.Control.Foreground%2A> proprietà <xref:System.Windows.Controls.Control.FontSize%2A> e non sono associate al modello, l'impostazione di tali proprietà ha effetto perché i relativi valori vengono ereditati.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Nell'esempio precedente viene generato un output simile alla figura seguente.  
  
 ![Due pulsanti, uno blu e uno viola.](./media/ndp-buttontwo.png "NDP_ButtonTwo")  
Due pulsanti con diversi colori di sfondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Modifica dell'aspetto di un controllo in base allo stato  
 La differenza tra un pulsante con l'aspetto predefinito e il pulsante dell'esempio precedente è che il pulsante predefinito cambia leggermente in relazione allo stato. Ad esempio, l'aspetto del pulsante predefinito cambia quando viene premuto o quando il puntatore del mouse viene spostato sul pulsante. <xref:System.Windows.Controls.ControlTemplate> Sebbene non modifichi la funzionalità di un controllo, modifica il comportamento visivo del controllo. Il comportamento visivo descrive l'aspetto del controllo quando è in un determinato stato. Per comprendere la differenza tra la funzionalità e il comportamento visivo di un controllo, si consideri l'esempio del pulsante. La funzionalità del pulsante consiste nel generare l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento quando viene fatto clic, ma il comportamento visivo del pulsante consiste nel modificarne l'aspetto quando viene puntato o premuto.  
  
 Gli oggetti <xref:System.Windows.VisualState> vengono usati per specificare l'aspetto di un controllo quando si trova in un determinato stato. Un <xref:System.Windows.VisualState> oggetto contiene <xref:System.Windows.Media.Animation.Storyboard> un oggetto che modifica l'aspetto degli <xref:System.Windows.Controls.ControlTemplate>elementi presenti in. Non è necessario scrivere codice per eseguire questa operazione perché la logica del controllo cambia stato usando <xref:System.Windows.VisualStateManager>. Quando il controllo entra nello stato specificato dalla <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Media.Animation.Storyboard> , inizia. Quando il controllo esce dallo stato, <xref:System.Windows.Media.Animation.Storyboard> viene arrestato.  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.VisualState> l'oggetto che modifica l'aspetto <xref:System.Windows.Controls.Button> di un oggetto quando il puntatore del mouse viene spostato su di esso. Il <xref:System.Windows.Media.Animation.Storyboard> colore del bordo del pulsante viene modificato modificando il colore `BorderBrush`di. Se si <xref:System.Windows.Controls.ControlTemplate> fa riferimento all'esempio all'inizio di questo argomento, si ricorderà che `BorderBrush` è il nome dell'oggetto <xref:System.Windows.Media.SolidColorBrush> assegnato a <xref:System.Windows.Controls.Border.Background%2A> del <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Il controllo è responsabile della definizione degli stati come parte del relativo contratto e questo aspetto verrà, esaminato in dettaglio nella sezione [Personalizzazione di altri controlli sulla base del contratto di controllo](#customizing_other_controls_by_understanding_the_control_contract) più avanti in questo argomento. Nella tabella seguente sono elencati gli stati specificati per <xref:System.Windows.Controls.Button>.  
  
|Nome VisualState|Nome VisualStateGroup|DESCRIZIONE|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|Disabilitata|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
  
 `MouseOver` `Normal` `Disabled` `Pressed`Definisce due gruppi di stati: il `CommonStates` gruppo contiene gli Stati,, e. <xref:System.Windows.Controls.Button> Mentre il gruppo `FocusStates` contiene gli stati `Focused` e `Unfocused`. Gli stati nello stesso gruppo si escludono a vicenda. Il controllo è sempre in uno stato specifico per ogni gruppo. Ad esempio, un <xref:System.Windows.Controls.Button> oggetto può avere lo stato attivo anche quando il puntatore del mouse non è posizionato <xref:System.Windows.Controls.Button> su di `Focused` esso, quindi un oggetto `MouseOver`nello stato può `Normal` essere nello stato, `Pressed`o.  
  
 Si aggiungono <xref:System.Windows.VisualState> oggetti <xref:System.Windows.VisualStateGroup> a oggetti. Si aggiungono <xref:System.Windows.VisualStateGroup> oggetti <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> alla proprietà associata. Nell'esempio seguente vengono definiti <xref:System.Windows.VisualState> gli oggetti per `Normal`gli `MouseOver`Stati, `Pressed` `CommonStates` e, che sono tutti inclusi nel gruppo. Il <xref:System.Windows.VisualState.Name%2A> di ogni <xref:System.Windows.VisualState> corrisponde al nome nella tabella precedente. Lo stato `Disabled` e gli stati del gruppo `FocusStates` sono stati omessi per brevità, ma sono inclusi nell'esempio completo alla fine di questo argomento.  
  
> [!NOTE]
> Assicurarsi di impostare la <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà associata nella radice <xref:System.Windows.FrameworkElement> di <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Nell'esempio precedente viene generato un output simile alle figure seguenti.  
  
 ![Un pulsante con un modello di controllo personalizzato.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Pulsante che usa un modello del controllo personalizzato nello stato normale  
  
 ![Un pulsante con un bordo rosso.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Pulsante che usa un modello del controllo personalizzato nello stato di passaggio del mouse  
  
 ![Il bordo è trasparente in un pulsante premuto.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Pulsante che usa un modello del controllo personalizzato nello stato premuto  
  
 Per trovare gli stati visivi dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Impostazione del comportamento di un controllo nella transizione tra stati  
 Nell'esempio precedente, l'aspetto del pulsante cambia anche quando viene selezionato dall'utente, ma se non viene premuto per almeno un secondo, l'utente non vede l'effetto. Per impostazione predefinita, l'animazione impiega un secondo per attivarsi. Poiché gli utenti possono fare clic e rilasciare un pulsante in tempi molto inferiori, il feedback visivo non sarà efficace se si lascia lo <xref:System.Windows.Controls.ControlTemplate> stato predefinito.  
  
 È possibile specificare la quantità di tempo necessaria per eseguire un'animazione per la transizione graduale di un controllo da uno stato a un altro mediante <xref:System.Windows.VisualTransition> l'aggiunta di <xref:System.Windows.Controls.ControlTemplate>oggetti all'oggetto. Quando si crea un <xref:System.Windows.VisualTransition>oggetto, è necessario specificare uno o più degli elementi seguenti:  
  
- Il tempo necessario affinché si verifichi una transizione tra stati.  
  
- Le modifiche aggiuntive nell'aspetto del controllo che si verificano al momento della transizione.  
  
- A cui viene <xref:System.Windows.VisualTransition> applicato l'oggetto.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Impostazione della durata di una transizione  
 È possibile specificare il tempo necessario per una transizione impostando <xref:System.Windows.VisualTransition.GeneratedDuration%2A> la proprietà. Nell'esempio precedente viene specificato <xref:System.Windows.VisualState> un valore che specifica che il bordo del pulsante diventa trasparente quando si preme il pulsante, ma l'animazione impiega troppo tempo per essere percettibile se il pulsante viene rapidamente premuto e rilasciato. È possibile usare un <xref:System.Windows.VisualTransition> oggetto per specificare la quantità di tempo impiegato dal controllo per passare allo stato premuto. Nell'esempio seguente viene specificato che il controllo impiega un centesimo di secondo per passare allo stato di pressione.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Impostazione delle modifiche all'aspetto del controllo durante una transizione  
 <xref:System.Windows.VisualTransition> Contiene un<xref:System.Windows.Media.Animation.Storyboard> che inizia quando il controllo esegue la transizione tra gli Stati. Ad esempio, è possibile specificare che una determinata animazione si verifica quando il controllo passa dallo stato `MouseOver` allo stato `Normal`. Nell'esempio seguente viene creato <xref:System.Windows.VisualTransition> un oggetto che specifica che quando l'utente sposta il puntatore del mouse fuori dal pulsante, il bordo del pulsante diventa blu, quindi in giallo, quindi in nero in 1,5 secondi.  
  
 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Impostazione dei casi in cui applicare un oggetto VisualTransition  
 Un <xref:System.Windows.VisualTransition> oggetto può essere limitato solo a determinati Stati oppure può essere applicato ogni volta che il controllo passa da uno stato all'altro. Nell'esempio <xref:System.Windows.VisualTransition> precedente, viene applicato quando il controllo passa `MouseOver` dallo stato allo `Normal` stato <xref:System.Windows.VisualTransition> ; nell'esempio precedente, viene applicato quando il controllo passa `Pressed` allo stato. Si limita quando viene <xref:System.Windows.VisualTransition> applicato un oggetto impostando <xref:System.Windows.VisualTransition.To%2A> le <xref:System.Windows.VisualTransition.From%2A> proprietà e. Nella tabella seguente vengono descritti i livelli di restrizione, in modo decrescente dal più restrittivo.  
  
|Tipo di restrizione|Valore di From|Valore di To|  
|-------------------------|-------------------|-----------------|  
|Da uno stato specifico un altro stato specifico|Nome di un oggetto<xref:System.Windows.VisualState>|Nome di un oggetto<xref:System.Windows.VisualState>|  
|Da qualsiasi stato a uno stato specifico|Non impostato|Nome di un oggetto<xref:System.Windows.VisualState>|  
|Da uno stato specifico a qualsiasi stato|Nome di un oggetto<xref:System.Windows.VisualState>|Non impostato|  
|Da qualsiasi stato a qualsiasi altro stato|Non impostato|Non impostato|  
  
 È possibile disporre di <xref:System.Windows.VisualTransition> più oggetti in <xref:System.Windows.VisualStateGroup> un che fanno riferimento allo stesso stato, ma verranno utilizzati nell'ordine specificato dalla tabella precedente. Nell'esempio seguente sono presenti due <xref:System.Windows.VisualTransition> oggetti. Quando il controllo passa dallo `Pressed` stato `MouseOver` allo stato <xref:System.Windows.VisualTransition.From%2A> , viene usato l'oggetto <xref:System.Windows.VisualTransition> con l'oggetto e <xref:System.Windows.VisualTransition.To%2A> il set. Quando il controllo passa da uno stato diverso da `Pressed` allo stato `MouseOver`, viene usato l'altro stato.  
  
 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualStateGroup.Transitions%2A> <xref:System.Windows.VisualTransition> <xref:System.Windows.VisualState> Dispone di una proprietà che contiene gli<xref:System.Windows.VisualStateGroup>oggetti che si applicano agli oggetti in. <xref:System.Windows.VisualStateGroup> L' <xref:System.Windows.Controls.ControlTemplate> autore può <xref:System.Windows.VisualTransition> includere le proprie esigenze. Tuttavia, se le <xref:System.Windows.VisualTransition.To%2A> proprietà <xref:System.Windows.VisualTransition.From%2A> e sono impostate su nomi di stato <xref:System.Windows.VisualStateGroup>che <xref:System.Windows.VisualTransition> non sono in, viene ignorato.  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.VisualStateGroup> l'oggetto `CommonStates`per l'oggetto. Nell'esempio viene definito <xref:System.Windows.VisualTransition> un oggetto per ognuna delle transizioni seguenti del pulsante.  
  
- Allo stato `Pressed`.  
  
- Allo stato `MouseOver`.  
  
- Dallo stato `Pressed` allo stato `MouseOver`.  
  
- Dallo stato `MouseOver` allo stato `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalizzazione di altri controlli sulla base del contratto di controllo  
 Un controllo che usa un <xref:System.Windows.Controls.ControlTemplate> oggetto per specificare la relativa struttura visiva ( <xref:System.Windows.FrameworkElement> usando oggetti) e il comportamento visivo ( <xref:System.Windows.VisualState> usando oggetti) usa il modello di controllo Parts. Molti dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usano questo modello. Le parti di cui <xref:System.Windows.Controls.ControlTemplate> un autore deve essere a conoscenza vengono comunicate tramite il contratto di controllo. Quando si conoscono le parti di un contratto di controllo, è possibile personalizzare l'aspetto di qualsiasi controllo che utilizza il modello di controllo part.  
  
 Un contratto di controllo include tre elementi:  
  
- Gli elementi visivi usati dalla logica del controllo.  
  
- Gli stati del controllo e il gruppo a cui appartiene ogni stato.  
  
- Le proprietà pubbliche che influiscono visivamente sul controllo.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementi visivi nel contratto di controllo  
 A volte la logica di un controllo interagisce <xref:System.Windows.FrameworkElement> con un che si <xref:System.Windows.Controls.ControlTemplate>trova in. Ad esempio, il controllo può gestire un evento di uno dei relativi elementi. Quando un controllo prevede di trovare un particolare <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>in, deve inviare tali informazioni all' <xref:System.Windows.Controls.ControlTemplate> autore. Il controllo Usa <xref:System.Windows.TemplatePartAttribute> per indicare il tipo di elemento previsto e il nome dell'elemento che deve essere. Non dispone <xref:System.Windows.FrameworkElement> di parti nel relativo contratto di controllo, ma anche di altri <xref:System.Windows.Controls.ComboBox>controlli, ad esempio,. <xref:System.Windows.Controls.Button>  
  
 Nell'esempio seguente vengono illustrati <xref:System.Windows.TemplatePartAttribute> gli oggetti specificati <xref:System.Windows.Controls.ComboBox> nella classe. La logica di <xref:System.Windows.Controls.ComboBox> prevede di trovare un oggetto <xref:System.Windows.Controls.TextBox> denominato `PART_EditableTextBox` e un <xref:System.Windows.Controls.Primitives.Popup> oggetto `PART_Popup` denominato nel <xref:System.Windows.Controls.ControlTemplate>relativo.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.ControlTemplate> oggetto semplificato per l' <xref:System.Windows.Controls.ComboBox> oggetto che include gli elementi specificati <xref:System.Windows.TemplatePartAttribute> <xref:System.Windows.Controls.ComboBox> dagli oggetti sulla classe.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Stati nel contratto di controllo  
 Anche gli stati di un controllo fanno parte del contratto di controllo. Nell'esempio di creazione di <xref:System.Windows.Controls.ControlTemplate> un oggetto <xref:System.Windows.Controls.Button> per un oggetto viene illustrato come specificare l' <xref:System.Windows.Controls.Button> aspetto di un oggetto a seconda degli Stati. Si crea un <xref:System.Windows.VisualState> per ogni stato specificato e si inseriscono tutti <xref:System.Windows.VisualState> gli <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> oggetti che <xref:System.Windows.VisualStateGroup>condividono un oggetto in un oggetto, come descritto in [modifica dell'aspetto di un controllo a seconda dello stato](#changing_the_appearance_of_a_control_depending_on_its_state) precedente in questo argomento. I <xref:System.Windows.TemplateVisualStateAttribute>controlli di terze parti devono specificare gli Stati tramite, che consente agli strumenti di progettazione, ad esempio Expression Blend, di esporre gli Stati del controllo per la creazione di modelli di controllo.  
  
 Per trovare il contratto di controllo dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Proprietà nel contratto di controllo  
 Anche le proprietà pubbliche che influiscono visivamente sul controllo sono incluse nel contratto di controllo. È possibile impostare queste proprietà per modificare l'aspetto del controllo senza creare un nuovo <xref:System.Windows.Controls.ControlTemplate>oggetto. È anche possibile usare l'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) per associare le proprietà degli elementi presenti in <xref:System.Windows.Controls.ControlTemplate> alle proprietà pubbliche definite da. <xref:System.Windows.Controls.Button>  
  
 L'esempio seguente illustra il contratto di controllo per il pulsante.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Quando si crea <xref:System.Windows.Controls.ControlTemplate>un oggetto, è spesso più semplice iniziare con un <xref:System.Windows.Controls.ControlTemplate> oggetto esistente e apportare modifiche. Per modificare una esistente <xref:System.Windows.Controls.ControlTemplate>, è possibile eseguire una delle operazioni seguenti:  
  
- Utilizzare una finestra di progettazione, ad esempio Expression Blend, che fornisce un'interfaccia utente grafica per la creazione di modelli del controllo. Per altre informazioni, vedere [Applicazione di stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
- Ottenere il valore <xref:System.Windows.Controls.ControlTemplate> predefinito e modificarlo. Per trovare i modelli del controllo predefiniti che sono inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Temi WPF predefiniti](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Esempio completo  
 Nell'esempio seguente viene illustrato il <xref:System.Windows.Controls.Button> completamento <xref:System.Windows.Controls.ControlTemplate> descritto in questo argomento.  
  
 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
