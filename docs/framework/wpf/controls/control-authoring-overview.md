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
ms.openlocfilehash: 5f36ef46bcca2cc99261660143507bac633ebdd3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651446"
---
# <a name="control-authoring-overview"></a>Panoramica della creazione di controlli
L'estendibilità del modello di controlli di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] riduce notevolmente l'esigenza di creare un nuovo controllo. In alcuni casi può tuttavia essere ancora necessario creare un controllo personalizzato. Questo argomento illustra le funzionalità che riducono al minimo l'esigenza di creare un controllo personalizzato e i diversi modelli di creazione di controlli in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viene anche illustrato come creare un nuovo controllo.  

<a name="when_to_write_a_new_control"></a>   
## <a name="alternatives-to-writing-a-new-control"></a>Alternative alla scrittura di un nuovo controllo  
 In precedenza, per ottenere un'esperienza personalizzata da un controllo esistente, le modifiche erano limitate alle proprietà standard del controllo, ad esempio colore di sfondo, spessore del bordo e dimensioni del carattere. Per estendere l'aspetto o il comportamento di un controllo oltre questi parametri predefiniti, era necessario creare un nuovo controllo, in genere ereditando da un controllo esistente ed eseguendo l'override del metodo responsabile del disegno del controllo.  Sebbene ciò sia ancora possibile, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di personalizzare i controlli esistenti usando un modello di contenuto avanzato, stili, modelli e trigger. L'elenco seguente fornisce alcuni esempi relativi a come usare queste funzionalità per creare esperienze coerenti e personalizzate senza dover creare un nuovo controllo.  
  
- **Contenuto avanzato.** Molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard supportano il contenuto avanzato. Ad esempio, la proprietà di contenuto di un <xref:System.Windows.Controls.Button> JE typu <xref:System.Object>, quindi, teoricamente qualsiasi elemento può essere visualizzato una <xref:System.Windows.Controls.Button>.  Per visualizzare un'immagine e testo in un pulsante, è possibile aggiungere un'immagine e un <xref:System.Windows.Controls.TextBlock> a un <xref:System.Windows.Controls.StackPanel> e assegnare le <xref:System.Windows.Controls.StackPanel> per il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà. Poiché i controlli possono visualizzare dati arbitrari ed elementi visivi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], c'è una minore esigenza di creare un nuovo controllo o di modificarne uno esistente per supportare una visualizzazione complessa. Per altre informazioni sul modello di contenuto per <xref:System.Windows.Controls.Button> e i modelli in altri contenuti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [modello di contenuto WPF](wpf-content-model.md).  
  
- **Stili.** Oggetto <xref:System.Windows.Style> è una raccolta di valori che rappresentano le proprietà per un controllo. Usando gli stili, è possibile creare una rappresentazione riutilizzabile dell'aspetto e del comportamento desiderati di un controllo, senza scriverne uno nuovo. Ad esempio, si supponga di voler tutti i <xref:System.Windows.Controls.TextBlock> controlli con tipo di carattere Arial di colore rosso con una dimensione pari a 14. È possibile creare uno stile come risorsa e impostare le proprietà appropriate di conseguenza. Quindi ogni <xref:System.Windows.Controls.TextBlock> aggiungere all'applicazione avrà lo stesso aspetto.  
  
- **Modelli di dati.** Oggetto <xref:System.Windows.DataTemplate> consente di personalizzare la modalità di visualizzazione dei dati in un controllo. Ad esempio, un <xref:System.Windows.DataTemplate> può essere utilizzato per specificare la modalità di visualizzazione dei dati un <xref:System.Windows.Controls.ListBox>.  Per un esempio, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).  Oltre alla personalizzazione dell'aspetto dei dati, un <xref:System.Windows.DataTemplate> può includere elementi dell'interfaccia utente, che consente una notevole flessibilità nelle interfacce utente personalizzate.  Ad esempio, usando un <xref:System.Windows.DataTemplate>, è possibile creare un <xref:System.Windows.Controls.ComboBox> in cui ogni elemento contiene una casella di controllo.  
  
- **Modelli di controllo.** In molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usano un <xref:System.Windows.Controls.ControlTemplate> per definire la struttura e l'aspetto, separando così l'aspetto di un controllo della funzionalità del controllo. Consente di modificare radicalmente l'aspetto di un controllo mediante la ridefinizione relativo <xref:System.Windows.Controls.ControlTemplate>.  Si supponga, ad esempio, di voler creare un controllo con l'aspetto di un semaforo. Il controllo ha una funzionalità e un'interfaccia utente semplici.  È costituito da tre cerchi, che possono essere illuminati soltanto uno alla volta. Dopo alcune reflection, in modo che un <xref:System.Windows.Controls.RadioButton> offre le funzionalità di essere selezionati solo una alla volta, ma l'aspetto predefinito del <xref:System.Windows.Controls.RadioButton> non ha nulla a che le luci su un semaforo.  Poiché il <xref:System.Windows.Controls.RadioButton> Usa un modello di controllo per definire l'aspetto, è possibile ridefinire facilmente il <xref:System.Windows.Controls.ControlTemplate> per soddisfare i requisiti di controllo e usare i pulsanti di opzione per creare il semaforo.  
  
    > [!NOTE]
    >  Anche se un <xref:System.Windows.Controls.RadioButton> possibile usare una <xref:System.Windows.DataTemplate>, un <xref:System.Windows.DataTemplate> non è sufficiente in questo esempio.  Il <xref:System.Windows.DataTemplate> definisce l'aspetto del contenuto di un controllo. Nel caso di un <xref:System.Windows.Controls.RadioButton>, il contenuto è qualsiasi elemento visualizzato a destra del cerchio che indica se il <xref:System.Windows.Controls.RadioButton> sia selezionata.  Nell'esempio del semaforo il pulsante di opzione deve essere costituito semplicemente da un cerchio in grado di "illuminarsi". Poiché l'aspetto richiesto per il semaforo è molto diverso l'aspetto predefinito del <xref:System.Windows.Controls.RadioButton>, è necessario ridefinire il <xref:System.Windows.Controls.ControlTemplate>.  In genere un <xref:System.Windows.DataTemplate> viene usato per definire il contenuto o i dati di un controllo e un <xref:System.Windows.Controls.ControlTemplate> viene usato per la definizione di strutturazione di un controllo.  
  
- **Trigger.** Oggetto <xref:System.Windows.Trigger> consente di modificare in modo dinamico l'aspetto e il comportamento di un controllo senza creare un nuovo controllo. Ad esempio, si supponga che si dispone di più <xref:System.Windows.Controls.ListBox> controlli nell'applicazione e gli elementi in ogni <xref:System.Windows.Controls.ListBox> per essere in grassetto e colore rosso quando vengono selezionati. Potrebbe essere il primo impulso per creare una classe che eredita da <xref:System.Windows.Controls.ListBox> ed eseguire l'override di <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> metodo per modificare l'aspetto dell'elemento selezionato, ma un approccio migliore consiste nell'aggiungere un trigger a uno stile di un <xref:System.Windows.Controls.ListBoxItem> che modifica l'aspetto di l'elemento selezionato. Un trigger consente di modificare i valori delle proprietà o di eseguire determinate azioni in base al valore di una proprietà. Un <xref:System.Windows.EventTrigger> consente di eseguire determinate azioni quando si verifica un evento.  
  
 Per altre informazioni su stili, modelli e trigger, vedere [Applicazione di stili e modelli](styling-and-templating.md).  
  
 In genere, se il controllo rispecchia la funzionalità di un controllo esistente, ma si vuole che abbia un aspetto diverso, valutare innanzitutto la possibilità di usare uno dei metodi descritti in questa sezione per modificare l'aspetto del controllo esistente.  
  
<a name="models_for_control_authoring"></a>   
## <a name="models-for-control-authoring"></a>Modelli per la modifica dei controlli  
 Il modello di contenuto avanzato, gli stili, i modelli e i trigger riducono al minimo la necessità di creare un nuovo controllo. Se, tuttavia, è necessario creare un nuovo controllo, è importante conoscere i diversi modelli di creazione di controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce tre modelli generali per la creazione di un controllo, ognuno dei quali offre un set di funzionalità e un livello di flessibilità specifici. Le classi base per i tre modelli sono <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>, e <xref:System.Windows.FrameworkElement>.  
  
### <a name="deriving-from-usercontrol"></a>Derivazione da UserControl  
 Il modo più semplice per creare un controllo nella [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivarlo da <xref:System.Windows.Controls.UserControl>. Quando si crea un controllo che eredita da <xref:System.Windows.Controls.UserControl>, si aggiungono i componenti esistenti per il <xref:System.Windows.Controls.UserControl>denominare i componenti e fare riferimento ai gestori di eventi in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. È quindi possibile fare riferimento agli elementi denominati e definire i gestori eventi nel codice. Questo modello di sviluppo è molto simile al modello usato per lo sviluppo di applicazioni in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Se creato correttamente, un <xref:System.Windows.Controls.UserControl> possono sfruttare i vantaggi di contenuto avanzato, stili e trigger. Tuttavia, se il controllo eredita da <xref:System.Windows.Controls.UserControl>, gli utenti che usano il controllo non sarà in grado di usare una <xref:System.Windows.DataTemplate> o <xref:System.Windows.Controls.ControlTemplate> per personalizzarne l'aspetto.  È necessario derivare il <xref:System.Windows.Controls.Control> classe o una delle relative classi derivate (diverso da <xref:System.Windows.Controls.UserControl>) per creare un controllo personalizzato che supporta i modelli.  
  
#### <a name="benefits-of-deriving-from-usercontrol"></a>Vantaggi della derivazione da UserControl  
 Prendere in considerazione la derivazione da <xref:System.Windows.Controls.UserControl> se applica tutte le operazioni seguenti:  
  
- Si vuole creare il controllo in modo analogo a come si crea un'applicazione.  
  
- Il controllo è costituito esclusivamente da componenti esistenti.  
  
- Non è necessario supportare una personalizzazione complessa.  
  
### <a name="deriving-from-control"></a>Derivazione da Control  
 Derivazione dal <xref:System.Windows.Controls.Control> classe è il modello usato dalla maggior parte dell'oggetto esistente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli. Quando si crea un controllo che eredita dal <xref:System.Windows.Controls.Control> (classe), si definisce l'aspetto del controllo con i modelli. In tal modo, la logica operativa viene separata dalla rappresentazione visiva. È anche possibile ottenere la separazione dell'interfaccia utente e per la logica usando i comandi e le associazioni invece evitando riferimenti agli elementi e gli eventi di <xref:System.Windows.Controls.ControlTemplate> laddove possibile.  Se l'interfaccia utente e per la logica del controllo sono separate in modo appropriato, un utente del controllo può ridefinire il controllo <xref:System.Windows.Controls.ControlTemplate> per personalizzarne l'aspetto. Sebbene la compilazione di una classe personalizzata <xref:System.Windows.Controls.Control> non è così semplice come la compilazione una <xref:System.Windows.Controls.UserControl>, un oggetto personalizzato <xref:System.Windows.Controls.Control> offre la massima flessibilità.  
  
#### <a name="benefits-of-deriving-from-control"></a>Vantaggi della derivazione da Control  
 Prendere in considerazione che deriva da <xref:System.Windows.Controls.Control> invece di usare il <xref:System.Windows.Controls.UserControl> classe se una qualsiasi delle condizioni seguenti:  
  
- Si desidera che l'aspetto del controllo per essere personalizzabile tramite il <xref:System.Windows.Controls.ControlTemplate>.  
  
- Si vuole che il controllo supporti temi diversi.  
  
### <a name="deriving-from-frameworkelement"></a>Derivazione da FrameworkElement  
 I controlli che derivano da <xref:System.Windows.Controls.UserControl> o <xref:System.Windows.Controls.Control> si basano sulla composizione di elementi esistenti. Per molti scenari, questa è una soluzione accettabile, perché qualsiasi oggetto che eredita da <xref:System.Windows.FrameworkElement> possono trovarsi in un <xref:System.Windows.Controls.ControlTemplate>. A volte, tuttavia, le funzionalità di composizione semplice di elementi non sono sufficienti per definire l'aspetto di un controllo. Per questi scenari, è necessario basare un componente in <xref:System.Windows.FrameworkElement> è la scelta giusta.  
  
 Esistono due metodi standard per la compilazione <xref:System.Windows.FrameworkElement>-componenti basati su: rendering diretto e personalizzate elemento composizione. Il rendering diretto comporta l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo di <xref:System.Windows.FrameworkElement> e fornendo <xref:System.Windows.Media.DrawingContext> operazioni che definiscono in modo esplicito gli elementi visivi del componente. Si tratta del metodo usato da <xref:System.Windows.Controls.Image> e <xref:System.Windows.Controls.Border>. Composizione personalizzata prevede l'uso di oggetti di tipo <xref:System.Windows.Media.Visual> per comporre l'aspetto del componente. Per un esempio, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track> è un esempio di un controllo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che usa la composizione di elementi personalizzati. È anche possibile combinare il rendering diretto e la composizione personalizzata di elementi nello stesso controllo.  
  
#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vantaggi della derivazione da FrameworkElement  
 Prendere in considerazione la derivazione da <xref:System.Windows.FrameworkElement> se una qualsiasi delle condizioni seguenti:  
  
- Si vuole controllare l'aspetto del controllo in modo più preciso rispetto a quanto possibile con la composizione semplice di elementi.  
  
- Si vuole definire l'aspetto del controllo definendo una logica di rendering personalizzata.  
  
- Si vuole comporre gli elementi esistenti in nuovi modi, che vanno oltre le possibilità offerte da <xref:System.Windows.Controls.UserControl> e <xref:System.Windows.Controls.Control>.  
  
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
  
- Definire un <xref:System.Windows.DependencyProperty> identificatore denominata `ValueProperty` come una `public` `static` `readonly` campo.  
  
- Registrare il nome della proprietà con il sistema di proprietà, chiamando <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>, per specificare le informazioni seguenti:  
  
    - Nome della proprietà.  
  
    - Tipo della proprietà.  
  
    - Tipo proprietario della proprietà.  
  
    - Metadati della proprietà. I metadati contengono il valore della proprietà predefinito, un <xref:System.Windows.CoerceValueCallback> e un <xref:System.Windows.PropertyChangedCallback>.  
  
- Definizione di una proprietà del wrapper [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] denominata `Value`, ovvero lo stesso nome usato per registrare la proprietà di dipendenza, implementando le funzioni di accesso `get` e `set` della proprietà. Si noti che il `get` e `set` chiamare solo funzioni di accesso <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> rispettivamente. È consigliabile che le funzioni di accesso delle proprietà di dipendenza non contengano logica aggiuntiva perché i client e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] possono ignorare le funzioni di accesso e chiamare il metodo <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> direttamente. Ad esempio, quando una proprietà è associata a un'origine dati, la funzione di accesso `set` della proprietà non viene chiamata.  Anziché aggiungere logica aggiuntiva per get e set di funzioni di accesso, usare il <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>, e <xref:System.Windows.PropertyChangedCallback> delegati per rispondere o per controllare il valore in caso di modifiche.  Per altre informazioni su questi callback, vedere [Callback e convalida delle proprietà di dipendenza](../advanced/dependency-property-callbacks-and-validation.md).  
  
- Definire un metodo per la <xref:System.Windows.CoerceValueCallback> denominato `CoerceValue`. `CoerceValue` garantisce che `Value` sia maggiore o uguale a `MinValue` e minore o uguale a `MaxValue`.  
  
- Definire un metodo per la <xref:System.Windows.PropertyChangedCallback>, denominato `OnValueChanged`. `OnValueChanged` Crea una <xref:System.Windows.RoutedPropertyChangedEventArgs%601> dell'oggetto e lo prepara per la generazione di `ValueChanged` evento indirizzato. Gli eventi indirizzati sono illustrati nella sezione successiva.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 Per altre informazioni, vedere [Proprietà di dipendenza personalizzate](../advanced/custom-dependency-properties.md).  
  
### <a name="use-routed-events"></a>Usare gli eventi indirizzati  
 Come le proprietà di dipendenza estendono il concetto di proprietà [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con funzionalità aggiuntive, gli eventi indirizzati estendono il concetto di eventi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] standard. Quando si crea un nuovo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è anche consigliabile implementare l'evento come evento indirizzato, perché gli eventi indirizzati supportano i comportamenti seguenti:  
  
- Gli eventi possono essere gestiti in un elemento padre di più controlli. Nel caso di un evento di bubbling, un singolo elemento padre nell'albero degli elementi può sottoscrivere l'evento. Gli autori dell'applicazione possono quindi usare un solo gestore per rispondere all'evento di più controlli. Ad esempio, se il controllo fa parte di ogni elemento in un <xref:System.Windows.Controls.ListBox> (perché è incluso un <xref:System.Windows.DataTemplate>), lo sviluppatore dell'applicazione può definire il gestore eventi per l'evento del controllo nel <xref:System.Windows.Controls.ListBox>. Il gestore eventi viene chiamato ogni volta che l'evento si verifica in uno dei controlli.  
  
- Gli eventi indirizzati possono essere usati un <xref:System.Windows.EventSetter>, che consente agli sviluppatori di applicazioni specificare il gestore di evento all'interno di uno stile.  
  
- Gli eventi indirizzati possono essere usati un' <xref:System.Windows.EventTrigger>, è utile per l'animazione di proprietà utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).  
  
 L'esempio seguente definisce un evento indirizzato mediante le operazioni seguenti:  
  
- Definire un <xref:System.Windows.RoutedEvent> identificatore denominata `ValueChangedEvent` come una `public` `static` `readonly` campo.  
  
- Registrare l'evento indirizzato chiamando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> (metodo). L'esempio specifica le informazioni seguenti quando chiama <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>:  
  
    - Il nome dell'evento è `ValueChanged`.  
  
    - La strategia di routing è <xref:System.Windows.RoutingStrategy.Bubble>, il che significa che viene chiamato prima di tutto un gestore di evento nell'origine (l'oggetto che genera l'evento) e quindi i gestori eventi per gli elementi padre dell'origine vengono chiamati in successione, inizia con il gestore eventi su più vicina elemento padre.  
  
    - Il tipo del gestore dell'evento è <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, costruito con un <xref:System.Decimal> tipo.  
  
    - Il tipo proprietario dell'evento è `NumericUpDown`.  
  
- Dichiarazione di un evento pubblico denominato `ValueChanged` e inserimento di dichiarazioni delle funzioni di accesso dell'evento. Nell'esempio viene chiamato <xref:System.Windows.UIElement.AddHandler%2A> nella `add` dichiarazione di funzione di accesso e <xref:System.Windows.UIElement.RemoveHandler%2A> nel `remove` dichiarazione di funzione di accesso da utilizzare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] servizi eventi.  
  
- Creazione di un metodo virtuale protetto denominato `OnValueChanged` che genera l'evento `ValueChanged`.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 Per altre informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md) e [Creare un evento indirizzato personalizzato](../advanced/how-to-create-a-custom-routed-event.md).  
  
### <a name="use-binding"></a>Usare il binding  
 Per separare l'interfaccia utente del controllo dalla relativa logica, è possibile usare il data binding. Ciò è particolarmente importante se si definisce l'aspetto del controllo utilizzando un <xref:System.Windows.Controls.ControlTemplate>. Se si usa il data binding, potrebbe non essere più necessario fare riferimento a parti specifiche dell'interfaccia utente dal codice. È consigliabile evitare di fare riferimento a elementi appartenenti al <xref:System.Windows.Controls.ControlTemplate> perché quando il codice fa riferimento a elementi presenti nel <xref:System.Windows.Controls.ControlTemplate> e il <xref:System.Windows.Controls.ControlTemplate> viene modificato, l'elemento referenziato dovrà essere incluso nel nuovo <xref:System.Windows.Controls.ControlTemplate>.  
  
 L'esempio seguente aggiorna il <xref:System.Windows.Controls.TextBlock> del `NumericUpDown` controllo, assegnandogli un nome e la casella di testo di riferimento in base al nome in codice.  
  
 [!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 L'esempio seguente usa il binding per ottenere lo stesso risultato.  
  
 [!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../data/data-binding-overview.md).  
  
### <a name="design-for-designers"></a>Progettare le finestre di progettazione  
 Per ottenere supporto per i controlli WPF personalizzati in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)], ad esempio per la modifica delle proprietà con la finestra Proprietà, attenersi alle linee guida riportate di seguito.  Per altre informazioni sullo sviluppo per il [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], vedere [progettazione XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).  
  
#### <a name="dependency-properties"></a>Proprietà di dipendenza  
 Implementare le funzioni di accesso [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` e `set` come descritto in precedenza in "Usare le proprietà di dipendenza". Le finestre di progettazione possono usare il wrapper per rilevare la presenza di una proprietà di dipendenza, ma, come accade per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e per i client del controllo, non è necessario chiamare le funzioni di accesso quando si ottiene o si imposta la proprietà.  
  
#### <a name="attached-properties"></a>Proprietà associate  
 Per implementare le proprietà associate nei controlli personalizzati, attenersi alle linee guida seguenti:  
  
- Avere una `public` `static` `readonly` <xref:System.Windows.DependencyProperty> nel formato *PropertyName* `Property` creato usando il <xref:System.Windows.DependencyProperty.RegisterAttached%2A> (metodo). Il nome della proprietà che viene passato a <xref:System.Windows.DependencyProperty.RegisterAttached%2A> deve corrispondere *NomeProprietà*.  
  
- Implementare una coppia di metodi CLR`public` `static` denominati `Set`*NomeProprietà* e `Get`*NomeProprietà*. Entrambi i metodi devono accettare una classe derivata da <xref:System.Windows.DependencyProperty> come primo argomento. Il metodo `Set`*NomeProprietà* accetta anche un argomento il cui tipo corrisponde al tipo di dati registrato per la proprietà. Il metodo `Get`*NomeProprietà* deve restituire un valore dello stesso tipo. In assenza del metodo `Set`*NomeProprietà*, la proprietà viene contrassegnata come di sola lettura.  
  
- `Set` *PropertyName* e `Get` *PropertyName* devono essere indirizzati direttamente al <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> metodi sulla dipendenza di destinazione dell'oggetto, rispettivamente. Le finestre di progettazione possono accedere alla proprietà associata eseguendo una chiamata tramite il wrapper del metodo oppure una chiamata diretta all'oggetto dipendenza di destinazione.  
  
 Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).  
  
### <a name="define-and-use-shared-resources"></a>Definire e usare risorse condivise  
 È possibile includere il controllo nello stesso assembly dell'applicazione oppure inserirlo in un pacchetto in un assembly separato che può essere usato in più applicazioni. Nella maggior parte dei casi, le informazioni di questo argomento si applicano indipendentemente dal metodo usato.  È importante tuttavia notare una differenza.  Quando si inserisce un controllo nello stesso assembly di un'applicazione, è possibile aggiungere risorse globali al file App.xaml. Ma non dispone di un assembly che contiene solo controlli un <xref:System.Windows.Application> oggetto associato, in modo che non è disponibile un file app. Xaml.  
  
 Quando un'applicazione cerca una risorsa, la ricerca viene effettuata a tre livelli nell'ordine seguente:  
  
1. Livello dell'elemento.  
  
     Il sistema inizia dall'elemento che fa riferimento alla risorsa, quindi esegue la ricerca delle risorse dell'elemento padre logico continuando fino a raggiungere l'elemento radice.  
  
2. Livello dell'applicazione.  
  
     Risorse definite dal <xref:System.Windows.Application> oggetto.  
  
3. Livello del tema.  
  
     I dizionari a livello di tema vengono archiviati in una sottocartella denominata Themes.  I file nella cartella Themes corrispondono ai temi.  Potrebbero ad esempio essere presenti Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml e così via.  Può esserci anche un file denominato generic.xaml.  Quando il sistema cerca una risorsa a livello di tema, la ricerca viene effettuata prima nel file specifico del tema e poi nel file generic.xaml.  
  
 Quando il controllo si trova in un assembly separato dall'applicazione, è necessario inserire le risorse globali a livello di elemento o a livello di tema. Entrambi i metodi offrono alcuni vantaggi.  
  
#### <a name="defining-resources-at-the-element-level"></a>Definizione delle risorse a livello di elemento  
 È possibile definire le risorse condivise a livello di elemento creando un dizionario risorse personalizzato e unendolo al dizionario risorse del controllo.  Quando si usa questo metodo, è possibile assegnare un nome qualsiasi al file di risorse, che può trovarsi nella stessa cartella dei controlli. Le risorse a livello di elemento possono anche usare semplici stringhe come chiavi. L'esempio seguente crea un <xref:System.Windows.Media.LinearGradientBrush> file di risorse denominato Dictionary1.xaml.  
  
 [!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 Una volta definito il dizionario, è necessario unirlo al dizionario risorse del controllo.  A tale scopo, è possibile usare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o il codice.  
  
 L'esempio seguente unisce un dizionario risorse usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 Lo svantaggio di questo approccio è che un <xref:System.Windows.ResourceDictionary> oggetto viene creato ogni volta che è possibile farvi riferimento.  Ad esempio, se si dispongono di 10 controlli personalizzati nella libreria e si uniscono i dizionari delle risorse condivise per ogni controllo usando XAML, è creare 10 identici <xref:System.Windows.ResourceDictionary> oggetti.  È possibile evitare questo problema creando una classe statica che unisce le risorse nel codice e restituisce l'oggetto risultante <xref:System.Windows.ResourceDictionary>.  
  
 L'esempio seguente crea una classe che restituisce un oggetto condiviso <xref:System.Windows.ResourceDictionary>.  
  
 [!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 L'esempio seguente unisce la risorsa condivisa con le risorse di un controllo personalizzato nel costruttore del controllo prima di chiamare `InitializeComponent`.  Poiché il `SharedDictionaryManager.SharedDictionary` è una proprietà statica, il <xref:System.Windows.ResourceDictionary> viene creata una sola volta. Poiché il dizionario risorse è stato unito prima di chiamare `InitializeComponent`, le risorse sono disponibili per il controllo nel relativo file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### <a name="defining-resources-at-the-theme-level"></a>Definizione delle risorse a livello di tema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di creare risorse per diversi temi di Windows.  L'autore di un controllo può definire una risorsa per un tema specifico in modo da modificare l'aspetto del controllo a seconda del tema in uso. Ad esempio, l'aspetto di un <xref:System.Windows.Controls.Button> in di Windows classico tema (il tema predefinito per Windows 2000) è diverso da un <xref:System.Windows.Controls.Button> nel tema Windows Luna (il tema predefinito per Windows XP) perché il <xref:System.Windows.Controls.Button> utilizza una diversa <xref:System.Windows.Controls.ControlTemplate> per ogni tema.  
  
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
  
 L'[esempio di controllo personalizzato NumericUpDown con supporto per temi e automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=160025) contiene due dizionari risorse per li controllo `NumericUpDown`: uno in generic.xaml e uno in Luna.NormalColor.xaml.  È possibile eseguire l'applicazione e passare tra il tema argento in Windows XP e un altro tema per vedere la differenza tra i due modelli del controllo. Se si usa Windows Vista, è possibile rinominare Luna.NormalColor.xaml in Aero.NormalColor.xaml e passare tra due temi, ad esempio tra il tema Windows Classico e il tema predefinito per Windows Vista.  
  
 Quando si inserisce un <xref:System.Windows.Controls.ControlTemplate> in uno qualsiasi dei file di dizionario risorse specifiche per i temi, è necessario creare un costruttore statico per il controllo e chiamare il <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> metodo su di <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, come illustrato nell'esempio seguente.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definizione delle chiavi e relativo riferimento per le risorse del tema  
 Quando si definisce una risorsa a livello di elemento, è possibile assegnare una stringa come chiave e accedere alla risorsa tramite la stringa. Quando si definisce una risorsa a livello di tema, è necessario usare un <xref:System.Windows.ComponentResourceKey> come chiave.  L'esempio seguente definisce una risorsa in generic.xaml.  
  
 [!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]  
  
 Nell'esempio seguente fa riferimento alla risorsa, specificando il <xref:System.Windows.ComponentResourceKey> come chiave.  
  
 [!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]  
  
##### <a name="specifying-the-location-of-theme-resources"></a>Indicazione del percorso delle risorse del tema  
 Per trovare le risorse per un controllo, l'applicazione host deve sapere che l'assembly contiene risorse specifiche del controllo. È possibile eseguire questa operazione aggiungendo la <xref:System.Windows.ThemeInfoAttribute> all'assembly che contiene il controllo. Il <xref:System.Windows.ThemeInfoAttribute> ha un <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> proprietà che specifica il percorso delle risorse generiche, e un <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> proprietà che specifica il percorso delle risorse specifiche per i temi.  
  
 L'esempio seguente imposta la <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> e <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> delle proprietà per <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, per specificare che le risorse generiche e specifici del tema sono nello stesso assembly come controllo.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## <a name="see-also"></a>Vedere anche

- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md)
- [Personalizzazione dei controlli](control-customization.md)
