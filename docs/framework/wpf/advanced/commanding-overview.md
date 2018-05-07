---
title: Cenni preliminari sull'esecuzione di comandi
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
ms.openlocfilehash: 0d426d8cf174a61c724e97b5e7af5c1428679716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="commanding-overview"></a>Cenni preliminari sull'esecuzione di comandi
<a name="introduction"></a> I comandi sono un meccanismo di input in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] che consente la gestione dell'input a un livello più semantico rispetto all'input dei dispositivi. Sono esempi di comandi le operazioni **Copia**, **Taglia** e **Incolla** disponibili in molte applicazioni.  
  
 Questa panoramica presenta i comandi disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], le classi che fanno parte del modello di esecuzione dei comandi e le procedure per usare e creare comandi nelle applicazioni.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Cosa sono i comandi?](#commands_at_10000_feet)  
  
-   [Esempio di comando semplice in WPF](#simple_command)  
  
-   [Quattro concetti principali dell'esecuzione dei comandi WPF](#Four_main_Concepts)  
  
-   [Libreria dei comandi](#Command_Library)  
  
-   [Creazione di comandi personalizzati](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>Cosa sono i comandi?  
 I comandi hanno diversi scopi. Il primo scopo è di separare la semantica e l'oggetto che richiama un comando dalla logica che esegue il comando. In questo modo, più codici sorgente diversi possono richiamare la stessa logica di comando che può quindi essere personalizzata per obiettivi differenti. Le operazioni di modifica **Copia**, **Taglia** e **Incolla**, ad esempio, disponibili in molte applicazioni, possono essere richiamate usando azioni dell'utente diverse se vengono implementate tramite i comandi. Un'applicazione potrebbe consentire a un utente di tagliare gli oggetti o il testo selezionati facendo clic su un pulsante, scegliendo una voce da un menu o usando una combinazione di tasti, ad esempio CTRL+X. Usando i comandi è possibile associare ogni tipo di azione utente alla stessa logica.  
  
 Un altro scopo dei comandi è di indicare se un'azione è disponibile. Per continuare con l'esempio in cui viene tagliato un oggetto o un testo, l'azione ha senso solo quando viene selezionato un elemento. Se un utente tenta di tagliare un oggetto o un testo senza avere selezionato alcun elemento, non viene eseguita alcuna operazione. Per indicarlo all'utente, in molte applicazioni vengono disabilitati i pulsanti e le voci di menu in modo che l'utente sappia se è possibile eseguire un'azione. Un comando è possibile indicare se un'azione è possibile implementando il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo. Un pulsante può sottoscrivere il <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento ed essere disabilitato se <xref:System.Windows.Input.ICommand.CanExecute%2A> restituisce `false` oppure essere abilitato se <xref:System.Windows.Input.ICommand.CanExecute%2A> restituisce `true`.  
  
 La semantica di un comando può essere coerente tra le applicazioni e le classi, tuttavia la logica dell'azione è specifica dell'oggetto particolare su cui si agisce. La combinazione di tasti CTRL+X richiama il comando **Taglia** nelle classi di testo, nelle classi di immagine e nei Web browser, tuttavia la logica effettiva per l'esecuzione dell'operazione **Taglia** viene definita dall'applicazione in cui si esegue l'operazione di taglio. Oggetto <xref:System.Windows.Input.RoutedCommand> consente ai client implementare la logica. Un oggetto testo può tagliare il testo selezionato negli Appunti, mentre un oggetto immagine può tagliare l'immagine selezionata. Quando un'applicazione gestisce il <xref:System.Windows.Input.CommandManager.Executed> evento, dispone di accesso alla destinazione del comando e può richiedere l'azione appropriata in base al tipo della destinazione.  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>Esempio di comando semplice in WPF  
 Il modo più semplice per utilizzare un comando di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nell'utilizzare un oggetto predefinito <xref:System.Windows.Input.RoutedCommand> da una delle classi della libreria di comando; utilizzare un controllo che offre supporto nativo per la gestione del comando; e utilizzare un controllo che offre supporto nativo per richiamare un comando.  Il <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando è uno dei comandi predefiniti di <xref:System.Windows.Input.ApplicationCommands> classe.  Il <xref:System.Windows.Controls.TextBox> controllo dispone di logica incorporata per la gestione di <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando.  E <xref:System.Windows.Controls.MenuItem> classe offre supporto nativo per richiamare i comandi.  
  
 Nell'esempio seguente viene illustrato come impostare un <xref:System.Windows.Controls.MenuItem> in modo che quando si fa clic, richiami il <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando un <xref:System.Windows.Controls.TextBox>, supponendo che il <xref:System.Windows.Controls.TextBox> ha lo stato attivo della tastiera.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>Quattro concetti principali dell'esecuzione dei comandi WPF  
 Il modello di comando indirizzato di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può essere suddiviso in quattro concetti principali: il comando, l'origine del comando, la destinazione del comando e l'associazione del comando:  
  
-   Il *comando* è l'azione da eseguire.  
  
-   L'*origine del comando* è l'oggetto che richiama il comando.  
  
-   La *destinazione del comando* è l'oggetto su cui viene eseguito il comando.  
  
-   L'*associazione del comando* è l'oggetto che esegue il mapping della logica di comando al comando.  
  
 Nell'esempio precedente, il <xref:System.Windows.Input.ApplicationCommands.Paste%2A> è il comando, il <xref:System.Windows.Controls.MenuItem> è l'origine del comando, il <xref:System.Windows.Controls.TextBox> è la destinazione del comando e l'associazione del comando viene fornito dal <xref:System.Windows.Controls.TextBox> controllo.  Vale la pena notare che non è sempre il caso che la <xref:System.Windows.Input.CommandBinding> viene fornito dal controllo che rappresenta la classe di destinazione del comando.  Molto spesso le <xref:System.Windows.Input.CommandBinding> dallo sviluppatore dell'applicazione, è necessario creare o <xref:System.Windows.Input.CommandBinding> possono essere associati a un predecessore della destinazione del comando.  
  
<a name="Commands"></a>   
### <a name="commands"></a>Comandi:  
 I comandi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono creati implementando il <xref:System.Windows.Input.ICommand> interfaccia.  <xref:System.Windows.Input.ICommand> espone due metodi, ovvero <xref:System.Windows.Input.ICommand.Execute%2A>, e <xref:System.Windows.Input.ICommand.CanExecute%2A>e un evento, <xref:System.Windows.Input.ICommand.CanExecuteChanged>. <xref:System.Windows.Input.ICommand.Execute%2A> esegue le azioni che sono associate con il comando. <xref:System.Windows.Input.ICommand.CanExecute%2A> Determina se il comando può essere eseguito il comando sulla destinazione corrente. <xref:System.Windows.Input.ICommand.CanExecuteChanged> viene generato se il gestore che centralizza le operazioni di comando rileva una modifica nell'origine del comando che potrebbe invalidare un comando che è stato generato ma non ancora eseguito dall'associazione del comando.  Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementazione di <xref:System.Windows.Input.ICommand> è il <xref:System.Windows.Input.RoutedCommand> ed è l'obiettivo di questa panoramica.  
  
 Le origini di input principali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono il mouse, la tastiera, l'input penna e i comandi indirizzati.  Utilizzano gli input più orientati al dispositivo un <xref:System.Windows.RoutedEvent> per notificare agli oggetti in una pagina dell'applicazione che si è verificato un evento di input.  Oggetto <xref:System.Windows.Input.RoutedCommand> non è diverso.  Il <xref:System.Windows.Input.RoutedCommand.Execute%2A> e <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> metodi di un <xref:System.Windows.Input.RoutedCommand> non contengono la logica dell'applicazione per il comando, ma piuttosto generano gli eventi indirizzati che effettuano il tunneling e bubbling nella struttura ad albero fino a quando non viene rilevato un oggetto con un <xref:System.Windows.Input.CommandBinding>.  Il <xref:System.Windows.Input.CommandBinding> contiene i gestori per questi eventi e i gestori di cui eseguono il comando.  Per altre informazioni sul routing di eventi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Il <xref:System.Windows.Input.RoutedCommand.Execute%2A> metodo su un <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> eventi sulla destinazione del comando.  Il <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> metodo su un <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.CanExecute> e <xref:System.Windows.Input.CommandManager.PreviewCanExecute> eventi sulla destinazione del comando.  Questi tunnel eventi e a bolle attraverso l'albero degli elementi fino a quando non viene rilevato un oggetto che ha un <xref:System.Windows.Input.CommandBinding> per quel comando specifico.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un set di comandi indirizzati comuni distribuito in diverse classi: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, e <xref:System.Windows.Documents.EditingCommands>.  Queste classi sono costituite solo il <xref:System.Windows.Input.RoutedCommand> oggetti e non la logica di implementazione del comando.  La logica di implementazione è responsabilità dell'oggetto sul quale viene eseguito il comando.  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>Origini dei comandi  
 Un'origine del comando è l'oggetto che richiama il comando.  Sono esempi di origini comando <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button>, e <xref:System.Windows.Input.KeyGesture>.  
  
 Comando origini in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in genere implementato il <xref:System.Windows.Input.ICommandSource> interfaccia.  
  
 <xref:System.Windows.Input.ICommandSource> espone tre proprietà: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, e <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> è il comando da eseguire quando viene richiamata l'origine del comando.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è l'oggetto su cui eseguire il comando.  Vale la pena notare che in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> proprietà <xref:System.Windows.Input.ICommandSource> è applicabile solo quando il <xref:System.Windows.Input.ICommand> è un <xref:System.Windows.Input.RoutedCommand>.  Se il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è impostata su un <xref:System.Windows.Input.ICommandSource> e il comando corrispondente non è un <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando viene ignorata. Se il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> non è impostata, l'elemento con stato attivo della tastiera sarà la destinazione del comando.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> è un tipo di dati definito dall'utente utilizzato per passare informazioni ai gestori di implementazione del comando.  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le classi che implementano <xref:System.Windows.Input.ICommandSource> sono <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink>, e <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, e <xref:System.Windows.Documents.Hyperlink> richiamare un comando quando vengono selezionati e una <xref:System.Windows.Input.InputBinding> richiama un comando quando il <xref:System.Windows.Input.InputGesture> associata viene eseguito.  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.MenuItem> in un <xref:System.Windows.Controls.ContextMenu> come origine di un comando di <xref:System.Windows.Input.ApplicationCommands.Properties%2A> comando.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 In genere, un comando di origine resterà in ascolto il <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> evento.  Questo evento informa l'origine del comando relativamente alla probabile modifica della capacità del comando di essere eseguito sulla destinazione del comando corrente.  L'origine del comando può determinare lo stato corrente del <xref:System.Windows.Input.RoutedCommand> utilizzando il <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> metodo.  L'origine comando può quindi disabilitarsi, se l'esecuzione del comando non riesce.  Un esempio di questo è un <xref:System.Windows.Controls.MenuItem> colore grigio quando non è possibile eseguire un comando.  
  
 Un <xref:System.Windows.Input.InputGesture> può essere utilizzato come un comando di origine.  Due tipi di movimenti di input in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono il <xref:System.Windows.Input.KeyGesture> e <xref:System.Windows.Input.MouseGesture>.  È possibile considerare un <xref:System.Windows.Input.KeyGesture> come tasto di scelta rapida, ad esempio CTRL + C.  Oggetto <xref:System.Windows.Input.KeyGesture> è costituita da un <xref:System.Windows.Input.Key> e un set di <xref:System.Windows.Input.ModifierKeys>.  Oggetto <xref:System.Windows.Input.MouseGesture> è costituita da un <xref:System.Windows.Input.MouseAction> e un insieme facoltativo di <xref:System.Windows.Input.ModifierKeys>.  
  
 Affinché un <xref:System.Windows.Input.InputGesture> per agire come un comando di origine, deve essere associata a un comando. Questa operazione può essere eseguita in diversi modi.  Un modo consiste nell'utilizzare un <xref:System.Windows.Input.InputBinding>.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Input.KeyBinding> tra un <xref:System.Windows.Input.KeyGesture> e <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Un altro modo per associare un <xref:System.Windows.Input.InputGesture> per un <xref:System.Windows.Input.RoutedCommand> consiste nell'aggiungere il <xref:System.Windows.Input.InputGesture> per il <xref:System.Windows.Input.InputGestureCollection> sul <xref:System.Windows.Input.RoutedCommand>.  
  
 Nell'esempio seguente viene illustrato come aggiungere un <xref:System.Windows.Input.KeyGesture> per il <xref:System.Windows.Input.InputGestureCollection> di un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 Oggetto <xref:System.Windows.Input.CommandBinding> associa un comando con i gestori di eventi che implementano il comando.  
  
 Il <xref:System.Windows.Input.CommandBinding> classe contiene un <xref:System.Windows.Input.CommandBinding.Command%2A> , proprietà e <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>, e <xref:System.Windows.Input.CommandBinding.CanExecute> eventi.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> è il comando che il <xref:System.Windows.Input.CommandBinding> è associato.  I gestori di eventi associati al <xref:System.Windows.Input.CommandBinding.PreviewExecuted> e <xref:System.Windows.Input.CommandBinding.Executed> eventi implementano la logica di comando.  I gestori eventi associati per il <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> e <xref:System.Windows.Input.CommandBinding.CanExecute> eventi determinano se il comando è possibile eseguire il comando sulla destinazione corrente.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Input.CommandBinding> nella radice <xref:System.Windows.Window> di un'applicazione.  Il <xref:System.Windows.Input.CommandBinding> associa il <xref:System.Windows.Input.ApplicationCommands.Open%2A> con <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute> gestori.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Successivamente, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler> vengono creati.  Il <xref:System.Windows.Input.ExecutedRoutedEventHandler> apre un <xref:System.Windows.MessageBox> che viene visualizzata una stringa indicante che è stato eseguito il comando.  Il <xref:System.Windows.Input.CanExecuteRoutedEventHandler> imposta il <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> proprietà `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Oggetto <xref:System.Windows.Input.CommandBinding> è collegato a un oggetto specifico, come la radice <xref:System.Windows.Window> dell'applicazione o di un controllo.  L'oggetto che il <xref:System.Windows.Input.CommandBinding> è collegato a definisce l'ambito dell'associazione.  Ad esempio, un <xref:System.Windows.Input.CommandBinding> associata a un predecessore del comando di destinazione può essere raggiunto dal <xref:System.Windows.Input.CommandBinding.Executed> evento, ma un <xref:System.Windows.Input.CommandBinding> associata a un discendente del comando di destinazione non può essere raggiunto.  Si tratta di una conseguenza diretta del modo in cui un <xref:System.Windows.RoutedEvent> tunnel e bolle dall'oggetto che genera l'evento.  
  
 In alcune situazioni il <xref:System.Windows.Input.CommandBinding> associato alla destinazione del comando, ad esempio con il <xref:System.Windows.Controls.TextBox> classe e <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, e <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comandi. Tuttavia, spesso è più conveniente collegare il <xref:System.Windows.Input.CommandBinding> a un predecessore della destinazione del comando, ad esempio principale <xref:System.Windows.Window> oppure l'oggetto di applicazione, soprattutto se lo stesso <xref:System.Windows.Input.CommandBinding> può essere utilizzato per più destinazioni comando.  Si tratta di decisioni di progettazione di cui tenere conto quando si crea l'infrastruttura di esecuzione dei comandi.  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>Destinazione del comando  
 La destinazione del comando è l'elemento su cui viene eseguito il comando.  Per quanto riguarda un <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando è l'elemento in corrispondenza di cui il routing di <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandManager.CanExecute> Avvia.  Come indicato in precedenza, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> proprietà <xref:System.Windows.Input.ICommandSource> è applicabile solo quando il <xref:System.Windows.Input.ICommand> è un <xref:System.Windows.Input.RoutedCommand>.  Se il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è impostata su un <xref:System.Windows.Input.ICommandSource> e il comando corrispondente non è un <xref:System.Windows.Input.RoutedCommand>, la destinazione del comando viene ignorata.  
  
 L'origine del comando può impostare in modo esplicito la destinazione del comando.  Se la destinazione del comando non viene definita, l'elemento con lo stato attivo verrà usato come destinazione del comando.  Uno dei vantaggi dell'uso dell'elemento con lo stato attivo come destinazione del comando consiste nel fatto che consente allo sviluppatore di applicazioni di usare la stessa origine del comando per richiamare un comando su più destinazioni senza tenere traccia della destinazione del comando.  Ad esempio, se un <xref:System.Windows.Controls.MenuItem> richiama il **Incolla** comando in un'applicazione che ha un <xref:System.Windows.Controls.TextBox> controllo e un <xref:System.Windows.Controls.PasswordBox> (controllo), la destinazione può essere il <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.PasswordBox> a seconda di quale controllo con lo stato attivo.  
  
 L'esempio seguente mostra come impostare in modo esplicito la destinazione del comando nel markup e nel code-behind.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>CommandManager  
 Il <xref:System.Windows.Input.CommandManager> funge da un numero di comandi funzioni correlate.  Fornisce un set di metodi statici per l'aggiunta e rimozione di <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute>, e <xref:System.Windows.Input.CommandManager.CanExecute> gestori di eventi da e verso un elemento specifico.  Fornisce un modo per registrare <xref:System.Windows.Input.CommandBinding> e <xref:System.Windows.Input.InputBinding> gli oggetti in una classe specifica.  Il <xref:System.Windows.Input.CommandManager> fornisce inoltre un modo, tramite il <xref:System.Windows.Input.CommandManager.RequerySuggested> evento per notificare a un comando quando deve essere generato il <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento.  
  
 Il <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> metodo forza il <xref:System.Windows.Input.CommandManager> per generare il <xref:System.Windows.Input.CommandManager.RequerySuggested> evento.  Ciò è utile per le condizioni che devono disattivare o attivare un comando ma che non sono condizioni che il <xref:System.Windows.Input.CommandManager> è a conoscenza di.  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>Libreria dei comandi  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un set di comandi predefiniti.  Libreria del comando include le classi seguenti: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>e <xref:System.Windows.Input.ComponentCommands>.  Queste classi forniscono comandi, ad esempio <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> e <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, e <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Molti di questi comandi includono un set di associazioni di input predefinite.  Se, ad esempio, si specifica che l'applicazione gestisce il comando di copia, si ottiene automaticamente l'associazione di tastiera "CTRL+C". Si ottengono anche associazioni per altri dispositivi di input, quali i movimenti della penna [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] e informazioni sulle funzioni vocali.  
  
 Quando si fa riferimento ai comandi delle diverse librerie dei comandi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in genere è possibile omettere il nome della classe di libreria che espone la proprietà del comando statico. Di solito i nomi dei comandi sono stringhe non ambigue ed esistono tipi proprietari che forniscono un raggruppamento logico di comandi, ma che non sono necessari per la risoluzione dell'ambiguità. Ad esempio, è possibile specificare `Command="Cut"` anziché il più dettagliato `Command="ApplicationCommands.Cut"`. Si tratta di un meccanismo utile integrato nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore per i comandi (più precisamente, è un comportamento del convertitore di tipi di <xref:System.Windows.Input.ICommand>, quali il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riferimenti processore in fase di caricamento).  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>Creazione di comandi personalizzati  
 Se i comandi delle classi della libreria dei comandi non soddisfano le proprie esigenze, è possibile creare comandi personalizzati.  Questa operazione può essere eseguita in due modi.  Il primo è da zero e l'implementazione di <xref:System.Windows.Input.ICommand> interfaccia.  Viceversa e l'approccio più comune consiste nel creare un <xref:System.Windows.Input.RoutedCommand> o <xref:System.Windows.Input.RoutedUICommand>.  
  
 Per un esempio di creazione di un oggetto personalizzato <xref:System.Windows.Input.RoutedCommand>, vedere [creare un esempio di RoutedCommand personalizzato](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [Cenni preliminari sull'input](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Implementare ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [How to: Add a Command to a MenuItem (Procedura: Aggiungere un comando a un MenuItem)](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)  
 [Create a Custom RoutedCommand Sample (Creare un esempio di oggetto RoutedCommand personalizzato)](http://go.microsoft.com/fwlink/?LinkID=159980)
