---
title: Creazione di un controllo dall'aspetto personalizzabile
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
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e76e1d814df5946d0e0f946cbc8d55507a07c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Creazione di un controllo dall'aspetto personalizzabile
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]offre la possibilità di creare un controllo il cui aspetto può essere personalizzato. Ad esempio, è possibile modificare l'aspetto di un <xref:System.Windows.Controls.CheckBox> oltre l'impostazione delle proprietà eseguirà creando un nuovo <xref:System.Windows.Controls.ControlTemplate>. La figura seguente mostra un <xref:System.Windows.Controls.CheckBox> che utilizza un valore predefinito <xref:System.Windows.Controls.ControlTemplate> e un <xref:System.Windows.Controls.CheckBox> che utilizza un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Una casella di controllo con il modello di controllo predefinito. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Oggetto CheckBox che usa il modello del controllo predefinito  
  
 ![Una casella di controllo con un modello di controllo personalizzato. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Oggetto CheckBox che usa un modello del controllo personalizzato  
  
 Se si segue il modello di parti e stati quando si crea un controllo, l'aspetto del controllo sarà personalizzabile. Gli strumenti di progettazione, ad esempio Microsoft Expression Blend supportano il modello di parti e stati, pertanto, quando si segue questo modello del controllo sarà personalizzabile in questi tipi di applicazioni.  In questo argomento viene illustrato il modello di parti e stati e come utilizzarlo quando si crea un controllo personalizzato. In questo argomento viene utilizzato un esempio di un controllo personalizzato, `NumericUpDown`, per illustrare la filosofia di questo modello.  Il `NumericUpDown` controllo consente di visualizzare un valore numerico, che un utente può aumentare o diminuire facendo clic sui pulsanti del controllo.  La figura seguente mostra il `NumericUpDown` controllo illustrato in questo argomento.  
  
 ![Controllo personalizzato NumericUpDown. ] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
Un controllo personalizzato NumericUpDown  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Prerequisiti](#prerequisites)  
  
-   [Modello delle parti e stati](#parts_and_states_model)  
  
-   [Che definisce la struttura visiva e il comportamento di un controllo visivo in un oggetto ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Utilizzo di parti di ControlTemplate nel codice](#using_parts_of_the_controltemplate_in_code)  
  
-   [Fornire il contratto di controllo](#providing_the_control_contract)  
  
-   [Esempio completo](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone di conoscere le procedure creare un nuovo <xref:System.Windows.Controls.ControlTemplate> per un controllo esistente, si ha familiarità con gli elementi di un contratto di controllo e comprendere i concetti illustrati in [personalizzazione dell'aspetto di un controllo esistente da Creazione di ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Per creare un controllo che può disporre di personalizzare l'aspetto, è necessario creare un controllo da cui eredita il <xref:System.Windows.Controls.Control> classe o una delle sue sottoclassi diverso da <xref:System.Windows.Controls.UserControl>.  Un controllo che eredita da <xref:System.Windows.Controls.UserControl> è un controllo che è possibile creare rapidamente, ma non viene utilizzato un <xref:System.Windows.Controls.ControlTemplate> e non è possibile personalizzare l'aspetto.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Modello delle parti e stati  
 Il modello di parti e stati specifica come definire la struttura visiva e il comportamento di un controllo visivo. Per seguire il modello di parti e stati, è necessario eseguire le operazioni seguenti:  
  
-   Definire la struttura e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> di un controllo.  
  
-   Quando la logica del controllo interagisce con parti del modello di controllo, seguire alcune procedure consigliate.  
  
-   Forniscono un controllo per specificare cosa deve essere incluso un contratto di <xref:System.Windows.Controls.ControlTemplate>.  
  
 Quando si definisce la struttura e il comportamento visivo nel <xref:System.Windows.Controls.ControlTemplate> possono modificare la struttura visiva e il comportamento visivo del controllo di un controllo, gli autori dell'applicazione creando un nuovo <xref:System.Windows.Controls.ControlTemplate> anziché scrivere codice.   È necessario fornire agli autori di un contratto di controllo che indica l'applicazione cui <xref:System.Windows.FrameworkElement> gli oggetti e stati devono essere definiti nel <xref:System.Windows.Controls.ControlTemplate>. È necessario seguire alcune procedure consigliate quando si interagisce con le parti nel <xref:System.Windows.Controls.ControlTemplate> in modo che il controllo gestisce correttamente un incompleto <xref:System.Windows.Controls.ControlTemplate>.  Se si seguono queste tre principi, gli autori dell'applicazione sarà in grado di creare un <xref:System.Windows.Controls.ControlTemplate> per il controllo con la stessa facilità con cui possono essere per i controlli che spedite con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Nella sezione seguente viene spiegata ciascuna di queste indicazioni nel dettaglio.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Che definisce la struttura visiva e il comportamento di un controllo visivo in un oggetto ControlTemplate  
 Quando si crea il controllo personalizzato tramite il modello di parti e stati, si definisce il controllo struttura visiva e comportamento visivo nel relativo <xref:System.Windows.Controls.ControlTemplate> invece che nella propria logica.  La struttura visiva di un controllo è formata <xref:System.Windows.FrameworkElement> gli oggetti che costituiscono il controllo.  Il comportamento visivo è il modo in cui che il controllo viene visualizzato quando si trova in un determinato stato.   Per ulteriori informazioni sulla creazione di un <xref:System.Windows.Controls.ControlTemplate> che specifica la struttura visiva e il comportamento visivo di un controllo, vedere [personalizzazione dell'aspetto di un controllo esistente tramite la creazione di ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 Nell'esempio del `NumericUpDown` controllo, la struttura visiva include due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli e un <xref:System.Windows.Controls.TextBlock>.  Se si aggiungono questi controlli nel codice del `NumericUpDown` controllo, nel relativo costruttore, ad esempio le posizioni dei controlli sarebbe modificabile.  Anziché definire il controllo struttura visiva e il comportamento visivo nel codice, è necessario definirli nel <xref:System.Windows.Controls.ControlTemplate>.  Quindi agli sviluppatori di personalizzare la posizione dei pulsanti e <xref:System.Windows.Controls.TextBlock> e specificare il comportamento si verifica quando `Value` è negativo perché la <xref:System.Windows.Controls.ControlTemplate> può essere sostituito.  
  
 L'esempio seguente mostra la struttura visiva del `NumericUpDown` controllo, che include un <xref:System.Windows.Controls.Primitives.RepeatButton> per aumentare `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> per ridurre `Value`e un <xref:System.Windows.Controls.TextBlock> per visualizzare `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Un comportamento di visual il `NumericUpDown` controllo è che il valore è un tipo di carattere rosso se è negativo.  Se si modifica il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> in codice quando il `Value` è negativo, il `NumericUpDown` visualizzerà sempre un valore negativo rosso. Specificare il comportamento del controllo in visual il <xref:System.Windows.Controls.ControlTemplate> aggiungendo <xref:System.Windows.VisualState> oggetti per il <xref:System.Windows.Controls.ControlTemplate>.  Nell'esempio seguente il <xref:System.Windows.VisualState> gli oggetti per il `Positive` e `Negative` stati.  `Positive`e `Negative` (il controllo è sempre esattamente uno dei due) si escludono a vicenda, pertanto nell'esempio viene inserito il <xref:System.Windows.VisualState> oggetti in un unico <xref:System.Windows.VisualStateGroup>.  Quando il controllo entra il `Negative` stato, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> diventa rosso.  Quando il controllo è nel `Positive` stato, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> ritorna al valore originale.  Definizione <xref:System.Windows.VisualState> gli oggetti in un <xref:System.Windows.Controls.ControlTemplate> verrà discussa [personalizzazione dell'aspetto di un controllo esistente tramite la creazione di ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Assicurarsi di impostare il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà nella directory principale associata <xref:System.Windows.FrameworkElement> del <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>Utilizzo di parti di ControlTemplate nel codice  
 Oggetto <xref:System.Windows.Controls.ControlTemplate> autore omettere <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti, intenzionalmente o accidentalmente, ma la logica del controllo potrebbe essere necessario le parti per funzionare correttamente. Il modello di parti e stati specifica che il controllo deve essere resiliente a un <xref:System.Windows.Controls.ControlTemplate> che manca <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> oggetti.  Il controllo non deve generare un'eccezione o segnalare un errore se un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, o <xref:System.Windows.VisualStateGroup> manca il <xref:System.Windows.Controls.ControlTemplate>. In questa sezione vengono descritte le procedure consigliate per l'interazione con <xref:System.Windows.FrameworkElement> oggetti e la gestione degli stati.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Prevedere FrameworkElement oggetti mancanti  
 Quando si definisce <xref:System.Windows.FrameworkElement> gli oggetti di <xref:System.Windows.Controls.ControlTemplate>, la logica del controllo potrebbe essere necessario interagire con alcuni di essi.  Ad esempio, il `NumericUpDown` controllo sottoscrive dei pulsanti <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per aumentare o diminuire `Value` e imposta il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà del <xref:System.Windows.Controls.TextBlock> a `Value`. Se un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> omette il <xref:System.Windows.Controls.TextBlock> o i pulsanti, cui è ammissibile che il controllo perde alcune delle proprie funzionalità, ma è necessario assicurarsi che il controllo non causa un errore. Ad esempio, se un <xref:System.Windows.Controls.ControlTemplate> non contiene i pulsanti per modificare `Value`, `NumericUpDown` perde tale funzionalità, ma un'applicazione che utilizza il <xref:System.Windows.Controls.ControlTemplate> continuerà a essere eseguito.  
  
 Le procedure seguenti garantirà che il controllo risponda correttamente alla mancanza di <xref:System.Windows.FrameworkElement> oggetti:  
  
1.  Impostare il `x:Name` attributo per ogni <xref:System.Windows.FrameworkElement> che è necessario fare riferimento nel codice.  
  
2.  Definire le proprietà private per ogni <xref:System.Windows.FrameworkElement> che è necessario interagire.  
  
3.  Sottoscrivere e annullare la sottoscrizione a tutti gli eventi che gestisce il controllo nel <xref:System.Windows.FrameworkElement> proprietà della funzione di accesso set.  
  
4.  Impostare il <xref:System.Windows.FrameworkElement> proprietà definito nel passaggio 2 di <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> (metodo). Si tratta del primo che il <xref:System.Windows.FrameworkElement> nel <xref:System.Windows.Controls.ControlTemplate> è disponibile per il controllo. Utilizzare il `x:Name` del <xref:System.Windows.FrameworkElement> da ottenere il <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Verificare che il <xref:System.Windows.FrameworkElement> non `null` prima di accedere ai relativi membri.  Se è `null`, non indicano un errore.  
  
 Negli esempi seguenti viene illustrato come la `NumericUpDown` controllo interagisce con <xref:System.Windows.FrameworkElement> oggetti in base alle indicazioni nell'elenco precedente.  
  
 Nell'esempio che definisce la struttura di visual il `NumericUpDown` controllare nel <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton> che aumenta `Value` è relativo `x:Name` attributo impostato su `UpButton`.  Nell'esempio seguente dichiara una proprietà denominata `UpButtonElement` che rappresenta il <xref:System.Windows.Controls.Primitives.RepeatButton> dichiarato nel <xref:System.Windows.Controls.ControlTemplate>. Il `set` innanzitutto Annulla la sottoscrizione della funzione di accesso per il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento se `UpDownElement` non `null`, quindi imposta la proprietà e quindi sottoscrive il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. È inoltre disponibile una proprietà definita, ma non riportati di seguito, per gli altri <xref:System.Windows.Controls.Primitives.RepeatButton>, denominato `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 Nell'esempio seguente il <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per il `NumericUpDown` controllo.  Nell'esempio viene utilizzato il <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> metodo per ottenere il <xref:System.Windows.FrameworkElement> oggetti dal <xref:System.Windows.Controls.ControlTemplate>.  Si noti che nell'esempio viene case in cui <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> trova un <xref:System.Windows.FrameworkElement> con il nome specificato non è del tipo previsto. È inoltre consigliabile ignorare gli elementi che hanno specificato `x:Name` ma sono di tipo errato.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Seguendo le procedure illustrate negli esempi precedenti, verificare che il controllo continuerà l'esecuzione quando il <xref:System.Windows.Controls.ControlTemplate> manca un <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Utilizzare l'oggetto VisualStateManager per gestire gli Stati  
 Il <xref:System.Windows.VisualStateManager> consente di tenere traccia degli stati di un controllo ed esegue la logica necessaria per la transizione tra stati. Quando si aggiunge <xref:System.Windows.VisualState> oggetti per il <xref:System.Windows.Controls.ControlTemplate>, la loro aggiunta a un <xref:System.Windows.VisualStateGroup> e aggiungere il <xref:System.Windows.VisualStateGroup> per il <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> proprietà associata in modo che il <xref:System.Windows.VisualStateManager> può accedervi.  
  
 Nell'esempio seguente si ripete il precedente esempio che illustra il <xref:System.Windows.VisualState> gli oggetti che corrisponde alla `Positive` e `Negative` stati del controllo. Il <xref:System.Windows.Media.Animation.Storyboard> nel `Negative` <xref:System.Windows.VisualState> attiva il <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> rosso.   Quando il `NumericUpDown` controllo si trova nella `Negative` stato, lo storyboard nel `Negative` stato inizia.  Il <xref:System.Windows.Media.Animation.Storyboard> nel `Negative` stato si interrompe quando il controllo viene restituito il `Positive` dello stato.  Il `Positive` <xref:System.Windows.VisualState> non deve contenere un <xref:System.Windows.Media.Animation.Storyboard> perché quando il <xref:System.Windows.Media.Animation.Storyboard> per il `Negative` si arresta, il <xref:System.Windows.Controls.TextBlock.Foreground%2A> restituisce al colore originale.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Si noti che il <xref:System.Windows.Controls.TextBlock> viene assegnato un nome, ma la <xref:System.Windows.Controls.TextBlock> non è incluso nel contratto di controllo per `NumericUpDown` poiché la logica del controllo non fa riferimento il <xref:System.Windows.Controls.TextBlock>.  Gli elementi che fanno riferimento al <xref:System.Windows.Controls.ControlTemplate> hanno nomi, ma non è necessario far parte del contratto di controllo perché un nuovo <xref:System.Windows.Controls.ControlTemplate> per il controllo non potrebbe essere necessario fare riferimento a tale elemento.  Ad esempio, un utente che crea un nuovo <xref:System.Windows.Controls.ControlTemplate> per `NumericUpDown` potrebbe decidere di non indicano che `Value` è negativo, modificando il <xref:System.Windows.Controls.Control.Foreground%2A>.  In questo caso, né il codice né la <xref:System.Windows.Controls.ControlTemplate> riferimenti di <xref:System.Windows.Controls.TextBlock> in base al nome.  
  
 La logica del controllo è responsabile della modifica dello stato del controllo. Nell'esempio seguente viene illustrato che il `NumericUpDown` chiamate di controllo di <xref:System.Windows.VisualStateManager.GoToState%2A> metodo per iniziare il `Positive` stato quando `Value` è 0 o maggiore e il `Negative` stato quando `Value` è minore di 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Il <xref:System.Windows.VisualStateManager.GoToState%2A> metodo esegue la logica necessaria per avviare e interrompere lo storyboard in modo appropriato. Quando un controllo chiama <xref:System.Windows.VisualStateManager.GoToState%2A> di modifica dello stato, il <xref:System.Windows.VisualStateManager> esegue le operazioni seguenti:  
  
-   Se il <xref:System.Windows.VisualState> che sta per il controllo ha un <xref:System.Windows.Media.Animation.Storyboard>, lo storyboard viene avviato. Quindi, se il <xref:System.Windows.VisualState> è che il controllo proviene da un <xref:System.Windows.Media.Animation.Storyboard>, lo storyboard verrà interrotto.  
  
-   Se il controllo è già nello stato in cui è specificato, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue azioni né restituisce `true`.  
  
-   Se lo stato specificato non esiste nel <xref:System.Windows.Controls.ControlTemplate> di `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue azioni né restituisce `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Procedure consigliate per l'utilizzo dell'oggetto VisualStateManager  
 È consigliabile eseguire il comando seguente per mantenere gli stati del controllo:  
  
-   Usare le proprietà per rilevare lo stato.  
  
-   Creare un metodo di supporto per la transizione tra stati.  
  
 Il `NumericUpDown` controlli utilizza relativo `Value` proprietà da rilevare se è attiva la `Positive` o `Negative` stato.  Il `NumericUpDown` controllo definisce anche la `Focused` e `UnFocused` indicato, le tracce di <xref:System.Windows.UIElement.IsFocused%2A> proprietà. Se si utilizzano gli Stati che naturalmente non corrispondono a una proprietà del controllo, è possibile definire una proprietà privata per tenere traccia dello stato.  
  
 Centralizza le chiamate a un unico metodo che consente di aggiornare tutti gli stati di <xref:System.Windows.VisualStateManager> e mantenere gestibile il codice. Nell'esempio seguente il `NumericUpDown` metodo di supporto del controllo, `UpdateStates`. Quando `Value` è maggiore o uguale a 0, il <xref:System.Windows.Controls.Control> è il `Positive` dello stato.  Quando `Value` è minore di 0, il controllo è nel `Negative` dello stato.  Quando <xref:System.Windows.UIElement.IsFocused%2A> è `true`, il controllo è nel `Focused` stato; in caso contrario, è il `Unfocused` dello stato.  Il controllo può chiamare `UpdateStates` ogni volta che è necessario modificare lo stato, indipendentemente dal fatto di stato che viene modificato.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Se si passa un nome di stato a <xref:System.Windows.VisualStateManager.GoToState%2A> quando il controllo è già in tale stato, <xref:System.Windows.VisualStateManager.GoToState%2A> non esegue alcuna operazione, in modo che non è necessario verificare la presenza di stato corrente del controllo.  Ad esempio, se `Value` cambia da un numero negativo per un altro numero negativo, lo storyboard per il `Negative` stato non è stato interrotto e l'utente non verrà visualizzata una modifica nel controllo.  
  
 Il <xref:System.Windows.VisualStateManager> Usa <xref:System.Windows.VisualStateGroup> gli oggetti per determinare lo stato per uscire dall'installazione quando si chiama <xref:System.Windows.VisualStateManager.GoToState%2A>. Il controllo è sempre in uno stato per ogni <xref:System.Windows.VisualStateGroup> definita nel relativo <xref:System.Windows.Controls.ControlTemplate> lasciando solo uno stato quando entra in un altro stato dallo stesso <xref:System.Windows.VisualStateGroup>. Ad esempio, il <xref:System.Windows.Controls.ControlTemplate> del `NumericUpDown` controllo definisce il `Positive` e `Negative` <xref:System.Windows.VisualState> gli oggetti in uno <xref:System.Windows.VisualStateGroup> e `Focused` e `Unfocused` <xref:System.Windows.VisualState> oggetti in un altro. (È possibile visualizzare il `Focused` e `Unfocused` <xref:System.Windows.VisualState> definito nel [esempio completo](#complete_example) in questo argomento quando il controllo esce dal `Positive` allo stato di `Negative` stato, o viceversa, il è il `Focused` o `Unfocused` stato.  
  
 Esistono tre posizioni tipico in cui è possibile modificare lo stato di un controllo:  
  
-   Quando il <xref:System.Windows.Controls.ControlTemplate> è collegato il <xref:System.Windows.Controls.Control>.  
  
-   Quando viene modificata una proprietà.  
  
-   Quando si verifica un evento.  
  
 Gli esempi seguenti illustrano l'aggiornamento dello stato del `NumericUpDown` controllo in questi casi.  
  
 È necessario aggiornare lo stato del controllo nel <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> metodo in modo che il controllo viene visualizzato il corretto stato quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato. L'esempio seguente chiama `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> per garantire che il controllo è negli stati appropriati.  Ad esempio, si supponga di creare un `NumericUpDown` e quindi impostare il relativo <xref:System.Windows.Controls.Control.Foreground%2A> verde e `Value` a -5.  Se non si chiama `UpdateStates` quando il <xref:System.Windows.Controls.ControlTemplate> viene applicato al `NumericUpDown` (controllo), il controllo non è nel `Negative` lo stato e il valore è di colore verde anziché rosso.  È necessario chiamare `UpdateStates` per inserire il controllo `Negative` dello stato.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 È spesso necessario aggiornare gli stati di un controllo quando una proprietà cambia. Nell'esempio seguente viene illustrato l'intero `ValueChangedCallback` metodo. Poiché `ValueChangedCallback` viene chiamato quando `Value` cambia, le chiamate al metodo `UpdateStates` nel caso in cui `Value` cambia da positivo a negativo o viceversa. È possibile chiamare `UpdateStates` quando `Value` cambia ma rimane positivo o negativo in quanto in tal caso, il controllo non verrà modificato gli stati.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 È inoltre potrebbe essere necessario aggiornare gli stati quando si verifica un evento. Nell'esempio seguente viene illustrato che il `NumericUpDown` chiamate `UpdateStates` sul <xref:System.Windows.Controls.Control> per gestire il <xref:System.Windows.UIElement.GotFocus> evento.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 Il <xref:System.Windows.VisualStateManager> consente di gestire gli stati del controllo. Tramite il <xref:System.Windows.VisualStateManager>, assicurarsi che il controllo correttamente transizione tra stati.  Seguire le indicazioni descritte in questa sezione per l'utilizzo di <xref:System.Windows.VisualStateManager>, il codice del controllo rimane leggibile e conservabile.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Fornire il contratto di controllo  
 Fornire un contratto di controllo in modo che <xref:System.Windows.Controls.ControlTemplate> riconoscerà gli autori degli elementi da inserire nel modello. Un contratto di controllo include tre elementi:  
  
-   Gli elementi visivi usati dalla logica del controllo.  
  
-   Gli stati del controllo e il gruppo a cui appartiene ogni stato.  
  
-   Le proprietà pubbliche che influiscono visivamente sul controllo.  
  
 Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate> è necessario conoscere <xref:System.Windows.FrameworkElement> gli oggetti utilizzati dalla logica del controllo, è il tipo di ogni oggetto e il relativo nome. Oggetto <xref:System.Windows.Controls.ControlTemplate> autore deve inoltre conoscere il nome di ogni possibile stato può essere il controllo e quali <xref:System.Windows.VisualStateGroup> lo stato è.  
  
 Restituire il `NumericUpDown` prevede che il controllo di esempio, il <xref:System.Windows.Controls.ControlTemplate> siano gli elementi seguenti <xref:System.Windows.FrameworkElement> oggetti:  
  
-   Oggetto <xref:System.Windows.Controls.Primitives.RepeatButton> chiamato `UpButton`.  
  
-   Oggetto <xref:System.Windows.Controls.Primitives.RepeatButton> chiamato`DownButton.`  
  
 Il controllo può essere degli stati seguenti:  
  
-   Nel`ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   Nel`FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Per specificare quali <xref:System.Windows.FrameworkElement> prevede che il controllo di oggetti, si utilizza il <xref:System.Windows.TemplatePartAttribute>, che consente di specificare il nome e il tipo degli elementi previsti.  Per specificare gli stati possibili di un controllo, utilizzare il <xref:System.Windows.TemplateVisualStateAttribute>, che specifica il nome dello stato e che <xref:System.Windows.VisualStateGroup> a cui appartiene.  Inserire il <xref:System.Windows.TemplatePartAttribute> e <xref:System.Windows.TemplateVisualStateAttribute> nella definizione di classe del controllo.  
  
 Inoltre, qualsiasi proprietà pubblica che influisce sull'aspetto del controllo è una parte del contratto di controllo.  
  
 Nell'esempio seguente viene specificato il <xref:System.Windows.FrameworkElement> oggetto e stati per il `NumericUpDown` controllo.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Esempio completo  
 L'esempio seguente è l'intero <xref:System.Windows.Controls.ControlTemplate> per il `NumericUpDown` controllo.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 Nell'esempio seguente viene illustrata la logica per il `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)
