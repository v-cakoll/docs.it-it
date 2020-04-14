---
title: Panoramica della creazione di controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: 2326520039085beb5f5294e23db67b67f9d7d7da
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243271"
---
# <a name="control-authoring-overview"></a>Cenni preliminari sulla creazione di controlli

L'estendibilità del modello di controlli di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] riduce notevolmente l'esigenza di creare un nuovo controllo. In alcuni casi può tuttavia essere ancora necessario creare un controllo personalizzato. Questo argomento illustra le funzionalità che riducono al minimo l'esigenza di creare un controllo personalizzato e i diversi modelli di creazione di controlli in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viene anche illustrato come creare un nuovo controllo.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternative alla scrittura di un nuovo controllo

In precedenza, per ottenere un'esperienza personalizzata da un controllo esistente, le modifiche erano limitate alle proprietà standard del controllo, ad esempio colore di sfondo, spessore del bordo e dimensioni del carattere. Per estendere l'aspetto o il comportamento di un controllo oltre questi parametri predefiniti, era necessario creare un nuovo controllo, in genere ereditando da un controllo esistente ed eseguendo l'override del metodo responsabile del disegno del controllo.  Sebbene ciò sia ancora possibile, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di personalizzare i controlli esistenti usando un modello di contenuto avanzato, stili, modelli e trigger. L'elenco seguente fornisce alcuni esempi relativi a come usare queste funzionalità per creare esperienze coerenti e personalizzate senza dover creare un nuovo controllo.

- **Contenuto avanzato.** Molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard supportano il contenuto avanzato. Ad esempio, la proprietà <xref:System.Windows.Controls.Button> content <xref:System.Object>di un è di tipo , <xref:System.Windows.Controls.Button>in modo teorico qualsiasi elemento può essere visualizzato su un oggetto .  Per fare in modo che un pulsante visualizzi <xref:System.Windows.Controls.TextBlock> un'immagine e un testo, è possibile aggiungere un'immagine e un a <xref:System.Windows.Controls.StackPanel> a e assegnare l'oggetto <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.ContentControl.Content%2A> alla proprietà . Poiché i controlli possono visualizzare dati arbitrari ed elementi visivi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], c'è una minore esigenza di creare un nuovo controllo o di modificarne uno esistente per supportare una visualizzazione complessa. Per ulteriori informazioni sul <xref:System.Windows.Controls.Button> modello di contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]per e altri modelli di contenuto in , vedere MODELLO di [contenuto WPF](wpf-content-model.md).

- **Stili.** Un <xref:System.Windows.Style> oggetto è una raccolta di valori che rappresentano le proprietà per un controllo. Usando gli stili, è possibile creare una rappresentazione riutilizzabile dell'aspetto e del comportamento desiderati di un controllo, senza scriverne uno nuovo. Si supponga, ad esempio, <xref:System.Windows.Controls.TextBlock> che si desidera che tutti i controlli abbiano un carattere Arial rosso e con una dimensione del carattere pari a 14. È possibile creare uno stile come risorsa e impostare le proprietà appropriate di conseguenza. Quindi <xref:System.Windows.Controls.TextBlock> ogni elemento che si aggiunge all'applicazione avrà lo stesso aspetto.

- **Modelli di dati.** Oggetto <xref:System.Windows.DataTemplate> consente di personalizzare la modalità di visualizzazione dei dati in un controllo. Ad esempio, <xref:System.Windows.DataTemplate> un oggetto può essere utilizzato per <xref:System.Windows.Controls.ListBox>specificare la modalità di visualizzazione dei dati in un oggetto .  Per un esempio, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).  Oltre a personalizzare l'aspetto dei <xref:System.Windows.DataTemplate> dati, un può includere elementi dell'interfaccia utente, che offre molta flessibilità nelle classi utente personalizzate.  Ad esempio, utilizzando <xref:System.Windows.DataTemplate>un oggetto <xref:System.Windows.Controls.ComboBox> , è possibile creare un oggetto in cui ogni elemento contiene una casella di controllo.

- **Modelli di controllo.** Molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in <xref:System.Windows.Controls.ControlTemplate> uso un per definire la struttura e l'aspetto del controllo, che separa l'aspetto di un controllo dalla funzionalità del controllo. È possibile modificare drasticamente l'aspetto <xref:System.Windows.Controls.ControlTemplate>di un controllo ridefinendone l'estensione.  Si supponga, ad esempio, di voler creare un controllo con l'aspetto di un semaforo. Il controllo ha una funzionalità e un'interfaccia utente semplici.  È costituito da tre cerchi, che possono essere illuminati soltanto uno alla volta. Dopo qualche riflessione, si <xref:System.Windows.Controls.RadioButton> potrebbe rendersi conto che un offre la funzionalità <xref:System.Windows.Controls.RadioButton> di uno solo essere selezionato alla volta, ma l'aspetto predefinito del sembra niente come le luci su un semaforo.  Poiché <xref:System.Windows.Controls.RadioButton> utilizza un modello di controllo per definirne <xref:System.Windows.Controls.ControlTemplate> l'aspetto, è facile ridefinire l'oggetto per adattarlo ai requisiti del controllo e utilizzare i pulsanti di opzione per creare il semaforo.

  > [!NOTE]
  > Sebbene <xref:System.Windows.Controls.RadioButton> un <xref:System.Windows.DataTemplate>oggetto <xref:System.Windows.DataTemplate> può utilizzare un oggetto , un oggetto non è sufficiente in questo esempio.  L'oggetto <xref:System.Windows.DataTemplate> definisce l'aspetto del contenuto di un controllo. Nel caso di <xref:System.Windows.Controls.RadioButton>un oggetto , il contenuto viene visualizzato a <xref:System.Windows.Controls.RadioButton> destra del cerchio che indica se l'oggetto è selezionato.  Nell'esempio del semaforo il pulsante di opzione deve essere costituito semplicemente da un cerchio in grado di "illuminarsi". Poiché il requisito di aspetto per il semaforo è così diverso dall'aspetto predefinito di <xref:System.Windows.Controls.RadioButton>, è necessario ridefinire l'oggetto <xref:System.Windows.Controls.ControlTemplate>.  In generale, un <xref:System.Windows.DataTemplate> oggetto viene utilizzato per definire il <xref:System.Windows.Controls.ControlTemplate> contenuto (o i dati) di un controllo e un oggetto viene utilizzato per definire la modalità di struttura di un controllo.

- **Trigger.** A <xref:System.Windows.Trigger> consente di modificare dinamicamente l'aspetto e il comportamento di un controllo senza creare un nuovo controllo. Si supponga, ad <xref:System.Windows.Controls.ListBox> esempio, di disporre di più <xref:System.Windows.Controls.ListBox> controlli nell'applicazione e di voler che gli elementi in ognuno di essi siano in grassetto e in rosso quando vengono selezionati. Il primo istinto potrebbe essere quello <xref:System.Windows.Controls.ListBox> di creare <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> una classe che eredita da ed eseguire l'override del metodo per <xref:System.Windows.Controls.ListBoxItem> modificare l'aspetto dell'elemento selezionato, ma un approccio migliore consiste nell'aggiungere un trigger a uno stile di un che modifica l'aspetto dell'elemento selezionato. Un trigger consente di modificare i valori delle proprietà o di eseguire determinate azioni in base al valore di una proprietà. Oggetto <xref:System.Windows.EventTrigger> consente di eseguire azioni quando si verifica un evento.

Per altre informazioni su stili, modelli e trigger, vedere [Applicazione di stili e modelli](styling-and-templating.md).

In genere, se il controllo rispecchia la funzionalità di un controllo esistente, ma si vuole che abbia un aspetto diverso, valutare innanzitutto la possibilità di usare uno dei metodi descritti in questa sezione per modificare l'aspetto del controllo esistente.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelli per la modifica dei controlli

Il modello di contenuto avanzato, gli stili, i modelli e i trigger riducono al minimo la necessità di creare un nuovo controllo. Se, tuttavia, è necessario creare un nuovo controllo, è importante conoscere i diversi modelli di creazione di controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce tre modelli generali per la creazione di un controllo, ognuno dei quali offre un set di funzionalità e un livello di flessibilità specifici. Le classi base per <xref:System.Windows.Controls.UserControl>i <xref:System.Windows.Controls.Control>tre <xref:System.Windows.FrameworkElement>modelli sono , , e .

### <a name="deriving-from-usercontrol"></a>Derivazione da UserControl

Il modo più semplice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per creare <xref:System.Windows.Controls.UserControl>un controllo consiste nel derivare da . Quando si compila un controllo <xref:System.Windows.Controls.UserControl>che eredita da <xref:System.Windows.Controls.UserControl>, si aggiungono componenti esistenti a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], si assegnano un nome ai componenti e si fa riferimento ai gestori eventi in . È quindi possibile fare riferimento agli elementi denominati e definire i gestori eventi nel codice. Questo modello di sviluppo è molto simile al modello usato per lo sviluppo di applicazioni in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Se compilato correttamente, un <xref:System.Windows.Controls.UserControl> oggetto può sfruttare i vantaggi di contenuti avanzati, stili e trigger. Tuttavia, se il <xref:System.Windows.Controls.UserControl>controllo eredita da , gli utenti che <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ControlTemplate> utilizzano il controllo non saranno in grado di utilizzare un o per personalizzarne l'aspetto.  È necessario derivare <xref:System.Windows.Controls.Control> dalla classe o da una <xref:System.Windows.Controls.UserControl>delle relative classi derivate (diverse da ) per creare un controllo personalizzato che supporti i modelli.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vantaggi della derivazione da UserControl

Valutare la <xref:System.Windows.Controls.UserControl> possibilità di derivare da se si applicano tutte le condizioni seguenti:Consider riving riving from if all of the following apply:

- Si vuole creare il controllo in modo analogo a come si crea un'applicazione.

- Il controllo è costituito esclusivamente da componenti esistenti.

- Non è necessario supportare una personalizzazione complessa.

### <a name="deriving-from-control"></a>Derivazione da Control

La derivazione <xref:System.Windows.Controls.Control> dalla classe è il modello [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzato dalla maggior parte dei controlli esistenti. Quando si crea un controllo <xref:System.Windows.Controls.Control> che eredita dalla classe , è possibile definirne l'aspetto utilizzando i modelli. In tal modo, la logica operativa viene separata dalla rappresentazione visiva. È anche possibile garantire il disaccoppiamento dell'interfaccia utente e della logica usando comandi e <xref:System.Windows.Controls.ControlTemplate> associazioni anziché eventi ed evitando di fare riferimento agli elementi in quando possibile.  Se l'interfaccia utente e la logica del controllo sono correttamente disaccoppiate, un utente del controllo può ridefinire il controllo <xref:System.Windows.Controls.ControlTemplate> per personalizzarne l'aspetto. Anche se <xref:System.Windows.Controls.Control> la creazione di un <xref:System.Windows.Controls.UserControl>costume <xref:System.Windows.Controls.Control> personalizzato non è semplice come la creazione di un oggetto , una proprietà offre la massima flessibilità.

#### <a name="benefits-of-deriving-from-control"></a>Vantaggi della derivazione da Control

Valutare la <xref:System.Windows.Controls.Control> possibilità di <xref:System.Windows.Controls.UserControl> derivare da anziché utilizzare la classe se si verifica una delle condizioni seguenti:

- Si desidera che l'aspetto del <xref:System.Windows.Controls.ControlTemplate>controllo sia personalizzabile tramite il file .

- Si vuole che il controllo supporti temi diversi.

### <a name="deriving-from-frameworkelement"></a>Derivazione da FrameworkElement

Controlli che <xref:System.Windows.Controls.UserControl> derivano da o <xref:System.Windows.Controls.Control> si basano sulla composizione di elementi esistenti. Per molti scenari, si tratta di una soluzione <xref:System.Windows.FrameworkElement> accettabile, perché <xref:System.Windows.Controls.ControlTemplate>qualsiasi oggetto che eredita da può essere in un oggetto . A volte, tuttavia, le funzionalità di composizione semplice di elementi non sono sufficienti per definire l'aspetto di un controllo. Per questi scenari, basare <xref:System.Windows.FrameworkElement> un componente su è la scelta giusta.

Esistono due metodi standard <xref:System.Windows.FrameworkElement>per la creazione di componenti basati su: il rendering diretto e la composizione degli elementi personalizzati. Il rendering diretto <xref:System.Windows.UIElement.OnRender%2A> comporta <xref:System.Windows.FrameworkElement> l'override del metodo di e la fornitura <xref:System.Windows.Media.DrawingContext> di operazioni che definiscono in modo esplicito gli oggetti visivi del componente. Questo è il <xref:System.Windows.Controls.Image> metodo <xref:System.Windows.Controls.Border>utilizzato da e . La composizione di elementi <xref:System.Windows.Media.Visual> personalizzati prevede l'utilizzo di oggetti di tipo per comporre l'aspetto del componente. Per un esempio, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>è un esempio di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un controllo in che utilizza la composizione di elementi personalizzati. È anche possibile combinare il rendering diretto e la composizione personalizzata di elementi nello stesso controllo.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vantaggi della derivazione da FrameworkElement

Si consiglia <xref:System.Windows.FrameworkElement> di derivare da se si verifica una delle seguenti condizioni:

- Si vuole controllare l'aspetto del controllo in modo più preciso rispetto a quanto possibile con la composizione semplice di elementi.

- Si vuole definire l'aspetto del controllo definendo una logica di rendering personalizzata.

- Si desidera comporre elementi esistenti in modi nuovi che <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control>vanno oltre ciò che è possibile con e .

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>Nozioni di base sulla creazione di controlli

Come illustrato in precedenza, una delle funzionalità più efficaci di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è la possibilità di andare oltre l'impostazione delle proprietà di base di un controllo per modificare l'aspetto e il comportamento senza dover necessariamente creare un controllo personalizzato. Le funzionalità di applicazione di stili, data binding e trigger sono possibili grazie al sistema di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e al sistema di eventi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Le sezioni seguenti descrivono alcune procedure da seguire, indipendentemente dal modello usato per creare il controllo personalizzato, in modo che gli utenti del controllo personalizzato possano usare le funzionalità come farebbero per un controllo incluso in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="use-dependency-properties"></a>Usare le proprietà di dipendenza

Con le proprietà di dipendenza è possibile eseguire le operazioni indicate di seguito:

- Impostare la proprietà in uno stile.

- Associare la proprietà a un'origine dati.

- Usare una risorsa dinamica come valore della proprietà.

- Animare la proprietà.

Se si vuole che una proprietà del controllo supporti queste funzionalità, è necessario implementarla come proprietà di dipendenza. L'esempio seguente definisce una proprietà di dipendenza denominata `Value` mediante le operazioni seguenti:

- Definire <xref:System.Windows.DependencyProperty> un `ValueProperty` identificatore `public` `static` `readonly` denominato come campo.

- Registrare il nome della proprietà <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>con il sistema di proprietà, chiamando , per specificare quanto segue:

  - Nome della proprietà.

  - Tipo della proprietà.

  - Tipo proprietario della proprietà.

  - Metadati della proprietà. I metadati contengono il valore <xref:System.Windows.CoerceValueCallback> predefinito <xref:System.Windows.PropertyChangedCallback>della proprietà, a e un oggetto .

- Definire una proprietà `Value`wrapper CLR denominata , che è lo stesso nome utilizzato per `get` `set` registrare la proprietà di dipendenza, implementando la proprietà e le funzioni di accesso. Si noti che le `get` funzioni di accesso `set` e chiamano <xref:System.Windows.DependencyObject.GetValue%2A> solo e <xref:System.Windows.DependencyObject.SetValue%2A> rispettivamente. È consigliabile che le funzioni di accesso delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di dipendenza non <xref:System.Windows.DependencyObject.GetValue%2A> contengano logica aggiuntiva perché i client e possano ignorare le funzioni di accesso e chiamare e <xref:System.Windows.DependencyObject.SetValue%2A> direttamente. Ad esempio, quando una proprietà è associata a un'origine dati, la funzione di accesso `set` della proprietà non viene chiamata.  Anziché aggiungere logica aggiuntiva alle funzioni di <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback>accesso <xref:System.Windows.PropertyChangedCallback> get e set, utilizzare i delegati , e per rispondere o controllare il valore quando viene modificato.  Per altre informazioni su questi callback, vedere [Callback e convalida delle proprietà di dipendenza](../advanced/dependency-property-callbacks-and-validation.md).

- Definire un metodo <xref:System.Windows.CoerceValueCallback> `CoerceValue`per l'oggetto denominato . `CoerceValue` garantisce che `Value` sia maggiore o uguale a `MinValue` e minore o uguale a `MaxValue`.

- Definire un metodo <xref:System.Windows.PropertyChangedCallback>per `OnValueChanged`l'oggetto , denominato . `OnValueChanged`crea <xref:System.Windows.RoutedPropertyChangedEventArgs%601> un oggetto e si `ValueChanged` prepara a generare l'evento indirizzato. Gli eventi indirizzati sono illustrati nella sezione successiva.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Per altre informazioni, vedere [Proprietà Dependency personalizzate](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Usare gli eventi indirizzati

Così come le proprietà di dipendenza estendono la nozione di proprietà CLR con funzionalità aggiuntive, gli eventi indirizzati estendono la nozione di eventi CLR standard. Quando si crea un nuovo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è anche consigliabile implementare l'evento come evento indirizzato, perché gli eventi indirizzati supportano i comportamenti seguenti:

- Gli eventi possono essere gestiti in un elemento padre di più controlli. Nel caso di un evento di bubbling, un singolo elemento padre nell'albero degli elementi può sottoscrivere l'evento. Gli autori dell'applicazione possono quindi usare un solo gestore per rispondere all'evento di più controlli. Ad esempio, se il controllo fa parte <xref:System.Windows.Controls.ListBox> di ogni elemento <xref:System.Windows.DataTemplate>di un oggetto (poiché è incluso in <xref:System.Windows.Controls.ListBox>un oggetto ), lo sviluppatore dell'applicazione può definire il gestore eventi per l'evento del controllo nell'oggetto . Il gestore eventi viene chiamato ogni volta che l'evento si verifica in uno dei controlli.

- Gli eventi indirizzati possono <xref:System.Windows.EventSetter>essere utilizzati in un oggetto , che consente agli sviluppatori di applicazioni di specificare il gestore di un evento all'interno di uno stile.

- Gli eventi indirizzati possono <xref:System.Windows.EventTrigger>essere utilizzati in un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]oggetto , utile per animare le proprietà utilizzando . Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](../graphics-multimedia/animation-overview.md)

L'esempio seguente definisce un evento indirizzato mediante le operazioni seguenti:

- Definire <xref:System.Windows.RoutedEvent> un `ValueChangedEvent` identificatore `public` `static` `readonly` denominato come campo.

- Registrare l'evento indirizzato chiamando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> metodo . L'esempio specifica le seguenti <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>informazioni quando chiama :

  - Il nome dell'evento è `ValueChanged`.

  - La strategia <xref:System.Windows.RoutingStrategy.Bubble>di routing è , il che significa che un gestore eventi nell'origine (l'oggetto che genera l'evento) viene chiamato prima e quindi i gestori eventi sugli elementi padre dell'origine vengono chiamati in successione, a partire dal gestore eventi nell'elemento padre più vicino.

  - Il tipo del gestore eventi <xref:System.Windows.RoutedPropertyChangedEventHandler%601> <xref:System.Decimal> è , costruito con un tipo.

  - Il tipo proprietario dell'evento è `NumericUpDown`.

- Dichiarazione di un evento pubblico denominato `ValueChanged` e inserimento di dichiarazioni delle funzioni di accesso dell'evento. Nell'esempio <xref:System.Windows.UIElement.AddHandler%2A> viene `add` chiamato nella <xref:System.Windows.UIElement.RemoveHandler%2A> dichiarazione della funzione di accesso e nella dichiarazione della `remove` funzione di accesso per utilizzare i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] servizi eventi.

- Creazione di un metodo virtuale protetto denominato `OnValueChanged` che genera l'evento `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Per altre informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md) e [Creare un evento indirizzato personalizzato](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Usare il binding

Per separare l'interfaccia utente del controllo dalla relativa logica, è possibile usare il data binding. Ciò è particolarmente importante se si definisce <xref:System.Windows.Controls.ControlTemplate>l'aspetto del controllo utilizzando un oggetto . Se si usa il data binding, potrebbe non essere più necessario fare riferimento a parti specifiche dell'interfaccia utente dal codice. È consigliabile evitare di fare riferimento a <xref:System.Windows.Controls.ControlTemplate> elementi presenti nel because quando <xref:System.Windows.Controls.ControlTemplate> il <xref:System.Windows.Controls.ControlTemplate> codice fa riferimento a elementi inclusi nell'oggetto e viene modificato, l'elemento a cui si fa riferimento deve essere incluso nel nuovo <xref:System.Windows.Controls.ControlTemplate>oggetto .

Nell'esempio `NumericUpDown` seguente <xref:System.Windows.Controls.TextBlock> viene aggiornato il controllo, assegnandovi un nome e facendo riferimento alla casella di testo in base al nome nel codice.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

L'esempio seguente usa il binding per ottenere lo stesso risultato.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Per ulteriori informazioni sull'associazione dati, vedere [Cenni preliminari sull'associazione dati.](../../../desktop-wpf/data/data-binding-overview.md)

### <a name="design-for-designers"></a>Progettare le finestre di progettazione

Per ricevere il supporto per i controlli WPF personalizzati in WPF Designer per Visual Studio (ad esempio, la modifica di proprietà con il proprietà finestra), seguire queste linee guida.  Per ulteriori informazioni sullo sviluppo di Progettazione WPF, vedere [Progettare XAML in Visual Studio.](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)

#### <a name="dependency-properties"></a>Proprietà di dipendenza

Assicurarsi di `get` implementare CLR e `set` le funzioni di accesso come descritto in precedenza, in "Utilizzare le proprietà di dipendenza". Le finestre di progettazione possono usare il wrapper per rilevare la presenza di una proprietà di dipendenza, ma, come accade per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e per i client del controllo, non è necessario chiamare le funzioni di accesso quando si ottiene o si imposta la proprietà.

#### <a name="attached-properties"></a>Proprietà associate

Per implementare le proprietà associate nei controlli personalizzati, attenersi alle linee guida seguenti:

- Avere `public` `static` `readonly` <xref:System.Windows.DependencyProperty> un form *PropertyName* `Property` che è <xref:System.Windows.DependencyProperty.RegisterAttached%2A> stato creato utilizzando il metodo . Il nome della proprietà <xref:System.Windows.DependencyProperty.RegisterAttached%2A> passato a deve corrispondere a *PropertyName*.

- Implementare una coppia di metodi CLR`public` `static` denominati `Set`*NomeProprietà* e `Get`*NomeProprietà*. Entrambi i metodi devono <xref:System.Windows.DependencyProperty> accettare una classe derivata da come primo argomento. Il metodo `Set`*NomeProprietà* accetta anche un argomento il cui tipo corrisponde al tipo di dati registrato per la proprietà. Il metodo `Get`*NomeProprietà* deve restituire un valore dello stesso tipo. In assenza del metodo `Set`*NomeProprietà*, la proprietà viene contrassegnata come di sola lettura.

- `Set`*PropertyName* `Get`e *PropertyName* devono <xref:System.Windows.DependencyObject.GetValue%2A> essere <xref:System.Windows.DependencyObject.SetValue%2A> indirizzati direttamente ai metodi e nell'oggetto di dipendenza di destinazione, rispettivamente. Le finestre di progettazione possono accedere alla proprietà associata eseguendo una chiamata tramite il wrapper del metodo oppure una chiamata diretta all'oggetto dipendenza di destinazione.

Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definire e usare risorse condivise

È possibile includere il controllo nello stesso assembly dell'applicazione oppure inserirlo in un pacchetto in un assembly separato che può essere usato in più applicazioni. Nella maggior parte dei casi, le informazioni di questo argomento si applicano indipendentemente dal metodo usato.  È importante tuttavia notare una differenza.  Quando si inserisce un controllo nello stesso assembly di un'applicazione, è possibile aggiungere risorse globali al file App.xaml. Tuttavia, a un assembly che <xref:System.Windows.Application> contiene solo controlli non è associato un oggetto, pertanto non è disponibile un file App.xaml.

Quando un'applicazione cerca una risorsa, la ricerca viene effettuata a tre livelli nell'ordine seguente:

1. Livello dell'elemento.

   Il sistema inizia dall'elemento che fa riferimento alla risorsa, quindi esegue la ricerca delle risorse dell'elemento padre logico continuando fino a raggiungere l'elemento radice.

2. Livello dell'applicazione.

   Risorse definite <xref:System.Windows.Application> dall'oggetto.

3. Livello del tema.

   I dizionari a livello di tema vengono archiviati in una sottocartella denominata Themes.  I file nella cartella Themes corrispondono ai temi.  Potrebbero ad esempio essere presenti Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml e così via.  Può esserci anche un file denominato generic.xaml.  Quando il sistema cerca una risorsa a livello di tema, la ricerca viene effettuata prima nel file specifico del tema e poi nel file generic.xaml.

Quando il controllo si trova in un assembly separato dall'applicazione, è necessario inserire le risorse globali a livello di elemento o a livello di tema. Entrambi i metodi offrono alcuni vantaggi.

#### <a name="defining-resources-at-the-element-level"></a>Definizione delle risorse a livello di elemento

È possibile definire risorse condivise a livello di elemento creando un dizionario risorse personalizzato e unendolo al dizionario risorse del controllo.  Quando si usa questo metodo, è possibile assegnare un nome qualsiasi al file di risorse, che può trovarsi nella stessa cartella dei controlli. Le risorse a livello di elemento possono anche usare semplici stringhe come chiavi. Nell'esempio seguente <xref:System.Windows.Media.LinearGradientBrush> viene creato un file di risorse denominato Dictionary1.xaml.The following example creates a resource file named Dictionary1.xaml.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Una volta definito il dizionario, è necessario unirlo al dizionario risorse del controllo.  A tale scopo, è possibile usare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o il codice.

L'esempio seguente unisce un dizionario risorse usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Lo svantaggio di questo <xref:System.Windows.ResourceDictionary> approccio è che un oggetto viene creato ogni volta che si fa riferimento ad esso.  Ad esempio, se nella libreria sono in disporre di 10 controlli personalizzati e unire i <xref:System.Windows.ResourceDictionary> dizionari risorse condivisi per ogni controllo tramite XAML, creare 10 oggetti identici.  È possibile evitare questo problema creando una classe statica <xref:System.Windows.ResourceDictionary>che unisce le risorse nel codice e restituisce l'oggetto risultante.

Nell'esempio riportato di seguito <xref:System.Windows.ResourceDictionary>viene creata una classe che restituisce un oggetto shared .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

L'esempio seguente unisce la risorsa condivisa con le risorse di un controllo personalizzato nel costruttore del controllo prima di chiamare `InitializeComponent`.  Poiché `SharedDictionaryManager.SharedDictionary` l'oggetto è <xref:System.Windows.ResourceDictionary> una proprietà statica, l'oggetto viene creato una sola volta. Poiché il dizionario risorse è stato unito prima di chiamare `InitializeComponent`, le risorse sono disponibili per il controllo nel relativo file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definizione delle risorse a livello di tema

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di creare risorse per diversi temi di Windows.  L'autore di un controllo può definire una risorsa per un tema specifico in modo da modificare l'aspetto del controllo a seconda del tema in uso. Ad esempio, l'aspetto di <xref:System.Windows.Controls.Button> un nel tema classico di Windows (il tema <xref:System.Windows.Controls.Button> predefinito per Windows 2000) è diverso da <xref:System.Windows.Controls.Button> un nel <xref:System.Windows.Controls.ControlTemplate> tema Luna di Windows (il tema predefinito per Windows XP) perché utilizza un diverso per ogni tema.

Le risorse specifiche di un tema vengono inserite in un dizionario risorse con un nome file specifico. Questi file devono trovarsi in una cartella denominata `Themes` che è una sottocartella della cartella contenente il controllo. La tabella seguente elenca i file del dizionario risorse e il tema associato a ogni file:

|Nome file del dizionario risorse|Tema di Windows|
|-----------------------------------|-------------------|
|`Classic.xaml`|Aspetto classico di Windows 9x/2000 in Windows XP|
|`Luna.NormalColor.xaml`|Tema blu predefinito in Windows XP|
|`Luna.Homestead.xaml`|Tema verde oliva in Windows XP|
|`Luna.Metallic.xaml`|Tema argento in Windows XP|
|`Royale.NormalColor.xaml`|Tema predefinito in Windows XP Media Center Edition|
|`Aero.NormalColor.xaml`|Tema predefinito in Windows Vista|

Non è necessario definire una risorsa per ogni tema. Se una risorsa non è definita per un tema specifico, il controllo la cerca in `Classic.xaml`. Se la risorsa non è definita nel file che corrisponde al tema corrente o in `Classic.xaml`, il controllo usa la risorsa generica, che si trova in un file del dizionario risorse denominato `generic.xaml`.  Il file `generic.xaml` si trova nella stessa cartella dei file del dizionario risorse specifico del tema. Anche se `generic.xaml` non corrisponde a un tema di Windows specifico, è comunque un dizionario a livello di tema.

L'esempio di controllo personalizzato NumericUpDown di [C](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) o [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) con `NumericUpDown` tema e supporto dell'automazione dell'interfaccia utente contiene due dizionari risorse per il controllo: uno in generic.xaml e l'altro in Luna.NormalColor.xaml.

Quando si <xref:System.Windows.Controls.ControlTemplate> inserisce un oggetto in uno dei file del dizionario risorse specifico <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> del tema, è necessario creare un costruttore statico per il controllo e chiamare il metodo su <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, come illustrato nell'esempio seguente.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definizione delle chiavi e relativo riferimento per le risorse del tema

Quando si definisce una risorsa a livello di elemento, è possibile assegnare una stringa come chiave e accedere alla risorsa tramite la stringa. Quando si definisce una risorsa a livello <xref:System.Windows.ComponentResourceKey> di tema, è necessario utilizzare un come chiave.  L'esempio seguente definisce una risorsa in generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Nell'esempio seguente viene fatto <xref:System.Windows.ComponentResourceKey> riferimento alla risorsa specificando la chiave .

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Indicazione del percorso delle risorse del tema

Per trovare le risorse per un controllo, l'applicazione host deve sapere che l'assembly contiene risorse specifiche del controllo. A tale scopo, <xref:System.Windows.ThemeInfoAttribute> è possibile aggiungere l'oggetto all'assembly che contiene il controllo. La <xref:System.Windows.ThemeInfoAttribute> dispone <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> di una proprietà che specifica la <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> posizione delle risorse generiche e di una proprietà che specifica la posizione delle risorse specifiche del tema.

Nell'esempio riportato di seguito le <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> proprietà e vengono impostate su <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, per specificare che le risorse generiche e specifiche del tema si trovano nello stesso assembly del controllo.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Vedere anche

- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md)
- [Personalizzazione dei controlli](control-customization.md)
