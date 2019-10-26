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
ms.openlocfilehash: 0c79ba3dd42f2e65eb241409946e921577ced5f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920058"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate
<a name="introduction"></a>Un <xref:System.Windows.Controls.ControlTemplate> specifica la struttura visiva e il comportamento visivo di un controllo. È possibile personalizzare l'aspetto di un controllo assegnando un nuovo <xref:System.Windows.Controls.ControlTemplate>. Quando si crea una <xref:System.Windows.Controls.ControlTemplate>, si sostituisce l'aspetto di un controllo esistente senza modificarne la funzionalità. È ad esempio possibile fare in modo che i pulsanti all'interno dell'applicazione si trovino invece della forma quadrata predefinita, ma il pulsante genera comunque l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.

 In questo argomento vengono illustrate le varie parti di un <xref:System.Windows.Controls.ControlTemplate>, viene illustrata la creazione di una semplice <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>e viene illustrato come comprendere il contratto di controllo di un controllo in modo che sia possibile personalizzarne l'aspetto. Poiché si crea un <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile modificare l'aspetto di un controllo senza scrivere alcun codice. È anche possibile usare una finestra di progettazione, ad esempio Blend per Visual Studio, per creare modelli di controlli personalizzati. In questo argomento vengono illustrati alcuni esempi nell'[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che personalizzano l'aspetto di un <xref:System.Windows.Controls.Button> e viene elencato l'esempio completo alla fine dell'argomento. Per ulteriori informazioni sull'utilizzo di Blend per Visual Studio, vedere applicazione di [stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).

 Le illustrazioni seguenti mostrano un <xref:System.Windows.Controls.Button> che usa il <xref:System.Windows.Controls.ControlTemplate> creato in questo argomento.

 ![Pulsante con un modello del controllo personalizzato.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Pulsante che usa un modello del controllo personalizzato

 ![Pulsante con un bordo rosso.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Pulsante che usa un modello del controllo personalizzato e su cui è posizionato il puntatore del mouse

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites
 Questo argomento si basa sul presupposto che si sappiano creare e usare i controlli e gli stili come descritto in [Controlli](index.md). I concetti illustrati in questo argomento si applicano agli elementi che ereditano dalla classe <xref:System.Windows.Controls.Control>, ad eccezione del <xref:System.Windows.Controls.UserControl>. Non è possibile applicare una <xref:System.Windows.Controls.ControlTemplate> a un <xref:System.Windows.Controls.UserControl>.

<a name="when_you_should_create_a_controltemplate"></a>
## <a name="when-you-should-create-a-controltemplate"></a>Quando creare un oggetto ControlTemplate
 I controlli hanno molte proprietà, ad esempio <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>e <xref:System.Windows.Controls.Control.FontFamily%2A>, che è possibile impostare per specificare diversi aspetti dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate. Ad esempio, è possibile impostare la proprietà <xref:System.Windows.Controls.Control.Foreground%2A> su Blue e <xref:System.Windows.Controls.Control.FontStyle%2A> su Italic in un <xref:System.Windows.Controls.CheckBox>.

 Senza la possibilità di creare una nuova <xref:System.Windows.Controls.ControlTemplate> per i controlli, tutti i controlli in ogni applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hanno lo stesso aspetto generale, che limita la possibilità di creare un'applicazione con un aspetto personalizzato. Per impostazione predefinita, ogni <xref:System.Windows.Controls.CheckBox> presenta caratteristiche simili. Ad esempio, il contenuto del <xref:System.Windows.Controls.CheckBox> è sempre a destra dell'indicatore di selezione e il segno di spunta viene sempre usato per indicare che è selezionata l'<xref:System.Windows.Controls.CheckBox>.

 Viene creato un <xref:System.Windows.Controls.ControlTemplate> quando si desidera personalizzare l'aspetto del controllo oltre a quello che l'impostazione delle altre proprietà del controllo. Nell'esempio di <xref:System.Windows.Controls.CheckBox>si supponga che il contenuto della casella di controllo sia sopra l'indicatore di selezione e che si desideri che la X indichi che la <xref:System.Windows.Controls.CheckBox> è selezionata. Queste modifiche vengono specificate nella <xref:System.Windows.Controls.ControlTemplate> della <xref:System.Windows.Controls.CheckBox>.

 Nella figura seguente viene illustrato un <xref:System.Windows.Controls.CheckBox> che utilizza una <xref:System.Windows.Controls.ControlTemplate>predefinita.

 ![Casella di controllo con il modello del controllo predefinito.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Oggetto CheckBox che usa il modello del controllo predefinito

 Nella figura seguente viene illustrato un <xref:System.Windows.Controls.CheckBox> che utilizza una <xref:System.Windows.Controls.ControlTemplate> personalizzata per inserire il contenuto del <xref:System.Windows.Controls.CheckBox> sopra l'indicatore di selezione e visualizza una X quando viene selezionata la <xref:System.Windows.Controls.CheckBox>.

 ![Casella di controllo con un modello del controllo personalizzato.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Oggetto CheckBox che usa un modello del controllo personalizzato

 Il <xref:System.Windows.Controls.ControlTemplate> per l'<xref:System.Windows.Controls.CheckBox> in questo esempio è relativamente complesso, quindi in questo argomento viene utilizzato un esempio più semplice di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button>.

<a name="changing_the_visual_structure_of_a_control"></a>
## <a name="changing-the-visual-structure-of-a-control"></a>Modifica della struttura visiva di un controllo
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un controllo è spesso un oggetto <xref:System.Windows.FrameworkElement> composito. Quando si crea una <xref:System.Windows.Controls.ControlTemplate>, si combinano <xref:System.Windows.FrameworkElement> oggetti per compilare un unico controllo. Un <xref:System.Windows.Controls.ControlTemplate> deve avere un solo <xref:System.Windows.FrameworkElement> come elemento radice. L'elemento radice contiene in genere altri oggetti <xref:System.Windows.FrameworkElement>. La combinazione degli oggetti costituisce la struttura visiva del controllo.

 Nell'esempio seguente viene creata una <xref:System.Windows.Controls.ControlTemplate> personalizzata per la <xref:System.Windows.Controls.Button>. Il <xref:System.Windows.Controls.ControlTemplate> crea la struttura visiva del <xref:System.Windows.Controls.Button>. In questo esempio, l'aspetto del pulsante non cambia quando si sposta il puntatore del mouse o si fa clic su di esso. La procedura per modificare l'aspetto del pulsante quando è in uno stato diverso viene descritta più avanti in questo argomento.

 In questo esempio, la struttura visiva è costituita dalle parti seguenti:

- <xref:System.Windows.Controls.Border> `RootElement` denominata che funge da <xref:System.Windows.FrameworkElement>radice del modello.

- <xref:System.Windows.Controls.Grid> figlio di `RootElement`.

- <xref:System.Windows.Controls.ContentPresenter> che Visualizza il contenuto del pulsante. Il <xref:System.Windows.Controls.ContentPresenter> consente la visualizzazione di qualsiasi tipo di oggetto.

 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]

### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Mantenimento della funzionalità delle proprietà di un controllo tramite TemplateBinding
 Quando si crea una nuova <xref:System.Windows.Controls.ControlTemplate>, è comunque possibile usare le proprietà pubbliche per modificare l'aspetto del controllo. L'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) associa una proprietà di un elemento che si trova nel <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica definita dal controllo. Quando si usa [TemplateBinding](../advanced/templatebinding-markup-extension.md), si consente alle proprietà del controllo di fungere da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../advanced/templatebinding-markup-extension.md).

 Nell'esempio seguente viene ripetuta la parte dell'esempio precedente che usa l'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) per associare le proprietà degli elementi presenti nel <xref:System.Windows.Controls.ControlTemplate> alle proprietà pubbliche definite dal pulsante.

 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]

 In questo esempio, il <xref:System.Windows.Controls.Grid> ha il modello di proprietà <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> associato <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Poiché <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> è associato a un modello, è possibile creare più pulsanti che utilizzano lo stesso <xref:System.Windows.Controls.ControlTemplate> e impostare il <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> su valori diversi su ciascun pulsante. Se <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> non è associato a una proprietà di un elemento nel <xref:System.Windows.Controls.ControlTemplate>, l'impostazione del <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> di un pulsante non avrà alcun effetto sull'aspetto del pulsante.

 Tenere presente che i nomi delle due proprietà non devono necessariamente essere identici. Nell'esempio precedente, la proprietà <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> del <xref:System.Windows.Controls.Button> è associata al modello alla proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> della <xref:System.Windows.Controls.ContentPresenter>. In questo modo il contenuto del pulsante può essere posizionato orizzontalmente. <xref:System.Windows.Controls.ContentPresenter> non dispone di una proprietà denominata `HorizontalContentAlignment`, ma <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> può essere associata a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Quando si associa al modello una proprietà, accertarsi che le proprietà di origine e destinazione siano dello stesso tipo.

 La classe <xref:System.Windows.Controls.Control> definisce diverse proprietà che devono essere utilizzate dal modello di controllo per influire sul controllo quando vengono impostate. Il modo in cui il <xref:System.Windows.Controls.ControlTemplate> usa la proprietà dipende dalla proprietà. Il <xref:System.Windows.Controls.ControlTemplate> deve utilizzare la proprietà in uno dei modi seguenti:

- Un elemento nel modello di <xref:System.Windows.Controls.ControlTemplate> viene associato alla proprietà.

- Un elemento del <xref:System.Windows.Controls.ControlTemplate> eredita la proprietà da un <xref:System.Windows.FrameworkElement>padre.

 Nella tabella seguente sono elencate le proprietà visive ereditate da un controllo dalla classe <xref:System.Windows.Controls.Control>. Indica anche se il modello del controllo predefinito di un controllo usa il valore della proprietà ereditato o se deve essere associato al modello.

|proprietà|Metodo di utilizzo|
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

 La tabella elenca solo le proprietà visive ereditate dalla classe <xref:System.Windows.Controls.Control>. Oltre alle proprietà elencate nella tabella, un controllo può ereditare anche le proprietà <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>e <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> dall'elemento del framework padre.

 Inoltre, se il <xref:System.Windows.Controls.ContentPresenter> si trova nella <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ContentControl>, il <xref:System.Windows.Controls.ContentPresenter> verrà associato automaticamente alle proprietà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A>. Analogamente, un <xref:System.Windows.Controls.ItemsPresenter> che si trova nella <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ItemsControl> verrà automaticamente associato alle proprietà <xref:System.Windows.Controls.ItemsControl.Items%2A> e <xref:System.Windows.Controls.ItemsPresenter>.

 Nell'esempio seguente vengono creati due pulsanti che utilizzano il <xref:System.Windows.Controls.ControlTemplate> definito nell'esempio precedente. Nell'esempio vengono impostate le proprietà <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>e <xref:System.Windows.Controls.Control.FontSize%2A> su ciascun pulsante. L'impostazione della proprietà <xref:System.Windows.Controls.Control.Background%2A> ha effetto perché è associato a un modello nel <xref:System.Windows.Controls.ControlTemplate>. Anche se le proprietà <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.FontSize%2A> non sono associate al modello, l'impostazione ha effetto perché i relativi valori vengono ereditati.

 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]

 Nell'esempio precedente viene generato un output simile alla figura seguente.

 ![Due pulsanti, uno blu e uno viola.](./media/ndp-buttontwo.png "NDP_ButtonTwo")
Due pulsanti con diversi colori di sfondo

<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Modifica dell'aspetto di un controllo in base allo stato
 La differenza tra un pulsante con l'aspetto predefinito e il pulsante dell'esempio precedente è che il pulsante predefinito cambia leggermente in relazione allo stato. Ad esempio, l'aspetto del pulsante predefinito cambia quando viene premuto o quando il puntatore del mouse viene spostato sul pulsante. Sebbene il <xref:System.Windows.Controls.ControlTemplate> non modifichi la funzionalità di un controllo, modifica il comportamento visivo del controllo. Il comportamento visivo descrive l'aspetto del controllo quando è in un determinato stato. Per comprendere la differenza tra la funzionalità e il comportamento visivo di un controllo, si consideri l'esempio del pulsante. La funzionalità del pulsante consiste nel generare l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> quando viene fatto clic, ma il comportamento visivo del pulsante è modificarne l'aspetto quando viene puntato o premuto.

 Si utilizzano oggetti <xref:System.Windows.VisualState> per specificare l'aspetto di un controllo quando si trova in un determinato stato. Un <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> che modifica l'aspetto degli elementi presenti nell'<xref:System.Windows.Controls.ControlTemplate>. Non è necessario scrivere codice per eseguire questa operazione perché la logica del controllo cambia stato usando il <xref:System.Windows.VisualStateManager>. Quando il controllo entra nello stato specificato dalla proprietà <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType>, inizia l'<xref:System.Windows.Media.Animation.Storyboard>. Quando il controllo esce dallo stato, il <xref:System.Windows.Media.Animation.Storyboard> si arresta.

 Nell'esempio seguente viene illustrata la <xref:System.Windows.VisualState> che modifica l'aspetto di un <xref:System.Windows.Controls.Button> quando il puntatore del mouse è posizionato su di esso. Il <xref:System.Windows.Media.Animation.Storyboard> modifica il colore del bordo del pulsante modificando il colore del `BorderBrush`. Se si fa riferimento all'esempio <xref:System.Windows.Controls.ControlTemplate> all'inizio di questo argomento, si ricorderà che `BorderBrush` è il nome del <xref:System.Windows.Media.SolidColorBrush> assegnato alla <xref:System.Windows.Controls.Border.Background%2A> del <xref:System.Windows.Controls.Border>.

 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]

 Il controllo è responsabile della definizione degli stati come parte del relativo contratto e questo aspetto verrà, esaminato in dettaglio nella sezione [Personalizzazione di altri controlli sulla base del contratto di controllo](#customizing_other_controls_by_understanding_the_control_contract) più avanti in questo argomento. Nella tabella seguente sono elencati gli stati specificati per il <xref:System.Windows.Controls.Button>.

|Nome VisualState|Nome VisualStateGroup|Descrizione|
|----------------------|---------------------------|-----------------|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Premuto|CommonStates|Il controllo è premuto.|
|Disabilitato|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|

 Il <xref:System.Windows.Controls.Button> definisce due gruppi di stati: il gruppo di `CommonStates` contiene gli Stati `Normal`, `MouseOver`, `Pressed`e `Disabled`. Mentre il gruppo `FocusStates` contiene gli stati `Focused` e `Unfocused`. Gli stati nello stesso gruppo si escludono a vicenda. Il controllo è sempre in uno stato specifico per ogni gruppo. Ad esempio, un <xref:System.Windows.Controls.Button> può avere lo stato attivo anche quando il puntatore del mouse non è posizionato su di esso, quindi una <xref:System.Windows.Controls.Button> nello stato `Focused` può essere nello stato `MouseOver`, `Pressed`o `Normal`.

 Si aggiungono oggetti <xref:System.Windows.VisualState> agli oggetti <xref:System.Windows.VisualStateGroup>. Si aggiungono oggetti <xref:System.Windows.VisualStateGroup> alla proprietà <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> associata. Nell'esempio seguente vengono definiti gli oggetti <xref:System.Windows.VisualState> per gli Stati `Normal`, `MouseOver`e `Pressed`, che sono tutti inclusi nel gruppo di `CommonStates`. Il <xref:System.Windows.VisualState.Name%2A> di ogni <xref:System.Windows.VisualState> corrisponde al nome nella tabella precedente. Lo stato `Disabled` e gli stati del gruppo `FocusStates` sono stati omessi per brevità, ma sono inclusi nell'esempio completo alla fine di questo argomento.

> [!NOTE]
> Assicurarsi di impostare la proprietà <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> associata nella <xref:System.Windows.FrameworkElement> radice della <xref:System.Windows.Controls.ControlTemplate>.

 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]

 Nell'esempio precedente viene generato un output simile alle figure seguenti.

 ![Pulsante con un modello del controllo personalizzato.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Pulsante che usa un modello del controllo personalizzato nello stato normale

 ![Pulsante con un bordo rosso.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Pulsante che usa un modello del controllo personalizzato nello stato di passaggio del mouse

 ![Il bordo è trasparente in un pulsante premuto.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")
Pulsante che usa un modello del controllo personalizzato nello stato premuto

 Per trovare gli stati visivi dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](control-styles-and-templates.md).

<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Impostazione del comportamento di un controllo nella transizione tra stati
 Nell'esempio precedente, l'aspetto del pulsante cambia anche quando viene selezionato dall'utente, ma se non viene premuto per almeno un secondo, l'utente non vede l'effetto. Per impostazione predefinita, l'animazione impiega un secondo per attivarsi. Poiché gli utenti possono fare clic e rilasciare un pulsante in tempi molto inferiori, il feedback visivo non sarà efficace se si lascia il <xref:System.Windows.Controls.ControlTemplate> nello stato predefinito.

 È possibile specificare la quantità di tempo necessaria per eseguire un'animazione per la transizione graduale di un controllo da uno stato a un altro mediante l'aggiunta di oggetti <xref:System.Windows.VisualTransition> al <xref:System.Windows.Controls.ControlTemplate>. Quando si crea una <xref:System.Windows.VisualTransition>, è necessario specificare uno o più degli elementi seguenti:

- Il tempo necessario affinché si verifichi una transizione tra stati.

- Le modifiche aggiuntive nell'aspetto del controllo che si verificano al momento della transizione.

- A quali stati viene applicata la <xref:System.Windows.VisualTransition>.

### <a name="specifying-the-duration-of-a-transition"></a>Impostazione della durata di una transizione
 È possibile specificare il tempo necessario per una transizione impostando la proprietà <xref:System.Windows.VisualTransition.GeneratedDuration%2A>. Nell'esempio precedente è presente un <xref:System.Windows.VisualState> che specifica che il bordo del pulsante diventa trasparente quando si preme il pulsante, ma l'animazione impiega troppo tempo per essere percettibile se il pulsante viene rapidamente premuto e rilasciato. È possibile usare un <xref:System.Windows.VisualTransition> per specificare la quantità di tempo impiegato dal controllo per passare allo stato premuto. Nell'esempio seguente viene specificato che il controllo impiega un centesimo di secondo per passare allo stato di pressione.

 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]

### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Impostazione delle modifiche all'aspetto del controllo durante una transizione
 Il <xref:System.Windows.VisualTransition> contiene una <xref:System.Windows.Media.Animation.Storyboard> che inizia quando il controllo esegue la transizione tra gli Stati. Ad esempio, è possibile specificare che una determinata animazione si verifica quando il controllo passa dallo stato `MouseOver` allo stato `Normal`. Nell'esempio seguente viene creato un <xref:System.Windows.VisualTransition> che specifica che quando l'utente sposta il puntatore del mouse dal pulsante, il bordo del pulsante passa a blu, quindi a giallo, quindi al nero in 1,5 secondi.

 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]

### <a name="specifying-when-a-visualtransition-is-applied"></a>Impostazione dei casi in cui applicare un oggetto VisualTransition
 È possibile limitare l'applicazione di una <xref:System.Windows.VisualTransition> solo a determinati Stati oppure applicarla ogni volta che il controllo passa da uno stato all'altro. Nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicato quando il controllo passa dallo stato di `MouseOver` allo stato `Normal`; Nell'esempio precedente, il <xref:System.Windows.VisualTransition> viene applicato quando il controllo entra nello stato di `Pressed`. Si limita quando viene applicata una <xref:System.Windows.VisualTransition> impostando le proprietà <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A>. Nella tabella seguente vengono descritti i livelli di restrizione, in modo decrescente dal più restrittivo.

|Tipo di restrizione|Valore di From|Valore di To|
|-------------------------|-------------------|-----------------|
|Da uno stato specifico un altro stato specifico|Nome di un <xref:System.Windows.VisualState>|Nome di un <xref:System.Windows.VisualState>|
|Da qualsiasi stato a uno stato specifico|Non impostato|Nome di un <xref:System.Windows.VisualState>|
|Da uno stato specifico a qualsiasi stato|Nome di un <xref:System.Windows.VisualState>|Non impostato|
|Da qualsiasi stato a qualsiasi altro stato|Non impostato|Non impostato|

 È possibile disporre di più oggetti <xref:System.Windows.VisualTransition> in un <xref:System.Windows.VisualStateGroup> che fanno riferimento allo stesso stato, ma verranno utilizzati nell'ordine specificato dalla tabella precedente. Nell'esempio seguente sono presenti due oggetti <xref:System.Windows.VisualTransition>. Quando il controllo passa dallo stato `Pressed` allo stato di `MouseOver`, viene utilizzato il <xref:System.Windows.VisualTransition> con <xref:System.Windows.VisualTransition.From%2A> e set di <xref:System.Windows.VisualTransition.To%2A>. Quando il controllo passa da uno stato diverso da `Pressed` allo stato `MouseOver`, viene usato l'altro stato.

 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]

 Il <xref:System.Windows.VisualStateGroup> dispone di una proprietà <xref:System.Windows.VisualStateGroup.Transitions%2A> che contiene gli oggetti <xref:System.Windows.VisualTransition> che si applicano agli oggetti <xref:System.Windows.VisualState> nel <xref:System.Windows.VisualStateGroup>. In qualità di autore del <xref:System.Windows.Controls.ControlTemplate>, è possibile includere tutti i <xref:System.Windows.VisualTransition> desiderati. Tuttavia, se le proprietà <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> sono impostate su nomi di stato che non sono presenti nel <xref:System.Windows.VisualStateGroup>, il <xref:System.Windows.VisualTransition> viene ignorato.

 Nell'esempio seguente viene illustrata la <xref:System.Windows.VisualStateGroup> per l'`CommonStates`. Nell'esempio viene definito un <xref:System.Windows.VisualTransition> per ognuna delle transizioni seguenti del pulsante.

- Allo stato `Pressed`.

- Allo stato `MouseOver`.

- Dallo stato `Pressed` allo stato `MouseOver`.

- Dallo stato `MouseOver` allo stato `Normal`.

 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]

<a name="customizing_other_controls_by_understanding_the_control_contract"></a>
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalizzazione di altri controlli sulla base del contratto di controllo
 Un controllo che usa un <xref:System.Windows.Controls.ControlTemplate> per specificare la struttura visiva (usando oggetti <xref:System.Windows.FrameworkElement>) e il comportamento visivo (usando oggetti <xref:System.Windows.VisualState>) usa il modello di controllo Parts. Molti dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usano questo modello. Le parti di cui un autore <xref:System.Windows.Controls.ControlTemplate> deve essere a conoscenza vengono comunicate tramite il contratto di controllo. Quando si conoscono le parti di un contratto di controllo, è possibile personalizzare l'aspetto di qualsiasi controllo che utilizza il modello di controllo part.

 Un contratto di controllo include tre elementi:

- Gli elementi visivi usati dalla logica del controllo.

- Gli stati del controllo e il gruppo a cui appartiene ogni stato.

- Le proprietà pubbliche che influiscono visivamente sul controllo.

### <a name="visual-elements-in-the-control-contract"></a>Elementi visivi nel contratto di controllo
 A volte la logica di un controllo interagisce con un <xref:System.Windows.FrameworkElement> che si trova nel <xref:System.Windows.Controls.ControlTemplate>. Ad esempio, il controllo può gestire un evento di uno dei relativi elementi. Quando un controllo prevede di trovare un particolare <xref:System.Windows.FrameworkElement> nel <xref:System.Windows.Controls.ControlTemplate>, deve inviare tali informazioni all'autore <xref:System.Windows.Controls.ControlTemplate>. Il controllo Usa il <xref:System.Windows.TemplatePartAttribute> per indicare il tipo di elemento previsto e il nome dell'elemento. Il <xref:System.Windows.Controls.Button> non dispone di <xref:System.Windows.FrameworkElement> parti nel relativo contratto di controllo, ma anche di altri controlli, ad esempio <xref:System.Windows.Controls.ComboBox>.

 Nell'esempio seguente vengono illustrati gli oggetti <xref:System.Windows.TemplatePartAttribute> specificati nella classe <xref:System.Windows.Controls.ComboBox>. La logica di <xref:System.Windows.Controls.ComboBox> prevede di trovare una <xref:System.Windows.Controls.TextBox> denominata `PART_EditableTextBox` e una <xref:System.Windows.Controls.Primitives.Popup> denominata `PART_Popup` nell'<xref:System.Windows.Controls.ControlTemplate>.

 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]

 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.ControlTemplate> semplificato per la <xref:System.Windows.Controls.ComboBox> che include gli elementi specificati dagli oggetti <xref:System.Windows.TemplatePartAttribute> della classe <xref:System.Windows.Controls.ComboBox>.

 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]

### <a name="states-in-the-control-contract"></a>Stati nel contratto di controllo
 Anche gli stati di un controllo fanno parte del contratto di controllo. Nell'esempio di creazione di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Button> viene illustrato come specificare l'aspetto di un <xref:System.Windows.Controls.Button> a seconda degli Stati. Si crea un <xref:System.Windows.VisualState> per ogni stato specificato e si inseriscono tutti gli oggetti <xref:System.Windows.VisualState> che condividono un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> in un <xref:System.Windows.VisualStateGroup>, come descritto in [modifica dell'aspetto di un controllo a seconda dello stato](#changing_the_appearance_of_a_control_depending_on_its_state) precedente in questo argomento. I controlli di terze parti devono specificare gli Stati usando il <xref:System.Windows.TemplateVisualStateAttribute>, che consente agli strumenti di progettazione, ad esempio [finestra di progettazione XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio) in Visual Studio e Blend per Visual Studio, di esporre gli Stati del controllo per la creazione di modelli di controllo.

 Per trovare il contratto di controllo dei controlli inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Stili e modelli di Control](control-styles-and-templates.md).

### <a name="properties-in-the-control-contract"></a>Proprietà nel contratto di controllo
 Anche le proprietà pubbliche che influiscono visivamente sul controllo sono incluse nel contratto di controllo. È possibile impostare queste proprietà per modificare l'aspetto del controllo senza creare una nuova <xref:System.Windows.Controls.ControlTemplate>. È anche possibile usare l'estensione di markup [TemplateBinding](../advanced/templatebinding-markup-extension.md) per associare le proprietà degli elementi presenti nel <xref:System.Windows.Controls.ControlTemplate> alle proprietà pubbliche definite dall'<xref:System.Windows.Controls.Button>.

 L'esempio seguente illustra il contratto di controllo per il pulsante.

 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]

 Quando si crea una <xref:System.Windows.Controls.ControlTemplate>, è spesso più semplice iniziare con una <xref:System.Windows.Controls.ControlTemplate> esistente e apportare modifiche. Per modificare un <xref:System.Windows.Controls.ControlTemplate>esistente, è possibile eseguire una delle operazioni seguenti:

- Utilizzare una finestra di progettazione, ad esempio Blend per Visual Studio, che fornisce un'interfaccia utente grafica per la creazione di modelli di controllo. Per altre informazioni, vedere [Applicazione di stili a un controllo che supporta modelli](https://go.microsoft.com/fwlink/?LinkId=161153).

- Ottenere il <xref:System.Windows.Controls.ControlTemplate> predefinito e modificarlo. Per trovare i modelli del controllo predefiniti che sono inclusi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Temi WPF predefiniti](https://go.microsoft.com/fwlink/?LinkID=158252).

<a name="complete_example"></a>
## <a name="complete-example"></a>Esempio completo
 Nell'esempio seguente viene illustrata la<xref:System.Windows.Controls.ControlTemplate> di <xref:System.Windows.Controls.Button>completa descritta in questo argomento.

 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]

## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
