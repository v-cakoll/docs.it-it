---
title: Cenni preliminari sull'esecuzione di comandi
description: Informazioni sul comando, un meccanismo di input in Windows Presentation Foundation che consente la gestione dell'input a un livello più semantico rispetto all'input del dispositivo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
ms.openlocfilehash: 4f7d12fbf0de9b1546f15061ab7eb1318378bbbb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168125"
---
# <a name="commanding-overview"></a>Cenni preliminari sull'esecuzione di comandi
<a name="introduction"></a> I comandi sono un meccanismo di input in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] che consente la gestione dell'input a un livello più semantico rispetto all'input dei dispositivi. Sono esempi di comandi le operazioni **Copia**, **Taglia** e **Incolla** disponibili in molte applicazioni.  
  
 Questa panoramica presenta i comandi disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], le classi che fanno parte del modello di esecuzione dei comandi e le procedure per usare e creare comandi nelle applicazioni.  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Cosa sono i comandi?](#commands_at_10000_feet)  
  
- [Esempio di comando semplice in WPF](#simple_command)  
  
- [Quattro concetti principali dell'esecuzione dei comandi WPF](#Four_main_Concepts)  
  
- [Libreria dei comandi](#Command_Library)  
  
- [Creazione di comandi personalizzati](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>
## <a name="what-are-commands"></a>Cosa sono i comandi?  
 I comandi hanno diversi scopi. Il primo scopo è di separare la semantica e l'oggetto che richiama un comando dalla logica che esegue il comando. In questo modo, più codici sorgente diversi possono richiamare la stessa logica di comando che può quindi essere personalizzata per obiettivi differenti. Le operazioni di modifica **Copia**, **Taglia** e **Incolla**, ad esempio, disponibili in molte applicazioni, possono essere richiamate usando azioni dell'utente diverse se vengono implementate tramite i comandi. Un'applicazione potrebbe consentire a un utente di tagliare gli oggetti o il testo selezionati facendo clic su un pulsante, scegliendo una voce da un menu o usando una combinazione di tasti, ad esempio CTRL+X. Usando i comandi è possibile associare ogni tipo di azione utente alla stessa logica.  
  
 Un altro scopo dei comandi è di indicare se un'azione è disponibile. Per continuare con l'esempio in cui viene tagliato un oggetto o un testo, l'azione ha senso solo quando viene selezionato un elemento. Se un utente tenta di tagliare un oggetto o un testo senza avere selezionato alcun elemento, non viene eseguita alcuna operazione. Per indicarlo all'utente, in molte applicazioni vengono disabilitati i pulsanti e le voci di menu in modo che l'utente sappia se è possibile eseguire un'azione. Un comando può indicare se un'azione è possibile implementando il metodo <xref:System.Windows.Input.ICommand.CanExecute%2A>. Un pulsante può sottoscrivere l'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> ed essere disabilitato se <xref:System.Windows.Input.ICommand.CanExecute%2A> restituisce `false` oppure essere abilitato se <xref:System.Windows.Input.ICommand.CanExecute%2A> restituisce `true`.  
  
 La semantica di un comando può essere coerente tra le applicazioni e le classi, tuttavia la logica dell'azione è specifica dell'oggetto particolare su cui si agisce. La combinazione di tasti CTRL+X richiama il comando **Taglia** nelle classi di testo, nelle classi di immagine e nei Web browser, tuttavia la logica effettiva per l'esecuzione dell'operazione **Taglia** viene definita dall'applicazione in cui si esegue l'operazione di taglio. <xref:System.Windows.Input.RoutedCommand> consente ai client di implementare la logica. Un oggetto testo può tagliare il testo selezionato negli Appunti, mentre un oggetto immagine può tagliare l'immagine selezionata. Quando un'applicazione gestisce l'evento <xref:System.Windows.Input.CommandManager.Executed>, può accedere alla destinazione del comando ed eseguire l'azione appropriata in base al tipo della destinazione.  
  
<a name="simple_command"></a>
## <a name="simple-command-example-in-wpf"></a>Esempio di comando semplice in WPF  
 Il modo più semplice per usare un comando in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nell'uso di un oggetto <xref:System.Windows.Input.RoutedCommand> predefinito di una delle classi della libreria dei comandi, nell'uso di un controllo con supporto nativo per gestire il comando e nell'uso di un controllo con supporto nativo per richiamare un comando.  Il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> è uno dei comandi predefiniti della classe <xref:System.Windows.Input.ApplicationCommands>.  Il controllo <xref:System.Windows.Controls.TextBox> è dotato di logica incorporata per la gestione del comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  E la classe <xref:System.Windows.Controls.MenuItem> è dotata del supporto nativo per la chiamata di comandi.  
  
 L'esempio seguente illustra come impostare un oggetto <xref:System.Windows.Controls.MenuItem> in modo che quando si fa clic su di esso, richiami il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> in un <xref:System.Windows.Controls.TextBox>, supponendo che <xref:System.Windows.Controls.TextBox> abbia lo stato attivo della tastiera.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>
## <a name="four-main-concepts-in-wpf-commanding"></a>Quattro concetti principali dell'esecuzione dei comandi WPF  
 Il modello di comando indirizzato di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può essere suddiviso in quattro concetti principali: il comando, l'origine del comando, la destinazione del comando e l'associazione del comando:  
  
- Il *comando* è l'azione da eseguire.  
  
- L'*origine del comando* è l'oggetto che richiama il comando.  
  
- La *destinazione del comando* è l'oggetto su cui viene eseguito il comando.  
  
- L'*associazione del comando* è l'oggetto che esegue il mapping della logica di comando al comando.  
  
 Nell'esempio precedente, il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> corrisponde al comando, <xref:System.Windows.Controls.MenuItem> è l'origine del comando, <xref:System.Windows.Controls.TextBox> è la destinazione del comando e l'associazione del comando viene fornita dal controllo <xref:System.Windows.Controls.TextBox>.  È importante notare che non sempre l'oggetto <xref:System.Windows.Input.CommandBinding> viene fornito dal controllo che rappresenta la classe di destinazione del comando.  Molto spesso è lo sviluppatore dell'applicazione che deve creare <xref:System.Windows.Input.CommandBinding>. In altri casi, può esistere un collegamento tra <xref:System.Windows.Input.CommandBinding> e un predecessore della destinazione del comando.  
  
<a name="Commands"></a>
### <a name="commands"></a>Comandi  
 I comandi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono creati tramite l'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.  <xref:System.Windows.Input.ICommand> espone due metodi, <xref:System.Windows.Input.ICommand.Execute%2A> e <xref:System.Windows.Input.ICommand.CanExecute%2A>, e un evento, <xref:System.Windows.Input.ICommand.CanExecuteChanged>. <xref:System.Windows.Input.ICommand.Execute%2A> esegue le azioni associate al comando. <xref:System.Windows.Input.ICommand.CanExecute%2A> determina se il comando può essere eseguito nella destinazione corrente del comando stesso. <xref:System.Windows.Input.ICommand.CanExecuteChanged> viene generato se il gestore che centralizza le operazioni di comando rileva una modifica nell'origine del comando che potrebbe invalidare un comando generato ma non ancora eseguito dall'associazione del comando.  L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di <xref:System.Windows.Input.ICommand> è la classe <xref:System.Windows.Input.RoutedCommand> e costituisce l'obiettivo di questa panoramica.  
  
 Le origini di input principali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono il mouse, la tastiera, l'input penna e i comandi indirizzati.  La maggior parte degli input orientati al dispositivo usano un oggetto <xref:System.Windows.RoutedEvent> per notificare agli oggetti di una pagina dell'applicazione che si è verificato un evento di input.  <xref:System.Windows.Input.RoutedCommand> non è diverso.  I metodi <xref:System.Windows.Input.RoutedCommand.Execute%2A> e <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> di <xref:System.Windows.Input.RoutedCommand> non contengono la logica dell'applicazione per il comando, ma generano eventi indirizzati che effettuano il tunneling e il bubbling attraverso la struttura ad albero degli elementi finché non rilevano un oggetto con <xref:System.Windows.Input.CommandBinding>.  <xref:System.Windows.Input.CommandBinding> contiene i gestori per questi eventi e sono i gestori a eseguire il comando.  Per altre informazioni sul routing di eventi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Il metodo <xref:System.Windows.Input.RoutedCommand.Execute%2A> in un <xref:System.Windows.Input.RoutedCommand> genera gli eventi <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> nella destinazione del comando.  Il metodo <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> in un <xref:System.Windows.Input.RoutedCommand> genera gli eventi <xref:System.Windows.Input.CommandManager.CanExecute> e <xref:System.Windows.Input.CommandManager.PreviewCanExecute> nella destinazione del comando.  Questi eventi eseguono il tunneling e il bubbling nell'albero degli elementi finché non incontrano un oggetto con un <xref:System.Windows.Input.CommandBinding> per quel particolare comando.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un set di comandi indirizzati comuni distribuito in diverse classi: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> e <xref:System.Windows.Documents.EditingCommands>.  Queste classi sono costituite solo da oggetti <xref:System.Windows.Input.RoutedCommand> e non dalla logica di implementazione del comando.  La logica di implementazione è responsabilità dell'oggetto sul quale viene eseguito il comando.  
  
<a name="Command_Sources"></a>
### <a name="command-sources"></a>Origini dei comandi  
 Un'origine del comando è l'oggetto che richiama il comando.  <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> e <xref:System.Windows.Input.KeyGesture> sono esempi di origini del comando.  
  
 Le origini del comando in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in genere implementano l'interfaccia <xref:System.Windows.Input.ICommandSource>.  
  
 <xref:System.Windows.Input.ICommandSource> espone tre proprietà: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> e <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
- <xref:System.Windows.Input.ICommandSource.Command%2A> è il comando da eseguire quando viene richiamata l'origine del comando.  
  
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è l'oggetto su cui eseguire il comando.  Si noti che in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la proprietà <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> in <xref:System.Windows.Input.ICommandSource> è applicabile solo quando <xref:System.Windows.Input.ICommand> è <xref:System.Windows.Input.RoutedCommand>.  Se <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è impostato su un <xref:System.Windows.Input.ICommandSource> e il comando corrispondente non è un <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando viene ignorata. Se <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> non è impostato, viene rappresentato dall'elemento con lo stato attivo della tastiera.  
  
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> è un tipo di dati definito dall'utente usato per passare informazioni ai gestori che implementano il comando.  
  
 Le classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che implementano <xref:System.Windows.Input.ICommandSource> sono <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> e <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> e <xref:System.Windows.Documents.Hyperlink> richiamano un comando quando ricevono un clic e <xref:System.Windows.Input.InputBinding> richiama un comando quando l'oggetto <xref:System.Windows.Input.InputGesture> associato viene eseguito.  
  
 L'esempio seguente illustra come usare un oggetto <xref:System.Windows.Controls.MenuItem> in un oggetto <xref:System.Windows.Controls.ContextMenu> come origine del comando <xref:System.Windows.Input.ApplicationCommands.Properties%2A>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Un'origine del comando è in genere in ascolto dell'evento <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>.  Questo evento informa l'origine del comando relativamente alla probabile modifica della capacità del comando di essere eseguito sulla destinazione del comando corrente.  L'origine del comando può eseguire una query dello stato corrente dell'oggetto <xref:System.Windows.Input.RoutedCommand> tramite il metodo <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>.  L'origine comando può quindi disabilitarsi, se l'esecuzione del comando non riesce.  Un esempio è un oggetto <xref:System.Windows.Controls.MenuItem> che si disattiva quando non è possibile eseguire il comando corrispondente.  
  
 Un oggetto <xref:System.Windows.Input.InputGesture> può essere usato come origine del comando.  Due tipi di movimento di input in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono <xref:System.Windows.Input.KeyGesture> e <xref:System.Windows.Input.MouseGesture>.  È possibile considerare un oggetto <xref:System.Windows.Input.KeyGesture> come tasto di scelta rapida, ad esempio CTRL + C.  Un <xref:System.Windows.Input.KeyGesture> è costituito da un <xref:System.Windows.Input.Key> e da un set di <xref:System.Windows.Input.ModifierKeys>.  Un <xref:System.Windows.Input.MouseGesture> è costituito da un <xref:System.Windows.Input.MouseAction> e da un set di <xref:System.Windows.Input.ModifierKeys> facoltativo.  
  
 Affinché un oggetto <xref:System.Windows.Input.InputGesture> funzioni come origine del comando, deve essere associato a un comando. Questa operazione può essere eseguita in diversi modi.  Un modo consiste nell'uso di un oggetto <xref:System.Windows.Input.InputBinding>.  
  
 L'esempio seguente illustra come creare un <xref:System.Windows.Input.KeyBinding> tra un <xref:System.Windows.Input.KeyGesture> e un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Un altro modo per associare un <xref:System.Windows.Input.InputGesture> a un <xref:System.Windows.Input.RoutedCommand> consiste nell'aggiungere l'oggetto <xref:System.Windows.Input.InputGesture> a <xref:System.Windows.Input.InputGestureCollection> per <xref:System.Windows.Input.RoutedCommand>.  
  
 L'esempio seguente illustra come aggiungere un <xref:System.Windows.Input.KeyGesture> alla raccolta <xref:System.Windows.Input.InputGestureCollection> di un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>
### <a name="commandbinding"></a>CommandBinding  
 Una classe <xref:System.Windows.Input.CommandBinding> associa un comando ai gestori degli eventi che implementano il comando.  
  
 La classe <xref:System.Windows.Input.CommandBinding> contiene la proprietà <xref:System.Windows.Input.CommandBinding.Command%2A> e gli eventi <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> e <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> è il comando a cui <xref:System.Windows.Input.CommandBinding> è associato.  I gestori degli eventi associati agli eventi <xref:System.Windows.Input.CommandBinding.PreviewExecuted> e <xref:System.Windows.Input.CommandBinding.Executed> implementano la logica di comando.  I gestori eventi associati agli eventi <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> e <xref:System.Windows.Input.CommandBinding.CanExecute> determinano se il comando può essere eseguito nella destinazione corrente.  
  
 L'esempio seguente illustra come creare un <xref:System.Windows.Input.CommandBinding> in <xref:System.Windows.Window> radice di un'applicazione.  <xref:System.Windows.Input.CommandBinding> associa il comando <xref:System.Windows.Input.ApplicationCommands.Open%2A> ai gestori <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Successivamente vengono creati <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> apre un oggetto <xref:System.Windows.MessageBox> che visualizza una stringa che indica che il comando è stato eseguito.  Il metodo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> imposta la proprietà <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> su `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Un oggetto <xref:System.Windows.Input.CommandBinding> viene collegato a un oggetto specifico, ad esempio all'oggetto <xref:System.Windows.Window> radice dell'applicazione o di un controllo.  L'oggetto a cui è collegato l'oggetto <xref:System.Windows.Input.CommandBinding> definisce l'ambito dell'associazione.  È ad esempio possibile raggiungere un oggetto <xref:System.Windows.Input.CommandBinding> collegato a un predecessore della destinazione del comando tramite l'evento <xref:System.Windows.Input.CommandBinding.Executed>, ma un oggetto <xref:System.Windows.Input.CommandBinding> collegato a un discendente della destinazione del comando non è raggiungibile.  Si tratta di una conseguenza diretta del modo in cui un oggetto <xref:System.Windows.RoutedEvent> effettua il tunneling e il bubbling dall'oggetto che genera l'evento.  
  
 In alcune situazioni l'oggetto <xref:System.Windows.Input.CommandBinding> è collegato alla destinazione del comando stessa, ad esempio con la classe <xref:System.Windows.Controls.TextBox> e i comandi <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> e <xref:System.Windows.Input.ApplicationCommands.Paste%2A>. Tuttavia, spesso è consigliabile associare l'oggetto <xref:System.Windows.Input.CommandBinding> a un predecessore della destinazione del comando, ad esempio l'oggetto <xref:System.Windows.Window> principale o l'oggetto Application, specialmente se lo stesso oggetto <xref:System.Windows.Input.CommandBinding> può essere usato per più destinazioni di comandi.  Si tratta di decisioni di progettazione di cui tenere conto quando si crea l'infrastruttura di esecuzione dei comandi.  
  
<a name="Commane_Target"></a>
### <a name="command-target"></a>Destinazione del comando  
 La destinazione del comando è l'elemento su cui viene eseguito il comando.  Per quanto riguarda <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando è l'elemento in corrispondenza del quale inizia il routing di <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandManager.CanExecute>.  Come notato in precedenza, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la proprietà <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> in <xref:System.Windows.Input.ICommandSource> è applicabile solo quando <xref:System.Windows.Input.ICommand> è un oggetto <xref:System.Windows.Input.RoutedCommand>.  Se <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è impostato su un <xref:System.Windows.Input.ICommandSource> e il comando corrispondente non è un <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando viene ignorata.  
  
 L'origine del comando può impostare in modo esplicito la destinazione del comando.  Se la destinazione del comando non viene definita, l'elemento con lo stato attivo verrà usato come destinazione del comando.  Uno dei vantaggi dell'uso dell'elemento con lo stato attivo come destinazione del comando consiste nel fatto che consente allo sviluppatore di applicazioni di usare la stessa origine del comando per richiamare un comando su più destinazioni senza tenere traccia della destinazione del comando.  Se, ad esempio, un oggetto <xref:System.Windows.Controls.MenuItem> richiama il comando **Incolla** in un'applicazione che ha un controllo <xref:System.Windows.Controls.TextBox> e un controllo <xref:System.Windows.Controls.PasswordBox>, la destinazione può essere l'oggetto <xref:System.Windows.Controls.TextBox> o l'oggetto <xref:System.Windows.Controls.PasswordBox> a seconda del controllo con stato attivo.  
  
 L'esempio seguente mostra come impostare in modo esplicito la destinazione del comando nel markup e nel code-behind.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>
### <a name="the-commandmanager"></a>CommandManager  
 <xref:System.Windows.Input.CommandManager> svolge un certo numero di funzioni correlate a comandi.  Rende disponibile un set di metodi statici per l'aggiunta e la rimozione di gestori degli eventi <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> e <xref:System.Windows.Input.CommandManager.CanExecute> da e verso un elemento specifico.  Rappresenta un modo per registrare oggetti <xref:System.Windows.Input.CommandBinding> e <xref:System.Windows.Input.InputBinding> in una classe specifica.  <xref:System.Windows.Input.CommandManager> consente anche, tramite l'evento <xref:System.Windows.Input.CommandManager.RequerySuggested>, di notificare a un comando quando deve essere generato l'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  
  
 Il metodo <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> impone a <xref:System.Windows.Input.CommandManager> di generare l'evento <xref:System.Windows.Input.CommandManager.RequerySuggested>.  Ciò è utile per le condizioni che richiedono l'abilitazione o la disabilitazione di un comando ma che l'oggetto <xref:System.Windows.Input.CommandManager> non è in grado di rilevare.  
  
<a name="Command_Library"></a>
## <a name="command-library"></a>Libreria dei comandi  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un set di comandi predefiniti.  La libreria dei comandi è costituita dalle classi seguenti: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> e <xref:System.Windows.Input.ComponentCommands>.  Queste classi forniscono comandi quali <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> e <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> e <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Molti di questi comandi includono un set di associazioni di input predefinite.  Se ad esempio si specifica che l'applicazione gestisce il comando copy, si ottiene automaticamente il tasto di scelta rapida "CTRL + C". si ottengono anche binding per altri dispositivi di input, ad esempio i movimenti di penna di Tablet PC e le informazioni vocali.  
  
 Quando si fa riferimento ai comandi delle diverse librerie dei comandi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in genere è possibile omettere il nome della classe di libreria che espone la proprietà del comando statico. Di solito i nomi dei comandi sono stringhe non ambigue ed esistono tipi proprietari che forniscono un raggruppamento logico di comandi, ma che non sono necessari per la risoluzione dell'ambiguità. Ad esempio, è possibile specificare `Command="Cut"` anziché il più dettagliato `Command="ApplicationCommands.Cut"`. Si tratta di un meccanismo pratico incorporato nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore per i comandi (più precisamente, si tratta di un comportamento del convertitore di tipi di <xref:System.Windows.Input.ICommand> , a cui il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore fa riferimento in fase di caricamento).  
  
<a name="creating_commands"></a>
## <a name="creating-custom-commands"></a>Creazione di comandi personalizzati  
 Se i comandi delle classi della libreria dei comandi non soddisfano le proprie esigenze, è possibile creare comandi personalizzati.  Questa operazione può essere eseguita in due modi.  Il primo prevede la progettazione da zero e l'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.  L'altro, che rappresenta l'approccio più comune, consiste nel creare un oggetto <xref:System.Windows.Input.RoutedCommand> o <xref:System.Windows.Input.RoutedUICommand>.  
  
 Per un esempio di creazione di un oggetto <xref:System.Windows.Input.RoutedCommand> personalizzato, vedere [Create a Custom RoutedCommand Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand) (Creare un esempio di oggetto RoutedCommand personalizzato).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.RoutedCommand>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Input.InputBinding>
- <xref:System.Windows.Input.CommandManager>
- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Implementare ICommandSource](how-to-implement-icommandsource.md)
- [How to: Add a Command to a MenuItem (Procedura: Aggiungere un comando a un MenuItem)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
- [Create a Custom RoutedCommand Sample (Creare un esempio di oggetto RoutedCommand personalizzato)](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand)
