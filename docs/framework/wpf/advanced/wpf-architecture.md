---
title: Architettura
ms.date: 03/30/2017
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
ms.openlocfilehash: db9938f26f31506737eb0395fa389da01a1ee444
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735073"
---
# <a name="wpf-architecture"></a>Architettura WPF
In questo argomento viene fornita una presentazione guidata della gerarchia di classi Windows Presentation Foundation (WPF). Viene illustrata la maggior parte dei principali sottosistemi di WPF e viene descritta la modalità di interazione. Vengono inoltre illustrate alcune delle scelte effettuate dagli architetti di WPF.  

<a name="System_Object"></a>   
## <a name="systemobject"></a>System.Object  
 Il modello di programmazione WPF primario viene esposto tramite codice gestito. Nelle fasi iniziali della fase di progettazione di WPF sono state illustrate alcune discussioni sulla posizione in cui deve essere disegnata la linea tra i componenti gestiti del sistema e quelli non gestiti. CLR fornisce una serie di funzionalità che rendono lo sviluppo più produttivo e affidabile (inclusa la gestione della memoria, la gestione degli errori, Common Type System e così via), ma hanno un costo.  
  
 I componenti principali di WPF sono illustrati nella figura seguente. Le sezioni rosse del diagramma (PresentationFramework, PresentationCore e milcore) sono le parti principali del codice di WPF. Di queste, solo milcore è un componente non gestito. Milcore è scritto in codice non gestito per consentire una stretta integrazione con DirectX. Tutte le visualizzazioni in WPF vengono eseguite tramite il motore DirectX, consentendo un efficiente rendering dell'hardware e del software. WPF necessitava anche di un controllo accurato sulla memoria e sull'esecuzione. Il motore di composizione in milcore è estremamente sensibile alle prestazioni ed è necessario rinunciare a molti vantaggi di CLR per ottenere prestazioni ottimali.  
  
 ![Posizione di WPF all'interno dell'.NET Framework.](./media/wpf-architect1.PNG "wpf_architect1")  
  
 La comunicazione tra le parti gestite e non gestite di WPF viene discussa più avanti in questo argomento. Il resto del modello di programmazione gestito viene descritto di seguito.  
  
<a name="System_Threading_DispatcherObject"></a>   
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 La maggior parte degli oggetti in WPF deriva da <xref:System.Windows.Threading.DispatcherObject>, che fornisce i costrutti di base per la gestione della concorrenza e del threading. WPF si basa su un sistema di messaggistica implementato dal dispatcher. Funziona in modo molto simile a quello del messaggio Win32 familiare; in realtà, il dispatcher WPF USA messaggi User32 per l'esecuzione di chiamate cross-thread.  
  
 Esistono due concetti principali da comprendere quando si discute la concorrenza in WPF, ovvero il dispatcher e l'affinità di thread.  
  
 Durante la fase di progettazione di WPF, lo scopo era quello di passare a un singolo thread di esecuzione, ma a un modello "creata un'affinità" non thread. L'affinità di thread si verifica quando un componente utilizza l'identità del thread in esecuzione per archiviare un tipo di stato. Nella forma più comune, per archiviare lo stato viene utilizzata l'archiviazione locale di thread (TLS). L'affinità di thread richiede che ciascun thread di esecuzione logico appartenga a un solo thread fisico del sistema operativo, che può richiedere un elevato consumo di memoria. Alla fine, il modello di threading di WPF è stato tenuto in sincronia con il modello di threading User32 esistente dell'esecuzione a thread singolo con affinità di thread. Il motivo principale di questa interoperabilità è che i sistemi, ad esempio OLE 2,0, gli appunti e Internet Explorer, richiedono l'esecuzione di affinità a thread singolo (STA).  
  
 Disponendo di oggetti con threading STA, è necessaria una modalità di comunicazione tra thread e di conferma di utilizzo del thread corretto. Qui si colloca il ruolo del dispatcher. Il dispatcher è un sistema di base di invio di messaggi con più code in ordine di priorità. Gli esempi di messaggi includono le notifiche di input non elaborato (spostamenti del mouse), le funzionalità del framework (layout) o i comandi utente (esecuzione di metodi). Derivando da <xref:System.Windows.Threading.DispatcherObject>, viene creato un oggetto CLR con un comportamento STA e viene assegnato un puntatore a un dispatcher in fase di creazione.  
  
<a name="System_Windows_DependencyObject"></a>   
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Una delle principali filosofie dell'architettura utilizzate nella creazione di WPF era una preferenza per le proprietà di metodi o eventi. Le proprietà sono dichiarative e consentono di specificare più facilmente lo scopo anziché l'azione. In tal modo veniva anche supportato un sistema basato sui modelli o sui dati per la visualizzazione dei contenuti dell'interfaccia utente. Lo scopo di tale approccio era di creare un maggior numero di proprietà con cui stabilire l'associazione per poter controllare meglio il comportamento di un'applicazione.  
  
 Per avere un maggior numero di sistemi basati sulle proprietà, è necessario un sistema di proprietà più completo rispetto a quello fornito da CLR. Un semplice esempio è rappresentato dalle notifiche di modifica. Per abilitare l'associazione bidirezionale, è necessario che entrambi i lati supportino la notifica di modifica. Per associare il comportamento a valori di proprietà, è necessario ricevere una notifica quando tale valore viene modificato. Il Framework Microsoft .NET dispone di un'interfaccia, **INotifyPropertyChange**, che consente a un oggetto di pubblicare notifiche di modifica, ma è facoltativo.  
  
 WPF fornisce un sistema di proprietà più completo, derivato dal tipo di <xref:System.Windows.DependencyObject>. Il sistema di proprietà è effettivamente un sistema di proprietà delle "dipendenze" nel senso che tiene traccia delle dipendenze tra espressioni di proprietà e riconvalida automaticamente i valori delle proprietà quando tali dipendenze vengono modificate. Se, ad esempio, si dispone di una proprietà che eredita (come <xref:System.Windows.Controls.Control.FontSize%2A>), il sistema viene aggiornato automaticamente se la proprietà viene modificata in un elemento padre di un elemento che eredita il valore.  
  
 La base del sistema di proprietà WPF è il concetto di espressione di proprietà. Nella prima versione di WPF, il sistema di espressioni di proprietà viene chiuso e tutte le espressioni vengono fornite come parte del Framework. Le espressioni rappresentano il motivo per cui il sistema di proprietà non dispone di associazione dati, stili o ereditarietà hardcoded forniti invece dai livelli successivi all'interno del framework.  
  
 Il sistema di proprietà, inoltre, presenta possibilità limitate di archiviazione per i valori di proprietà. Poiché gli oggetti hanno decine, se non centinaia, di proprietà e la maggior parte dei valori si trova nel relativo stato predefinito (ereditato, impostato per stile e così via), non tutte le istanze di un oggetto devono avere il peso di ciascuna proprietà in esso definita.  
  
 La nuova funzionalità finale del sistema di proprietà è la nozione di proprietà associate. Gli elementi WPF sono basati sul principio della composizione e sul riutilizzo dei componenti. Spesso è necessario che un elemento contenitore, ad esempio un elemento di layout <xref:System.Windows.Controls.Grid>, richieda dati aggiuntivi sugli elementi figlio per controllarne il comportamento, ad esempio le informazioni sulla riga o sulla colonna. Anziché associare tutte queste proprietà a ciascun elemento, un oggetto può fornire le definizioni delle proprietà per qualsiasi altro oggetto, come avviene per le funzionalità "expando" di JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>   
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Dopo avere definito un sistema, è necessario ottenere pixel disegnati sullo schermo. La classe <xref:System.Windows.Media.Visual> fornisce per la compilazione di una struttura ad albero di oggetti visivi, ognuno dei quali contiene facoltativamente istruzioni di disegno e metadati su come eseguire il rendering di tali istruzioni (ritaglio, trasformazione e così via). <xref:System.Windows.Media.Visual> è progettato per essere estremamente leggero e flessibile, la maggior parte delle funzionalità non hanno un'esposizione API pubblica e si basano molto sulle funzioni di callback protette.  
  
 <xref:System.Windows.Media.Visual> è effettivamente il punto di ingresso del sistema di composizione WPF. <xref:System.Windows.Media.Visual> è il punto di connessione tra questi due sottosistemi, l'API gestita e il milcore non gestito.  
  
 WPF Visualizza i dati attraversando le strutture di dati non gestite gestite da milcore. Queste strutture, denominate nodi di composizione, rappresentano una struttura di visualizzazione gerarchica ad albero con istruzioni di rendering in ciascun nodo. La struttura ad albero, illustrata a destra nella figura riportata di seguito, è accessibile solo mediante un protocollo di messaggistica.  
  
 Quando si programma WPF, si creano <xref:System.Windows.Media.Visual> elementi e tipi derivati, che comunicano internamente all'albero della composizione tramite questo protocollo di messaggistica. Ogni <xref:System.Windows.Media.Visual> in WPF può creare uno, nessuno o più nodi di composizione.  
  
 ![Struttura ad albero visuale Windows Presentation Foundation.](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 In questo caso va notato un dettaglio molto importante relativo all'architettura: l'intera struttura ad albero degli elementi visivi e delle istruzioni di disegno è memorizzata nella cache. Nei termini grafici, WPF usa un sistema di rendering mantenuto. Ciò fornisce al sistema elevate frequenze di aggiornamento senza che il sistema di composizione si blocchi sui callback al codice utente e consente di impedire la visualizzazione di applicazioni che non rispondono.  
  
 Un altro dettaglio importante, non facilmente individuabile nel diagramma, è il modo in cui il sistema esegue effettivamente la composizione.  
  
 In User32 e GDI il sistema funziona in un sistema di ritaglio in modalità immediata. Quando è necessario eseguire il rendering di un componente, il sistema stabilisce un limite di ritaglio al di fuori del quale il componente non può toccare i pixel; successivamente, viene chiesto al componente di disegnare i pixel in tale casella. Questo sistema funziona molto bene nei sistemi con memoria limitata poiché quando vengono apportate modifiche basta intervenire solo sul componente interessato. Non sono mai richiesti due componenti per il colore di un singolo pixel.  
  
 WPF usa un modello di disegno "algoritmo del pittore". Ciò significa che anziché ritagliare ogni componente, viene richiesto il rendering di ciascun componente dallo sfondo al primo piano della visualizzazione. In tal modo ciascun componente viene disegnato sulla visualizzazione del componente precedente. Il vantaggio di questo modello è la possibilità di avere forme complesse, parzialmente trasparenti. Con l'attuale hardware grafico moderno, questo modello è relativamente veloce, che non era il caso in cui User32/GDI fosse stato creato.  
  
 Come indicato in precedenza, una filosofia di base di WPF consiste nel passare a un modello di programmazione più dichiarativo "incentrato sulle proprietà". Nel sistema visuale questo è evidente in un paio di punti interessanti.  
  
 Innanzitutto, se si pensa al sistema grafico in modalità memorizzata, si nota un deciso allontanamento da un modello imperativo di tipo DrawLine/DrawLine verso un modello orientato ai dati di tipo new Line()/new Line(). Questo spostamento verso il rendering basato sui dati consente operazioni complesse sulle istruzioni di disegno da esprimere utilizzando le proprietà. I tipi che derivano da <xref:System.Windows.Media.Drawing> sono in effetti il modello a oggetti per il rendering.  
  
 In secondo luogo, se si esamina il sistema di animazione appare evidente che è quasi completamente dichiarativo. Anziché richiedere a uno sviluppatore di calcolare la posizione o il colore successivo, è possibile esprimere le animazioni come un set di proprietà su un oggetto di animazione. Le animazioni possono quindi esprimere l'intenzione dello sviluppatore o del progettista (spostare questo pulsante da questa a quella posizione in 5 secondi) e il sistema può stabilire il modo più efficace per raggiungere tale scopo.  
  
<a name="System_Windows_UIElement"></a>   
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement> definisce sottosistemi di base, tra cui layout, input ed eventi.  
  
 Il layout è un concetto di base di WPF. In molti sistemi è presente un insieme fisso di modelli di layout (HTML supporta tre modelli di layout: flusso, assoluto e tabelle) oppure non è presente alcun modello di layout (User32 supporta effettivamente solo il posizionamento assoluto). WPF ha iniziato con il presupposto che gli sviluppatori e i progettisti volevano un modello di layout flessibile ed estendibile, che poteva essere basato su valori di proprietà anziché su una logica imperativa. A livello di <xref:System.Windows.UIElement>, viene introdotto il contratto di base per il layout, ovvero un modello a due fasi con <xref:System.Windows.UIElement.Measure%2A> e <xref:System.Windows.UIElement.Arrange%2A>.  
  
 <xref:System.Windows.UIElement.Measure%2A> consente a un componente di determinare la quantità di dimensioni che si desidera eseguire. Si tratta di una fase separata da <xref:System.Windows.UIElement.Arrange%2A> perché in molte situazioni un elemento padre chiede a un figlio di misurare più volte per determinare la posizione e le dimensioni ottimali. Il fatto che gli elementi padre chiedano agli elementi figlio di misurare dimostrano un'altra filosofia chiave di WPF, ovvero le dimensioni del contenuto. Tutti i controlli in WPF supportano la possibilità di ridimensionare le dimensioni naturali del contenuto. Tutto ciò semplifica il processo di localizzazione e consente il layout dinamico degli elementi quando gli oggetti vengono ridimensionati. La fase <xref:System.Windows.UIElement.Arrange%2A> consente a un elemento padre di posizionare e determinare le dimensioni finali di ogni elemento figlio.  
  
 Spesso si parla del lato output di WPF, <xref:System.Windows.Media.Visual> e degli oggetti correlati. Esiste, tuttavia, una straordinaria quantità di innovazione anche sul lato input. Probabilmente la modifica più importante nel modello di input per WPF è il modello coerente in base al quale gli eventi di input vengono instradati attraverso il sistema.  
  
 L'input come segnale proviene da un driver di dispositivo in modalità kernel e viene indirizzato verso il processo e il thread corretti mediante un complicato processo che interessa il kernel di Windows e User32. Una volta che il messaggio User32 corrispondente all'input viene indirizzato a WPF, viene convertito in un messaggio di input non elaborato WPF e inviato al dispatcher. WPF consente la conversione di eventi di input non elaborati in più eventi effettivi, consentendo l'implementazione di funzionalità come "MouseEnter" a un livello basso del sistema con recapito garantito.  
  
 Ciascun evento di input viene convertito in almeno due eventi: un evento in "anteprima" e l'evento effettivo. Tutti gli eventi in WPF hanno una nozione di routing nell'albero degli elementi. Gli eventi vengono detti "bolle" se passano da una destinazione verso l'alto nell'albero alla radice e vengono detti "tunnel" se iniziano alla radice e passano a una destinazione. Gli eventi di input in anteprima effettuano il tunneling consentendo a qualsiasi elemento della struttura ad albero di filtrare o svolgere un'azione sull'evento. Gli eventi regolari (non in anteprima) vengono propagati dalla destinazione fino alla radice.  
  
 Questa suddivisione tra fase di tunneling e fase di bubbling consente di implementare funzionalità, quali i tasti di scelta rapida, in modo coerente in un contesto composito. In User32 i tasti di scelta rapida vengono implementati con una sola tabella globale che contiene tutti i tasti da supportare (mapping di Ctrl+N su "Nuovo"). Nel dispatcher dell'applicazione viene chiamato **TranslateAccelerator** che rileva la presenza dei messaggi di input in User32 e stabilisce se esiste una corrispondenza con un tasto di scelta rapida registrato. In WPF questa operazione non funzionerebbe perché il sistema è completamente "componibile", qualsiasi elemento può gestire e utilizzare qualsiasi tasto di scelta rapida. Questo modello a due fasi per l'input consente ai componenti di implementare il proprio "TranslateAccelerator".  
  
 Per eseguire ulteriormente questo passaggio, <xref:System.Windows.UIElement> introduce anche il concetto di CommandBindings. Il sistema di comandi WPF consente agli sviluppatori di definire le funzionalità in termini di un punto finale del comando, ovvero un elemento che implementa <xref:System.Windows.Input.ICommand>. Le associazioni di comandi consentono a un elemento di definire un mapping tra un movimento di input (Ctrl+N) e un comando (Nuovo). I movimenti di input e le definizioni dei comandi sono estendibili e possono essere collegati al momento dell'utilizzo. In tal modo, ad esempio, è possibile consentire a un utente finale di personalizzare le combinazioni di tasti da utilizzare in un'applicazione.  
  
 Fino a questo punto nell'argomento, le funzionalità di base di WPF, ovvero le funzionalità implementate nell'assembly PresentationCore, hanno avuto lo stato attivo. Quando si compila WPF, è stata ottenuta una netta separazione tra le parti fondamentali (ad esempio il contratto per il layout con **misura** e **disposizione**) e le parti del Framework, ad esempio l'implementazione di un layout specifico come <xref:System.Windows.Controls.Grid>. Lo scopo era quello di fornire un punto di estendibilità basso nello stack per consentire agli sviluppatori esterni di creare i propri framework, se necessario.  
  
<a name="System_Windows_FrameworkElement"></a>   
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement> possono essere esaminati in due modi diversi. Introduce un set di criteri e personalizzazioni nei sottosistemi introdotti in livelli inferiori di WPF. e dall'altro un insieme di nuovi sottosistemi.  
  
 Il criterio principale introdotto da <xref:System.Windows.FrameworkElement> riguarda il layout dell'applicazione. <xref:System.Windows.FrameworkElement> si basa sul contratto di layout di base introdotto da <xref:System.Windows.UIElement> e aggiunge la nozione di "slot" del layout che rende più semplice per gli autori di layout avere un set coerente di semantica di layout basata su Proprietà. Proprietà quali <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A>e <xref:System.Windows.FrameworkElement.Margin%2A> (per citarne alcune) forniscono tutti i componenti derivati da <xref:System.Windows.FrameworkElement> comportamento coerente all'interno dei contenitori di layout.  
  
 <xref:System.Windows.FrameworkElement> offre anche un'esposizione più semplice delle API a molte funzionalità disponibili nei livelli principali di WPF. Ad esempio, <xref:System.Windows.FrameworkElement> fornisce accesso diretto all'animazione tramite il metodo <xref:System.Windows.FrameworkElement.BeginStoryboard%2A>. Un <xref:System.Windows.Media.Animation.Storyboard> consente di creare script per più animazioni rispetto a un set di proprietà.  
  
 I due aspetti più importanti che <xref:System.Windows.FrameworkElement> introduce sono data binding e gli stili.  
  
 Il sottosistema data binding in WPF dovrebbe essere relativamente familiare a chiunque abbia utilizzato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o ASP.NET per la creazione di un'applicazione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. In ciascuno di questi sistemi è possibile effettuare in modo semplice l'associazione di una o più proprietà di un dato elemento a un blocco di dati. WPF dispone del supporto completo per l'associazione di proprietà, trasformazione ed elenco.  
  
 Una delle funzionalità più interessanti di data binding in WPF è l'introduzione dei modelli di dati. che consentono di specificare in modo dichiarativo come deve essere visualizzato un blocco di dati. Anziché creare un'interfaccia utente personalizzata che può essere associata ai dati, è possibile aggirare il problema e fare in modo che siano i dati a stabilire il tipo di visualizzazione da creare.  
  
 L'applicazione degli stili è effettivamente un tipo di associazione dati semplice e il suo utilizzo consente di associare un set di proprietà di una definizione condivisa a una o più istanze di un elemento. Gli stili vengono applicati a un elemento in base al riferimento esplicito (impostando la proprietà <xref:System.Windows.FrameworkElement.Style%2A>) o in modo implicito associando uno stile al tipo CLR dell'elemento.  
  
<a name="System_Windows_Controls_Control"></a>   
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 La funzionalità più significativa dei controlli è l'applicazione di modelli. Considerando il sistema di composizione di WPF come un sistema di rendering in modalità memorizzata, l'applicazione di modelli consente a un controllo di descriverne il rendering in modo dichiarativo e con parametri. Una <xref:System.Windows.Controls.ControlTemplate> non è nient'altro che uno script per creare un set di elementi figlio, con binding alle proprietà offerte dal controllo.  
  
 <xref:System.Windows.Controls.Control> fornisce un set di proprietà predefinite, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Control.Padding%2A>, per citarne alcuni, che possono quindi essere utilizzati dagli autori di modelli per personalizzare la visualizzazione di un controllo. L'implementazione di un controllo fornisce un modello dati e un modello di interazione. Il modello di interazione definisce un set di comandi (ad esempio, Chiudi per una finestra) e di associazioni a movimenti di input (ad esempio, fare clic sulla X rossa nell'angolo superiore della finestra). Il modello dati fornisce un set di proprietà per la personalizzazione del modello di interazione o della visualizzazione (stabilita dal modello).  
  
 Questa suddivisione tra modello dati (proprietà), modello di interazione (comandi ed eventi) e modello di visualizzazione (modelli) consente una personalizzazione completa dell'aspetto e del comportamento di un controllo.  
  
 Una caratteristica comune del modello dati dei controlli è il modello di contenuto. Se si osserva un controllo come <xref:System.Windows.Controls.Button>, si noterà che è presente una proprietà denominata "Content" di tipo <xref:System.Object>. In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e ASP.NET questa proprietà è in genere una stringa, ma limita il tipo di contenuto che è possibile inserire in un pulsante. Il contenuto di un pulsante può essere una stringa semplice, un oggetto dati complesso o l'intera struttura ad albero di un elemento. Nel caso di un oggetto dati, il modello dati viene utilizzato per costruire una visualizzazione.  
  
<a name="Summary"></a>   
## <a name="summary"></a>Riepilogo  
 WPF è progettato per consentire la creazione di sistemi di presentazione dinamici basati sui dati. Ogni parte del sistema è progettata per la creazione di oggetti utilizzando set di proprietà che ne definiscono il comportamento. L'associazione dati è una parte fondamentale del sistema ed è integrata a ogni livello.  
  
 Le applicazioni tradizionali creano una visualizzazione e associano successivamente i dati. In WPF tutte le informazioni sul controllo, ogni aspetto dello schermo, vengono generate da un tipo di data binding. Il testo che si trova nei pulsanti viene visualizzato creando un controllo composto all'interno del pulsante e associando la relativa visualizzazione alla proprietà del contenuto del pulsante.  
  
 Quando si inizia a sviluppare applicazioni basate su WPF, il suo aspetto è molto familiare. È possibile impostare proprietà, usare oggetti e associare dati nello stesso modo in cui è possibile usare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o ASP.NET. Con un'analisi più approfondita dell'architettura di WPF, si noterà che esiste la possibilità di creare applicazioni molto più ricche che considerano fondamentalmente i dati come driver di base dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Threading.DispatcherObject>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Controls.Control>
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Layout](layout.md)
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
