---
title: Architecture
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
ms.openlocfilehash: b16be8470a47f3e8e362feb0b13e10aa901baacb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187127"
---
# <a name="wpf-architecture"></a>Architettura WPF
In questo argomento viene fornita una presentazione guidata della gerarchia di classi di Windows Presentation Foundation (WPF). Copre la maggior parte dei principali sottosistemi di WPFWPF e descrive come interagiscono. Descrive inoltre alcune delle scelte effettuate dagli architetti di WPFWPF.  

<a name="System_Object"></a>
## <a name="systemobject"></a>System.Object  
 Il modello di programmazione WPF WPF primario viene esposto tramite codice gestito. All'inizio della fase di progettazione di WPFWPF si sono svolti numerosi dibattiti sulla posizione in cui la linea deve essere tracciata tra i componenti gestiti del sistema e quelli non gestiti. CLR fornisce una serie di funzionalità che rendono lo sviluppo più produttivo e affidabile (compresa la gestione della memoria, la gestione degli errori, il sistema di tipi comuni e così via), ma hanno un costo.  
  
 I componenti principali di WPFWPF sono illustrati nella figura seguente. Le sezioni rosse del diagramma (PresentationFramework, PresentationCore e milcore) sono le parti di codice principali di WPFWPF. Di queste, solo milcore è un componente non gestito. Milcore è scritto in codice non gestito per consentire una stretta integrazione con DirectX. Tutta la visualizzazione in WPFWPF viene eseguita tramite il motore DirectX, consentendo un rendering hardware e software efficiente. WPFWPF richiedeva anche un controllo preciso sulla memoria e sull'esecuzione. Il motore di composizione in milcore è estremamente sensibile alle prestazioni e ha richiesto di rinunciare a molti vantaggi di CLR per ottenere prestazioni.  
  
 ![Posizione di WPF in .NET Framework](./media/wpf-architect1.PNG "wpf_architect1")  
  
 La comunicazione tra le parti gestite e non gestite di WPFWPF viene descritta più avanti in questo argomento. Il resto del modello di programmazione gestito viene descritto di seguito.  
  
<a name="System_Threading_DispatcherObject"></a>
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 La maggior parte <xref:System.Windows.Threading.DispatcherObject>degli oggetti in WPFWPF deriva da , che fornisce i costrutti di base per la gestione della concorrenza e del threading. WPFWPF si basa su un sistema di messaggistica implementato dal dispatcher. Questo funziona in modo molto simile al familiare message pump Win32; infatti, il dispatcher WPF utilizza i messaggi User32 per l'esecuzione di chiamate cross thread.  
  
 Esistono due concetti fondamentali da comprendere quando si discute della concorrenza in WPFWPF, ovvero l'affinità di dispatcher e thread.  
  
 Durante la fase di progettazione di WPFWPF, l'obiettivo era quello di passare a un singolo thread di esecuzione, ma un modello "affinizzato" non thread. L'affinità di thread si verifica quando un componente utilizza l'identità del thread in esecuzione per archiviare un tipo di stato. Nella forma più comune, per archiviare lo stato viene utilizzata l'archiviazione locale di thread (TLS). L'affinità di thread richiede che ciascun thread di esecuzione logico appartenga a un solo thread fisico del sistema operativo, che può richiedere un elevato consumo di memoria. Alla fine, il modello di threading di WPF è stato tenuto in sincronia con il modello di threading User32 esistente dell'esecuzione a thread singolo con affinità di thread. Il motivo principale è stato l'interoperabilità: sistemi come OLE 2.0, gli Appunti e Internet Explorer richiedono tutti l'esecuzione di affinità a thread singolo (STA).  
  
 Disponendo di oggetti con threading STA, è necessaria una modalità di comunicazione tra thread e di conferma di utilizzo del thread corretto. Qui si colloca il ruolo del dispatcher. Il dispatcher è un sistema di base di invio di messaggi con più code in ordine di priorità. Gli esempi di messaggi includono le notifiche di input non elaborato (spostamenti del mouse), le funzionalità del framework (layout) o i comandi utente (esecuzione di metodi). Derivando da <xref:System.Windows.Threading.DispatcherObject>, si crea un oggetto CLR con comportamento STA e verrà fornito un puntatore a un dispatcher al momento della creazione.  
  
<a name="System_Windows_DependencyObject"></a>
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Una delle filosofie architettoniche principali utilizzate nella compilazione di WPFWPF era una preferenza per le proprietà rispetto a i metodi o gli eventi. Le proprietà sono dichiarative e consentono di specificare più facilmente lo scopo anziché l'azione. In tal modo veniva anche supportato un sistema basato sui modelli o sui dati per la visualizzazione dei contenuti dell'interfaccia utente. Lo scopo di tale approccio era di creare un maggior numero di proprietà con cui stabilire l'associazione per poter controllare meglio il comportamento di un'applicazione.  
  
 Per avere più del sistema guidato da proprietà, un sistema di proprietà più ricco di quello che CLR fornisce era necessario. Un semplice esempio è rappresentato dalle notifiche di modifica. Per abilitare l'associazione bidirezionale, è necessario che entrambi i lati supportino la notifica di modifica. Per associare il comportamento a valori di proprietà, è necessario ricevere una notifica quando tale valore viene modificato. Microsoft .NET Framework dispone di un'interfaccia, **INotifyPropertyChange**, che consente a un oggetto di pubblicare le notifiche di modifica, tuttavia è facoltativo.  
  
 WPFWPF fornisce un sistema di <xref:System.Windows.DependencyObject> proprietà più ricco, derivato dal tipo. Il sistema di proprietà è effettivamente un sistema di proprietà delle "dipendenze" nel senso che tiene traccia delle dipendenze tra espressioni di proprietà e riconvalida automaticamente i valori delle proprietà quando tali dipendenze vengono modificate. Ad esempio, se si dispone di <xref:System.Windows.Controls.Control.FontSize%2A>una proprietà che eredita (ad esempio ), il sistema viene aggiornato automaticamente se la proprietà viene modificata in un elemento padre di un elemento che eredita il valore.  
  
 La base del sistema di proprietà WPFWPF è il concetto di un'espressione di proprietà. In questa prima versione di WPFWPF, il sistema di espressioni di proprietà viene chiuso e le espressioni vengono tutte fornite come parte del framework. Le espressioni rappresentano il motivo per cui il sistema di proprietà non dispone di associazione dati, stili o ereditarietà hardcoded forniti invece dai livelli successivi all'interno del framework.  
  
 Il sistema di proprietà, inoltre, presenta possibilità limitate di archiviazione per i valori di proprietà. Poiché gli oggetti hanno decine, se non centinaia, di proprietà e la maggior parte dei valori si trova nel relativo stato predefinito (ereditato, impostato per stile e così via), non tutte le istanze di un oggetto devono avere il peso di ciascuna proprietà in esso definita.  
  
 La nuova funzionalità finale del sistema di proprietà è la nozione di proprietà associate. Gli elementi WPFWPF si basano sul principio della composizione e del riutilizzo dei componenti. È spesso il caso che alcuni <xref:System.Windows.Controls.Grid> elementi contenitore (ad esempio un elemento di layout) necessitano di dati aggiuntivi sugli elementi figlio per controllarne il comportamento (ad esempio le informazioni di riga/colonna). Anziché associare tutte queste proprietà a ciascun elemento, un oggetto può fornire le definizioni delle proprietà per qualsiasi altro oggetto, come avviene per le funzionalità "expando" di JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Dopo avere definito un sistema, è necessario ottenere pixel disegnati sullo schermo. La <xref:System.Windows.Media.Visual> classe fornisce per la compilazione di una struttura ad albero di oggetti visivi, ognuno facoltativamente contenente istruzioni di disegno e metadati su come eseguire il rendering di tali istruzioni (ritaglio, trasformazione e così via). <xref:System.Windows.Media.Visual>è progettato per essere estremamente leggero e flessibile, in modo che la maggior parte delle funzionalità non hanno alcuna esposizione API pubblica e si basano pesantemente sulle funzioni di callback protette.  
  
 <xref:System.Windows.Media.Visual>è davvero il punto di ingresso al sistema di composizione WPF. <xref:System.Windows.Media.Visual>è il punto di connessione tra questi due sottosistemi, l'API gestita e il milcore non gestito.  
  
 WPFWPF visualizza i dati attraversando le strutture di dati non gestite gestite dal milcore. Queste strutture, denominate nodi di composizione, rappresentano una struttura di visualizzazione gerarchica ad albero con istruzioni di rendering in ciascun nodo. La struttura ad albero, illustrata a destra nella figura riportata di seguito, è accessibile solo mediante un protocollo di messaggistica.  
  
 Quando si programma <xref:System.Windows.Media.Visual> WPFWPF, si creano elementi e tipi derivati, che comunicano internamente con la struttura ad albero della composizione tramite questo protocollo di messaggistica. Ognuno <xref:System.Windows.Media.Visual> in WPFWPF può creare uno, nessuno o più nodi di composizione.  
  
 ![Struttura ad albero visuale di Windows Presentation Foundation](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 In questo caso va notato un dettaglio molto importante relativo all'architettura: l'intera struttura ad albero degli elementi visivi e delle istruzioni di disegno è memorizzata nella cache. In termini grafici, WPFWPF usa un sistema di rendering mantenuto. Ciò fornisce al sistema elevate frequenze di aggiornamento senza che il sistema di composizione si blocchi sui callback al codice utente e consente di impedire la visualizzazione di applicazioni che non rispondono.  
  
 Un altro dettaglio importante, non facilmente individuabile nel diagramma, è il modo in cui il sistema esegue effettivamente la composizione.  
  
 In User32 e GDI, il sistema funziona su un sistema di ritaglio in modalità immediata. Quando è necessario eseguire il rendering di un componente, il sistema stabilisce un limite di ritaglio al di fuori del quale il componente non può toccare i pixel; successivamente, viene chiesto al componente di disegnare i pixel in tale casella. Questo sistema funziona molto bene nei sistemi con memoria limitata poiché quando vengono apportate modifiche basta intervenire solo sul componente interessato. Non sono mai richiesti due componenti per il colore di un singolo pixel.  
  
 WPFWPF usa un modello di disegno "algoritmo del pittore". Ciò significa che anziché ritagliare ogni componente, viene richiesto il rendering di ciascun componente dallo sfondo al primo piano della visualizzazione. In tal modo ciascun componente viene disegnato sulla visualizzazione del componente precedente. Il vantaggio di questo modello è la possibilità di avere forme complesse, parzialmente trasparenti. Con l'hardware grafico moderno di oggi, questo modello è relativamente veloce (che non era il caso quando User32 / GDI sono stati creati).  
  
 Come accennato in precedenza, una filosofia di base di WPFWPF è quella di passare a un modello più dichiarativo, "property centric" di programmazione. Nel sistema visuale questo è evidente in un paio di punti interessanti.  
  
 Innanzitutto, se si pensa al sistema grafico in modalità memorizzata, si nota un deciso allontanamento da un modello imperativo di tipo DrawLine/DrawLine verso un modello orientato ai dati di tipo new Line()/new Line(). Questo spostamento verso il rendering basato sui dati consente operazioni complesse sulle istruzioni di disegno da esprimere utilizzando le proprietà. I tipi da <xref:System.Windows.Media.Drawing> cui derivano sono in effetti il modello a oggetti per il rendering.  
  
 In secondo luogo, se si esamina il sistema di animazione appare evidente che è quasi completamente dichiarativo. Anziché richiedere a uno sviluppatore di calcolare la posizione o il colore successivo, è possibile esprimere le animazioni come un set di proprietà su un oggetto di animazione. Le animazioni possono quindi esprimere l'intenzione dello sviluppatore o del progettista (spostare questo pulsante da questa a quella posizione in 5 secondi) e il sistema può stabilire il modo più efficace per raggiungere tale scopo.  
  
<a name="System_Windows_UIElement"></a>
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement>definisce i sottosistemi principali, inclusi Layout, Input ed Eventi.  
  
 Il layout è un concetto di base in WPFWPF. In molti sistemi è presente un insieme fisso di modelli di layout (HTML supporta tre modelli di layout: flusso, assoluto e tabelle) oppure non è presente alcun modello di layout (User32 supporta effettivamente solo il posizionamento assoluto). WPFWPF è iniziato con l'assunto che gli sviluppatori e progettisti desideravano un modello di layout flessibile ed estensibile, che potesse essere guidato dai valori delle proprietà anziché dalla logica imperativa. A <xref:System.Windows.UIElement> livello, viene introdotto il contratto di <xref:System.Windows.UIElement.Measure%2A> base <xref:System.Windows.UIElement.Arrange%2A> per il layout: un modello a due fasi con e passa.  
  
 <xref:System.Windows.UIElement.Measure%2A>consente a un componente di determinare la quantità di dimensioni che desidera prendere. Questa è una <xref:System.Windows.UIElement.Arrange%2A> fase separata da perché ci sono molte situazioni in cui un elemento padre chiederà a un elemento figlio di misurare più volte per determinare la sua posizione e dimensione ottimali. Il fatto che gli elementi padre assegnino elementi figlio da misurare dimostra un'altra filosofia chiave di WPFWPF: dimensione al contenuto. Tutti i controlli in WPFWPF supportano la possibilità di ridimensionare in base alle dimensioni naturali del contenuto. Tutto ciò semplifica il processo di localizzazione e consente il layout dinamico degli elementi quando gli oggetti vengono ridimensionati. La <xref:System.Windows.UIElement.Arrange%2A> fase consente a un padre di posizionare e determinare la dimensione finale di ogni elemento figlio.  
  
 Un sacco di tempo è spesso speso <xref:System.Windows.Media.Visual> a parlare del lato di output di WPFWPF – e gli oggetti correlati. Esiste, tuttavia, una straordinaria quantità di innovazione anche sul lato input. Probabilmente la modifica più fondamentale nel modello di input per WPFWPF è il modello coerente con cui gli eventi di input vengono indirizzati attraverso il sistema.  
  
 L'input come segnale proviene da un driver di dispositivo in modalità kernel e viene indirizzato verso il processo e il thread corretti mediante un complicato processo che interessa il kernel di Windows e User32. Una volta che il messaggio User32 corrispondente all'input viene instradato a WPFWPF, viene convertito in un messaggio di input non elaborato WPF e inviato al dispatcher. WPFWPF consente la conversione di eventi di input non elaborati in più eventi effettivi, consentendo l'implementazione di funzionalità come "MouseEnter" a un livello basso del sistema con recapito garantito.  
  
 Ciascun evento di input viene convertito in almeno due eventi: un evento in "anteprima" e l'evento effettivo. Tutti gli eventi in WPFWPF hanno una nozione di routing attraverso la struttura ad albero dell'elemento. Si dice che gli eventi "bolle" se attraversino da una destinazione fino all'albero alla radice e si dicano "tunnel" se iniziano dalla radice e attraversano verso il basso fino a un bersaglio. Gli eventi di input in anteprima effettuano il tunneling consentendo a qualsiasi elemento della struttura ad albero di filtrare o svolgere un'azione sull'evento. Gli eventi regolari (non in anteprima) vengono propagati dalla destinazione fino alla radice.  
  
 Questa suddivisione tra fase di tunneling e fase di bubbling consente di implementare funzionalità, quali i tasti di scelta rapida, in modo coerente in un contesto composito. In User32 i tasti di scelta rapida vengono implementati con una sola tabella globale che contiene tutti i tasti da supportare (mapping di Ctrl+N su "Nuovo"). Nel dispatcher dell'applicazione viene chiamato **TranslateAccelerator** che rileva la presenza dei messaggi di input in User32 e stabilisce se esiste una corrispondenza con un tasto di scelta rapida registrato. In WPFWPF questo non funzionerebbe perché il sistema è completamente "componibile": qualsiasi elemento può gestire e usare qualsiasi tasto di scelta rapida. Questo modello a due fasi per l'input consente ai componenti di implementare il proprio "TranslateAccelerator".  
  
 Per fare un ulteriore passo avanti, <xref:System.Windows.UIElement> introduce anche la nozione di CommandBindings. Il sistema di comando WPFWPF consente agli sviluppatori di definire <xref:System.Windows.Input.ICommand>la funzionalità in termini di un punto finale del comando, ovvero un elemento che implementa . Le associazioni di comandi consentono a un elemento di definire un mapping tra un movimento di input (Ctrl+N) e un comando (Nuovo). I movimenti di input e le definizioni dei comandi sono estendibili e possono essere collegati al momento dell'utilizzo. In tal modo, ad esempio, è possibile consentire a un utente finale di personalizzare le combinazioni di tasti da utilizzare in un'applicazione.  
  
 A questo punto dell'argomento, le funzionalità "core" di WPFWPF – funzionalità implementate nell'assembly PresentationCore, sono state oggetto di attenzione. Quando si compila WPFWPF, una netta separazione tra parti fondamentali (ad esempio il contratto per <xref:System.Windows.Controls.Grid>il layout con **Measure** e **Arrange**) e le parti del framework (come l'implementazione di un layout specifico come ) è il risultato desiderato. Lo scopo era quello di fornire un punto di estendibilità basso nello stack per consentire agli sviluppatori esterni di creare i propri framework, se necessario.  
  
<a name="System_Windows_FrameworkElement"></a>
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>possono essere esaminati in due modi diversi. Introduce un set di criteri e personalizzazioni nei sottosistemi introdotti nei livelli inferiori di WPFWPF. e dall'altro un insieme di nuovi sottosistemi.  
  
 Il criterio principale <xref:System.Windows.FrameworkElement> introdotto da è intorno al layout dell'applicazione. <xref:System.Windows.FrameworkElement>si basa sul contratto <xref:System.Windows.UIElement> di layout di base introdotto da e aggiunge la nozione di "slot" di layout che rende più semplice per gli autori di layout avere un set coerente di semantica di layout basata sulle proprietà. Proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>come <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> , e (per citarne alcune) forniscono tutti i componenti derivati da <xref:System.Windows.FrameworkElement> un comportamento coerente all'interno dei contenitori di layout.  
  
 <xref:System.Windows.FrameworkElement>fornisce inoltre una più semplice esposizione delle API a molte funzionalità presenti nei livelli principali di WPFWPF. Ad esempio, <xref:System.Windows.FrameworkElement> fornisce l'accesso <xref:System.Windows.FrameworkElement.BeginStoryboard%2A> diretto all'animazione tramite il metodo . A <xref:System.Windows.Media.Animation.Storyboard> fornisce un modo per eseguire lo script di più animazioni in un set di proprietà.  
  
 Le due operazioni <xref:System.Windows.FrameworkElement> più critiche introdotte sono l'associazione dati e gli stili.  
  
 Il sottosistema di associazione dati in WPFWPF deve essere relativamente [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]familiare a chiunque abbia utilizzato Windows Form o ASP.NET per la creazione di un'applicazione . In ciascuno di questi sistemi è possibile effettuare in modo semplice l'associazione di una o più proprietà di un dato elemento a un blocco di dati. WPFWPF supporta completamente l'associazione di proprietà, la trasformazione e l'associazione di elenchi.  
  
 Una delle funzionalità più interessanti dell'associazione dati in WPFWPF è l'introduzione di modelli di dati. che consentono di specificare in modo dichiarativo come deve essere visualizzato un blocco di dati. Anziché creare un'interfaccia utente personalizzata che può essere associata ai dati, è possibile aggirare il problema e fare in modo che siano i dati a stabilire il tipo di visualizzazione da creare.  
  
 L'applicazione degli stili è effettivamente un tipo di associazione dati semplice e il suo utilizzo consente di associare un set di proprietà di una definizione condivisa a una o più istanze di un elemento. Gli stili vengono applicati a un elemento <xref:System.Windows.FrameworkElement.Style%2A> tramite riferimento esplicito (impostando la proprietà) o in modo implicito associando uno stile al tipo CLR dell'elemento.  
  
<a name="System_Windows_Controls_Control"></a>
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 La funzionalità più significativa dei controlli è l'applicazione di modelli. Considerando il sistema di composizione di WPF come un sistema di rendering in modalità memorizzata, l'applicazione di modelli consente a un controllo di descriverne il rendering in modo dichiarativo e con parametri. A <xref:System.Windows.Controls.ControlTemplate> non è altro che uno script per creare un set di elementi figlio, con associazioni alle proprietà offerte dal controllo.  
  
 <xref:System.Windows.Controls.Control>fornisce un set di <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A>proprietà <xref:System.Windows.Controls.Control.Padding%2A>predefinite, , , , per citarne alcune, che gli autori di modelli possono quindi utilizzare per personalizzare la visualizzazione di un controllo. L'implementazione di un controllo fornisce un modello dati e un modello di interazione. Il modello di interazione definisce un set di comandi (ad esempio, Chiudi per una finestra) e di associazioni a movimenti di input (ad esempio, fare clic sulla X rossa nell'angolo superiore della finestra). Il modello dati fornisce un set di proprietà per la personalizzazione del modello di interazione o della visualizzazione (stabilita dal modello).  
  
 Questa suddivisione tra modello dati (proprietà), modello di interazione (comandi ed eventi) e modello di visualizzazione (modelli) consente una personalizzazione completa dell'aspetto e del comportamento di un controllo.  
  
 Una caratteristica comune del modello dati dei controlli è il modello di contenuto. Se si esamina un <xref:System.Windows.Controls.Button>controllo come , si noterà che dispone <xref:System.Object>di una proprietà denominata "Content" di tipo . In Windows Form e ASP.NET, questa proprietà sarebbe in genere una stringa, tuttavia ciò limita il tipo di contenuto che è possibile inserire in un pulsante. Il contenuto di un pulsante può essere una stringa semplice, un oggetto dati complesso o l'intera struttura ad albero di un elemento. Nel caso di un oggetto dati, il modello dati viene utilizzato per costruire una visualizzazione.  
  
<a name="Summary"></a>
## <a name="summary"></a>Summary  
 WPFWPF è progettato per consentire la creazione di sistemi di presentazione dinamici basati sui dati. Ogni parte del sistema è progettata per la creazione di oggetti utilizzando set di proprietà che ne definiscono il comportamento. L'associazione dati è una parte fondamentale del sistema ed è integrata a ogni livello.  
  
 Le applicazioni tradizionali creano una visualizzazione e associano successivamente i dati. In WPFWPF, tutto ciò che riguarda il controllo, ogni aspetto della visualizzazione, viene generato da un tipo di associazione dati. Il testo che si trova nei pulsanti viene visualizzato creando un controllo composto all'interno del pulsante e associando la relativa visualizzazione alla proprietà del contenuto del pulsante.  
  
 Quando si inizia a sviluppare applicazioni basate su WPF, dovrebbe essere molto familiare. È possibile impostare proprietà, utilizzare oggetti e associare dati in modo molto simile all'utilizzo di Windows Form o ASP.NET. Con un'indagine più approfondita sull'architettura di WPFWPF, si scoprirà che esiste la possibilità per la creazione di applicazioni molto più ricche che trattano fondamentalmente i dati come driver di base dell'applicazione.  
  
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
