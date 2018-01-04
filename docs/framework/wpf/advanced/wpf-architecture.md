---
title: Architettura WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], attached
- attached properties [WPF]
- architecture [WPF]
- unmanaged components [WPF]
- affinity thread [WPF]
- Storyboards [WPF]
- milcore [WPF]
- components [WPF], unmanaged
- painter's algorithm
- interfaces [WPF], INotifyPropertyChange
- CommandBindings [WPF]
- data templates [WPF]
- thread [WPF], affinity
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d688bb460b01c0b3fe4d7571916b887cd485b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-architecture"></a>Architettura WPF
Questo argomento fornisce una presentazione guidata della gerarchia di classi di [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]. Viene illustrata la maggior parte dei sottosistemi principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]e ne vengono descritte le modalità di interazione. Vengono inoltre forniti i dettagli relativi ad alcune scelte effettuate dagli architetti di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
  
<a name="System_Object"></a>   
## <a name="systemobject"></a>System.Object  
 Il principale modello di programmazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] viene esposto tramite codice gestito. Nella fase iniziale della progettazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ci sono stati diversi dibattiti in merito al punto in cui tracciare una linea tra i componenti gestiti del sistema e quelli non gestiti. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] fornisce numerose funzionalità che consentono uno sviluppo più produttivo e potente (che include gestione della memoria, gestione degli errori, Common Type System e così via) ma che presentano anche alcuni svantaggi.  
  
 La figura riportata di seguito mostra i componenti principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Le sezioni in rosso del diagramma (PresentationFramework, PresentationCore e milcore) sono le parti di codice principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Di queste, solo milcore è un componente non gestito. Milcore è scritto in codice non gestito per consentire una stretta integrazione con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tutto viene visualizzato tramite il motore [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], consentendo un rendering efficiente dell'hardware e del software. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ha richiesto anche un controllo dettagliato sulla memoria e sull'esecuzione. Il motore di composizione di milcore è estremamente sensibile alle prestazioni e ha richiesto la rinuncia a molti vantaggi di [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] per migliorarne il livello.  
  
 ![Posizione di WPF all'interno di .NET Framework.](../../../../docs/framework/wpf/advanced/media/wpf-architect1.PNG "wpf_architect1")  
  
 La comunicazione tra le parti gestite e quelle non gestite di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] viene discussa più avanti in questo argomento. Il resto del modello di programmazione gestito viene descritto di seguito.  
  
<a name="System_Threading_DispatcherObject"></a>   
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 La maggior parte degli oggetti in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] derivano da <xref:System.Windows.Threading.DispatcherObject>, che fornisce i costrutti di base per la gestione della concorrenza e threading. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] si basa su un sistema di messaggistica implementato dal dispatcher. Funziona in modo molto simile al noto message pump di [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]; il dispatcher [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizza infatti i messaggi User32 per l'esecuzione di chiamate cross-thread.  
  
 Quando si discute di concorrenza in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] i due concetti fondamentali da comprendere sono il dispatcher e l'affinità di thread.  
  
 Durante la fase di progettazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], l'obiettivo era di passare a un singolo thread di esecuzione ma con un modello ottimizzato per l'affinità in assenza di altri thread. L'affinità di thread si verifica quando un componente utilizza l'identità del thread in esecuzione per archiviare un tipo di stato. Nella forma più comune, per archiviare lo stato viene utilizzata l'archiviazione locale di thread (TLS). L'affinità di thread richiede che ciascun thread di esecuzione logico appartenga a un solo thread fisico del sistema operativo, che può richiedere un elevato consumo di memoria. Alla fine, il modello di threading di WPF è stato tenuto in sincronia con il modello di threading User32 esistente dell'esecuzione a thread singolo con affinità di thread. Il motivo principale per questo oggetto è stato l'interoperabilità: sistemi quali [!INCLUDE[TLA2#tla_ole2.0](../../../../includes/tla2sharptla-ole2-0-md.md)], Appunti e Internet Explorer richiedono tutti l'esecuzione di affinità di thread singolo (STA).  
  
 Disponendo di oggetti con threading STA, è necessaria una modalità di comunicazione tra thread e di conferma di utilizzo del thread corretto. Qui si colloca il ruolo del dispatcher. Il dispatcher è un sistema di base di invio di messaggi con più code in ordine di priorità. Gli esempi di messaggi includono le notifiche di input non elaborato (spostamenti del mouse), le funzionalità del framework (layout) o i comandi utente (esecuzione di metodi). Mediante la derivazione da <xref:System.Windows.Threading.DispatcherObject>, si crea un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oggetto comportamento STA e dotato di un puntatore a un dispatcher al momento della creazione.  
  
<a name="System_Windows_DependencyObject"></a>   
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Una delle filosofie di base relative all'architettura utilizzata nella compilazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è stata quella di preferire le proprietà ai metodi o agli eventi. Le proprietà sono dichiarative e consentono di specificare più facilmente lo scopo anziché l'azione. In tal modo veniva anche supportato un sistema basato sui modelli o sui dati per la visualizzazione dei contenuti dell'interfaccia utente. Lo scopo di tale approccio era di creare un maggior numero di proprietà con cui stabilire l'associazione per poter controllare meglio il comportamento di un'applicazione.  
  
 Perché una parte maggiore del sistema fosse basata sulle proprietà, era necessario disporre di un sistema di proprietà più ricco di quello fornito da [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Un semplice esempio è rappresentato dalle notifiche di modifica. Per abilitare l'associazione bidirezionale, è necessario che entrambi i lati supportino la notifica di modifica. Per associare il comportamento a valori di proprietà, è necessario ricevere una notifica quando tale valore viene modificato. [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] dispone di un'interfaccia opzionale, **INotifyPropertyChange**, che consente a un oggetto di pubblicare le notifiche di modifica.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]fornisce un sistema di proprietà più ricco, derivato dal <xref:System.Windows.DependencyObject> tipo. Il sistema di proprietà è effettivamente un sistema di proprietà delle "dipendenze" nel senso che tiene traccia delle dipendenze tra espressioni di proprietà e riconvalida automaticamente i valori delle proprietà quando tali dipendenze vengono modificate. Ad esempio, se si dispone di una proprietà che eredita (ad esempio <xref:System.Windows.Controls.Control.FontSize%2A>), il sistema viene aggiornato automaticamente se viene modificata la proprietà su un elemento padre di un elemento che eredita il valore.  
  
 Il concetto di espressione di proprietà è alla base del sistema di proprietà di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In questa prima versione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], il sistema delle espressioni di proprietà è chiuso e tutte le espressioni vengono fornite come parte del framework. Le espressioni rappresentano il motivo per cui il sistema di proprietà non dispone di associazione dati, stili o ereditarietà hardcoded forniti invece dai livelli successivi all'interno del framework.  
  
 Il sistema di proprietà, inoltre, presenta possibilità limitate di archiviazione per i valori di proprietà. Poiché gli oggetti hanno decine, se non centinaia, di proprietà e la maggior parte dei valori si trova nel relativo stato predefinito (ereditato, impostato per stile e così via), non tutte le istanze di un oggetto devono avere il peso di ciascuna proprietà in esso definita.  
  
 La nuova funzionalità finale del sistema di proprietà è la nozione di proprietà associate. Gli elementi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono basati sul principio di composizione e riutilizzo del componente. È spesso il caso che alcune contenente l'elemento (ad esempio un <xref:System.Windows.Controls.Grid> elemento di layout) necessari ulteriori dati sugli elementi figlio per controllare il comportamento (ad esempio le informazioni di riga/colonna). Anziché associare tutte queste proprietà a ciascun elemento, un oggetto può fornire le definizioni delle proprietà per qualsiasi altro oggetto, come avviene per le funzionalità "expando" di JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>   
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Dopo avere definito un sistema, è necessario ottenere pixel disegnati sullo schermo. La <xref:System.Windows.Media.Visual> classe fornisce per la creazione di una struttura ad albero di oggetti visivi, ognuna delle quali contiene facoltativamente le istruzioni di disegnare e i metadati relativi a come eseguire il rendering di tali istruzioni (ritaglio, trasformazione e così via). <xref:System.Windows.Media.Visual>è progettato per essere estremamente semplice e flessibile, pertanto la maggior parte delle funzionalità ha non [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] esposizione e si basano su funzioni di callback protette.  
  
 <xref:System.Windows.Media.Visual>è il punto di ingresso per il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sistema di composizione. <xref:System.Windows.Media.Visual>è il punto di connessione tra questi due sottosistemi, gestiti [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] e milcore non gestito.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] visualizza i dati spostandosi all'interno di strutture di dati non gestiti gestite da milcore. Queste strutture, denominate nodi di composizione, rappresentano una struttura di visualizzazione gerarchica ad albero con istruzioni di rendering in ciascun nodo. La struttura ad albero, illustrata a destra nella figura riportata di seguito, è accessibile solo mediante un protocollo di messaggistica.  
  
 Durante la programmazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], si crea <xref:System.Windows.Media.Visual> gli elementi e i tipi derivati, che comunicano internamente con la struttura ad albero di composizione mediante il protocollo di messaggistica. Ogni <xref:System.Windows.Media.Visual> in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può creare uno, nessuno o più nodi di composizione.  
  
 ![Struttura ad albero visuale di Windows Presentation Foundation.](../../../../docs/framework/wpf/advanced/media/wpf-architecture2.PNG "wpf_architecture2")  
  
 In questo caso va notato un dettaglio molto importante relativo all'architettura: l'intera struttura ad albero degli elementi visivi e delle istruzioni di disegno è memorizzata nella cache. In termini di grafica, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizza un sistema di rendering memorizzato. Ciò fornisce al sistema elevate frequenze di aggiornamento senza che il sistema di composizione si blocchi sui callback al codice utente e consente di impedire la visualizzazione di applicazioni che non rispondono.  
  
 Un altro dettaglio importante, non facilmente individuabile nel diagramma, è il modo in cui il sistema esegue effettivamente la composizione.  
  
 In User32 e [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] il sistema funziona in base a un sistema di ritaglio in modalità immediata. Quando è necessario eseguire il rendering di un componente, il sistema stabilisce un limite di ritaglio al di fuori del quale il componente non può toccare i pixel; successivamente, viene chiesto al componente di disegnare i pixel in tale casella. Questo sistema funziona molto bene nei sistemi con memoria limitata poiché quando vengono apportate modifiche basta intervenire solo sul componente interessato. Non sono mai richiesti due componenti per il colore di un singolo pixel.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizza un modello di disegno denominato "algoritmo del pittore". Ciò significa che anziché ritagliare ogni componente, viene richiesto il rendering di ciascun componente dallo sfondo al primo piano della visualizzazione. In tal modo ciascun componente viene disegnato sulla visualizzazione del componente precedente. Il vantaggio di questo modello è la possibilità di avere forme complesse, parzialmente trasparenti. L'hardware grafico moderno rende questo modello relativamente veloce, a differenza di quando sono stati creati User32 e [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 Come accennato in precedenza, uno degli scopi principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è di passare a un modello di programmazione più dichiarativo, basato sulle proprietà. Nel sistema visuale questo è evidente in un paio di punti interessanti.  
  
 Innanzitutto, se si pensa al sistema grafico in modalità memorizzata, si nota un deciso allontanamento da un modello imperativo di tipo DrawLine/DrawLine verso un modello orientato ai dati di tipo new Line()/new Line(). Questo spostamento verso il rendering basato sui dati consente operazioni complesse sulle istruzioni di disegno da esprimere utilizzando le proprietà. I tipi che derivano da <xref:System.Windows.Media.Drawing> sono effettivamente il modello a oggetti per il rendering.  
  
 In secondo luogo, se si esamina il sistema di animazione appare evidente che è quasi completamente dichiarativo. Anziché richiedere a uno sviluppatore di calcolare la posizione o il colore successivo, è possibile esprimere le animazioni come un set di proprietà su un oggetto di animazione. Le animazioni possono quindi esprimere l'intenzione dello sviluppatore o del progettista (spostare questo pulsante da questa a quella posizione in 5 secondi) e il sistema può stabilire il modo più efficace per raggiungere tale scopo.  
  
<a name="System_Windows_UIElement"></a>   
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement>Definisce i sottosistemi principali incluso Layout, l'Input e gli eventi.  
  
 Layout è un concetto fondamentale di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In molti sistemi è presente un insieme fisso di modelli di layout (HTML supporta tre modelli di layout: flusso, assoluto e tabelle) oppure non è presente alcun modello di layout (User32 supporta effettivamente solo il posizionamento assoluto). [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è nato dal presupposto che gli sviluppatori e i progettisti avessero bisogno di un modello di layout flessibile ed estendibile da basare sui valori di proprietà piuttosto che sulla logica imperativa. Nel <xref:System.Windows.UIElement> livello, il contratto di base per il layout viene introdotto: due fasi di modello con <xref:System.Windows.UIElement.Measure%2A> e <xref:System.Windows.UIElement.Arrange%2A> passa.  
  
 <xref:System.Windows.UIElement.Measure%2A>Consente di stabilire le dimensioni si desidera utilizzare un componente. Si tratta di una fase diversa da <xref:System.Windows.UIElement.Arrange%2A> perché ci sono molte situazioni in cui un elemento padre chiede la misurazione più volte per determinare la posizione ottimale e le dimensioni di un elemento figlio. Il fatto che gli elementi padre chiedano agli elementi figlio di eseguire le misurazioni consente di dimostrare un altro concetto chiave di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ovvero il ridimensionamento del contenuto. Tutti i controlli di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supportano la capacità di adattare il contenuto alle relative dimensioni standard. Tutto ciò semplifica il processo di localizzazione e consente il layout dinamico degli elementi quando gli oggetti vengono ridimensionati. Il <xref:System.Windows.UIElement.Arrange%2A> fase consente a un elemento padre posizionare e stabilire le dimensioni finali di ogni elemento figlio.  
  
 Un tempo è spesso parla lato dell'output di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] – <xref:System.Windows.Media.Visual> e gli oggetti correlati. Esiste, tuttavia, una straordinaria quantità di innovazione anche sul lato input. La modifica più importante al modello di input per [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è probabilmente rappresentata dal modello coerente in base al quale gli eventi di input vengono indirizzati attraverso il sistema.  
  
 L'input come segnale proviene da un driver di dispositivo in modalità kernel e viene indirizzato verso il processo e il thread corretti mediante un complicato processo che interessa il kernel di Windows e User32. Dopo essere stato indirizzato verso [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], il messaggio User32 corrispondente all'input viene convertito in un messaggio di input non elaborato [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e inviato al dispatcher. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente la conversione degli eventi di input non elaborati in più eventi effettivi, abilitando l'implementazione di funzioni quali "MouseEnter" a un livello basso del sistema con recapito garantito.  
  
 Ciascun evento di input viene convertito in almeno due eventi: un evento in "anteprima" e l'evento effettivo. Tutti gli eventi di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dispongono di una nozione di indirizzamento mediante la struttura ad albero dell'elemento. Si parla di eventi di "bubbling" se passano da una destinazione nella parte superiore della struttura ad albero alla relativa radice e di "eventi di tunneling" se partono dalla radice per raggiungere la destinazione. Gli eventi di input in anteprima effettuano il tunneling consentendo a qualsiasi elemento della struttura ad albero di filtrare o svolgere un'azione sull'evento. Gli eventi regolari (non in anteprima) vengono propagati dalla destinazione fino alla radice.  
  
 Questa suddivisione tra fase di tunneling e fase di bubbling consente di implementare funzionalità, quali i tasti di scelta rapida, in modo coerente in un contesto composito. In User32 i tasti di scelta rapida vengono implementati con una sola tabella globale che contiene tutti i tasti da supportare (mapping di Ctrl+N su "Nuovo"). Nel dispatcher dell'applicazione viene chiamato **TranslateAccelerator** che rileva la presenza dei messaggi di input in User32 e stabilisce se esiste una corrispondenza con un tasto di scelta rapida registrato. Questa procedura non funziona in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] perché il sistema è totalmente "componibile", ovvero qualsiasi elemento può gestire e utilizzare qualsiasi tasto di scelta rapida. Questo modello a due fasi per l'input consente ai componenti di implementare il proprio "TranslateAccelerator".  
  
 Eseguire questo passaggio ulteriori, <xref:System.Windows.UIElement> introduce inoltre la nozione di CommandBindings. Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sistema comando consente agli sviluppatori di definire la funzionalità in termini di un punto di fine comando – qualcosa che implementa <xref:System.Windows.Input.ICommand>. Le associazioni di comandi consentono a un elemento di definire un mapping tra un movimento di input (Ctrl+N) e un comando (Nuovo). I movimenti di input e le definizioni dei comandi sono estendibili e possono essere collegati al momento dell'utilizzo. In tal modo, ad esempio, è possibile consentire a un utente finale di personalizzare le combinazioni di tasti da utilizzare in un'applicazione.  
  
 Fino a questo punto sono state trattate le funzionalità principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ovvero quelle implementate nell'assembly PresentationCore. Durante la compilazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], pulire la separazione tra le parti fondamentali (ad esempio il contratto per il layout con **misura** e **disponi**) e le parti framework (ad esempio, l'implementazione di un oggetto specifico layout come <xref:System.Windows.Controls.Grid>) è il risultato desiderato. Lo scopo era quello di fornire un punto di estendibilità basso nello stack per consentire agli sviluppatori esterni di creare i propri framework, se necessario.  
  
<a name="System_Windows_FrameworkElement"></a>   
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>può essere esaminato in due modi diversi. da un lato presenta un insieme di criteri e personalizzazioni dei sottosistemi introdotti nei livelli inferiori di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e dall'altro un insieme di nuovi sottosistemi.  
  
 I criteri principali introdotti da <xref:System.Windows.FrameworkElement> intorno al layout dell'applicazione. <xref:System.Windows.FrameworkElement>si basa sul contratto di base del layout introdotto da <xref:System.Windows.UIElement> e aggiunge la nozione di "slot" che rende più semplice per gli autori di layout per disporre di un set coerenza di semantica basata sulle proprietà di layout. Le proprietà come <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A>, e <xref:System.Windows.FrameworkElement.Margin%2A> (solo per citarne alcune) assegnano tutti i componenti derivati da <xref:System.Windows.FrameworkElement> un comportamento coerente all'interno di contenitori di layout.  
  
 <xref:System.Windows.FrameworkElement>fornisce inoltre più semplice [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] esposizione a molte funzionalità trovata nei livelli principali di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Ad esempio, <xref:System.Windows.FrameworkElement> fornisce accesso diretto all'animazione mediante il <xref:System.Windows.FrameworkElement.BeginStoryboard%2A> metodo. Oggetto <xref:System.Windows.Media.Animation.Storyboard> fornisce un modo per script più animazioni rispetto a un set di proprietà.  
  
 I due elementi più importanti che <xref:System.Windows.FrameworkElement> introduce sono data binding e stili.  
  
 Il sottosistema di associazione dati di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dovrebbe essere relativamente familiare a chiunque abbia utilizzato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] per creare un'applicazione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. In ciascuno di questi sistemi è possibile effettuare in modo semplice l'associazione di una o più proprietà di un dato elemento a un blocco di dati. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce supporto completo per l'associazione di proprietà, la trasformazione e l'associazione di elenco.  
  
 Una delle funzionalità più interessanti dell'associazione dati in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è l'introduzione dei modelli di dati che consentono di specificare in modo dichiarativo come deve essere visualizzato un blocco di dati. Anziché creare un'interfaccia utente personalizzata che può essere associata ai dati, è possibile aggirare il problema e fare in modo che siano i dati a stabilire il tipo di visualizzazione da creare.  
  
 L'applicazione degli stili è effettivamente un tipo di associazione dati semplice e il suo utilizzo consente di associare un set di proprietà di una definizione condivisa a una o più istanze di un elemento. Gli stili vengono applicati a un elemento riferimento esplicito (impostando il <xref:System.Windows.FrameworkElement.Style%2A> proprietà) o in modo implicito mediante l'associazione di uno stile con il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] tipo dell'elemento.  
  
<a name="System_Windows_Controls_Control"></a>   
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 La funzionalità più significativa dei controlli è l'applicazione di modelli. Considerando il sistema di composizione di WPF come un sistema di rendering in modalità memorizzata, l'applicazione di modelli consente a un controllo di descriverne il rendering in modo dichiarativo e con parametri. Oggetto <xref:System.Windows.Controls.ControlTemplate> è semplicemente più di uno script per creare elementi di un set di figlio con le associazioni alle proprietà offerte dal controllo.  
  
 <xref:System.Windows.Controls.Control>fornisce un set di proprietà predefinite, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Padding%2A>, solo per citarne alcune, quindi consente agli autori di modelli per personalizzare la visualizzazione di un controllo. L'implementazione di un controllo fornisce un modello dati e un modello di interazione. Il modello di interazione definisce un set di comandi (ad esempio, Chiudi per una finestra) e di associazioni a movimenti di input (ad esempio, fare clic sulla X rossa nell'angolo superiore della finestra). Il modello dati fornisce un set di proprietà per la personalizzazione del modello di interazione o della visualizzazione (stabilita dal modello).  
  
 Questa suddivisione tra modello dati (proprietà), modello di interazione (comandi ed eventi) e modello di visualizzazione (modelli) consente una personalizzazione completa dell'aspetto e del comportamento di un controllo.  
  
 Una caratteristica comune del modello dati dei controlli è il modello di contenuto. Se si osserva un controllo come <xref:System.Windows.Controls.Button>, si noterà che contiene una proprietà denominata "Content" di tipo <xref:System.Object>. In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)], questa proprietà è in genere una stringa; tuttavia questo limita il tipo di contenuto che può essere inserito in un pulsante. Il contenuto di un pulsante può essere una stringa semplice, un oggetto dati complesso o l'intera struttura ad albero di un elemento. Nel caso di un oggetto dati, il modello dati viene utilizzato per costruire una visualizzazione.  
  
<a name="Summary"></a>   
## <a name="summary"></a>Riepilogo  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è progettato per consentire la creazione di sistemi di presentazione dinamici, basati sui dati. Ogni parte del sistema è progettata per la creazione di oggetti utilizzando set di proprietà che ne definiscono il comportamento. L'associazione dati è una parte fondamentale del sistema ed è integrata a ogni livello.  
  
 Le applicazioni tradizionali creano una visualizzazione e associano successivamente i dati. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], tutti gli elementi del controllo e ogni aspetto della visualizzazione sono generati da un tipo di associazione dati. Il testo che si trova nei pulsanti viene visualizzato creando un controllo composto all'interno del pulsante e associando la relativa visualizzazione alla proprietà del contenuto del pulsante.  
  
 Lo sviluppo di applicazioni basate su [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dovrebbe risultare molto familiare per gli utenti. È possibile impostare proprietà, utilizzare oggetti e associare dati in modo molto simile a quanto avviene in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)]. Un'indagine più approfondita dell'architettura di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], evidenzierà la possibilità di creare applicazioni molto più ricche in cui i dati vengono considerati gli elementi principali dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Threading.DispatcherObject>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Controls.Control>  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
