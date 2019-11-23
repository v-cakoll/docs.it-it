---
title: Cenni preliminari sull'input
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [WPF]
- input [WPF], overview
- keyboard focus [WPF]
- keyboard input [WPF]
- touch events [WPF]
- event routing [WPF]
- touch input [WPF]
- manipulation [WPF]
- logical focus [WPF]
- stylus input [WPF]
- text input [WPF]
- input events [WPF], handling
- WPF [WPF], input overview
- manipulation events [WPF]
- mouse input [WPF]
- mouse capture [WPF]
- focus [WPF]
- mouse position [WPF]
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
ms.openlocfilehash: a90c74542c1a6604ed27d37f882385b67402dd92
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005022"
---
# <a name="input-overview"></a>Cenni preliminari sull'input
<a name="introduction"></a>Il sottosistema [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un'API potente per ottenere input da un'ampia gamma di dispositivi, tra cui mouse, tastiera, tocco e stilo. Questo argomento descrive i servizi forniti da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e illustra l'architettura dei sistemi di input.

<a name="input_api"></a>
## <a name="input-api"></a>API di input
 L'esposizione dell'API di input primaria si trova nelle classi degli elementi di base: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>e <xref:System.Windows.FrameworkContentElement>.  Per altre informazioni sugli elementi di base, vedere [Cenni preliminari sugli elementi di base](base-elements-overview.md).  Queste classi forniscono funzionalità per gli eventi di input correlati, ad esempio, a pressioni di tasti, pulsanti del mouse, rotellina del mouse, movimento del mouse, gestione dello stato attivo, stato mouse capture e altro. Inserendo l'API di input sugli elementi di base, invece di considerare tutti gli eventi di input come un servizio, l'architettura di input consente di originare gli eventi di input da un determinato oggetto nell'interfaccia utente e di supportare uno schema di routing degli eventi in base al quale più di un elemento dispone di un opp ortunity per la gestione di un evento di input. A molti eventi di input è associata una coppia di eventi.  Ad esempio, l'evento di riduzione della chiave è associato agli eventi <xref:System.Windows.Input.Keyboard.KeyDown> e <xref:System.Windows.Input.Keyboard.PreviewKeyDown>.  La differenza tra questi eventi consiste nel modo in cui ne viene eseguito il routing all'elemento di destinazione.  Gli eventi di anteprima scendono lungo l'albero degli elementi (tunneling), dall'elemento radice all'elemento di destinazione.  Gli eventi di bubbling invece salgono dall'elemento di destinazione all'elemento radice.  Il routing degli eventi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è illustrato in modo più dettagliato più avanti in questo articolo e nell'articolo [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).

### <a name="keyboard-and-mouse-classes"></a>Classi Keyboard e Mouse
 Oltre all'API di input sulle classi degli elementi di base, le classi <xref:System.Windows.Input.Keyboard> Class e <xref:System.Windows.Input.Mouse> forniscono un'API aggiuntiva per lavorare con l'input della tastiera e del mouse.

 Esempi di API di input nella classe <xref:System.Windows.Input.Keyboard> sono la proprietà <xref:System.Windows.Input.Keyboard.Modifiers%2A>, che restituisce il <xref:System.Windows.Input.ModifierKeys> attualmente premuto e il metodo <xref:System.Windows.Input.Keyboard.IsKeyDown%2A>, che determina se viene premuto un tasto specificato.

 Nell'esempio seguente viene usato il metodo <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> per determinare se una <xref:System.Windows.Input.Key> è nello stato di inattività.

 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]

 Gli esempi di API di input nella classe <xref:System.Windows.Input.Mouse> sono <xref:System.Windows.Input.Mouse.MiddleButton%2A>, che ottiene lo stato del pulsante centrale del mouse e <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, che ottiene l'elemento sul quale si trova attualmente il puntatore del mouse.

 Nell'esempio seguente viene determinato se il <xref:System.Windows.Input.Mouse.LeftButton%2A> sul mouse si trova nello stato <xref:System.Windows.Input.MouseButtonState.Pressed>.

 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](~/samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]

 Le classi <xref:System.Windows.Input.Mouse> e <xref:System.Windows.Input.Keyboard> sono descritte in dettaglio in questa panoramica.

### <a name="stylus-input"></a>Input dello stilo
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone del supporto integrato per l'<xref:System.Windows.Input.Stylus>.  Il <xref:System.Windows.Input.Stylus> è un input penna reso popolare dal Tablet PC.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni possono trattare lo stilo come mouse tramite l'API del mouse, ma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espone anche un'astrazione del dispositivo stilo che utilizza un modello simile a quello della tastiera e del mouse.  Tutte le API correlate allo stilo contengono la parola "stilo".

 Dal momento che lo stilo può funzionare come un mouse, le applicazioni che supportano solo l'input del mouse possono comunque ottenere automaticamente un certo livello di supporto dello stilo. Quando lo stilo viene usato in questo modo, l'applicazione può gestire l'evento dello stilo appropriato gestendo l'evento del mouse corrispondente. Inoltre, tramite l'astrazione del dispositivo stilo, sono disponibili anche servizi di livello superiore, come l'input penna.  Per altre informazioni sull'input penna, vedere [Nozioni di base sull'input penna](getting-started-with-ink.md).

<a name="event_routing"></a>
## <a name="event-routing"></a>Routing di eventi
 Un <xref:System.Windows.FrameworkElement> può contenere altri elementi come elementi figlio nel relativo modello di contenuto, formando una struttura ad albero di elementi.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'elemento padre può partecipare all'input diretto verso i relativi elementi figlio o agli altri discendenti mediante la gestione degli eventi. Ciò risulta particolarmente utile per la creazione di controlli a partire da controlli più piccoli, processo noto come "composizione di controlli" o "composizione". Per altre informazioni sugli alberi degli elementi e sulla loro relazione con le route degli eventi, vedere [Strutture ad albero in WPF](trees-in-wpf.md).

 Il routing degli eventi è il processo di inoltro degli eventi a più elementi, in modo che un oggetto o un elemento specifico lungo la route possa offrire una risposta significativa (tramite la gestione) a un evento che potrebbe essere stato originato da un elemento diverso.  Gli eventi indirizzati usano uno dei tre meccanismi di routing indicati di seguito: diretto, bubbling e tunneling.  Nel routing diretto, l'elemento di origine è l'unico elemento che riceve la notifica e l'evento non viene indirizzato a nessun altro elemento. Tuttavia, l'evento indirizzato diretto offre ancora alcune funzionalità aggiuntive che sono presenti solo per gli eventi indirizzati anziché per gli eventi CLR standard. Il bubbling viene eseguito procedendo verso l'alto nell'albero degli elementi, notificando innanzitutto l'elemento che ha originato l'evento, quindi l'elemento padre e così via.  Il tunneling parte dalla radice dell'albero degli elementi e procede verso il basso, terminando con l'elemento di origine.  Per altre informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).

 Gli eventi di input [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono in genere a coppie, costituite da un evento di tunneling e un evento di bubbling.  Gli eventi di tunneling si distinguono da quelli di bubbling tramite il prefisso "Preview".  Ad esempio, <xref:System.Windows.Input.Mouse.PreviewMouseMove> è la versione di tunneling di un evento di spostamento del mouse e <xref:System.Windows.Input.Mouse.MouseMove> è la versione di bubbling di questo evento. Questa coppia di eventi è una convenzione implementata a livello di elemento e non è una funzionalità intrinseca del sistema di eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per informazioni dettagliate, vedere la sezione Eventi di input WPF in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).

<a name="handling_input_events"></a>
## <a name="handling-input-events"></a>Gestione degli eventi di input
 Per ricevere input su un elemento, un gestore eventi deve essere associato a quel particolare evento.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tale associazione è semplice: è sufficiente fare riferimento al nome dell'evento come attributo dell'elemento che rimarrà in ascolto di questo evento.  Si imposta quindi il valore dell'attributo sul nome del gestore eventi definito, in base a un delegato.  Il gestore eventi deve essere scritto in codice, ad C# esempio e, può essere incluso in un file code-behind.

 Gli eventi della tastiera si verificano quando il sistema operativo segnala azioni dei tasti eseguite quando lo stato attivo della tastiera è su un elemento. Gli eventi del mouse e dello stilo rientrano ciascuno in due categorie: eventi che segnalano modifiche nella posizione del puntatore rispetto all'elemento ed eventi che segnalano modifiche nello stato dei pulsanti del dispositivo.

### <a name="keyboard-input-event-example"></a>Esempio di evento di input da tastiera
 L'esempio seguente illustra una situazione di ascolto della pressione del tasto freccia SINISTRA.  Viene creato un <xref:System.Windows.Controls.StackPanel> con una <xref:System.Windows.Controls.Button>.  Un gestore eventi per restare in attesa della pressione del tasto freccia sinistra viene collegato all'istanza di <xref:System.Windows.Controls.Button>.

 Nella prima sezione dell'esempio vengono creati il <xref:System.Windows.Controls.StackPanel> e il <xref:System.Windows.Controls.Button> e viene collegato il gestore eventi per il <xref:System.Windows.UIElement.KeyDown>.

 [!code-xaml[InputOvw#Input_OvwKeyboardExampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]

 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]

 La seconda sezione è scritta nel codice e definisce il gestore eventi.  Quando viene premuto il tasto freccia sinistra e il <xref:System.Windows.Controls.Button> dispone dello stato attivo della tastiera, il gestore viene eseguito e il colore <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato.  Se il tasto è premuto, ma non è il tasto freccia sinistra, il colore <xref:System.Windows.Controls.Control.Background%2A> della <xref:System.Windows.Controls.Button> viene nuovamente modificato sul colore iniziale.

 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]

### <a name="mouse-input-event-example"></a>Esempio di evento di input del mouse
 Nell'esempio seguente, il colore <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button> viene modificato quando il puntatore del mouse entra nell'<xref:System.Windows.Controls.Button>.  Il colore <xref:System.Windows.Controls.Control.Background%2A> viene ripristinato quando il mouse esce dall'<xref:System.Windows.Controls.Button>.

 La prima sezione dell'esempio crea il <xref:System.Windows.Controls.StackPanel> e il controllo <xref:System.Windows.Controls.Button> e connette i gestori eventi per gli eventi <xref:System.Windows.UIElement.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave> al <xref:System.Windows.Controls.Button>.

 [!code-xaml[InputOvw#Input_OvwMouseExampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]

 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]

 La seconda sezione dell'esempio è scritta nel codice e definisce i gestori eventi.  Quando il mouse entra nel <xref:System.Windows.Controls.Button>, il colore <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato in <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Quando il mouse esce dalla <xref:System.Windows.Controls.Button>, il colore <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene nuovamente modificato in <xref:System.Windows.Media.Brushes.AliceBlue%2A>.

 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]

 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]

<a name="text_input"></a>
## <a name="text-input"></a>Input di testo
 L'evento <xref:System.Windows.ContentElement.TextInput> consente di ascoltare l'input di testo in modo indipendente dal dispositivo. La tastiera è il mezzo principale per l'immissione di testo, ma anche i comandi vocali, il riconoscimento della grafia e altri dispositivi di input possono generare input di testo.

 Per l'input da tastiera, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] invia prima gli eventi <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> appropriati. Se tali eventi non vengono gestiti e la chiave è testuale, anziché una chiave di controllo come frecce direzionali o tasti funzione, viene generato un evento <xref:System.Windows.ContentElement.TextInput>.  Non è sempre presente un semplice mapping uno-a-uno tra <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> e <xref:System.Windows.ContentElement.TextInput> eventi perché più sequenze di tasti possono generare un singolo carattere di input di testo e le singole sequenze di tasti possono generare stringhe multicarattere.  Ciò vale soprattutto per le lingue quali il cinese, il giapponese e il coreano che usano IME (Input Method Editor) per generare le migliaia di caratteri possibili negli alfabeti corrispondenti.

 Quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Invia un evento <xref:System.Windows.ContentElement.KeyUp>/<xref:System.Windows.ContentElement.KeyDown>, <xref:System.Windows.Input.KeyEventArgs.Key%2A> viene impostato su <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> se le sequenze di tasti potrebbero far parte di un evento <xref:System.Windows.ContentElement.TextInput> (ad esempio, se si preme ALT + S). Ciò consente al codice in un gestore dell'evento <xref:System.Windows.ContentElement.KeyDown> di verificare la presenza di <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> e, se presente, di lasciare l'elaborazione per il gestore dell'evento di <xref:System.Windows.ContentElement.TextInput> generato successivamente. In questi casi, è possibile usare le varie proprietà dell'argomento <xref:System.Windows.Input.TextCompositionEventArgs> per determinare le sequenze di tasti originali. Analogamente, se un IME è attivo, <xref:System.Windows.Input.Key> ha il valore di <xref:System.Windows.Input.Key.ImeProcessed?displayProperty=nameWithType>e <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> fornisce la sequenza di tasti originale o le sequenze di tasti.

 Nell'esempio seguente viene definito un gestore per l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> e un gestore per l'evento <xref:System.Windows.UIElement.KeyDown>.

 Il primo segmento di codice o markup crea l'interfaccia utente.

 [!code-xaml[InputOvw#Input_OvwTextInputXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]

 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]

 Il secondo segmento di codice contiene i gestori eventi.

 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]

 Poiché gli eventi di input compongono la route dell'evento, il <xref:System.Windows.Controls.StackPanel> riceve l'input indipendentemente dall'elemento con lo stato attivo della tastiera. Il controllo <xref:System.Windows.Controls.TextBox> viene notificato per primo e viene chiamato il gestore `OnTextInputKeyDown` solo se il <xref:System.Windows.Controls.TextBox> non ha gestito l'input. Se viene utilizzato l'evento <xref:System.Windows.UIElement.PreviewKeyDown> al posto dell'evento <xref:System.Windows.UIElement.KeyDown>, viene chiamato per primo il gestore di `OnTextInputKeyDown`.

 In questo esempio la logica di gestione viene scritta due volte, una per CTRL+O e una per l'evento Click del pulsante. È possibile semplificare questa operazione usando i comandi, invece di gestire direttamente gli eventi di input.  I comandi vengono illustrati in questo articolo e in [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).

<a name="touch_and_manipulation"></a>
## <a name="touch-and-manipulation"></a>Tocco e manipolazione
 Il nuovo hardware e le nuove API del sistema operativo Windows 7 consentono alle applicazioni di ricevere contemporaneamente input da più tocchi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente alle applicazioni di rilevare il tocco e rispondere in un modo simile alle risposte ad altri tipi di input, ad esempio di mouse o tastiera, generando eventi quando si verifica il tocco.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espone due tipi di eventi quando si verifica il tocco: eventi di tocco ed eventi di manipolazione. Gli eventi di tocco forniscono dati non elaborati relativi a ogni dito appoggiato su un touchscreen e al suo movimento. Gli eventi di manipolazione interpretano l'input come azioni specifiche. Questa sezione illustra entrambi i tipi di eventi.

### <a name="prerequisites"></a>Prerequisites
 Per sviluppare un'applicazione che risponde al tocco, sono necessari i componenti seguenti.

- Visual Studio 2010.

- Windows 7.

- Un dispositivo, ad esempio un touchscreen, che supporta Windows Touch.

### <a name="terminology"></a>Terminologia
 Quando si parla di tocco, vengono usati i termini seguenti.

- **Tocco** è un tipo di input dell'utente riconosciuto da Windows 7. In genere, il tocco viene generato appoggiando le dita su uno schermo sensibile al tocco. Si noti che dispositivi come i touchpad, diffusi sui computer portatili, non supportano il tocco se il dispositivo si limita a convertire la posizione e il movimento del dito come input del mouse.

- **Multitocco** è un tocco che si verifica in più punti contemporaneamente. Windows 7 e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supportano l'input multitocco. Ogni volta che il tocco viene trattato nella documentazione relativa a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], i concetti illustrati si applicano al multitocco.

- Una **manipolazione** si verifica quando il tocco viene interpretato come azione fisica applicata a un oggetto. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli eventi di manipolazione interpretano l'input come una manipolazione di traslazione, espansione o rotazione.

- Un `touch device` rappresenta un dispositivo che produce un input tocco, ad esempio un singolo dito su un touchscreen.

### <a name="controls-that-respond-to-touch"></a>Controlli che rispondono al tocco
 È possibile scorrere i controlli seguenti trascinando un dito attraverso il controllo, se c'è contenuto non visualizzato.

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.ContextMenu>

- <xref:System.Windows.Controls.DataGrid>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListView>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.TextBox>

- <xref:System.Windows.Controls.ToolBar>

- <xref:System.Windows.Controls.TreeView>

 Il <xref:System.Windows.Controls.ScrollViewer> definisce la proprietà associata <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=nameWithType> che consente di specificare se il panning tocco è abilitato orizzontalmente, verticalmente, entrambi o nessuno dei due. La proprietà <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=nameWithType> specifica la velocità con cui lo scorrimento rallenta quando l'utente solleva il dito dal touchscreen. Il <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=nameWithType> proprietà associata specifica il rapporto tra offset di scorrimento e offset di modifica della conversione.

### <a name="touch-events"></a>Eventi di tocco
 Le classi base, <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>e <xref:System.Windows.ContentElement>definiscono gli eventi che è possibile sottoscrivere, in modo che l'applicazione possa rispondere al tocco. Gli eventi di tocco sono utili quando l'applicazione interpreta il tocco come qualcosa di diverso rispetto alla manipolazione di un oggetto. Un'applicazione che consente a un utente di disegnare con un dito o con più dita deve ad esempio sottoscrivere gli eventi di tocco.

 Tutte tre le classi definiscono gli eventi seguenti, che hanno un comportamento simile, indipendentemente dalla classe che li definisce.

- <xref:System.Windows.UIElement.TouchDown>

- <xref:System.Windows.UIElement.TouchMove>

- <xref:System.Windows.UIElement.TouchUp>

- <xref:System.Windows.UIElement.TouchEnter>

- <xref:System.Windows.UIElement.TouchLeave>

- <xref:System.Windows.UIElement.PreviewTouchDown>

- <xref:System.Windows.UIElement.PreviewTouchMove>

- <xref:System.Windows.UIElement.PreviewTouchUp>

- <xref:System.Windows.UIElement.GotTouchCapture>

- <xref:System.Windows.UIElement.LostTouchCapture>

 Analogamente agli eventi di tastiera e mouse, gli eventi di tocco sono eventi indirizzati. Gli eventi che iniziano con `Preview` sono eventi di tunneling e gli eventi che iniziano con `Touch` sono eventi di bubbling. Per altre informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md). Quando si gestiscono questi eventi, è possibile ottenere la posizione dell'input, relativa a qualsiasi elemento, chiamando il metodo <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> o <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A>.

 Per comprendere l'interazione tra gli eventi di tocco, si consideri lo scenario in cui un utente appoggia un dito su un elemento, muove il dito all'interno dell'elemento e quindi solleva il dito dall'elemento. La figura seguente illustra l'esecuzione degli eventi di bubbling. Gli eventi di tunneling vengono omessi per maggiore semplicità.

 ![Sequenza di eventi di tocco.](./media/ndp-touchevents.png "NDP_TouchEvents") Eventi di tocco

 L'elenco seguente descrive la sequenza degli eventi della figura precedente.

1. L'evento <xref:System.Windows.UIElement.TouchEnter> si verifica una volta quando l'utente inserisce un dito sull'elemento.

2. L'evento <xref:System.Windows.UIElement.TouchDown> si verifica una volta.

3. L'evento <xref:System.Windows.UIElement.TouchMove> si verifica più volte quando l'utente sposta il dito all'interno dell'elemento.

4. L'evento <xref:System.Windows.UIElement.TouchUp> si verifica una volta quando l'utente solleva il dito dall'elemento.

5. L'evento <xref:System.Windows.UIElement.TouchLeave> si verifica una volta.

 Quando vengono usate più di due dita, gli eventi si verificano per ogni dito.

### <a name="manipulation-events"></a>Eventi di manipolazione
 Per i casi in cui un'applicazione consente a un utente di modificare un oggetto, la classe <xref:System.Windows.UIElement> definisce gli eventi di manipolazione. A differenza degli eventi di tocco che segnalano semplicemente la posizione del tocco, gli eventi di manipolazione segnalano come può essere interpretato l'input. Ci sono tre tipi di manipolazioni: traslazione, espansione e rotazione. L'elenco seguente descrive come richiamare i tre tipi di manipolazioni.

- Appoggiare un dito su un oggetto e muovere il dito sul touchscreen per richiamare una manipolazione di traslazione. Ciò comporta in genere lo spostamento dell'oggetto.

- Appoggiare due dita su un oggetto e avvicinare o allontanare le dita tra loro per richiamare una manipolazione di espansione. Ciò comporta in genere il ridimensionamento dell'oggetto.

- Appoggiare due dita su un oggetto e ruotare le dita una attorno all'altra per richiamare una manipolazione di rotazione. Ciò comporta in genere la rotazione dell'oggetto.

 Si possono verificare più tipi di manipolazioni contemporaneamente.

 Quando gli oggetti rispondono alle manipolazioni, si può fare in modo che sembrino avere un'inerzia. In questo modo, gli oggetti possono simulare il mondo fisico. Ad esempio se si spinge un libro su un tavolo con sufficiente forza, il libro continuerà a muoversi anche dopo che lo si lascia. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di simulare questo comportamento generando eventi di manipolazione dopo che le dita dell'utente rilasciano l'oggetto.

 Per informazioni su come creare un'applicazione che consente all'utente di spostare, ridimensionare e ruotare un oggetto, vedere [Procedura dettagliata: creazione della prima applicazione a tocco](walkthrough-creating-your-first-touch-application.md).

 Il <xref:System.Windows.UIElement> definisce gli eventi di manipolazione seguenti.

- <xref:System.Windows.UIElement.ManipulationStarting>

- <xref:System.Windows.UIElement.ManipulationStarted>

- <xref:System.Windows.UIElement.ManipulationDelta>

- <xref:System.Windows.UIElement.ManipulationInertiaStarting>

- <xref:System.Windows.UIElement.ManipulationCompleted>

- <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>

 Per impostazione predefinita, un <xref:System.Windows.UIElement> non riceve questi eventi di manipolazione. Per ricevere eventi di manipolazione in un <xref:System.Windows.UIElement>, impostare <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=nameWithType> su `true`.

#### <a name="the-execution-path-of-manipulation-events"></a>Percorso di esecuzione degli eventi di manipolazione
 Si consideri uno scenario in cui un utente "lancia" un oggetto. L'utente appoggia un dito sull'oggetto, sposta il dito sul touchscreen per un breve tratto e quindi solleva il dito mentre l'oggetto si sta muovendo. Il risultato di questa azione è che l'oggetto si muoverà sotto il dito dell'utente e continuerà a muoversi dopo che l'utente ha sollevato il dito.

 La figura seguente mostra il percorso di esecuzione degli eventi di manipolazione, con informazioni importanti relative a ogni evento.

 ![Sequenza di eventi di manipolazione.](./media/ndp-manipulationevents.png "NDP_ManipulationEvents") Eventi di manipolazione

 L'elenco seguente descrive la sequenza degli eventi della figura precedente.

1. L'evento <xref:System.Windows.UIElement.ManipulationStarting> si verifica quando l'utente posiziona un dito sull'oggetto. Tra le altre cose, questo evento consente di impostare la proprietà <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. Negli eventi successivi la posizione della manipolazione sarà relativa all'<xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. In eventi diversi da <xref:System.Windows.UIElement.ManipulationStarting>questa proprietà è di sola lettura, pertanto l'evento <xref:System.Windows.UIElement.ManipulationStarting> è l'unico momento in cui è possibile impostare questa proprietà.

2. L'evento <xref:System.Windows.UIElement.ManipulationStarted> si verifica successivamente. Questo evento segnala l'origine della manipolazione.

3. L'evento <xref:System.Windows.UIElement.ManipulationDelta> si verifica più volte quando il dito di un utente si sposta su un touchscreen. La proprietà <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> della classe <xref:System.Windows.Input.ManipulationDeltaEventArgs> indica se la manipolazione viene interpretata come spostamento, espansione o traduzione. In questo contesto si esegue la maggior parte del lavoro di manipolazione di un oggetto.

4. L'evento <xref:System.Windows.UIElement.ManipulationInertiaStarting> si verifica quando le dita dell'utente perdono il contatto con l'oggetto. Questo evento consente di specificare la decelerazione delle manipolazioni durante l'inerzia. In questo modo, l'oggetto può emulare spazi fisici o attribuiti diversi, se si desidera. Si supponga, ad esempio, che l'applicazione includa due oggetti che rappresentano elementi nel mondo fisico e che uno di questi sia più pesante dell'altro. È possibile fare in modo che l'oggetto più pesante rallenti più velocemente rispetto a quello più leggero.

5. L'evento <xref:System.Windows.UIElement.ManipulationDelta> si verifica più volte quando si verifica un'inerzia. Si noti che questo evento si verifica quando le dita dell'utente si muovono sul touchscreen e quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] simula l'inerzia. In altre parole, <xref:System.Windows.UIElement.ManipulationDelta> si verifica prima e dopo l'evento <xref:System.Windows.UIElement.ManipulationInertiaStarting>. La proprietà <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=nameWithType> segnala se l'evento <xref:System.Windows.UIElement.ManipulationDelta> si verifica durante l'inerzia, quindi è possibile controllare tale proprietà ed eseguire azioni diverse, a seconda del valore.

6. L'evento <xref:System.Windows.UIElement.ManipulationCompleted> si verifica al termine della manipolazione e di qualsiasi inerzia. Ciò significa che, dopo che si sono verificati tutti gli eventi <xref:System.Windows.UIElement.ManipulationDelta>, viene generato l'evento <xref:System.Windows.UIElement.ManipulationCompleted> per segnalare che la manipolazione è stata completata.

 Il <xref:System.Windows.UIElement> definisce anche l'evento <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>. Questo evento si verifica quando viene chiamato il metodo <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> nell'evento <xref:System.Windows.UIElement.ManipulationDelta>. L'evento <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> consente alle applicazioni o ai componenti di fornire feedback visivo quando un oggetto raggiunge un limite. Ad esempio, la classe <xref:System.Windows.Window> gestisce l'evento <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> per far sì che la finestra si sposti leggermente quando viene rilevato il bordo.

 È possibile annullare la manipolazione chiamando il metodo <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> sugli argomenti dell'evento in qualsiasi evento di manipolazione eccetto <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> evento. Quando si chiama <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, gli eventi di manipolazione non vengono più generati e si verificano gli eventi del mouse per il tocco. La tabella seguente descrive la relazione tra il momento in cui viene annullata la manipolazione e gli eventi del mouse che si verificano.

|Evento su cui viene chiamato il metodo Cancel|Eventi del mouse che si verificano per l'input già avvenuto|
|----------------------------------------|-----------------------------------------------------------------|
|<xref:System.Windows.UIElement.ManipulationStarting> e <xref:System.Windows.UIElement.ManipulationStarted>|Eventi di pressione del pulsante del mouse.|
|<xref:System.Windows.UIElement.ManipulationDelta>|Eventi di pressione del pulsante e di spostamento del mouse.|
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> e <xref:System.Windows.UIElement.ManipulationCompleted>|Eventi di pressione e rilascio del pulsante e di spostamento del mouse.|

 Si noti che se si chiama <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> quando la manipolazione è in inerzia, il metodo restituisce `false` e l'input non genera eventi del mouse.

### <a name="the-relationship-between-touch-and-manipulation-events"></a>Relazione tra eventi di tocco e di manipolazione
 Un <xref:System.Windows.UIElement> può sempre ricevere eventi di tocco. Quando la proprietà <xref:System.Windows.UIElement.IsManipulationEnabled%2A> è impostata su `true`, un <xref:System.Windows.UIElement> può ricevere eventi di tocco e di manipolazione.  Se l'evento <xref:System.Windows.UIElement.TouchDown> non viene gestito (ovvero la proprietà <xref:System.Windows.RoutedEventArgs.Handled%2A> è `false`), la logica di manipolazione acquisisce il tocco sull'elemento e genera gli eventi di manipolazione. Se la proprietà <xref:System.Windows.RoutedEventArgs.Handled%2A> è impostata su `true` nell'evento <xref:System.Windows.UIElement.TouchDown>, la logica di manipolazione non genera eventi di manipolazione. La figura seguente mostra la relazione tra eventi di tocco ed eventi di manipolazione.

 ![Relazione tra eventi di tocco e manipolazione](./media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents") eventi di tocco e manipolazione

 L'elenco seguente descrive la relazione tra gli eventi di tocco e gli eventi di manipolazione illustrati nella figura precedente.

- Quando il primo dispositivo touch genera un evento <xref:System.Windows.UIElement.TouchDown> in un <xref:System.Windows.UIElement>, la logica di manipolazione chiama il metodo <xref:System.Windows.UIElement.CaptureTouch%2A>, che genera l'evento <xref:System.Windows.UIElement.GotTouchCapture>.

- Quando si verifica il <xref:System.Windows.UIElement.GotTouchCapture>, la logica di manipolazione chiama il metodo <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=nameWithType>, che genera l'evento di <xref:System.Windows.UIElement.ManipulationStarting>.

- Quando si verificano gli eventi di <xref:System.Windows.UIElement.TouchMove>, la logica di manipolazione genera gli eventi di <xref:System.Windows.UIElement.ManipulationDelta> che si verificano prima dell'evento di <xref:System.Windows.UIElement.ManipulationInertiaStarting>.

- Quando l'ultimo dispositivo touch sull'elemento genera l'evento <xref:System.Windows.UIElement.TouchUp>, la logica di manipolazione genera l'evento <xref:System.Windows.UIElement.ManipulationInertiaStarting>.

<a name="focus"></a>
## <a name="focus"></a>Stato attivo
 Ci sono due concetti principali relativi allo stato attivo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: lo stato attivo della tastiera e lo stato attivo logico.

### <a name="keyboard-focus"></a>Stato attivo della tastiera
 Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input dalla tastiera.  Su un desktop può esserci un solo elemento con lo stato attivo della tastiera.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'elemento con lo stato attivo della tastiera sarà <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> impostato su `true`.  Il metodo statico di <xref:System.Windows.Input.Keyboard> <xref:System.Windows.Input.Keyboard.FocusedElement%2A> restituisce l'elemento che dispone attualmente dello stato attivo della tastiera.

 Lo stato attivo della tastiera può essere ottenuto tramite tabulazione su un elemento o facendo clic sul mouse su determinati elementi, ad esempio un <xref:System.Windows.Controls.TextBox>.  Lo stato attivo della tastiera può essere ottenuto anche a livello di programmazione tramite il metodo <xref:System.Windows.Input.Keyboard.Focus%2A> sulla classe <xref:System.Windows.Input.Keyboard>.  <xref:System.Windows.Input.Keyboard.Focus%2A> tenta di assegnare lo stato attivo della tastiera all'elemento specificato.  L'elemento restituito da <xref:System.Windows.Input.Keyboard.Focus%2A> è l'elemento che dispone attualmente dello stato attivo della tastiera.

 Affinché un elemento ottenga lo stato attivo della tastiera, la proprietà <xref:System.Windows.UIElement.Focusable%2A> e le proprietà <xref:System.Windows.UIElement.IsVisible%2A> devono essere impostate su **true**.  Alcune classi, ad esempio <xref:System.Windows.Controls.Panel>, <xref:System.Windows.UIElement.Focusable%2A> impostate su `false` per impostazione predefinita. Pertanto, potrebbe essere necessario impostare questa proprietà su `true` se si desidera che l'elemento possa ottenere lo stato attivo.

 Nell'esempio seguente viene usato <xref:System.Windows.Input.Keyboard.Focus%2A> per impostare lo stato attivo della tastiera su una <xref:System.Windows.Controls.Button>.  La posizione consigliata per impostare lo stato attivo iniziale in un'applicazione si trova nel gestore dell'evento <xref:System.Windows.FrameworkElement.Loaded>.

 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]

 Per altre informazioni sullo stato attivo della tastiera, vedere [Cenni preliminari sullo stato attivo](focus-overview.md).

### <a name="logical-focus"></a>Stato attivo logico
 Lo stato attivo logico fa riferimento all'<xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in un ambito di stato attivo.  In un'applicazione possono esserci più elementi con lo stato attivo logico, ma in un determinato ambito di stato attivo può esserci un solo elemento con lo stato attivo logico.

 Un ambito di stato attivo è un elemento contenitore che tiene traccia dell'<xref:System.Windows.Input.FocusManager.FocusedElement%2A> all'interno dell'ambito.  Quando lo stato attivo lascia un ambito di stato attivo, l'elemento con lo stato attivo perde lo stato attivo della tastiera, ma mantiene quello logico.  Quando lo stato attivo torna nell'ambito di stato attivo, l'elemento con lo stato attivo ottiene nuovamente lo stato attivo della tastiera.  In questo modo, lo stato attivo della tastiera può essere passato tra più ambiti, ma l'elemento con lo stato attivo in un determinato ambito rimane sicuramente tale al ritorno dello stato attivo.

 Un elemento può essere trasformato in un ambito di stato attivo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] impostando la proprietà associata <xref:System.Windows.Input.FocusManager> <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> `true`o nel codice impostando la proprietà associata tramite il metodo <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.

 Nell'esempio seguente un <xref:System.Windows.Controls.StackPanel> viene trasformato in un ambito di stato attivo impostando la proprietà <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> associata.

 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]

 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]

 Per impostazione predefinita, le classi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che sono ambiti di stato attivo sono <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>e <xref:System.Windows.Controls.ContextMenu>.

 Un elemento con lo stato attivo della tastiera avrà anche lo stato attivo logico per l'ambito di stato attivo a cui appartiene. Pertanto, l'impostazione dello stato attivo su un elemento con il metodo <xref:System.Windows.Input.Keyboard.Focus%2A> sulla classe <xref:System.Windows.Input.Keyboard> o sulle classi degli elementi di base tenterà di assegnare lo stato attivo della tastiera e lo stato attivo logico dell'elemento.

 Per determinare l'elemento con stato attivo in un ambito di stato attivo, utilizzare <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Per modificare l'elemento con stato attivo per un ambito di stato attivo, utilizzare <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.

 Per altre informazioni sullo stato attivo logico, vedere [Cenni preliminari sullo stato attivo](focus-overview.md).

<a name="mouse_position"></a>
## <a name="mouse-position"></a>Posizione del mouse
 L'API di input [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce informazioni utili per quanto riguarda gli spazi delle coordinate.  Ad esempio, la coordinata `(0,0)` rappresenta la coordinata superiore sinistra, ma di quale elemento dell'albero? Si tratta dell'elemento che costituisce la destinazione dell'input? O dell'elemento a cui è associato il gestore eventi? Oppure di qualche altro elemento? Per evitare confusione, l'API di input [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] richiede di specificare il frame di riferimento quando si utilizzano le coordinate ottenute tramite il mouse. Il metodo <xref:System.Windows.Input.Mouse.GetPosition%2A> restituisce la coordinata del puntatore del mouse relativa all'elemento specificato.

<a name="mouse_capture"></a>
## <a name="mouse-capture"></a>Mouse Capture
 I dispositivi di tipo mouse hanno una caratteristica modale specifica nota come mouse capture. Tale caratteristica viene usata per mantenere uno stato di input di transizione all'avvio di un'operazione di trascinamento della selezione, in modo che le altre operazioni che riguardano la posizione su schermo nominale del puntatore del mouse non vengano necessariamente eseguite. Durante il trascinamento, l'utente non può fare clic senza interrompere il trascinamento della selezione, quindi la maggior parte dei segnali di passaggio del mouse risulterà inappropriata quando l'origine del trascinamento mantiene lo stato mouse capture. Il sistema di input espone le API che possono determinare lo stato di acquisizione del mouse, nonché le API che possono forzare l'acquisizione del mouse su un elemento specifico o cancellare lo stato di acquisizione del mouse. Per altre informazioni sulle operazioni di trascinamento della selezione, vedere [Cenni preliminari sul trascinamento della selezione](drag-and-drop-overview.md).

<a name="commands"></a>
## <a name="commands"></a>Commands
 I comandi consentono la gestione dell'input a un livello più semantico rispetto all'input dei dispositivi.  I comandi sono semplici direttive, come `Cut`, `Copy`, `Paste` o `Open`.  I comandi sono utili per centralizzare la logica di comando.  È possibile accedere allo stesso comando da un <xref:System.Windows.Controls.Menu>, da un <xref:System.Windows.Controls.ToolBar>o tramite un tasto di scelta rapida. I comandi forniscono anche un meccanismo per disabilitare i controlli quando il comando non è più disponibile.

 <xref:System.Windows.Input.RoutedCommand> è l'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di <xref:System.Windows.Input.ICommand>.  Quando viene eseguita una <xref:System.Windows.Input.RoutedCommand>, nella destinazione del comando vengono generati un <xref:System.Windows.Input.CommandManager.PreviewExecuted> e un evento <xref:System.Windows.Input.CommandManager.Executed>, che eseguono il tunneling e il bubbling attraverso l'albero degli elementi come altro input.  Se non è impostata una destinazione del comando, questa sarà rappresentata dall'elemento con lo stato attivo della tastiera.  La logica che esegue il comando è associata a un <xref:System.Windows.Input.CommandBinding>.  Quando un evento <xref:System.Windows.Input.CommandManager.Executed> raggiunge un <xref:System.Windows.Input.CommandBinding> per quel comando specifico, viene chiamato il <xref:System.Windows.Input.ExecutedRoutedEventHandler> sul <xref:System.Windows.Input.CommandBinding>.  Il gestore esegue l'azione del comando.

 Per altre informazioni sui comandi, vedere [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una libreria di comandi comuni costituiti da <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>e <xref:System.Windows.Documents.EditingCommands>oppure è possibile definirne di personalizzati.

 Nell'esempio seguente viene illustrato come configurare un <xref:System.Windows.Controls.MenuItem> in modo che, quando viene fatto clic, richiami il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> sul <xref:System.Windows.Controls.TextBox>, supponendo che il <xref:System.Windows.Controls.TextBox> abbia lo stato attivo della tastiera.

 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]

 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]

 Per altre informazioni sui comandi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).

<a name="the_input_system_and_base_elements"></a>
## <a name="the-input-system-and-base-elements"></a>Sistema di input ed elementi di base
 Gli eventi di input come gli eventi associati definiti dalle classi <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>e <xref:System.Windows.Input.Stylus> vengono generati dal sistema di input e inseriti in una determinata posizione nel modello a oggetti in base all'hit test della struttura ad albero visuale in fase di esecuzione.

 Ogni evento che <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>e <xref:System.Windows.Input.Stylus> definire come un evento associato viene anche nuovamente esposto dalle classi degli elementi di base <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> come nuovo evento indirizzato. Gli eventi indirizzati degli elementi di base vengono generati da classi che gestiscono l'evento associato originale e riutilizzano i dati dell'evento.

 Quando l'evento di input viene associato a un particolare elemento di origine tramite l'implementazione dell'evento di input dei relativi elementi di base, può essere indirizzato lungo la parte restante della route di un evento basata su una combinazione di oggetti albero logico e struttura ad albero visuale ed essere gestito dal codice dell'applicazione.  In genere, è più facile gestire questi eventi di input correlati al dispositivo usando gli eventi indirizzati in <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement>, perché è possibile usare una sintassi del gestore eventi più intuitiva sia in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che nel codice. È possibile scegliere di gestire invece l'evento associato che ha avviato il processo, ma potrebbero sorgere diversi problemi: l'evento associato potrebbe essere contrassegnato come gestito dalla gestione della classe dell'elemento di base, per cui potrebbe essere necessario usare i metodi della funzione di accesso invece della sintassi dell'evento vera e propria per associare i gestori per gli eventi associati.

<a name="whats_next"></a>
## <a name="whats-next"></a>Operazioni successive
 A questo punto si conoscono diverse tecniche per la gestione dell'input in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Si dovrebbe anche avere una conoscenza più approfondita dei vari tipi di eventi di input e dei meccanismi degli eventi indirizzati usati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Sono disponibili risorse aggiuntive che illustrano più dettagliatamente gli elementi del framework [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e il routing degli eventi. Per altre informazioni generali, vedere [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md), [Cenni preliminari sullo stato attivo](focus-overview.md), [Cenni preliminari sugli elementi di base](base-elements-overview.md), [Strutture ad albero in WPF](trees-in-wpf.md) e [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica sullo stato attivo](focus-overview.md)
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
- [Proprietà](properties-wpf.md)
