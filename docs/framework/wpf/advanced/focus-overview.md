---
title: Cenni preliminari sullo stato attivo
description: 'Informazioni sui due concetti principali in Windows Presentation Foundation che riguardano lo stato attivo: lo stato attivo della tastiera e lo stato attivo logico.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: 71aeb577cccd2c3b16df1c5a3cb772dd1f5479e2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165112"
---
# <a name="focus-overview"></a>Cenni preliminari sullo stato attivo
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lo stato attivo è basato su due concetti principali, lo stato attivo della tastiera e lo stato attivo logico.  Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input della tastiera, mentre lo stato attivo logico fa riferimento all'elemento di un ambito che ha ricevuto lo stato attivo.  In questa panoramica verranno illustrati in dettaglio questi concetti.  Comprendere le differenze esistenti tra questi concetti è fondamentale per la creazione di applicazioni complesse costituite da più aree in cui è possibile ottenere lo stato attivo.  
  
 Le classi principali che partecipano alla gestione dello stato attivo sono la <xref:System.Windows.Input.Keyboard> classe, la <xref:System.Windows.Input.FocusManager> classe e le classi degli elementi di base, ad esempio <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> .  Per altre informazioni sugli elementi di base, vedere [Cenni preliminari sugli elementi di base](base-elements-overview.md).  
  
 La <xref:System.Windows.Input.Keyboard> classe è preoccupata principalmente con lo stato attivo della tastiera e l'oggetto <xref:System.Windows.Input.FocusManager> è principalmente con lo stato attivo logico, ma non si tratta di una distinzione assoluta.  Un elemento con lo stato attivo della tastiera presenta anche lo stato attivo logico, mentre un elemento che ha ottenuto lo stato attivo logico non ha necessariamente lo stato attivo della tastiera.  Questa operazione è evidente quando si usa la <xref:System.Windows.Input.Keyboard> classe per impostare l'elemento con lo stato attivo della tastiera, perché imposta anche lo stato attivo logico sull'elemento.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Stato attivo della tastiera  
 Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input dalla tastiera.  Su un desktop può esserci un solo elemento con lo stato attivo della tastiera.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'elemento con lo stato attivo della tastiera sarà <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> impostato su `true` .  La proprietà statica della <xref:System.Windows.Input.Keyboard.FocusedElement%2A> <xref:System.Windows.Input.Keyboard> classe ottiene l'elemento che dispone attualmente dello stato attivo della tastiera.  
  
 Affinché un elemento ottenga lo stato attivo della tastiera, le <xref:System.Windows.UIElement.Focusable%2A> <xref:System.Windows.UIElement.IsVisible%2A> proprietà e sugli elementi di base devono essere impostate su `true` .  Alcune classi, ad esempio la <xref:System.Windows.Controls.Panel> classe base, sono <xref:System.Windows.UIElement.Focusable%2A> impostate su per `false` impostazione predefinita; pertanto, è necessario impostare <xref:System.Windows.UIElement.Focusable%2A> su `true` se si desidera che tale elemento possa ottenere lo stato attivo della tastiera.  
  
 Lo stato attivo della tastiera può essere ottenuto tramite interazione dell'utente con l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ad esempio usando il tasto TAB per spostarsi su un elemento o facendo clic con il mouse su alcuni elementi.  Lo stato attivo della tastiera può essere ottenuto anche a livello di programmazione tramite il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo nella <xref:System.Windows.Input.Keyboard> classe.  Il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo tenta di assegnare lo stato attivo della tastiera all'elemento specificato.  L'elemento restituito è l'elemento con lo stato attivo della tastiera e potrebbe non essere quello richiesto se l'oggetto stato attivo nuovo o quello precedente blocca la richiesta.  
  
 Nell'esempio seguente viene usato il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo per impostare lo stato attivo della tastiera su un oggetto <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 La <xref:System.Windows.UIElement.IsKeyboardFocused%2A> proprietà sulle classi degli elementi di base ottiene un valore che indica se l'elemento ha lo stato attivo della tastiera.  La <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> proprietà sulle classi degli elementi di base ottiene un valore che indica se l'elemento o uno dei relativi elementi figlio visivi ha lo stato attivo della tastiera.  
  
 Quando si imposta lo stato attivo iniziale all'avvio dell'applicazione, l'elemento che riceve lo stato attivo deve trovarsi nella struttura ad albero visuale della finestra iniziale caricata dall'applicazione e l'elemento deve avere <xref:System.Windows.UIElement.Focusable%2A> e <xref:System.Windows.UIElement.IsVisible%2A> impostare su `true` .  La posizione consigliata per impostare lo stato attivo iniziale è nel <xref:System.Windows.FrameworkElement.Loaded> gestore eventi.  Un <xref:System.Windows.Threading.Dispatcher> callback può essere utilizzato anche chiamando <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Stato attivo logico  
 Lo stato attivo logico fa riferimento a <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in un ambito di stato attivo.  Un ambito di stato attivo è un elemento che tiene traccia del <xref:System.Windows.Input.FocusManager.FocusedElement%2A> all'interno del relativo ambito.  Quando lo stato attivo della tastiera lascia un ambito di stato attivo, l'elemento con lo stato attivo perde lo stato attivo della tastiera, ma mantiene quello logico.  Quando lo stato attivo della tastiera torna nell'ambito di stato attivo, l'elemento con lo stato attivo ottiene lo stato attivo della tastiera.  In questo modo, lo stato attivo della tastiera può essere passato tra più ambiti, ma l'elemento con lo stato attivo nell'ambito di stato attivo ottiene sicuramente di nuovo lo stato attivo della tastiera quando lo stato attivo ritorna all'ambito di stato attivo.  
  
 In un'applicazione possono esserci più elementi con lo stato attivo logico, ma in un determinato ambito di stato attivo può esserci un solo elemento con lo stato attivo logico.  
  
 Un elemento con stato attivo della tastiera ha lo stato attivo logico per l'ambito a cui appartiene.  
  
 Un elemento può essere trasformato in un ambito di stato attivo in impostando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] la <xref:System.Windows.Input.FocusManager> proprietà associata <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> su `true` .  Nel codice, un elemento può essere trasformato in un ambito di stato attivo chiamando <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> .  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.StackPanel> trasformato in un ambito di stato attivo impostando la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> proprietà associata.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>Restituisce l'ambito dello stato attivo per l'elemento specificato.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Per impostazione predefinita, le classi in cui sono gli ambiti di stato attivo sono <xref:System.Windows.Window> ,, <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.ToolBar> e <xref:System.Windows.Controls.ContextMenu> .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Ottiene l'elemento con lo stato attivo per l'ambito dello stato attivo specificato.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>imposta l'elemento con stato attivo nell'ambito di stato attivo specificato.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>viene in genere utilizzato per impostare l'elemento con stato attivo iniziale.  
  
 L'esempio seguente illustra come impostare e ottenere l'elemento con lo stato attivo in un ambito di stato attivo.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Navigazione tramite tastiera  
 La <xref:System.Windows.Input.KeyboardNavigation> classe è responsabile dell'implementazione dello spostamento dello stato attivo della tastiera predefinito quando viene premuto uno dei tasti di navigazione.  ovvero TAB, MAIUSC+TAB, CTRL+TAB, CTRL+MAIUSC+TAB, tasto FRECCIA SU, tasto FRECCIA GIÙ, tasto FRECCIA SINISTRA e tasto FRECCIA DESTRA.  
  
 Il comportamento di navigazione di un contenitore di navigazione può essere modificato impostando le <xref:System.Windows.Input.KeyboardNavigation> proprietà associate <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> , <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> e <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A> .  Queste proprietà sono di tipo <xref:System.Windows.Input.KeyboardNavigationMode> e i valori possibili sono <xref:System.Windows.Input.KeyboardNavigationMode.Continue> , <xref:System.Windows.Input.KeyboardNavigationMode.Local> , <xref:System.Windows.Input.KeyboardNavigationMode.Contained> , <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> , <xref:System.Windows.Input.KeyboardNavigationMode.Once> e <xref:System.Windows.Input.KeyboardNavigationMode.None> .  Il valore predefinito è <xref:System.Windows.Input.KeyboardNavigationMode.Continue> , che indica che l'elemento non è un contenitore di navigazione.  
  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Menu> con un numero di <xref:System.Windows.Controls.MenuItem> oggetti.  La <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> proprietà associata è impostata <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> su in <xref:System.Windows.Controls.Menu> .  Quando lo stato attivo viene modificato utilizzando il tasto TAB all'interno di <xref:System.Windows.Controls.Menu> , lo stato attivo viene spostato da ogni elemento e quando l'ultimo elemento viene raggiunto, lo stato attivo torna al primo elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Spostamento dello stato attivo a livello di codice  
 Le API aggiuntive per lavorare con lo stato attivo sono <xref:System.Windows.UIElement.MoveFocus%2A> e <xref:System.Windows.UIElement.PredictFocus%2A> .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>imposta lo stato attivo sull'elemento successivo nell'applicazione.  <xref:System.Windows.Input.TraversalRequest>Per specificare la direzione, viene usato un oggetto.   Il <xref:System.Windows.Input.FocusNavigationDirection> passato a <xref:System.Windows.UIElement.MoveFocus%2A> specifica che è possibile spostare lo stato attivo in direzioni diverse, ad esempio <xref:System.Windows.Input.FocusNavigationDirection.First> , <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> e <xref:System.Windows.Input.FocusNavigationDirection.Down> .  
  
 Nell'esempio seguente viene usato <xref:System.Windows.FrameworkElement.MoveFocus%2A> per modificare l'elemento con lo stato attivo.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>Restituisce l'oggetto che riceve lo stato attivo se lo stato attivo deve essere modificato.  Attualmente, solo <xref:System.Windows.Input.FocusNavigationDirection.Up> , <xref:System.Windows.Input.FocusNavigationDirection.Down> , <xref:System.Windows.Input.FocusNavigationDirection.Left> e <xref:System.Windows.Input.FocusNavigationDirection.Right> sono supportati da <xref:System.Windows.FrameworkElement.PredictFocus%2A> .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Eventi di stato attivo  
 Gli eventi correlati allo stato attivo della tastiera sono <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> , <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> e <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> .  Gli eventi sono definiti come eventi associati sulla <xref:System.Windows.Input.Keyboard> classe, ma sono più facilmente accessibili come eventi indirizzati equivalenti nelle classi degli elementi di base.  Per altre informazioni sugli eventi, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>viene generato quando l'elemento ottiene lo stato attivo della tastiera.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>viene generato quando l'elemento perde lo stato attivo della tastiera.  Se l' <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> evento o l'evento <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> viene gestito e <xref:System.Windows.RoutedEventArgs.Handled%2A> è impostato su `true` , lo stato attivo non cambierà.  
  
 Nell'esempio seguente vengono collegati <xref:System.Windows.UIElement.GotKeyboardFocus> i <xref:System.Windows.UIElement.LostKeyboardFocus> gestori eventi e a un oggetto <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Quando <xref:System.Windows.Controls.TextBox> ottiene lo stato attivo della tastiera, la <xref:System.Windows.Controls.Control.Background%2A> proprietà di <xref:System.Windows.Controls.TextBox> viene modificata in <xref:System.Windows.Media.Brushes.LightBlue%2A> .  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Quando <xref:System.Windows.Controls.TextBox> perde lo stato attivo della tastiera, la <xref:System.Windows.Controls.Control.Background%2A> proprietà di <xref:System.Windows.Controls.TextBox> viene modificata di nuovo in bianco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Gli eventi correlati allo stato attivo logico sono <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> .  Questi eventi vengono definiti in <xref:System.Windows.Input.FocusManager> come eventi associati, ma non <xref:System.Windows.Input.FocusManager> espone wrapper di eventi CLR.  <xref:System.Windows.UIElement>ed <xref:System.Windows.ContentElement> esporre questi eventi più facilmente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
