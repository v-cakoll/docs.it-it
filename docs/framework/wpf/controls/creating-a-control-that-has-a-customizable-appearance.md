---
title: Creazione di un controllo dall'aspetto personalizzabile
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: d9cf092cf47d4fb70b15033d039777d3279b633a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283566"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Creazione di un controllo dall'aspetto personalizzabile

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consente di creare un controllo di cui è possibile personalizzare l'aspetto. È possibile, ad esempio, modificare l'aspetto di un <xref:System.Windows.Controls.CheckBox> oltre le impostazioni che possono essere eseguite dalle proprietà creando una nuova <xref:System.Windows.Controls.ControlTemplate>. Nella figura seguente viene illustrato un <xref:System.Windows.Controls.CheckBox> che utilizza una <xref:System.Windows.Controls.ControlTemplate> predefinita e una <xref:System.Windows.Controls.CheckBox> che utilizza un <xref:System.Windows.Controls.ControlTemplate>personalizzato.

![Casella di controllo con il modello del controllo predefinito.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Oggetto CheckBox che usa il modello del controllo predefinito

![Casella di controllo con un modello del controllo personalizzato.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Oggetto CheckBox che usa un modello del controllo personalizzato

Se si segue il modello parti e Stati quando si crea un controllo, l'aspetto del controllo sarà personalizzabile. Gli strumenti di progettazione, ad esempio Blend per Visual Studio supportano il modello parti e Stati. Pertanto, quando si segue questo modello, il controllo sarà personalizzabile in questi tipi di applicazioni.  In questo argomento viene illustrato il modello Parts and States e viene illustrato come seguirlo quando si crea un controllo personalizzato. In questo argomento viene utilizzato un esempio di controllo personalizzato, `NumericUpDown`, per illustrare la filosofia di questo modello.  Il controllo `NumericUpDown` Visualizza un valore numerico, che può essere aumentato o diminuito da un utente facendo clic sui pulsanti del controllo.  Nella figura seguente viene illustrato il controllo `NumericUpDown` descritto in questo argomento.

![Controllo personalizzato NumericUpDown.](./media/ndp-numericupdown.png "NDP_NumericUPDown")
Controllo NumericUpDown personalizzato

Di seguito sono elencate le diverse sezioni di questo argomento:

- [Prerequisiti](#prerequisites)

- [Modello di parti e Stati](#parts_and_states_model)

- [Definizione della struttura visiva e del comportamento visivo di un controllo in un oggetto ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [Utilizzo di parti di ControlTemplate nel codice](#using_parts_of_the_controltemplate_in_code)

- [Fornire il contratto di controllo](#providing_the_control_contract)

- [Esempio completo](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Prerequisiti

In questo argomento si presuppone che l'utente sia in grado di creare un nuovo <xref:System.Windows.Controls.ControlTemplate> per un controllo esistente, di avere familiarità con gli elementi di un contratto di controllo e di comprendere i concetti illustrati in [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).

> [!NOTE]
> Per creare un controllo per cui è possibile personalizzare l'aspetto, è necessario creare un controllo che erediti dalla classe <xref:System.Windows.Controls.Control> o una delle relative sottoclassi diverse da <xref:System.Windows.Controls.UserControl>.  Un controllo che eredita da <xref:System.Windows.Controls.UserControl> è un controllo che può essere creato rapidamente, ma non usa un <xref:System.Windows.Controls.ControlTemplate> e non è possibile personalizzarne l'aspetto.

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>Modello di parti e Stati

Il modello parti e stati specifica come definire la struttura visiva e il comportamento visivo di un controllo. Per seguire il modello parti e Stati, è necessario eseguire le operazioni seguenti:

- Definire la struttura visiva e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> di un controllo.

- Seguire alcune procedure consigliate quando la logica del controllo interagisce con parti del modello di controllo.

- Fornire un contratto di controllo per specificare gli elementi da includere nel <xref:System.Windows.Controls.ControlTemplate>.

Quando si definiscono la struttura visiva e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> di un controllo, gli autori dell'applicazione possono modificare la struttura visiva e il comportamento visivo del controllo creando un nuovo <xref:System.Windows.Controls.ControlTemplate> anziché scrivere codice.   È necessario fornire un contratto di controllo che indichi agli autori dell'applicazione quali <xref:System.Windows.FrameworkElement> gli oggetti e gli Stati devono essere definiti nel <xref:System.Windows.Controls.ControlTemplate>. È consigliabile seguire alcune procedure consigliate quando si interagisce con le parti nel <xref:System.Windows.Controls.ControlTemplate> in modo che il controllo gestisca correttamente una <xref:System.Windows.Controls.ControlTemplate>incompleta.  Se si seguono questi tre principi, gli autori di applicazioni saranno in grado di creare un <xref:System.Windows.Controls.ControlTemplate> per il controllo con la stessa facilità con cui sono disponibili per i controlli forniti con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La sezione seguente illustra in dettaglio ciascuno di questi consigli.

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definizione della struttura visiva e del comportamento visivo di un controllo in un oggetto ControlTemplate

Quando si crea il controllo personalizzato utilizzando il modello parti e Stati, si definisce la struttura visiva e il comportamento visivo del controllo nel relativo <xref:System.Windows.Controls.ControlTemplate> anziché nella relativa logica.  La struttura visiva di un controllo è costituita dal composto di <xref:System.Windows.FrameworkElement> oggetti che costituiscono il controllo.  Il comportamento visivo è il modo in cui il controllo viene visualizzato quando si trova in un determinato stato.   Per ulteriori informazioni sulla creazione di un <xref:System.Windows.Controls.ControlTemplate> che specifica la struttura visiva e il comportamento visivo di un controllo, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).

Nell'esempio del controllo `NumericUpDown` la struttura visiva include due controlli <xref:System.Windows.Controls.Primitives.RepeatButton> e un <xref:System.Windows.Controls.TextBlock>.  Se si aggiungono questi controlli nel codice del `NumericUpDown` controllo, nel costruttore, ad esempio, le posizioni di tali controlli non sono modificabili.  Anziché definire il comportamento visivo e la struttura visiva del controllo nel codice, è necessario definirlo nell'<xref:System.Windows.Controls.ControlTemplate>.  Quindi, uno sviluppatore di applicazioni per personalizzare la posizione dei pulsanti e <xref:System.Windows.Controls.TextBlock> e specificare il comportamento che si verifica quando `Value` è negativo perché la <xref:System.Windows.Controls.ControlTemplate> può essere sostituita.

Nell'esempio seguente viene illustrata la struttura visiva del controllo `NumericUpDown`, che include un <xref:System.Windows.Controls.Primitives.RepeatButton> per aumentare `Value`, un <xref:System.Windows.Controls.Primitives.RepeatButton> per ridurre `Value`e un <xref:System.Windows.Controls.TextBlock> per visualizzare `Value`.

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

Un comportamento visivo del controllo `NumericUpDown` è che il valore si trova in un tipo di carattere rosso se è negativo.  Se si modifica il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> nel codice quando il `Value` è negativo, il `NumericUpDown` visualizzerà sempre un valore negativo rosso. È possibile specificare il comportamento visivo del controllo nella <xref:System.Windows.Controls.ControlTemplate> aggiungendo <xref:System.Windows.VisualState> oggetti al <xref:System.Windows.Controls.ControlTemplate>.  Nell'esempio seguente vengono illustrati gli oggetti <xref:System.Windows.VisualState> per gli Stati `Positive` e `Negative`.  `Positive` e `Negative` si escludono a vicenda (il controllo si trova sempre esattamente in uno dei due), quindi l'esempio inserisce gli oggetti di <xref:System.Windows.VisualState> in un singolo <xref:System.Windows.VisualStateGroup>.  Quando il controllo entra nello stato `Negative`, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> della <xref:System.Windows.Controls.TextBlock> diventa rosso.  Quando il controllo si trova nello stato `Positive`, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> torna al valore originale.  La definizione di oggetti <xref:System.Windows.VisualState> in una <xref:System.Windows.Controls.ControlTemplate> è descritta più avanti in [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).

> [!NOTE]
> Assicurarsi di impostare la proprietà <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> associata nella <xref:System.Windows.FrameworkElement> radice della <xref:System.Windows.Controls.ControlTemplate>.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>Utilizzo di parti di ControlTemplate nel codice

Un autore <xref:System.Windows.Controls.ControlTemplate> potrebbe omettere <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti, intenzionalmente o per errore, ma la logica del controllo potrebbe avere bisogno di tali parti per funzionare correttamente. Il modello parti e stati specifica che il controllo deve essere resiliente a un <xref:System.Windows.Controls.ControlTemplate> che manca <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti.  Il controllo non deve generare un'eccezione o segnalare un errore nel caso in cui non sia presente un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>o <xref:System.Windows.VisualStateGroup> dalla <xref:System.Windows.Controls.ControlTemplate>. In questa sezione vengono descritte le procedure consigliate per l'interazione con gli oggetti <xref:System.Windows.FrameworkElement> e la gestione degli Stati.

### <a name="anticipate-missing-frameworkelement-objects"></a>Prevedere oggetti FrameworkElement mancanti

Quando si definiscono <xref:System.Windows.FrameworkElement> oggetti nel <xref:System.Windows.Controls.ControlTemplate>, la logica del controllo potrebbe dover interagire con alcuni di essi.  Ad esempio, il controllo `NumericUpDown` sottoscrive l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dei pulsanti per aumentare o diminuire `Value` e imposta la proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> del <xref:System.Windows.Controls.TextBlock> su `Value`. Se un <xref:System.Windows.Controls.ControlTemplate> personalizzato omette i pulsanti <xref:System.Windows.Controls.TextBlock> o, è accettabile che il controllo perda alcune delle sue funzionalità, ma è necessario assicurarsi che il controllo non provochi un errore. Se, ad esempio, un <xref:System.Windows.Controls.ControlTemplate> non contiene i pulsanti per modificare `Value`, il `NumericUpDown` perde tale funzionalità, ma un'applicazione che utilizza il <xref:System.Windows.Controls.ControlTemplate> continuerà a essere eseguita.

Con le procedure seguenti si garantisce che il controllo risponda correttamente agli oggetti <xref:System.Windows.FrameworkElement> mancanti:

1. Impostare l'attributo `x:Name` per ogni <xref:System.Windows.FrameworkElement> a cui è necessario fare riferimento nel codice.

2. Definire le proprietà private per ogni <xref:System.Windows.FrameworkElement> con cui è necessario interagire.

3. Sottoscrivere e annullare la sottoscrizione a tutti gli eventi gestiti dal controllo nella funzione di accesso set della proprietà <xref:System.Windows.FrameworkElement>.

4. Impostare le proprietà <xref:System.Windows.FrameworkElement> definite nel passaggio 2 nel metodo <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>. Questa è la prima che il <xref:System.Windows.FrameworkElement> nel <xref:System.Windows.Controls.ControlTemplate> sia disponibile per il controllo. Usare il `x:Name` della <xref:System.Windows.FrameworkElement> per ottenerlo dal <xref:System.Windows.Controls.ControlTemplate>.

5. Verificare che il <xref:System.Windows.FrameworkElement> non sia `null` prima di accedere ai relativi membri.  Se è `null`, non segnalare un errore.

Negli esempi seguenti viene illustrato il modo in cui il controllo `NumericUpDown` interagisce con gli oggetti <xref:System.Windows.FrameworkElement> in base alle raccomandazioni nell'elenco precedente.

Nell'esempio che definisce la struttura visiva del controllo `NumericUpDown` nel <xref:System.Windows.Controls.ControlTemplate>, il <xref:System.Windows.Controls.Primitives.RepeatButton> che aumenta `Value` ha il `x:Name` attributo impostato su `UpButton`.  Nell'esempio seguente viene dichiarata una proprietà denominata `UpButtonElement` che rappresenta l'<xref:System.Windows.Controls.Primitives.RepeatButton> dichiarata nel <xref:System.Windows.Controls.ControlTemplate>. La funzione di accesso `set` prima Annulla la sottoscrizione all'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del pulsante se `UpDownElement` non è `null`, quindi imposta la proprietà e quindi sottoscrive l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Esiste anche una proprietà definita, ma non mostrata, per gli altri <xref:System.Windows.Controls.Primitives.RepeatButton>, denominata `DownButtonElement`.

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

Nell'esempio seguente vengono illustrati i <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per il controllo `NumericUpDown`.  Nell'esempio viene usato il metodo <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> per ottenere gli oggetti <xref:System.Windows.FrameworkElement> dal <xref:System.Windows.Controls.ControlTemplate>.  Si noti che l'esempio protegge i casi in cui <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> trova una <xref:System.Windows.FrameworkElement> con il nome specificato che non corrisponde al tipo previsto. È inoltre consigliabile ignorare gli elementi che hanno il `x:Name` specificato ma sono di tipo errato.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Seguendo le procedure illustrate negli esempi precedenti, è possibile verificare che il controllo continuerà a essere eseguito quando manca un <xref:System.Windows.FrameworkElement>nel <xref:System.Windows.Controls.ControlTemplate>.

### <a name="use-the-visualstatemanager-to-manage-states"></a>Utilizzare l'oggetto VisualStateManager per gestire gli Stati

Il <xref:System.Windows.VisualStateManager> tiene traccia degli Stati di un controllo ed esegue la logica necessaria per la transizione tra gli Stati. Quando si aggiungono oggetti <xref:System.Windows.VisualState> al <xref:System.Windows.Controls.ControlTemplate>, è necessario aggiungerli a una <xref:System.Windows.VisualStateGroup> e aggiungere il <xref:System.Windows.VisualStateGroup> alla proprietà associata <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> in modo che l'<xref:System.Windows.VisualStateManager> abbia accesso a tali oggetti.

Nell'esempio seguente viene ripetuto l'esempio precedente che Mostra gli oggetti di <xref:System.Windows.VisualState> che corrispondono agli Stati `Positive` e `Negative` del controllo. Il <xref:System.Windows.Media.Animation.Storyboard> nel `Negative`<xref:System.Windows.VisualState> converte il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> rosso.   Quando il controllo `NumericUpDown` si trova nello stato `Negative`, inizia lo storyboard nello stato `Negative`.  Il <xref:System.Windows.Media.Animation.Storyboard> nello stato `Negative` si interrompe quando il controllo torna allo stato `Positive`.  Il `Positive`<xref:System.Windows.VisualState> non deve contenere un <xref:System.Windows.Media.Animation.Storyboard> perché quando il <xref:System.Windows.Media.Animation.Storyboard> per l'`Negative` si interrompe, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> torna al colore originale.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

Si noti che al <xref:System.Windows.Controls.TextBlock> viene assegnato un nome, ma il <xref:System.Windows.Controls.TextBlock> non è nel contratto di controllo per `NumericUpDown` perché la logica del controllo non fa mai riferimento al <xref:System.Windows.Controls.TextBlock>.  Gli elementi a cui viene fatto riferimento nel <xref:System.Windows.Controls.ControlTemplate> hanno nomi, ma non devono far parte del contratto di controllo perché un nuovo <xref:System.Windows.Controls.ControlTemplate> per il controllo potrebbe non dover fare riferimento a tale elemento.  Ad esempio, un utente che crea una nuova <xref:System.Windows.Controls.ControlTemplate> per `NumericUpDown` potrebbe decidere di non indicare che `Value` è negativo modificando il <xref:System.Windows.Controls.Control.Foreground%2A>.  In tal caso, né il codice né il <xref:System.Windows.Controls.ControlTemplate> fanno riferimento al <xref:System.Windows.Controls.TextBlock> in base al nome.

La logica del controllo è responsabile della modifica dello stato del controllo. Nell'esempio seguente viene illustrato che il controllo `NumericUpDown` chiama il metodo <xref:System.Windows.VisualStateManager.GoToState%2A> per passare allo stato `Positive` quando `Value` è 0 o superiore e lo stato `Negative` quando `Value` è minore di 0.

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

Il metodo <xref:System.Windows.VisualStateManager.GoToState%2A> esegue la logica necessaria per avviare e arrestare correttamente gli storyboard. Quando un controllo chiama <xref:System.Windows.VisualStateManager.GoToState%2A> per modificarne lo stato, il <xref:System.Windows.VisualStateManager> esegue le operazioni seguenti:

- Se il <xref:System.Windows.VisualState> cui il controllo avrà un <xref:System.Windows.Media.Animation.Storyboard>, inizia lo storyboard. Quindi, se il <xref:System.Windows.VisualState> dal quale il controllo ha una <xref:System.Windows.Media.Animation.Storyboard>, lo storyboard termina.

- Se il controllo è già nello stato specificato, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna azione e restituisce `true`.

- Se lo stato specificato non esiste nel <xref:System.Windows.Controls.ControlTemplate> di `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna azione e restituisce `false`.

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Procedure consigliate per l'utilizzo di VisualStateManager

Per mantenere gli Stati del controllo è consigliabile eseguire le operazioni seguenti:

- Usare le proprietà per tenere traccia dello stato.

- Creare un metodo helper per la transizione tra Stati.

Il controllo `NumericUpDown` usa la relativa proprietà `Value` per verificare se si trova nello stato `Positive` o `Negative`.  Il controllo `NumericUpDown` definisce anche gli Stati `Focused` e `UnFocused`, che tiene traccia della proprietà <xref:System.Windows.UIElement.IsFocused%2A>. Se si usano Stati che non corrispondono naturalmente a una proprietà del controllo, è possibile definire una proprietà privata per tenere traccia dello stato.

Un unico metodo che aggiorna tutti gli Stati centralizza le chiamate al <xref:System.Windows.VisualStateManager> e mantiene il codice gestibile. Nell'esempio seguente viene illustrato il metodo helper del controllo `NumericUpDown`, `UpdateStates`. Quando `Value` è maggiore o uguale a 0, l'<xref:System.Windows.Controls.Control> si trova nello stato `Positive`.  Quando `Value` è minore di 0, il controllo si trova nello stato `Negative`.  Quando <xref:System.Windows.UIElement.IsFocused%2A> viene `true`, il controllo si trova nello stato `Focused`; in caso contrario, si trova nello stato `Unfocused`.  Il controllo può chiamare `UpdateStates` ogni volta che è necessario modificarne lo stato, indipendentemente dalle modifiche apportate allo stato.

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

Se si passa un nome di stato a <xref:System.Windows.VisualStateManager.GoToState%2A> quando il controllo è già in tale stato, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna operazione, pertanto non è necessario controllare lo stato corrente del controllo.  Se, ad esempio, `Value` viene modificato da un numero negativo a un altro numero negativo, lo storyboard per lo stato del `Negative` non viene interrotto e l'utente non visualizzerà una modifica nel controllo.

Il <xref:System.Windows.VisualStateManager> utilizza <xref:System.Windows.VisualStateGroup> oggetti per determinare lo stato da uscire quando si chiama <xref:System.Windows.VisualStateManager.GoToState%2A>. Il controllo è sempre in uno stato per ogni <xref:System.Windows.VisualStateGroup> definito nel <xref:System.Windows.Controls.ControlTemplate> e lascia uno stato solo quando entra in un altro stato dallo stesso <xref:System.Windows.VisualStateGroup>. Ad esempio, il <xref:System.Windows.Controls.ControlTemplate> del controllo `NumericUpDown` definisce `Positive` e `Negative`<xref:System.Windows.VisualState> oggetti in un <xref:System.Windows.VisualStateGroup> e `Focused` e `Unfocused`<xref:System.Windows.VisualState> oggetti in un altro. È possibile visualizzare il `Focused` e `Unfocused`<xref:System.Windows.VisualState> definito nella sezione [esempio completo](#complete_example) di questo argomento quando il controllo passa dallo stato `Positive` allo stato `Negative` o viceversa, il controllo rimane nello stato `Focused` o `Unfocused`.

Esistono tre posizioni tipiche in cui lo stato di un controllo può cambiare:

- Quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato al <xref:System.Windows.Controls.Control>.

- Quando una proprietà viene modificata.

- Quando si verifica un evento.

Negli esempi seguenti viene illustrato l'aggiornamento dello stato del controllo `NumericUpDown` in questi casi.

È necessario aggiornare lo stato del controllo nel metodo <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> in modo che il controllo venga visualizzato nello stato corretto quando viene applicato il <xref:System.Windows.Controls.ControlTemplate>. Nell'esempio seguente viene chiamato `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per garantire che il controllo sia negli stati appropriati.  Si supponga, ad esempio, di creare un controllo `NumericUpDown`, quindi impostare il relativo <xref:System.Windows.Controls.Control.Foreground%2A> su verde e `Value` su-5.  Se non si chiama `UpdateStates` quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato al controllo `NumericUpDown`, il controllo non si trova nello stato `Negative` e il valore è verde anziché rosso.  È necessario chiamare `UpdateStates` per inserire il controllo nello stato `Negative`.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Spesso è necessario aggiornare gli Stati di un controllo quando una proprietà viene modificata. Nell'esempio seguente viene illustrato l'intero metodo `ValueChangedCallback`. Poiché `ValueChangedCallback` viene chiamato quando `Value` cambia, il metodo chiama `UpdateStates` in caso `Value` modificato da positivo a negativo o viceversa. È accettabile chiamare `UpdateStates` quando `Value` modifiche ma resta positivo o negativo perché in tal caso il controllo non modificherà gli Stati.

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

Potrebbe inoltre essere necessario aggiornare gli Stati quando si verifica un evento. Nell'esempio seguente viene illustrato che il `NumericUpDown` chiama `UpdateStates` sul <xref:System.Windows.Controls.Control> per gestire l'evento <xref:System.Windows.UIElement.GotFocus>.

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

Il <xref:System.Windows.VisualStateManager> consente di gestire gli Stati del controllo. Utilizzando la <xref:System.Windows.VisualStateManager>, è possibile verificare che il controllo passi correttamente tra gli Stati.  Se si seguono i consigli descritti in questa sezione per lavorare con il <xref:System.Windows.VisualStateManager>, il codice del controllo rimarrà leggibile e gestibile.

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>Fornire il contratto di controllo

Si fornisce un contratto di controllo in modo che <xref:System.Windows.Controls.ControlTemplate> autori conoscano gli elementi da inserire nel modello. Un contratto di controllo include tre elementi:

- Gli elementi visivi usati dalla logica del controllo.

- Gli stati del controllo e il gruppo a cui appartiene ogni stato.

- Le proprietà pubbliche che influiscono visivamente sul controllo.

Un utente che crea una nuova <xref:System.Windows.Controls.ControlTemplate> deve conoscere gli oggetti <xref:System.Windows.FrameworkElement> usati dalla logica del controllo, il tipo di ogni oggetto e il nome. Un autore <xref:System.Windows.Controls.ControlTemplate> deve anche comprendere il nome di ogni possibile stato in cui può trovarsi il controllo e in quale <xref:System.Windows.VisualStateGroup> lo stato è.

Tornando all'esempio `NumericUpDown`, il controllo prevede che i <xref:System.Windows.Controls.ControlTemplate> dispongano dei <xref:System.Windows.FrameworkElement> oggetti seguenti:

- <xref:System.Windows.Controls.Primitives.RepeatButton> chiamato `UpButton`.

- <xref:System.Windows.Controls.Primitives.RepeatButton> denominato `DownButton.`

 Il controllo può trovarsi negli Stati seguenti:

- Nella `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- Nella `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

Per specificare gli oggetti <xref:System.Windows.FrameworkElement> previsti dal controllo, usare il <xref:System.Windows.TemplatePartAttribute>, che specifica il nome e il tipo degli elementi previsti.  Per specificare i possibili stati di un controllo, usare il <xref:System.Windows.TemplateVisualStateAttribute>, che specifica il nome dello stato e la <xref:System.Windows.VisualStateGroup> a cui appartiene.  Inserire il <xref:System.Windows.TemplatePartAttribute> e <xref:System.Windows.TemplateVisualStateAttribute> nella definizione della classe del controllo.

Tutte le proprietà pubbliche che influiscono sull'aspetto del controllo fanno anche parte del contratto di controllo.

Nell'esempio seguente vengono specificati l'oggetto <xref:System.Windows.FrameworkElement> e gli Stati per il controllo `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>Esempio completo

L'esempio seguente è l'intero <xref:System.Windows.Controls.ControlTemplate> per il controllo `NumericUpDown`.

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

Nell'esempio seguente viene illustrata la logica per la `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>Vedere anche

- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
- [Personalizzazione dei controlli](control-customization.md)
