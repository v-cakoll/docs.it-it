---
title: Cenni preliminari sugli eventi indirizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached events [WPF]
- grouped button set [WPF]
- routed events [WPF]
- events [WPF], routed
- tunneling [WPF]
- events [WPF], attached
- routing strategies for events [WPF]
- button set [WPF], grouped
- bubbling [WPF]
ms.assetid: 1a2189ae-13b4-45b0-b12c-8de2e49c29d2
ms.openlocfilehash: a6baf073e25635f0a6dd666d681d8bc641128ea0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982360"
---
# <a name="routed-events-overview"></a>Cenni preliminari sugli eventi indirizzati
Questo argomento descrive il concetto di eventi indirizzati in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. L'argomento definisce la terminologia correlata agli eventi indirizzati, descrive in che modo questi eventi sono indirizzati lungo un albero di elementi, riepiloga le modalità di gestione degli eventi indirizzati e spiega come creare eventi indirizzati personalizzati.
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone una conoscenza di base della programmazione [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e orientata a oggetti, oltre che del modo in cui le relazioni tra elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] possono essere concettualizzate sotto forma di albero. Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e saper scrivere applicazioni o pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di base. Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) e [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="routing"></a>   
## <a name="what-is-a-routed-event"></a>Definizione di evento indirizzato  
 È possibile considerare gli eventi indirizzati da un punto di vista funzionale o da una prospettiva di implementazione. In questo argomento sono illustrati entrambi i concetti, perché alcuni utenti trovano più utile il primo e altri il secondo.  
  
 Definizione funzionale: Un evento indirizzato è un tipo di evento che può richiamare gestori su più listener in un albero degli elementi, invece che solo sull'oggetto che ha generato l'evento.  
  
 Definizione di implementazione: Un evento indirizzato è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento supportato da un'istanza del <xref:System.Windows.RoutedEvent> classe e viene elaborato dal [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema degli eventi.  
  
 Un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipica contiene molti elementi. Indipendentemente dal fatto che vengano creati nel codice o dichiarati in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], questi elementi sono legati tra loro da una relazione di albero degli elementi. La route dell'evento può procedere in una di due direzioni, in base alla definizione dell'evento, ma generalmente parte dall'elemento di origine e sale (bubbling) lungo l'albero degli elementi fino a raggiunge la radice dell'albero (in genere una pagina o una finestra). Questo concetto di bubbling può risultare familiare a chi in precedenza ha già usato il modello a oggetti DHTML.  
  
 Considerare il semplice albero degli elementi seguente:  
  
 [!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 Questo albero degli elementi produce un risultato analogo al seguente:  
  
 ![Pulsanti Sì, No e Annulla](./media/routedevent-ovw-1.gif "RoutedEvent_ovw_1")  
  
 In questo albero degli elementi semplificato, l'origine di un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi sono uno dei <xref:System.Windows.Controls.Button> gli elementi e a seconda del valore <xref:System.Windows.Controls.Button> è stato fatto clic è il primo elemento che ha la possibilità di gestire l'evento. Tuttavia, se nessun gestore associato per il <xref:System.Windows.Controls.Button> agisce sull'evento, quindi l'evento di bubbling verso l'alto al <xref:System.Windows.Controls.Button> padre nell'albero degli elementi, ovvero il <xref:System.Windows.Controls.StackPanel>. Potenzialmente, le bolle di eventi per <xref:System.Windows.Controls.Border>, quindi fino alla radice della pagina dell'albero degli elementi (non illustrata).  
  
 In altre parole, la route degli eventi per questo <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento è:  
  
 Button-->StackPanel-->Border-->...  
  
### <a name="top-level-scenarios-for-routed-events"></a>Scenari principali per gli eventi indirizzati  
 Di seguito è disponibile un breve riepilogo degli scenari per i quali si è reso necessario introdurre il concetto di evento indirizzato, con la spiegazione dei motivi per cui un evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] tipico non è adatto per questi scenari:  
  
 **La composizione e incapsulamento:** Vari controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di un modello di contenuto avanzato. Ad esempio, è possibile inserire un'immagine all'interno di un <xref:System.Windows.Controls.Button>, che estende in modo efficace la struttura ad albero visuale del pulsante. Tuttavia, l'immagine aggiunta non deve interrompere il comportamento di hit testing che fa sì che un pulsante rispondere a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del relativo contenuto, anche se l'utente fa clic su pixel che fanno tecnicamente parte dell'immagine.  
  
 **Singoli punti del gestore degli allegati:** In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], sarebbe necessario collegare lo stesso gestore più volte per elaborare gli eventi che possono essere generati da più elementi. Gli eventi indirizzati consentono di associare il gestore una sola volta, come illustrato nell'esempio precedente, e di usare la logica del gestore per determinare da dove proviene l'evento, se necessario. Ad esempio, questo potrebbe essere il gestore per il codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] illustrato in precedenza:  
  
 [!code-csharp[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#groupbuttoncodebehind)]
 [!code-vb[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#groupbuttoncodebehind)]  
  
 **Gestione della classe:** Instradato eventi permesso di un gestore statico definito dalla classe. Questo gestore di classi ha la possibilità di gestire un evento prima di qualsiasi gestore di istanze associato.  
  
 **Riferimento a un evento senza reflection:** Alcune tecniche di codice e markup richiedono un modo per identificare un evento specifico. Crea un evento indirizzato un <xref:System.Windows.RoutedEvent> campo come un identificatore, che fornisce una tecnica di identificazione di eventi affidabile che non richiede reflection statica di runtime.  
  
### <a name="how-routed-events-are-implemented"></a>Modalità di implementazione degli eventi indirizzati  
 Un evento indirizzato è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento supportato da un'istanza del <xref:System.Windows.RoutedEvent> classe e registrato con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema degli eventi. Il <xref:System.Windows.RoutedEvent> istanza ottenuta dalla registrazione viene generalmente mantenuta come un `public` `static` `readonly` membro del campo della classe che registra e pertanto è "proprietario" dell'evento indirizzato. La connessione all'evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con nome identico (in alcuni casi indicato come evento "wrapper") viene effettuata eseguendo l'override delle implementazioni di `add` e `remove` per l'evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Normalmente, `add` e `remove` vengono lasciati come impostazione predefinita implicita che usa la sintassi di evento specifica del linguaggio per aggiungere e rimuovere i gestori dell'evento. Il meccanismo di supporto e connessione di eventi indirizzati è concettualmente simile al modo in cui una proprietà di dipendenza è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proprietà supportata dal <xref:System.Windows.DependencyProperty> classe e registrato con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà.  
  
 L'esempio seguente illustra la dichiarazione per una classe personalizzata `Tap` evento indirizzato, incluse la registrazione e l'esposizione del <xref:System.Windows.RoutedEvent> campo dell'identificatore e il `add` e `remove` implementazioni per le `Tap` [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento.  
  
 [!code-csharp[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#addremovehandler)]
 [!code-vb[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#addremovehandler)]  
  
### <a name="routed-event-handlers-and-xaml"></a>Gestori di eventi indirizzati e XAML  
 Per aggiungere un gestore per un evento usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], il nome dell'evento deve essere dichiarato come attributo dell'elemento che è un listener di eventi. Il valore dell'attributo è il nome del metodo del gestore implementato, che deve trovarsi nella classe parziale del file code-behind.  
  
 [!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 La sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per l'aggiunta di gestori eventi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] standard è uguale a quella usata per l'aggiunta di gestori di eventi indirizzati, perché si aggiungono effettivamente i gestori al wrapper di eventi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], che ha un'implementazione sottostante degli eventi indirizzati. Per altre informazioni sull'aggiunta di gestori eventi in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="routing_strategies"></a>   
## <a name="routing-strategies"></a>Strategie di routing  
 Gli eventi indirizzati usano una delle tre strategie di routing illustrate di seguito:  
  
- **Bubbling:** Vengono richiamati i gestori eventi sull'origine dell'evento. L'evento indirizzato viene quindi indirizzato agli elementi padre successivi fino a raggiungere la radice dell'albero degli elementi. La maggior parte degli eventi indirizzati usa la strategia di bubbling. Gli eventi indirizzati di bubbling vengono in genere usati per segnalare l'input o le modifiche dello stato da controlli distinti o altri elementi dell'interfaccia utente.  
  
- **Diretto:** Solo l'elemento di origine ha la possibilità di richiamare i gestori in risposta. Questa strategia è analoga al "routing" usato da [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] per gli eventi. Tuttavia, a differenza di uno standard [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento, indirizzare gli eventi indirizzati supportano la gestione di classi (gestione delle classi è descritto in una sezione successiva) e può essere utilizzato da <xref:System.Windows.EventSetter> e <xref:System.Windows.EventTrigger>.  
  
- **Il tunneling:** Inizialmente, vengono richiamati i gestori di eventi alla radice dell'albero dell'elemento. L'evento indirizzato percorre quindi una route attraverso elementi figlio successivi, verso l'elemento nodo che rappresenta l'origine dell'evento indirizzato (l'elemento che ha generato l'evento indirizzato). Gli eventi indirizzati di tunneling vengono spesso usati o gestiti come parte della composizione di un controllo, in modo che gli eventi di parti composite possano essere deliberatamente eliminati o sostituiti da eventi specifici del controllo completo. Gli eventi di input forniti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono spesso implementati come coppia di tunneling/bubbling. Gli eventi di tunneling sono talvolta anche detti eventi di anteprima, per una convenzione di denominazione usata per le coppie.  
  
<a name="why_use"></a>   
## <a name="why-use-routed-events"></a>Vantaggi offerti dall'uso degli eventi indirizzati  
 Per gli sviluppatori di applicazioni non è sempre necessario o importante sapere se l'evento gestito è implementato come evento indirizzato. Gli eventi indirizzati hanno un comportamento speciale, che però è per lo più invisibile se l'evento viene gestito sull'elemento in cui è stato generato.  
  
 Gli eventi indirizzati diventano particolarmente efficaci se si usa uno degli scenari suggeriti: definizione di gestori comuni in una radice comune, composizione di un controllo personalizzato o definizione di una classe di controlli personalizzata.  
  
 Non è necessario che i listener e le origini degli eventi indirizzati condividano un evento comune nella gerarchia. Eventuali <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> può essere un listener di eventi per qualsiasi evento indirizzato. È quindi possibile usare il set completo di eventi indirizzati disponibile nel set di [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] come "interfaccia" concettuale tramite cui elementi diversi dell'applicazione possono scambiarsi informazioni sugli eventi. Questo concetto di "interfaccia" per gli eventi indirizzati è applicabile in particolar modo agli eventi di input.  
  
 Gli eventi indirizzati possono anche essere usati per comunicare nell'albero degli elementi, poiché i dati di un evento vengono trasmessi a ogni elemento nella route. Se un elemento modifica in qualche modo i dati dell'evento, tale modifica risulta disponibile per l'elemento successivo nella route.  
  
 Oltre all'aspetto del routing, ci sono altri due motivi per cui qualsiasi evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può essere implementato come evento indirizzato invece che come evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] standard. Se si implementano eventi personalizzati, considerare anche questi principi:  
  
- Determinati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stili e modelli caratteristiche, ad esempio <xref:System.Windows.EventSetter> e <xref:System.Windows.EventTrigger> richiedono che l'evento di cui viene fatto riferimento da un evento indirizzato. Si tratta dello scenario di identificatore dell'evento citato in precedenza.  
  
- Gli eventi indirizzati supportano un meccanismo di gestione delle classi in base al quale la classe può specificare metodi statici che hanno la possibilità di gestire gli eventi indirizzati prima che qualsiasi gestore di istanze registrato possa accedervi. Questa funzionalità è molto utile nella progettazione di controlli, perché la classe può imporre comportamenti di classe basati su eventi che non possono essere eliminati accidentalmente mediante la gestione di un evento su un'istanza.  
  
 Ognuna delle considerazioni precedenti viene discussa in una sezione separata di questo argomento.  
  
<a name="event_handing"></a>   
## <a name="adding-and-implementing-an-event-handler-for-a-routed-event"></a>Aggiunta e implementazione di un gestore eventi per un evento indirizzato  
 Per aggiungere un gestore eventi in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è sufficiente aggiungere il nome dell'evento a un elemento come attributo e impostare il valore dell'attributo come nome del gestore eventi che implementa un delegato appropriato, come nell'esempio seguente.  
  
 [!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 `b1SetColor` è il nome del gestore implementato che contiene il codice che gestisce il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. `b1SetColor` deve avere la stessa firma il <xref:System.Windows.RoutedEventHandler> delegato, ossia il delegato del gestore eventi per il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. Il primo parametro di tutti i delegati dei gestori di eventi indirizzati specifica l'elemento a cui viene aggiunto il gestore eventi, mentre il secondo parametro specifica i dati per l'evento.  
  
[!code-csharp[EventOvwSupport#SimpleHandlerA](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlera)]
[!code-vb[EventOvwSupport#SimpleHandlerA](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlera)]  
  
 <xref:System.Windows.RoutedEventHandler> è il delegato del gestore eventi indirizzati di base. Per gli eventi indirizzati specializzati per determinati controlli o scenari, i delegati da usare per i gestori di eventi indirizzati possono anche essere più specializzati, in modo da poter trasmettere dati di eventi specializzati. In uno scenario comune di input, ad esempio, è possibile gestire un <xref:System.Windows.UIElement.DragEnter> evento indirizzato. Il gestore deve implementare il <xref:System.Windows.DragEventHandler> delegare. Tramite il delegato più specifico, è possibile elaborare la <xref:System.Windows.DragEventArgs> nel gestore e leggere il <xref:System.Windows.DragEventArgs.Data%2A> proprietà, che contiene il payload degli Appunti dell'operazione di trascinamento.  
  
 Per un esempio completo di come aggiungere un gestore eventi a un elemento usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [Gestire un evento indirizzato](how-to-handle-a-routed-event.md).  
  
 L'aggiunta di un gestore per un evento indirizzato in un'applicazione creata nel codice è semplice. Gestori di eventi indirizzati possono sempre essere aggiunti tramite un metodo helper <xref:System.Windows.UIElement.AddHandler%2A> (che è lo stesso metodo che richiede il supporto esistente `add`.) Tuttavia, gli eventi indirizzati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti hanno in genere implementazioni di supporto per la logica `add` e `remove` che consentono l'aggiunta di gestori per gli eventi indirizzati tramite una sintassi di evento specifica del linguaggio, che è più intuitiva rispetto al metodo helper. Di seguito è illustrato un esempio di utilizzo del metodo helper:  
  
 [!code-csharp[EventOvwSupport#AddHandlerCode](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlercode)]
 [!code-vb[EventOvwSupport#AddHandlerCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlercode)]  
  
 L'esempio seguente mostra la C# sintassi dell'operatore (Visual Basic con sintassi dell'operatore leggermente diversa a causa della gestione della dereferenziazione):  
  
 [!code-csharp[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlerplusequals)]
 [!code-vb[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlerplusequals)]  
  
 Per un esempio di come aggiungere un gestore eventi nel codice, vedere [Aggiungere un gestore eventi mediante codice](how-to-add-an-event-handler-using-code.md).  
  
 Se si usa Visual Basic, è anche possibile usare il `Handles` (parola chiave) per aggiungere gestori come parte delle dichiarazioni dei gestori. Per altre informazioni, vedere [Visual Basic e la gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="concept_handled"></a>   
### <a name="the-concept-of-handled"></a>Concetto di gestito  
 Tutti gli eventi indirizzati condividono un'evento dati classe di base comune, <xref:System.Windows.RoutedEventArgs>. <xref:System.Windows.RoutedEventArgs> definisce il <xref:System.Windows.RoutedEventArgs.Handled%2A> proprietà, che accetta un valore booleano. Lo scopo del <xref:System.Windows.RoutedEventArgs.Handled%2A> proprietà consiste nell'abilitare qualsiasi gestore eventi lungo la route di contrassegnare l'evento indirizzato come *gestita*, impostando il valore di <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true`. Dopo essere stati elaborati dal gestore in corrispondenza di un elemento lungo la route, i dati di evento condivisi vengono nuovamente segnalati a ogni listener lungo la route.  
  
 Il valore di <xref:System.Windows.RoutedEventArgs.Handled%2A> influisce sul modo in cui un evento indirizzato viene segnalato o elaborato tragitto ulteriormente lungo la route. Se <xref:System.Windows.RoutedEventArgs.Handled%2A> è `true` nell'evento dati per un evento indirizzato, quindi i gestori in ascolto per l'evento indirizzato su altri elementi non vengono in genere non è più richiamati per quell'istanza particolare evento. Ciò vale sia per i gestori associati in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che per i gestori aggiunti da sintassi di associazione dei gestori eventi specifiche del linguaggio, come `+=` o `Handles`. Per gli scenari di gestori più comuni, il contrassegno di un evento come gestito impostando <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` viene interrotto, il routing per una route di tunneling o una route di bubbling, nonché per qualsiasi evento che viene gestita in un punto nella route da un gestore della classe.  
  
 Tuttavia, c'è un meccanismo "handledEventsToo" in base al quale i listener possono comunque eseguire gestori in risposta a eventi indirizzati in cui <xref:System.Windows.RoutedEventArgs.Handled%2A> è `true` nei dati dell'evento. In altre parole, la route dell'evento non viene effettivamente interrotta contrassegnando i dati di evento come gestiti. È possibile usare il meccanismo handledEventsToo solo nel codice o in un <xref:System.Windows.EventSetter>:  
  
- Nel codice, anziché usando una sintassi di evento specifica del linguaggio che funziona per uso generale [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] gli eventi, chiamare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] metodo <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> per aggiungere il gestore. Specificare il valore di `handledEventsToo` come `true`.  
  
- In un' <xref:System.Windows.EventSetter>, impostare il <xref:System.Windows.EventSetter.HandledEventsToo%2A> attributo `true`.  
  
 Oltre al comportamento che <xref:System.Windows.RoutedEventArgs.Handled%2A> stato produce negli eventi indirizzati, il concetto di <xref:System.Windows.RoutedEventArgs.Handled%2A> ha implicazioni per la modalità di progettazione dell'applicazione e scrivere il codice del gestore eventi. È possibile definire il concetto <xref:System.Windows.RoutedEventArgs.Handled%2A> come un semplice protocollo esposto dagli eventi indirizzati. Esattamente come si usa questo protocollo è dallo sviluppatore, ma la progettazione concettuale relativa come il valore di <xref:System.Windows.RoutedEventArgs.Handled%2A> dovrà essere utilizzato sia come indicato di seguito:  
  
- Se un evento indirizzato è contrassegnato come gestito, non è necessario che venga gestito nuovamente da altri elementi lungo la route.  
  
- Se un evento indirizzato non è contrassegnato come gestito, quindi altri listener precedenti nella route hanno scelto di non registrare un gestore oppure i gestori registrati hanno scelto di non modificare i dati dell'evento e impostare <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true`. È anche possibile, ovviamente, che il listener corrente sia il primo punto nella route. I gestori sul listener corrente a questo punto hanno tre possibilità:  
  
    - Non eseguire alcuna azione. L'evento rimane non gestito e viene indirizzato al listener successivo.  
  
    - Eseguire il codice in risposta all'evento, ma stabilire che l'azione eseguita non è sufficiente per contrassegnare l'evento come gestito. L'evento viene indirizzato al listener successivo.  
  
    - Eseguire il codice in risposta all'evento. Contrassegnare l'evento come gestito nei dati di evento passati al gestore, perché l'azione eseguita viene ritenuta sufficiente per contrassegnare l'evento come gestito. L'evento viene comunque indirizzato al listener successivo, ma con <xref:System.Windows.RoutedEventArgs.Handled%2A> = `true` nei dati dell'evento, in modo che solo `handledEventsToo` listener hanno la possibilità di richiamare altri gestori.  
  
 Questa progettazione concettuale è consolidata dal comportamento di routing descritto in precedenza: risulta più difficile (anche se è comunque possibile nel codice o stili) per collegare i gestori per gli eventi indirizzati richiamati anche se un gestore precedente lungo la route è già impostata <xref:System.Windows.RoutedEventArgs.Handled%2A>a `true`.  
  
 Per altre informazioni sulle <xref:System.Windows.RoutedEventArgs.Handled%2A>, la gestione delle classi degli eventi indirizzati e raccomandazioni su quando è appropriato contrassegnare un evento indirizzato come <xref:System.Windows.RoutedEventArgs.Handled%2A>, vedere [contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
 Nelle applicazioni, è piuttosto comune gestire un evento indirizzato di bubbling solo sull'oggetto che lo ha generato, senza preoccuparsi delle caratteristiche di routing dell'evento. È tuttavia comunque consigliabile contrassegnare l'evento indirizzato come gestito nei dati di evento, per evitare effetti collaterali imprevisti nel caso in cui un elemento più in alto nell'albero degli elementi abbia un gestore associato per lo stesso evento indirizzato.  
  
<a name="class_handlers"></a>   
## <a name="class-handlers"></a>Gestori di classi  
 Se si sta definendo una classe che deriva in qualche modo dal <xref:System.Windows.DependencyObject>, è anche possibile definire e collegare un gestore classi per un evento indirizzato che è un membro di evento dichiarato o ereditato della classe. I gestori di classi vengono richiamati prima dei gestori di listener di istanze associati a un'istanza di tale classe, ogni volta che un evento indirizzato raggiunge un'istanza dell'elemento nella relativa route.  
  
 Alcuni controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno una gestione intrinseca delle classi per determinati eventi indirizzati. In questo modo potrebbe sembrare che l'evento indirizzato non venga mai generato, ma in realtà viene gestito tramite classi e, usando determinate tecniche, può essere ancora gestito dai gestori di istanze. Molti controlli e classi di base, inoltre, espongono metodi virtuali che possono essere usati per eseguire l'override del comportamento di gestione delle classi. Per altre informazioni su come evitare un comportamento di gestione delle classi non desiderato e su come definire la gestione delle classi in una classe personalizzata, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="attached_events"></a>   
## <a name="attached-events-in-wpf"></a>Eventi associati in WPF  
 Il linguaggio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definisce anche un tipo di evento speciale noto come *evento associato*. Un evento associato consente di aggiungere un gestore per un determinato evento a un elemento arbitrario. L'elemento che gestisce l'evento non deve necessariamente definire o ereditare l'evento associato, né l'oggetto che genera potenzialmente l'evento o l'istanza di gestione di destinazione deve necessariamente definire o "possedere" in altro modo tale evento come membro della classe.  
  
 Il sistema di input di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fa largo uso degli eventi associati. Tuttavia, quasi tutti questi eventi associati vengono inoltrati tramite elementi di base. Gli eventi di input appaiono quindi come eventi indirizzati non associati equivalenti, membri della classe di elementi di base. Ad esempio, l'evento associato sottostante <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> può essere gestito più facilmente in qualsiasi dato <xref:System.Windows.UIElement> utilizzando <xref:System.Windows.UIElement.MouseDown> su esso <xref:System.Windows.UIElement> invece di utilizzare la sintassi dell'evento associato sia in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o codice.  
  
 Per altre informazioni sugli eventi associati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Cenni preliminari sugli eventi associati](attached-events-overview.md).  
  
<a name="Qualifying_Event_Names_in_XAML_for_Anticipated_Routing"></a>   
## <a name="qualified-event-names-in-xaml"></a>Nomi di evento completi in XAML  
 Un altro utilizzo della sintassi simile alla sintassi dell'evento associato *nometipo*.*nomeevento*, che però non è esattamente un utilizzo di un evento associato, è rappresentato dall'associazione di gestori per eventi indirizzati generati da elementi figlio. I gestori vengono associati a un elemento padre comune, per sfruttare il routing degli eventi, anche se l'evento indirizzato rilevante potrebbe non essere membro dell'elemento padre comune. Si consideri di nuovo questo esempio:  
  
 [!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 In questo caso, il listener dell'elemento padre in cui viene aggiunto il gestore di è un <xref:System.Windows.Controls.StackPanel>. Tuttavia, viene aggiunto un gestore per un evento indirizzato che è stato dichiarato e verrà generato dal <xref:System.Windows.Controls.Button> classe (<xref:System.Windows.Controls.Primitives.ButtonBase> effettivamente, ma disponibile a <xref:System.Windows.Controls.Button> attraverso l'ereditarietà). <xref:System.Windows.Controls.Button> "proprietario" dell'evento, ma i gestori di permessi system evento indirizzato per qualsiasi evento indirizzato a qualsiasi <xref:System.Windows.UIElement> oppure <xref:System.Windows.ContentElement> listener di istanze che a listener per un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] evento. Lo spazio dei nomi xmlns predefinito per questi nomi completi di attributo di evento è in genere lo spazio dei nomi xmlns [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinito, ma è anche possibile specificare spazi dei nomi con prefisso per eventi indirizzati personalizzati. Per altre informazioni su xmlns, vedere [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="how_event_processing_works"></a>   
## <a name="wpf-input-events"></a>Eventi di input WPF  
 Un'applicazione frequente degli eventi indirizzati nella piattaforma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] riguarda gli eventi di input. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i nomi degli eventi indirizzati di tunneling sono preceduti dalla parola "Preview" per convenzione. Gli eventi di input sono spesso in coppia, con un evento che rappresenta l'evento di bubbling e l'altro quello di tunneling. Ad esempio, il <xref:System.Windows.ContentElement.KeyDown> eventi e <xref:System.Windows.ContentElement.PreviewKeyDown> eventi hanno la stessa firma, ma il primo evento di input di bubbling e il secondo è il tunneling di eventi di input. In alcuni casi, gli eventi di input hanno solo una versione di bubbling o solo una versione indirizzata diretta. Nella documentazione, gli argomenti relativi agli eventi indirizzati contengono riferimenti incrociati a eventi indirizzati simili con strategie di routing alternative, se disponibili, e le sezioni nelle pagine di riferimenti gestiti chiariscono la strategia di routing per ogni evento indirizzato.  
  
 Gli eventi di input [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in coppia vengono implementati in modo che una singola azione di input dell'utente, ad esempio la pressione di un pulsante del mouse, generi entrambi gli eventi indirizzati della coppia in sequenza. Per prima cosa, viene generato l'evento di tunneling, che avanza nella route. Successivamente, viene generato l'evento di bubbling, che avanza nella route. I due eventi condividono letteralmente la stessa istanza di dati di evento, perché il <xref:System.Windows.UIElement.RaiseEvent%2A> chiamata al metodo nella classe di implementazione che genera l'evento di bubbling è in ascolto per i dati dell'evento dall'evento di tunneling e li riutilizza nel nuovo evento generato. I listener con gestori per l'evento di tunneling hanno l'opportunità di contrassegnare per primi l'evento indirizzato come gestito (prima i gestori di classi, quindi i gestori di istanze). Se un elemento nella route di tunneling ha contrassegnato l'evento indirizzato come gestito, i dati dell'evento già gestito vengono inviati per l'evento di bubbling e i gestori tipici associati per gli eventi di input di bubbling equivalenti non vengono richiamati. Dall'esterno, potrebbe sembrare che l'evento di bubbling gestito non sia mai stato generato. Questo comportamento di gestione è utile per la composizione di controlli in cui si vuole che tutti gli eventi di input basati su hit test o gli eventi di input basati su stato attivo vengano segnalati dal controllo finale, invece che dalle relative parti composite. L'elemento del controllo finale è più vicino alla radice nella composizione e quindi ha la possibilità di gestire tramite classi prima l'evento di tunneling ed eventualmente di "sostituire" tale evento indirizzato con un evento più specifico del controllo, come parte del codice sottostante la classe del controllo.  
  
 Come dimostrazione del funzionamento dell'elaborazione degli eventi di input, considerare l'esempio di evento di input seguente. Nell'albero della figura seguente `leaf element #2` è l'origine di un evento `PreviewMouseDown` e quindi di un evento `MouseDown`.  
  
 ![Diagramma del routing degli eventi](./media/wcsdkcoreinputevents.png "wcsdkCoreInputEvents")  
Bubbling e tunneling degli eventi di input  
  
 L'ordine di elaborazione degli eventi è il seguente:  
  
1. `PreviewMouseDown` (tunneling) sull'elemento radice.  
  
2. `PreviewMouseDown` (tunneling) sull'elemento intermedio 1.  
  
3. `PreviewMouseDown` (tunneling) sull'elemento di origine 2.  
  
4. `MouseDown` (bubbling) sull'elemento di origine 2.  
  
5. `MouseDown` (bubbling) sull'elemento intermedio 1.  
  
6. `MouseDown` (bubbling) sull'elemento radice.  
  
 Un delegato di un gestore di eventi indirizzati fornisce riferimenti a due oggetti: l'oggetto che ha generato l'evento e quello su cui è stato richiamato il gestore. L'oggetto in cui è stato richiamato il gestore è quello indicato dal parametro `sender`. L'oggetto in cui prima è stato generato l'evento viene segnalato dal <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà nei dati dell'evento. Un evento indirizzato può comunque essere generato e gestito dallo stesso oggetto, nel qual caso `sender` e <xref:System.Windows.RoutedEventArgs.Source%2A> sono identici (questo è il caso con i passaggi 3 e 4 nell'evento l'elaborazione di esempio di elenco).  
  
 A causa di tunneling e bubbling, gli elementi padre ricevono eventi di input in cui il <xref:System.Windows.RoutedEventArgs.Source%2A> è uno dei relativi figlio elementi. Quando è importante sapere che cos'è l'elemento di origine, è possibile identificare l'elemento di origine mediante l'accesso di <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà.  
  
 In genere, quando l'evento di input è stato contrassegnato <xref:System.Windows.RoutedEventArgs.Handled%2A>, ulteriormente non vengono richiamati i gestori. Solitamente è consigliabile contrassegnare gli eventi di input come gestiti non appena viene richiamato un gestore che applica la gestione logica specifica dell'applicazione al significato dell'evento di input.  
  
 L'eccezione a questa istruzione generale sullo <xref:System.Windows.RoutedEventArgs.Handled%2A> lo stato è che l'input gestori eventi registrati per ignorare intenzionalmente <xref:System.Windows.RoutedEventArgs.Handled%2A> lo stato dei dati dell'evento verrà comunque richiamato lungo la route. Per altre informazioni, vedere [Eventi di anteprima](preview-events.md) e [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
 Il modello di dati di evento condivisi tra eventi di tunneling e di bubbling e la generazione sequenziale di eventi prima di tunneling e quindi di bubbling non sono concetti generalmente veri per tutti gli eventi indirizzati. Questo comportamento viene implementato specificamente dal modo in cui i dispositivi di input [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] scelgono di generare e connettere le coppie di eventi di input. L'implementazione di eventi di input personalizzati è un scenario avanzato, ma si può scegliere di seguire tale modello anche per gli eventi di input personalizzati.  
  
 Alcune classi scelgono di gestire tramite classi determinati eventi di input, di solito con lo scopo di ridefinire il significato di un determinato evento di input generato dall'utente all'interno del controllo e di generare un nuovo evento. Per altre informazioni, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
 Per altre informazioni sull'input e su come input ed eventi interagiscono in scenari di applicazioni tipici, vedere [Cenni preliminari sull'input](input-overview.md).  
  
<a name="events_styles"></a>   
## <a name="eventsetters-and-eventtriggers"></a>EventSetters ed EventTriggers  
 Negli stili, è possibile includere pre-dichiarata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la gestione di sintassi nel markup tramite eventi un <xref:System.Windows.EventSetter>. Quando lo stile viene applicato, il gestore a cui si fa riferimento viene aggiunto all'istanza a cui è stato applicato lo stile. È possibile dichiarare un <xref:System.Windows.EventSetter> solo per un evento indirizzato. Di seguito è riportato un esempio. Si noti che il metodo `b1SetColor` a cui si fa riferimento qui si trova in un file code-behind.  
  
 [!code-xaml[EventOvwSupport#XAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/page2.xaml#xaml2)]  
  
 Il vantaggio è che lo stile contiene probabilmente numerose altre informazioni che è stato possibile applicare a qualsiasi pulsante nell'applicazione, e verificano le <xref:System.Windows.EventSetter> far parte di tale stile promuove il riutilizzo del codice anche a livello di markup. Inoltre, un <xref:System.Windows.EventSetter> astrae i nomi dei metodi per gestori in modo più avanzato rispetto al markup generale di pagina e dell'applicazione.  
  
 Un'altra sintassi specializzata che combina le funzionalità di animazione ed eventi indirizzati di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è un <xref:System.Windows.EventTrigger>. Come per gli <xref:System.Windows.EventSetter>, solo gli eventi indirizzati possono essere usati per un <xref:System.Windows.EventTrigger>. In genere, un' <xref:System.Windows.EventTrigger> viene dichiarato come parte di uno stile, ma un <xref:System.Windows.EventTrigger> possono anche essere dichiarate su elementi a livello di pagina come parte delle <xref:System.Windows.FrameworkElement.Triggers%2A> insieme, o in un <xref:System.Windows.Controls.ControlTemplate>. Un' <xref:System.Windows.EventTrigger> consente di specificare un <xref:System.Windows.Media.Animation.Storyboard> che viene eseguito ogni volta che un evento indirizzato raggiunge un elemento nella relativa route che dichiara un <xref:System.Windows.EventTrigger> per quell'evento. Il vantaggio di un' <xref:System.Windows.EventTrigger> rispetto alla semplice la gestione dell'evento e al conseguente avvio uno storyboard esistente è che un <xref:System.Windows.EventTrigger> fornisce un controllo migliore sullo storyboard e relativo comportamento in fase di esecuzione. Per altre informazioni, vedere [Usare i trigger di evento per controllare uno storyboard dopo il relativo avvio](../graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
<a name="more_about"></a>   
## <a name="more-about-routed-events"></a>Altre informazioni sugli eventi indirizzati  
 Questo argomento illustra gli eventi indirizzati principalmente con lo scopo di descrivere i concetti di base e di fornire istruzioni su come e quando rispondere agli eventi indirizzati già presenti nei vari controlli ed elementi di base. È tuttavia possibile creare un evento indirizzato personalizzato in una classe personalizzata insieme a tutto il supporto necessario, come delegati e classi di dati di evento specializzati. Il proprietario dell'evento indirizzato può essere qualsiasi classe, ma devono essere generati da e gestiti da eventi indirizzati <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> classi derivate per poter essere utili. Per altre informazioni sugli eventi personalizzati, vedere [Creare un evento indirizzato personalizzato](how-to-create-a-custom-routed-event.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.EventManager>
- <xref:System.Windows.RoutedEvent>
- <xref:System.Windows.RoutedEventArgs>
- [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Cenni preliminari sull'input](input-overview.md)
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Strutture ad albero in WPF](trees-in-wpf.md)
- [Modelli di eventi deboli](weak-event-patterns.md)
