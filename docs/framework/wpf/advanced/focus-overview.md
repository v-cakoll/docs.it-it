---
title: Cenni preliminari sullo stato attivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186660"
---
# <a name="focus-overview"></a>Cenni preliminari sullo stato attivo
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lo stato attivo è basato su due concetti principali, lo stato attivo della tastiera e lo stato attivo logico.  Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input della tastiera, mentre lo stato attivo logico fa riferimento all'elemento di un ambito che ha ricevuto lo stato attivo.  In questa panoramica verranno illustrati in dettaglio questi concetti.  Comprendere le differenze esistenti tra questi concetti è fondamentale per la creazione di applicazioni complesse costituite da più aree in cui è possibile ottenere lo stato attivo.  
  
 Le classi principali che partecipano <xref:System.Windows.Input.Keyboard> alla <xref:System.Windows.Input.FocusManager> gestione dello stato attivo sono <xref:System.Windows.UIElement> la <xref:System.Windows.ContentElement>classe, la classe e le classi degli elementi di base, ad esempio e .  Per altre informazioni sugli elementi di base, vedere [Cenni preliminari sugli elementi di base](base-elements-overview.md).  
  
 La <xref:System.Windows.Input.Keyboard> classe si occupa principalmente dello <xref:System.Windows.Input.FocusManager> stato attivo della tastiera e la classe riguarda principalmente lo stato attivo logico, ma questa non è una distinzione assoluta.  Un elemento con lo stato attivo della tastiera presenta anche lo stato attivo logico, mentre un elemento che ha ottenuto lo stato attivo logico non ha necessariamente lo stato attivo della tastiera.  Ciò è evidente <xref:System.Windows.Input.Keyboard> quando si utilizza la classe per impostare l'elemento che ha lo stato attivo della tastiera, in quanto imposta anche lo stato attivo logico sull'elemento.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Stato attivo della tastiera  
 Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input dalla tastiera.  Su un desktop può esserci un solo elemento con lo stato attivo della tastiera.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'elemento con <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> lo `true`stato attivo della tastiera sarà impostato su .  La proprietà <xref:System.Windows.Input.Keyboard.FocusedElement%2A> statica nella <xref:System.Windows.Input.Keyboard> classe ottiene l'elemento che ha attualmente lo stato attivo della tastiera.  
  
 Affinché un elemento ottenga <xref:System.Windows.UIElement.Focusable%2A> lo <xref:System.Windows.UIElement.IsVisible%2A> stato attivo della tastiera, `true`le proprietà e sugli elementi di base devono essere impostate su .  Alcune classi, ad <xref:System.Windows.Controls.Panel> esempio la <xref:System.Windows.UIElement.Focusable%2A> classe `false` base, sono state impostate su per impostazione predefinita; pertanto, è <xref:System.Windows.UIElement.Focusable%2A> `true` necessario impostare su se si desidera che tale elemento sia in grado di ottenere lo stato attivo della tastiera.  
  
 Lo stato attivo della tastiera può essere ottenuto tramite interazione dell'utente con l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ad esempio usando il tasto TAB per spostarsi su un elemento o facendo clic con il mouse su alcuni elementi.  Lo stato attivo della tastiera può <xref:System.Windows.Input.Keyboard.Focus%2A> anche <xref:System.Windows.Input.Keyboard> essere ottenuto a livello di codice utilizzando il metodo sulla classe.  Il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo tenta di assegnare lo stato attivo della tastiera all'elemento specificato.  L'elemento restituito è l'elemento con lo stato attivo della tastiera e potrebbe non essere quello richiesto se l'oggetto stato attivo nuovo o quello precedente blocca la richiesta.  
  
 Nell'esempio riportato di seguito viene utilizzato il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo per impostare lo stato attivo della tastiera su un <xref:System.Windows.Controls.Button>oggetto .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 La <xref:System.Windows.UIElement.IsKeyboardFocused%2A> proprietà nelle classi dell'elemento di base ottiene un valore che indica se l'elemento ha lo stato attivo della tastiera.  La <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> proprietà nelle classi dell'elemento di base ottiene un valore che indica se l'elemento o uno dei relativi elementi figlio visivi ha lo stato attivo della tastiera.  
  
 Quando si imposta lo stato attivo iniziale all'avvio dell'applicazione, l'elemento che riceve <xref:System.Windows.UIElement.Focusable%2A> lo <xref:System.Windows.UIElement.IsVisible%2A> stato `true`attivo deve trovarsi nella struttura ad albero visuale della finestra iniziale caricata dall'applicazione e l'elemento deve avere e impostato su .  La posizione consigliata per impostare lo stato attivo iniziale è nel <xref:System.Windows.FrameworkElement.Loaded> gestore eventi.  Un <xref:System.Windows.Threading.Dispatcher> callback può essere <xref:System.Windows.Threading.Dispatcher.Invoke%2A> utilizzato <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>anche chiamando o .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Stato attivo logico  
 Lo stato attivo <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> logico si riferisce all'ambito in un ambito dello stato attivo.  Un ambito dello stato attivo è <xref:System.Windows.Input.FocusManager.FocusedElement%2A> un elemento che tiene traccia dell'interno del relativo ambito.  Quando lo stato attivo della tastiera lascia un ambito di stato attivo, l'elemento con lo stato attivo perde lo stato attivo della tastiera, ma mantiene quello logico.  Quando lo stato attivo della tastiera torna nell'ambito di stato attivo, l'elemento con lo stato attivo ottiene lo stato attivo della tastiera.  In questo modo, lo stato attivo della tastiera può essere passato tra più ambiti, ma l'elemento con lo stato attivo nell'ambito di stato attivo ottiene sicuramente di nuovo lo stato attivo della tastiera quando lo stato attivo ritorna all'ambito di stato attivo.  
  
 In un'applicazione possono esserci più elementi con lo stato attivo logico, ma in un determinato ambito di stato attivo può esserci un solo elemento con lo stato attivo logico.  
  
 Un elemento con stato attivo della tastiera ha lo stato attivo logico per l'ambito a cui appartiene.  
  
 Un elemento può essere trasformato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in un <xref:System.Windows.Input.FocusManager> ambito <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> dello `true`stato attivo impostando la proprietà associata su .  Nel codice, un elemento può essere trasformato <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>in un ambito dello stato attivo chiamando .  
  
 Nell'esempio seguente <xref:System.Windows.Controls.StackPanel> viene creato un <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> ambito dello stato attivo impostando la proprietà associata.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>restituisce l'ambito dello stato attivo per l'elemento specificato.  
  
 Le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classi in cui sono <xref:System.Windows.Window>ambiti <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.ToolBar>dello <xref:System.Windows.Controls.ContextMenu>stato attivo per impostazione predefinita sono , , , e .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>ottiene l'elemento con lo stato attivo per l'ambito dello stato attivo specificato.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>imposta l'elemento con lo stato attivo nell'ambito dello stato attivo specificato.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>viene in genere utilizzato per impostare l'elemento con lo stato attivo iniziale.  
  
 L'esempio seguente illustra come impostare e ottenere l'elemento con lo stato attivo in un ambito di stato attivo.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Navigazione tramite tastiera  
 La <xref:System.Windows.Input.KeyboardNavigation> classe è responsabile dell'implementazione dello spostamento dello stato attivo della tastiera predefinito quando viene premuto uno dei tasti di spostamento.  ovvero TAB, MAIUSC+TAB, CTRL+TAB, CTRL+MAIUSC+TAB, tasto FRECCIA SU, tasto FRECCIA GIÙ, tasto FRECCIA SINISTRA e tasto FRECCIA DESTRA.  
  
 Il comportamento di navigazione di un contenitore <xref:System.Windows.Input.KeyboardNavigation> di <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>navigazione <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>può essere modificato impostando le proprietà associate , e .  Queste proprietà sono <xref:System.Windows.Input.KeyboardNavigationMode> di tipo <xref:System.Windows.Input.KeyboardNavigationMode.Continue>e <xref:System.Windows.Input.KeyboardNavigationMode.Local> <xref:System.Windows.Input.KeyboardNavigationMode.Contained>i <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> <xref:System.Windows.Input.KeyboardNavigationMode.Once>valori <xref:System.Windows.Input.KeyboardNavigationMode.None>possibili sono , , , , e .  Il valore <xref:System.Windows.Input.KeyboardNavigationMode.Continue>predefinito è , il che significa che l'elemento non è un contenitore di navigazione.  
  
 Nell'esempio seguente <xref:System.Windows.Controls.Menu> viene creato <xref:System.Windows.Controls.MenuItem> un con un numero di oggetti.  La <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> proprietà associata <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> è <xref:System.Windows.Controls.Menu>impostata su .  Quando lo stato attivo viene <xref:System.Windows.Controls.Menu>modificato utilizzando il tasto di tabulazione all'interno di , lo stato attivo si sposterà da ogni elemento e quando viene raggiunto l'ultimo elemento lo stato attivo tornerà al primo elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Spostamento dello stato attivo a livello di codice  
 API aggiuntive per lavorare <xref:System.Windows.UIElement.MoveFocus%2A> <xref:System.Windows.UIElement.PredictFocus%2A>con lo stato attivo sono e .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>passa lo stato attivo all'elemento successivo nell'applicazione.  A <xref:System.Windows.Input.TraversalRequest> viene utilizzato per specificare la direzione.   Il <xref:System.Windows.Input.FocusNavigationDirection> passato <xref:System.Windows.UIElement.MoveFocus%2A> a specifica le diverse direzioni <xref:System.Windows.Input.FocusNavigationDirection.First>in <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> cui <xref:System.Windows.Input.FocusNavigationDirection.Down>spostare lo stato attivo, ad esempio , e .  
  
 Nell'esempio <xref:System.Windows.FrameworkElement.MoveFocus%2A> seguente viene utilizzato per modificare l'elemento con lo stato attivo.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>restituisce l'oggetto che riceverebbe lo stato attivo se lo stato attivo dovesse essere modificato.  Attualmente, <xref:System.Windows.Input.FocusNavigationDirection.Up>solo <xref:System.Windows.Input.FocusNavigationDirection.Down> <xref:System.Windows.Input.FocusNavigationDirection.Left>, <xref:System.Windows.Input.FocusNavigationDirection.Right> , e <xref:System.Windows.FrameworkElement.PredictFocus%2A>sono supportati da .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Eventi di stato attivo  
 Gli eventi correlati allo <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> stato <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>attivo della tastiera sono , e , .  Gli eventi sono definiti come <xref:System.Windows.Input.Keyboard> eventi associati nella classe, ma sono più facilmente accessibili come eventi indirizzati equivalenti nelle classi degli elementi di base.  Per altre informazioni sugli eventi, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>viene generato quando l'elemento ottiene lo stato attivo della tastiera.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>viene generato quando l'elemento perde lo stato attivo della tastiera.  Se <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> l'evento <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> o l'evento viene gestito e <xref:System.Windows.RoutedEventArgs.Handled%2A> impostato su `true`, lo stato attivo non verrà modificato.  
  
 Nell'esempio riportato <xref:System.Windows.UIElement.GotKeyboardFocus> <xref:System.Windows.UIElement.LostKeyboardFocus> di seguito vengono <xref:System.Windows.Controls.TextBox>associati e gestori eventi a un oggetto .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Quando <xref:System.Windows.Controls.TextBox> ottiene lo stato <xref:System.Windows.Controls.Control.Background%2A> attivo della <xref:System.Windows.Controls.TextBox> tastiera, <xref:System.Windows.Media.Brushes.LightBlue%2A>la proprietà dell'oggetto viene modificata in .  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Quando <xref:System.Windows.Controls.TextBox> l'oggetto perde <xref:System.Windows.Controls.Control.Background%2A> lo stato <xref:System.Windows.Controls.TextBox> attivo della tastiera, la proprietà dell'oggetto viene reimpostata su bianco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Gli eventi correlati allo <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus>stato attivo logico sono e .  Questi eventi sono <xref:System.Windows.Input.FocusManager> definiti negli eventi associati, ma <xref:System.Windows.Input.FocusManager> non sono esposti wrapper di eventi CLR.  <xref:System.Windows.UIElement>ed <xref:System.Windows.ContentElement> esporre questi eventi in modo più conveniente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
