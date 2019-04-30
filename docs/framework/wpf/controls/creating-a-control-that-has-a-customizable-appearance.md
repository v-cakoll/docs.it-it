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
ms.openlocfilehash: a5d7c06502b66298d530d0180ffaf63862b9fc28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017793"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Creazione di un controllo dall'aspetto personalizzabile
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre la possibilità di creare un controllo dall'aspetto personalizzabile. Ad esempio, è possibile modificare l'aspetto di un <xref:System.Windows.Controls.CheckBox> oltre a quale impostazione proprietà eseguirà creando un nuovo <xref:System.Windows.Controls.ControlTemplate>. La figura seguente mostra una <xref:System.Windows.Controls.CheckBox> che usa un valore predefinito <xref:System.Windows.Controls.ControlTemplate> e una <xref:System.Windows.Controls.CheckBox> che usa un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Casella di controllo con il modello di controllo predefinito. ](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Oggetto CheckBox che usa il modello del controllo predefinito  
  
 ![Casella di controllo con un modello del controllo personalizzato. ](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Oggetto CheckBox che usa un modello del controllo personalizzato  
  
 Se si segue il modello di parti e stati quando si crea un controllo, l'aspetto del controllo sarà personalizzabile. Gli strumenti di progettazione, ad esempio Microsoft Expression Blend supportano il modello di parti e stati, in modo che quando si segue questo modello di controllo sarà personalizzabile in tali tipi di applicazioni.  In questo argomento viene illustrato come seguirla quando si crea un controllo personalizzato e il modello di parti e stati. In questo argomento viene utilizzato un esempio di un controllo personalizzato, `NumericUpDown`, per illustrare la filosofia di questo modello.  Il `NumericUpDown` controllo Visualizza un valore numerico, quale un utente può aumentare o diminuire facendo clic sui pulsanti del controllo.  La figura seguente illustra il `NumericUpDown` controllo che è descritti in questo argomento.  
  
 ![Controllo personalizzato NumericUpDown. ](./media/ndp-numericupdown.png "NDP_NumericUPDown")  
Un controllo personalizzato NumericUpDown  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Prerequisiti](#prerequisites)  
  
- [Modello delle parti e stati](#parts_and_states_model)  
  
- [Che definisce la struttura visiva e il comportamento di un controllo in un oggetto ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
- [Utilizzo delle Web part di ControlTemplate nel codice](#using_parts_of_the_controltemplate_in_code)  
  
- [Fornire il contratto di controllo](#providing_the_control_contract)  
  
- [Esempio completo](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone di conoscere le procedure creare una nuova <xref:System.Windows.Controls.ControlTemplate> per un controllo esistente, si ha familiarità con gli elementi di un contratto di controllo di e comprendere i concetti illustrati in [personalizzazione dell'aspetto di un controllo esistente da Creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Per creare un controllo che può avere l'aspetto del controllo personalizzato, è necessario creare un controllo da cui eredita il <xref:System.Windows.Controls.Control> classe o una delle sue sottoclassi diverso da <xref:System.Windows.Controls.UserControl>.  Un controllo che eredita da <xref:System.Windows.Controls.UserControl> è un controllo che può essere creato rapidamente, ma non usa un <xref:System.Windows.Controls.ControlTemplate> e non è possibile personalizzare l'aspetto del controllo.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Modello delle parti e stati  
 Il modello di parti e stati specifica la modalità definire la struttura visiva e il comportamento di un controllo. Per seguire il modello di parti e stati, è necessario eseguire le operazioni seguenti:  
  
- Definire la struttura visiva e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> di un controllo.  
  
- Seguire alcune procedure consigliate per la logica del controllo interagisce con le parti del modello di controllo.  
  
- Fornire un contratto di controllo per specificare cosa deve essere incluso nel <xref:System.Windows.Controls.ControlTemplate>.  
  
 Quando si definisce la struttura visiva e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> possono modificare la struttura visiva e il comportamento visivo del controllo di un controllo, gli autori dell'applicazione creando un nuovo <xref:System.Windows.Controls.ControlTemplate> anziché scrivere codice.   È necessario fornire un contratto di controllo indicante l'applicazione degli autori che <xref:System.Windows.FrameworkElement> oggetti e gli stati devono essere definiti nel <xref:System.Windows.Controls.ControlTemplate>. È consigliabile seguire alcune procedure consigliate quando si interagisce con le parti nel <xref:System.Windows.Controls.ControlTemplate> in modo che il controllo gestisce correttamente un incompleti <xref:System.Windows.Controls.ControlTemplate>.  Se si seguono questi tre principi, agli autori dell'applicazione sarà in grado di creare un <xref:System.Windows.Controls.ControlTemplate> per il controllo con la stessa facilità con cui possibile per i controlli forniti con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La sezione seguente illustra ognuna di queste raccomandazioni nel dettaglio.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Che definisce la struttura visiva e il comportamento di un controllo in un oggetto ControlTemplate  
 Quando si crea il controllo personalizzato tramite il modello di parti e stati, si definiscono struttura visiva del controllo e il comportamento visivo nel relativo <xref:System.Windows.Controls.ControlTemplate> anziché nella propria logica.  La struttura visiva di un controllo è formata <xref:System.Windows.FrameworkElement> gli oggetti che costituiscono il controllo.  Il comportamento visivo è il modo in cui che il controllo viene visualizzato quando si trova in un determinato stato.   Per altre informazioni sulla creazione di un <xref:System.Windows.Controls.ControlTemplate> che specifica la struttura visiva e il comportamento di un controllo, vedere [personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
 Nell'esempio del `NumericUpDown` (controllo), la struttura visiva sono inclusi due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli e un <xref:System.Windows.Controls.TextBlock>.  Se si aggiungono questi controlli nel codice del `NumericUpDown` controllo: nel relativo costruttore, ad esempio, le posizioni di tali controlli potrebbero non essere modificabili.  Invece di definire struttura visiva e il comportamento visivo del controllo nel codice, è consigliabile definirlo nel <xref:System.Windows.Controls.ControlTemplate>.  Quindi uno sviluppatore di applicazioni per personalizzare la posizione dei pulsanti e <xref:System.Windows.Controls.TextBlock> e specificare quale problema si verifica quando si `Value` è negativo perché il <xref:System.Windows.Controls.ControlTemplate> può essere sostituito.  
  
 L'esempio seguente illustra la struttura visiva del `NumericUpDown` controllo, che include un <xref:System.Windows.Controls.Primitives.RepeatButton> per aumentare `Value`, un <xref:System.Windows.Controls.Primitives.RepeatButton> diminuzione `Value`e una <xref:System.Windows.Controls.TextBlock> per visualizzare `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Un comportamento visivo del `NumericUpDown` controllo è che il valore è un tipo di carattere rosso se è negativo.  Se si modifica il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> nel codice quando il `Value` è negativo, il `NumericUpDown` mostreranno sempre un valore negativo rosso. Si specifica il comportamento visivo del controllo nel <xref:System.Windows.Controls.ControlTemplate> aggiungendo <xref:System.Windows.VisualState> gli oggetti per il <xref:System.Windows.Controls.ControlTemplate>.  L'esempio seguente illustra il <xref:System.Windows.VisualState> degli oggetti per il `Positive` e `Negative` stati.  `Positive` e `Negative` si escludono a vicenda (il controllo è sempre esattamente uno dei due), in modo che l'esempio inserisce il <xref:System.Windows.VisualState> gli oggetti in un'unica <xref:System.Windows.VisualStateGroup>.  Quando il controllo passa al `Negative` lo stato, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> diventa di colore rosso.  Quando il controllo è nel `Positive` lo stato, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> ritorna al valore originale.  Che definisce <xref:System.Windows.VisualState> oggetti un <xref:System.Windows.Controls.ControlTemplate> verrà discussa nelle [personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Assicurarsi di impostare il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà sulla directory radice associata <xref:System.Windows.FrameworkElement> del <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>Utilizzo delle Web part di ControlTemplate nel codice  
 Oggetto <xref:System.Windows.Controls.ControlTemplate> autore potrebbe omettere <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti, intenzionalmente o accidentalmente, ma per la logica del controllo potrebbe essere necessario quelle parti per funzionare correttamente. Il modello di parti e stati specifica che il controllo deve essere resiliente a un <xref:System.Windows.Controls.ControlTemplate> che non è presente <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti.  Il controllo non deve generare un'eccezione o segnalare un errore se un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, o <xref:System.Windows.VisualStateGroup> non è presente il <xref:System.Windows.Controls.ControlTemplate>. In questa sezione vengono descritte le procedure consigliate per l'interazione con <xref:System.Windows.FrameworkElement> oggetti e la gestione degli stati.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Prevedere la FrameworkElement (oggetti)  
 Quando si definiscono <xref:System.Windows.FrameworkElement> oggetti nel <xref:System.Windows.Controls.ControlTemplate>, potrebbe essere necessario interagire con alcuni di essi per la logica del controllo.  Ad esempio, il `NumericUpDown` controllo sottoscrive degli pulsanti <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi per aumentare o ridurre `Value` e imposta il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà del <xref:System.Windows.Controls.TextBlock> per `Value`. Se una classe personalizzata <xref:System.Windows.Controls.ControlTemplate> omette i <xref:System.Windows.Controls.TextBlock> o pulsanti di cui è ammissibile che il controllo perde alcune delle proprie funzionalità, ma è necessario assicurarsi che il controllo viene generato alcun errore. Ad esempio, se un <xref:System.Windows.Controls.ControlTemplate> non contiene i pulsanti per modificare `Value`, il `NumericUpDown` perde tali funzionalità, ma un'applicazione che utilizza il <xref:System.Windows.Controls.ControlTemplate> continuerà a essere eseguito.  
  
 Le seguenti procedure garantirà che il controllo risponda correttamente alla mancanza <xref:System.Windows.FrameworkElement> oggetti:  
  
1. Impostare il `x:Name` per ogni attributo <xref:System.Windows.FrameworkElement> che è necessario fare riferimento nel codice.  
  
2. Definire le proprietà private per ogni <xref:System.Windows.FrameworkElement> che occorre per interagirvi.  
  
3. Sottoscrivere e annullare la sottoscrizione a tutti gli eventi che gestisce il controllo nel <xref:System.Windows.FrameworkElement> proprietà della funzione di accesso set.  
  
4. Impostare il <xref:System.Windows.FrameworkElement> le proprietà definite nel passaggio 2 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> (metodo). Si tratta del primo che il <xref:System.Windows.FrameworkElement> nella <xref:System.Windows.Controls.ControlTemplate> è disponibile per il controllo. Usare la `x:Name` del <xref:System.Windows.FrameworkElement> scaricarla dal <xref:System.Windows.Controls.ControlTemplate>.  
  
5. Verificare che il <xref:System.Windows.FrameworkElement> non è `null` prima di accedere ai relativi membri.  Se si tratta di `null`, non segnalano un errore.  
  
 Gli esempi seguenti illustrano come il `NumericUpDown` tale controllo interagisce con <xref:System.Windows.FrameworkElement> oggetti conformemente ai suggerimenti nell'elenco precedente.  
  
 Nell'esempio che definisce la struttura visiva del `NumericUpDown` controllare nel <xref:System.Windows.Controls.ControlTemplate>, il <xref:System.Windows.Controls.Primitives.RepeatButton> che aumenta `Value` ha relativo `x:Name` attributo impostato su `UpButton`.  L'esempio seguente dichiara una proprietà denominata `UpButtonElement` che rappresenta il <xref:System.Windows.Controls.Primitives.RepeatButton> dichiarato nel <xref:System.Windows.Controls.ControlTemplate>. Il `set` funzione di accesso Annulla la sottoscrizione prima del pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento se `UpDownElement` non è `null`, quindi imposta la proprietà e quindi si registra presso il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. È anche disponibile una proprietà definita, ma non riportati di seguito, per gli altri <xref:System.Windows.Controls.Primitives.RepeatButton>, denominato `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 L'esempio seguente mostra le <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per il `NumericUpDown` controllo.  L'esempio Usa la <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> metodo per ottenere il <xref:System.Windows.FrameworkElement> oggetti dal <xref:System.Windows.Controls.ControlTemplate>.  Si noti che nell'esempio protegge casi in cui <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> consente di trovare un <xref:System.Windows.FrameworkElement> con il nome specificato non è del tipo previsto. È anche consigliata per ignorare gli elementi che hanno specificato `x:Name` ma sono di tipo errato.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Seguendo le procedure illustrate negli esempi precedenti, si assicura che il controllo continuerà l'esecuzione quando il <xref:System.Windows.Controls.ControlTemplate> non è presente un <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Usare l'oggetto VisualStateManager per gestire gli Stati  
 Il <xref:System.Windows.VisualStateManager> tiene sotto controllo gli stati di un controllo e consente di eseguire la logica necessaria per la transizione tra stati. Quando si aggiunge <xref:System.Windows.VisualState> gli oggetti per il <xref:System.Windows.Controls.ControlTemplate>, è necessario aggiungerlo una <xref:System.Windows.VisualStateGroup> e aggiungere il <xref:System.Windows.VisualStateGroup> per il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà associata in modo che il <xref:System.Windows.VisualStateManager> può accedere a tali.  
  
 Nell'esempio seguente ripete l'esempio precedente che mostra le <xref:System.Windows.VisualState> gli oggetti che corrisponde alla `Positive` e `Negative` stati del controllo. Il <xref:System.Windows.Media.Animation.Storyboard> nella `Negative` <xref:System.Windows.VisualState> diventa il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> rosso.   Quando la `NumericUpDown` controllo si trova nel `Negative` lo stato, lo storyboard nel `Negative` stato inizia.  Il <xref:System.Windows.Media.Animation.Storyboard> nella `Negative` lo stato viene arrestata quando il controllo torna al `Positive` dello stato.  Il `Positive` <xref:System.Windows.VisualState> non deve contenere un <xref:System.Windows.Media.Animation.Storyboard> perché quando il <xref:System.Windows.Media.Animation.Storyboard> per il `Negative` si arresta, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> restituisce al colore originale.  
  
 [!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Si noti che il <xref:System.Windows.Controls.TextBlock> viene assegnato un nome, ma la <xref:System.Windows.Controls.TextBlock> non è nel contratto di controllo per `NumericUpDown` poiché fa mai riferimento per la logica del controllo di <xref:System.Windows.Controls.TextBlock>.  Gli elementi a cui fa riferimento il <xref:System.Windows.Controls.ControlTemplate> hanno nomi, ma non è necessario far parte del contratto di controllo perché un nuovo <xref:System.Windows.Controls.ControlTemplate> per il controllo potrebbe non essere necessario fare riferimento a tale elemento.  Ad esempio, un utente che crea una nuova <xref:System.Windows.Controls.ControlTemplate> per `NumericUpDown` potrebbe decidere di non indicano che `Value` è negativo modificando il <xref:System.Windows.Controls.Control.Foreground%2A>.  In tal caso, né il codice né la <xref:System.Windows.Controls.ControlTemplate> riferimenti di <xref:System.Windows.Controls.TextBlock> in base al nome.  
  
 Per la logica del controllo è responsabile della modifica dello stato del controllo. L'esempio seguente mostra che il `NumericUpDown` le chiamate di controllo la <xref:System.Windows.VisualStateManager.GoToState%2A> metodo di autodocumentazione le `Positive` stato quando `Value` è 0 o maggiore e il `Negative` stato quando `Value` è minore di 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Il <xref:System.Windows.VisualStateManager.GoToState%2A> metodo esegue la logica necessaria per avviare e arrestare in modo appropriato gli storyboard. Quando un controllo chiama <xref:System.Windows.VisualStateManager.GoToState%2A> per modificare lo stato, il <xref:System.Windows.VisualStateManager> esegue le operazioni seguenti:  
  
- Se il <xref:System.Windows.VisualState> che sta per il controllo ha un <xref:System.Windows.Media.Animation.Storyboard>, lo storyboard viene avviato. Quindi, se il <xref:System.Windows.VisualState> proviene che il controllo dispone un <xref:System.Windows.Media.Animation.Storyboard>, le entità finali di uno storyboard.  
  
- Se il controllo è già nello stato in cui viene specificato <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna azione e restituisce `true`.  
  
- Se lo stato specificato non esiste nel <xref:System.Windows.Controls.ControlTemplate> dei `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna azione e restituisce `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Le procedure consigliate per l'utilizzo di VisualStateManager  
 È consigliabile eseguire il comando seguente per mantenere gli stati del controllo:  
  
- Usare le proprietà per rilevare lo stato.  
  
- Creare un metodo helper per eseguire la transizione tra stati.  
  
 Il `NumericUpDown` controlli utilizza relativi `Value` proprietà da rilevare se è presente nel `Positive` o `Negative` dello stato.  Il `NumericUpDown` controllo definisce anche il `Focused` e `UnFocused` indicato, le tracce di <xref:System.Windows.UIElement.IsFocused%2A> proprietà. Se si utilizzano gli Stati che naturalmente non corrispondono a una proprietà del controllo, è possibile definire una proprietà privata per tenere traccia dello stato.  
  
 Un solo metodo che consente di aggiornare tutti gli stati centralizza le chiamate al <xref:System.Windows.VisualStateManager> e mantenere gestibile il codice. L'esempio seguente mostra le `NumericUpDown` metodo di supporto del controllo, `UpdateStates`. Quando `Value` è maggiore o uguale a 0, il <xref:System.Windows.Controls.Control> è il `Positive` dello stato.  Quando `Value` è minore di 0, il controllo è attiva la `Negative` dello stato.  Quando <xref:System.Windows.UIElement.IsFocused%2A> viene `true`, il controllo è nel `Focused` stato; in caso contrario, si trova nel `Unfocused` dello stato.  Il controllo può chiamare `UpdateStates` ogni volta che è necessario modificare lo stato, indipendentemente dallo stato che viene modificato.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Se si passa un nome dello stato da <xref:System.Windows.VisualStateManager.GoToState%2A> quando il controllo è già in tale stato, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna operazione, in modo che non è necessario controllare lo stato del controllo corrente.  Ad esempio, se `Value` cambia da un numero negativo su un altro numero negativo, lo storyboard per il `Negative` stato non viene interrotta e l'utente non visualizzerà una modifica nel controllo.  
  
 Il <xref:System.Windows.VisualStateManager> viene utilizzato <xref:System.Windows.VisualStateGroup> gli oggetti per determinare quale stato di chiusura quando si chiama <xref:System.Windows.VisualStateManager.GoToState%2A>. Il controllo è sempre in uno stato per ogni <xref:System.Windows.VisualStateGroup> che viene definito nel relativo <xref:System.Windows.Controls.ControlTemplate> lasciando solo uno stato di quando entrerà in un altro stato dalla stessa <xref:System.Windows.VisualStateGroup>. Ad esempio, il <xref:System.Windows.Controls.ControlTemplate> del `NumericUpDown` controllo definisce il `Positive` e `Negative` <xref:System.Windows.VisualState> oggetti in una <xref:System.Windows.VisualStateGroup> e il `Focused` e `Unfocused` <xref:System.Windows.VisualState> gli oggetti in un altro. (È possibile visualizzare il `Focused` e `Unfocused` <xref:System.Windows.VisualState> definito nel [esempio completo](#complete_example) in questo argomento quando il controllo passa dal `Positive` torni allo stato il `Negative` stato, o viceversa, il controllo rimane in entrambi i `Focused` o `Unfocused` dello stato.  
  
 Ci sono tre posizioni tipiche in cui è possibile modificare lo stato di un controllo:  
  
- Quando la <xref:System.Windows.Controls.ControlTemplate> viene applicato al <xref:System.Windows.Controls.Control>.  
  
- Quando viene modificata una proprietà.  
  
- Quando si verifica un evento.  
  
 Gli esempi seguenti illustrano l'aggiornamento dello stato del `NumericUpDown` controllo in questi casi.  
  
 È necessario aggiornare lo stato del controllo nel <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> metodo in modo che il controllo viene visualizzato il corretto stato quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato. Nell'esempio seguente viene chiamato `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per garantire che il controllo è negli stati appropriati.  Ad esempio, si supponga di creare un `NumericUpDown` e quindi impostarne relativi <xref:System.Windows.Controls.Control.Foreground%2A> verde e `Value` a -5.  Se non si chiama `UpdateStates` quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato al `NumericUpDown` controllo, il controllo non è nel `Negative` lo stato e il valore è di colore verde anziché rossa.  È necessario chiamare `UpdateStates` per inserire il controllo `Negative` dello stato.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 È spesso necessario aggiorna gli stati di un controllo quando una proprietà viene modificata. Nell'esempio seguente illustra l'intera `ValueChangedCallback` (metodo). In quanto `ValueChangedCallback` viene chiamato quando `Value` cambia, le chiamate al metodo `UpdateStates` nel caso in cui `Value` modificato da positivo a negativo o viceversa. È possibile chiamare `UpdateStates` quando `Value` modifica ma rimane positivo o negativo in quanto in tal caso, il controllo non modificherà gli stati.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 È anche necessario aggiornare gli stati quando si verifica un evento. L'esempio seguente mostra che il `NumericUpDown` chiamate `UpdateStates` nel <xref:System.Windows.Controls.Control> per gestire il <xref:System.Windows.UIElement.GotFocus> evento.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 Il <xref:System.Windows.VisualStateManager> consente di gestire gli stati del controllo. Tramite il <xref:System.Windows.VisualStateManager>, assicurarsi che il controllo correttamente transizione tra stati.  Se si seguono i consigli descritti in questa sezione per l'utilizzo di <xref:System.Windows.VisualStateManager>, il codice del controllo rimane leggibile e gestibile.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Fornire il contratto di controllo  
 È fornire un contratto di controllo in modo che <xref:System.Windows.Controls.ControlTemplate> autori conosceranno le azioni da inserire nel modello. Un contratto di controllo include tre elementi:  
  
- Gli elementi visivi usati dalla logica del controllo.  
  
- Gli stati del controllo e il gruppo a cui appartiene ogni stato.  
  
- Le proprietà pubbliche che influiscono visivamente sul controllo.  
  
 Quando si crea una nuova <xref:System.Windows.Controls.ControlTemplate> deve sapere quali <xref:System.Windows.FrameworkElement> oggetti viene utilizzato per la logica del controllo, è il tipo di ogni oggetto e il relativo nome. Oggetto <xref:System.Windows.Controls.ControlTemplate> autore deve inoltre conoscere il nome di ogni possibile stato può essere presente il controllo e quali <xref:System.Windows.VisualStateGroup> lo stato è.  
  
 Restituzione per le `NumericUpDown` prevede che il controllo di esempio, il <xref:System.Windows.Controls.ControlTemplate> predisporre quanto segue <xref:System.Windows.FrameworkElement> oggetti:  
  
- Oggetto <xref:System.Windows.Controls.Primitives.RepeatButton> chiamato `UpButton`.  
  
- Oggetto <xref:System.Windows.Controls.Primitives.RepeatButton> chiamato `DownButton.`  
  
 Il controllo può essere nei seguenti stati:  
  
- Nel `ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    - `Positive`  
  
    - `Negative`  
  
- Nel `FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    - `Focused`  
  
    - `Unfocused`  
  
 Per specificare che cosa <xref:System.Windows.FrameworkElement> prevede che il controllo di oggetti, si utilizza il <xref:System.Windows.TemplatePartAttribute>, che consente di specificare il nome e il tipo degli elementi previsti.  Per specificare gli stati possibili di un controllo, usare il <xref:System.Windows.TemplateVisualStateAttribute>, che consente di specificare il nome dello stato e quali <xref:System.Windows.VisualStateGroup> a cui appartiene.  Inserire il <xref:System.Windows.TemplatePartAttribute> e <xref:System.Windows.TemplateVisualStateAttribute> nella definizione della classe del controllo.  
  
 Inoltre, qualsiasi proprietà pubblica che influisce sull'aspetto del controllo è una parte del contratto di controllo.  
  
 L'esempio seguente specifica i <xref:System.Windows.FrameworkElement> oggetto e gli stati per il `NumericUpDown` controllo.  
  
 [!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Esempio completo  
 L'esempio seguente è l'intera <xref:System.Windows.Controls.ControlTemplate> per il `NumericUpDown` controllo.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 L'esempio seguente illustra la logica per la `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>Vedere anche

- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
- [Personalizzazione dei controlli](control-customization.md)
