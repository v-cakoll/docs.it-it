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
ms.openlocfilehash: 3ea5519259ba2ee31bfd6bc25f6bedf1f1250799
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401540"
---
# <a name="control-authoring-overview"></a>Panoramica della creazione di controlli

L'estendibilità del modello di controlli di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] riduce notevolmente l'esigenza di creare un nuovo controllo. In alcuni casi può tuttavia essere ancora necessario creare un controllo personalizzato. Questo argomento illustra le funzionalità che riducono al minimo l'esigenza di creare un controllo personalizzato e i diversi modelli di creazione di controlli in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viene anche illustrato come creare un nuovo controllo.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternative alla scrittura di un nuovo controllo

In precedenza, per ottenere un'esperienza personalizzata da un controllo esistente, le modifiche erano limitate alle proprietà standard del controllo, ad esempio colore di sfondo, spessore del bordo e dimensioni del carattere. Per estendere l'aspetto o il comportamento di un controllo oltre questi parametri predefiniti, era necessario creare un nuovo controllo, in genere ereditando da un controllo esistente ed eseguendo l'override del metodo responsabile del disegno del controllo.  Sebbene ciò sia ancora possibile, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di personalizzare i controlli esistenti usando un modello di contenuto avanzato, stili, modelli e trigger. L'elenco seguente fornisce alcuni esempi relativi a come usare queste funzionalità per creare esperienze coerenti e personalizzate senza dover creare un nuovo controllo.

- **Contenuto avanzato.** Molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard supportano il contenuto avanzato. Ad esempio, la proprietà Content di un <xref:System.Windows.Controls.Button> oggetto è di <xref:System.Object>tipo, quindi teoricamente qualsiasi elemento può essere visualizzato <xref:System.Windows.Controls.Button>in un oggetto.  Per fare in modo che un pulsante visualizzi un'immagine e un testo, è possibile <xref:System.Windows.Controls.TextBlock> aggiungere un' <xref:System.Windows.Controls.StackPanel> immagine e un oggetto a <xref:System.Windows.Controls.ContentControl.Content%2A> un oggetto e assegnare <xref:System.Windows.Controls.StackPanel> alla proprietà. Poiché i controlli possono visualizzare dati arbitrari ed elementi visivi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], c'è una minore esigenza di creare un nuovo controllo o di modificarne uno esistente per supportare una visualizzazione complessa. Per ulteriori informazioni sul modello di contenuto per <xref:System.Windows.Controls.Button> e altri modelli di contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in, vedere modello di contenuto [WPF](wpf-content-model.md).

- **Stili.** Un <xref:System.Windows.Style> oggetto è una raccolta di valori che rappresentano le proprietà di un controllo. Usando gli stili, è possibile creare una rappresentazione riutilizzabile dell'aspetto e del comportamento desiderati di un controllo, senza scriverne uno nuovo. Si supponga, ad esempio, di volere che tutti <xref:System.Windows.Controls.TextBlock> i controlli abbiano un tipo di carattere rosso, Arial con una dimensione del carattere pari a 14. È possibile creare uno stile come risorsa e impostare le proprietà appropriate di conseguenza. Quindi, <xref:System.Windows.Controls.TextBlock> ogni aggiunta all'applicazione avrà lo stesso aspetto.

- **Modelli di dati.** Un <xref:System.Windows.DataTemplate> oggetto consente di personalizzare la modalità di visualizzazione dei dati in un controllo. È ad esempio possibile <xref:System.Windows.DataTemplate> utilizzare un oggetto per specificare la modalità di visualizzazione dei dati <xref:System.Windows.Controls.ListBox>in un oggetto.  Per un esempio, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).  Oltre a personalizzare l'aspetto dei dati, un <xref:System.Windows.DataTemplate> può includere elementi dell'interfaccia utente, che offre una grande flessibilità nelle interfacce utente personalizzate.  Usando <xref:System.Windows.DataTemplate>, ad esempio, è possibile creare un <xref:System.Windows.Controls.ComboBox> oggetto in cui ogni elemento contiene una casella di controllo.

- **Modelli di controllo.** Molti controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usano un <xref:System.Windows.Controls.ControlTemplate> oggetto per definire la struttura e l'aspetto del controllo, che separa l'aspetto di un controllo dalla funzionalità del controllo. È possibile modificare drasticamente l'aspetto di un controllo ridefinendo <xref:System.Windows.Controls.ControlTemplate>il relativo.  Si supponga, ad esempio, di voler creare un controllo con l'aspetto di un semaforo. Il controllo ha una funzionalità e un'interfaccia utente semplici.  È costituito da tre cerchi, che possono essere illuminati soltanto uno alla volta. Dopo un certo livello <xref:System.Windows.Controls.RadioButton> <xref:System.Windows.Controls.RadioButton> di reflection, è possibile tenere presente che in un viene offerta la funzionalità di una sola selezione alla volta, ma l'aspetto predefinito di non è simile a quello delle luci di un semaforo.  Poiché utilizza un modello di controllo per definirne l'aspetto, è facile ridefinire <xref:System.Windows.Controls.ControlTemplate> l'oggetto in base ai requisiti del controllo e utilizzare i pulsanti di opzione per impostare il semaforo. <xref:System.Windows.Controls.RadioButton>

  > [!NOTE]
  > Sebbene un <xref:System.Windows.Controls.RadioButton> oggetto possa usare <xref:System.Windows.DataTemplate>un oggetto <xref:System.Windows.DataTemplate> , in questo esempio non è sufficiente.  <xref:System.Windows.DataTemplate> Definisce l'aspetto del contenuto di un controllo. Nel caso di un oggetto <xref:System.Windows.Controls.RadioButton>, il contenuto è quello visualizzato a destra del cerchio che indica se l'oggetto <xref:System.Windows.Controls.RadioButton> è selezionato.  Nell'esempio del semaforo il pulsante di opzione deve essere costituito semplicemente da un cerchio in grado di "illuminarsi". Poiché il requisito di aspetto per il semaforo è così diverso dall'aspetto predefinito di <xref:System.Windows.Controls.RadioButton>, è necessario <xref:System.Windows.Controls.ControlTemplate>ridefinire.  In generale un <xref:System.Windows.DataTemplate> viene usato per definire il contenuto (o i dati) di un controllo e un <xref:System.Windows.Controls.ControlTemplate> oggetto viene usato per definire la struttura di un controllo.

- **Trigger.** <xref:System.Windows.Trigger> Consente di modificare dinamicamente l'aspetto e il comportamento di un controllo senza creare un nuovo controllo. Si supponga, ad esempio, di <xref:System.Windows.Controls.ListBox> avere più controlli nell'applicazione e che gli elementi in <xref:System.Windows.Controls.ListBox> ogni elemento siano in grassetto e rossi quando vengono selezionati. Il primo istinto potrebbe consistere nel creare una classe che <xref:System.Windows.Controls.ListBox> eredita da ed <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> eseguire l'override del metodo per modificare l'aspetto dell'elemento selezionato, ma un approccio migliore consiste nell'aggiungere un trigger a uno <xref:System.Windows.Controls.ListBoxItem> stile di un oggetto che modifica l'aspetto di elemento selezionato. Un trigger consente di modificare i valori delle proprietà o di eseguire determinate azioni in base al valore di una proprietà. Un <xref:System.Windows.EventTrigger> oggetto consente di intraprendere azioni quando si verifica un evento.

Per altre informazioni su stili, modelli e trigger, vedere [Applicazione di stili e modelli](styling-and-templating.md).

In genere, se il controllo rispecchia la funzionalità di un controllo esistente, ma si vuole che abbia un aspetto diverso, valutare innanzitutto la possibilità di usare uno dei metodi descritti in questa sezione per modificare l'aspetto del controllo esistente.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelli per la modifica dei controlli

Il modello di contenuto avanzato, gli stili, i modelli e i trigger riducono al minimo la necessità di creare un nuovo controllo. Se, tuttavia, è necessario creare un nuovo controllo, è importante conoscere i diversi modelli di creazione di controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce tre modelli generali per la creazione di un controllo, ognuno dei quali offre un set di funzionalità e un livello di flessibilità specifici. Le classi di base per i tre modelli <xref:System.Windows.Controls.UserControl>sono <xref:System.Windows.Controls.Control>, e <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Derivazione da UserControl

Il modo più semplice per creare un controllo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivare <xref:System.Windows.Controls.UserControl>da. Quando si compila un controllo che eredita da <xref:System.Windows.Controls.UserControl>, i componenti esistenti vengono aggiunti <xref:System.Windows.Controls.UserControl>a, vengono denominati i componenti e i gestori eventi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]di riferimento in. È quindi possibile fare riferimento agli elementi denominati e definire i gestori eventi nel codice. Questo modello di sviluppo è molto simile al modello usato per lo sviluppo di applicazioni in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Se compilato correttamente, un <xref:System.Windows.Controls.UserControl> può sfruttare i vantaggi di contenuto avanzato, stili e trigger. Tuttavia, se il controllo eredita da <xref:System.Windows.Controls.UserControl>, le persone che usano il controllo non saranno in grado di <xref:System.Windows.DataTemplate> usare o <xref:System.Windows.Controls.ControlTemplate> per personalizzarne l'aspetto.  È necessario derivare dalla <xref:System.Windows.Controls.Control> classe o da una delle classi derivate ( <xref:System.Windows.Controls.UserControl>diverse da) per creare un controllo personalizzato che supporta i modelli.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vantaggi della derivazione da UserControl

Provare a derivare da <xref:System.Windows.Controls.UserControl> se si applicano tutte le condizioni seguenti:

- Si vuole creare il controllo in modo analogo a come si crea un'applicazione.

- Il controllo è costituito esclusivamente da componenti esistenti.

- Non è necessario supportare una personalizzazione complessa.

### <a name="deriving-from-control"></a>Derivazione da Control

La derivazione <xref:System.Windows.Controls.Control> dalla classe è il modello usato dalla maggior parte dei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli esistenti. Quando si crea un controllo che eredita dalla classe <xref:System.Windows.Controls.Control> , l'aspetto viene definito usando i modelli. In tal modo, la logica operativa viene separata dalla rappresentazione visiva. È anche possibile garantire la separazione dell'interfaccia utente e della logica usando i comandi e le associazioni anziché gli eventi e evitando di fare riferimento agli <xref:System.Windows.Controls.ControlTemplate> elementi nel quando possibile.  Se l'interfaccia utente e la logica del controllo sono disaccoppiate correttamente, un utente del controllo può ridefinire il controllo <xref:System.Windows.Controls.ControlTemplate> per personalizzarne l'aspetto. Sebbene la creazione di <xref:System.Windows.Controls.Control> un oggetto personalizzato non sia semplice come <xref:System.Windows.Controls.UserControl>la creazione di <xref:System.Windows.Controls.Control> un, un oggetto personalizzato offre la massima flessibilità.

#### <a name="benefits-of-deriving-from-control"></a>Vantaggi della derivazione da Control

Provare a derivare da <xref:System.Windows.Controls.Control> anziché utilizzare la <xref:System.Windows.Controls.UserControl> classe se si verifica una delle condizioni seguenti:

- Si vuole che l'aspetto del controllo sia personalizzabile tramite <xref:System.Windows.Controls.ControlTemplate>.

- Si vuole che il controllo supporti temi diversi.

### <a name="deriving-from-frameworkelement"></a>Derivazione da FrameworkElement

Controlli che derivano <xref:System.Windows.Controls.UserControl> da <xref:System.Windows.Controls.Control> o si basano sulla composizione di elementi esistenti. Per molti scenari, si tratta di una soluzione accettabile, perché qualsiasi oggetto che eredita <xref:System.Windows.FrameworkElement> da può trovarsi <xref:System.Windows.Controls.ControlTemplate>in un. A volte, tuttavia, le funzionalità di composizione semplice di elementi non sono sufficienti per definire l'aspetto di un controllo. Per questi scenari, l'assegnazione di un <xref:System.Windows.FrameworkElement> componente a è la scelta ottimale.

Sono disponibili due metodi standard per la <xref:System.Windows.FrameworkElement>compilazione di componenti basati su, ovvero il rendering diretto e la composizione di elementi personalizzati. Il rendering diretto prevede l'override <xref:System.Windows.UIElement.OnRender%2A> del metodo <xref:System.Windows.FrameworkElement> di e <xref:System.Windows.Media.DrawingContext> l'esecuzione di operazioni che definiscono in modo esplicito gli oggetti visivi dei componenti. Si tratta del metodo utilizzato da <xref:System.Windows.Controls.Image> e <xref:System.Windows.Controls.Border>. La composizione di elementi personalizzati prevede l'uso <xref:System.Windows.Media.Visual> di oggetti di tipo per comporre l'aspetto del componente. Per un esempio, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>è un esempio di un controllo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che usa la composizione di elementi personalizzata. È anche possibile combinare il rendering diretto e la composizione personalizzata di elementi nello stesso controllo.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vantaggi della derivazione da FrameworkElement

Provare a derivare da <xref:System.Windows.FrameworkElement> se si verifica una delle condizioni seguenti:

- Si vuole controllare l'aspetto del controllo in modo più preciso rispetto a quanto possibile con la composizione semplice di elementi.

- Si vuole definire l'aspetto del controllo definendo una logica di rendering personalizzata.

- Si desidera comporre gli elementi esistenti in modi nuovi, oltre a quanto possibile con <xref:System.Windows.Controls.UserControl> e. <xref:System.Windows.Controls.Control>

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

- Definire un <xref:System.Windows.DependencyProperty> identificatore denominato `ValueProperty` come `public` `static` campo. `readonly`

- Registrare il nome della proprietà con il sistema di proprietà, <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>chiamando, per specificare gli elementi seguenti:

  - Nome della proprietà.

  - Tipo della proprietà.

  - Tipo proprietario della proprietà.

  - Metadati della proprietà. I metadati contengono il valore predefinito della proprietà, <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.PropertyChangedCallback>e.

- Definire una proprietà wrapper CLR denominata `Value`, che è lo stesso nome utilizzato per registrare la proprietà di dipendenza, implementando le funzioni di accesso `get` e `set` della proprietà. Si noti che `get` le `set` funzioni di accesso e <xref:System.Windows.DependencyObject.GetValue%2A> chiamano <xref:System.Windows.DependencyObject.SetValue%2A> rispettivamente e. È consigliabile che le funzioni di accesso delle proprietà di dipendenza non contengano logica aggiuntiva perché i client e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] possono ignorare le funzioni di accesso e chiamare <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> direttamente. Ad esempio, quando una proprietà è associata a un'origine dati, la funzione di accesso `set` della proprietà non viene chiamata.  Anziché aggiungere logica aggiuntiva alle funzioni di accesso get e set, utilizzare i <xref:System.Windows.ValidateValueCallback>delegati <xref:System.Windows.PropertyChangedCallback> , <xref:System.Windows.CoerceValueCallback>e per rispondere o controllare il valore durante la modifica.  Per altre informazioni su questi callback, vedere [Callback e convalida delle proprietà di dipendenza](../advanced/dependency-property-callbacks-and-validation.md).

- Definire un metodo per l' <xref:System.Windows.CoerceValueCallback> oggetto `CoerceValue`denominato. `CoerceValue` garantisce che `Value` sia maggiore o uguale a `MinValue` e minore o uguale a `MaxValue`.

- Definire un metodo per l' <xref:System.Windows.PropertyChangedCallback>oggetto, `OnValueChanged`denominato. `OnValueChanged`Crea un <xref:System.Windows.RoutedPropertyChangedEventArgs%601> oggetto e prepara per generare l' `ValueChanged` evento indirizzato. Gli eventi indirizzati sono illustrati nella sezione successiva.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Per altre informazioni, vedere [Proprietà di dipendenza personalizzate](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Usare gli eventi indirizzati

Così come le proprietà di dipendenza estendono il concetto di proprietà CLR con funzionalità aggiuntive, gli eventi indirizzati estendono la nozione di eventi CLR standard. Quando si crea un nuovo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è anche consigliabile implementare l'evento come evento indirizzato, perché gli eventi indirizzati supportano i comportamenti seguenti:

- Gli eventi possono essere gestiti in un elemento padre di più controlli. Nel caso di un evento di bubbling, un singolo elemento padre nell'albero degli elementi può sottoscrivere l'evento. Gli autori dell'applicazione possono quindi usare un solo gestore per rispondere all'evento di più controlli. Ad esempio, se il controllo fa parte di ogni elemento in un <xref:System.Windows.Controls.ListBox> (perché è incluso in un <xref:System.Windows.DataTemplate>), lo sviluppatore dell'applicazione può definire il gestore eventi per l'evento del <xref:System.Windows.Controls.ListBox>controllo in. Il gestore eventi viene chiamato ogni volta che l'evento si verifica in uno dei controlli.

- Gli eventi indirizzati possono essere usati in <xref:System.Windows.EventSetter>un oggetto, che consente agli sviluppatori di applicazioni di specificare il gestore di un evento all'interno di uno stile.

- Gli eventi indirizzati possono essere usati in <xref:System.Windows.EventTrigger>un oggetto, che è utile per l'animazione delle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]proprietà tramite. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).

L'esempio seguente definisce un evento indirizzato mediante le operazioni seguenti:

- Definire un <xref:System.Windows.RoutedEvent> identificatore denominato `ValueChangedEvent` come `public` `static` campo. `readonly`

- Registrare l'evento indirizzato chiamando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> metodo. Nell'esempio vengono specificate le informazioni seguenti quando viene <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>chiamato:

  - Il nome dell'evento è `ValueChanged`.

  - La strategia di routing <xref:System.Windows.RoutingStrategy.Bubble>è, il che significa che un gestore eventi nell'origine (l'oggetto che genera l'evento) viene chiamato per primo, quindi i gestori eventi negli elementi padre dell'origine vengono chiamati in successione, a partire dal gestore eventi nella più vicina elemento padre.

  - Il tipo del gestore eventi è <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, costruito con un <xref:System.Decimal> tipo.

  - Il tipo proprietario dell'evento è `NumericUpDown`.

- Dichiarazione di un evento pubblico denominato `ValueChanged` e inserimento di dichiarazioni delle funzioni di accesso dell'evento. L'esempio chiama <xref:System.Windows.UIElement.AddHandler%2A> `add` nella dichiarazione della <xref:System.Windows.UIElement.RemoveHandler%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzione di accesso e nella dichiarazione della funzionediaccessoperusareiservizieventi.`remove`

- Creazione di un metodo virtuale protetto denominato `OnValueChanged` che genera l'evento `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Per altre informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md) e [Creare un evento indirizzato personalizzato](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Usare il binding

Per separare l'interfaccia utente del controllo dalla relativa logica, è possibile usare il data binding. Questa operazione è particolarmente importante se si definisce l'aspetto del controllo usando un oggetto <xref:System.Windows.Controls.ControlTemplate>. Se si usa il data binding, potrebbe non essere più necessario fare riferimento a parti specifiche dell'interfaccia utente dal codice. È consigliabile evitare di fare riferimento <xref:System.Windows.Controls.ControlTemplate> a elementi presenti in perché quando il codice fa riferimento <xref:System.Windows.Controls.ControlTemplate> a elementi presenti in e <xref:System.Windows.Controls.ControlTemplate> viene modificato, è necessario includere l'elemento a cui si fa riferimento nel nuovo <xref:System.Windows.Controls.ControlTemplate>oggetto.

Nell'esempio seguente viene aggiornato <xref:System.Windows.Controls.TextBlock> l'oggetto `NumericUpDown` del controllo, viene assegnato un nome e viene fatto riferimento alla casella di testo in base al nome nel codice.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

L'esempio seguente usa il binding per ottenere lo stesso risultato.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../data/data-binding-overview.md).

### <a name="design-for-designers"></a>Progettare le finestre di progettazione

Per ottenere supporto per i controlli WPF personalizzati in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)], ad esempio per la modifica delle proprietà con la finestra Proprietà, attenersi alle linee guida riportate di seguito.  Per ulteriori informazioni sullo sviluppo per [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], vedere Progettazione di [XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Proprietà di dipendenza

Assicurarsi di implementare CLR `get` e `set` funzioni di accesso come descritto in precedenza, in "utilizza proprietà di dipendenza". Le finestre di progettazione possono usare il wrapper per rilevare la presenza di una proprietà di dipendenza, ma, come accade per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e per i client del controllo, non è necessario chiamare le funzioni di accesso quando si ottiene o si imposta la proprietà.

#### <a name="attached-properties"></a>Proprietà associate

Per implementare le proprietà associate nei controlli personalizzati, attenersi alle linee guida seguenti:

- Avere un `public` oggetto `static` `readonly`  nel formatoPropertyName`Property` che stava creando usando il<xref:System.Windows.DependencyProperty.RegisterAttached%2A>metodo. <xref:System.Windows.DependencyProperty> Il nome della proprietà passato a deve <xref:System.Windows.DependencyProperty.RegisterAttached%2A> corrispondere a *PropertyName*.

- Implementare una coppia di metodi CLR`public` `static` denominati `Set`*NomeProprietà* e `Get`*NomeProprietà*. Entrambi i metodi devono accettare una classe derivata <xref:System.Windows.DependencyProperty> da come primo argomento. Il metodo `Set`*NomeProprietà* accetta anche un argomento il cui tipo corrisponde al tipo di dati registrato per la proprietà. Il metodo `Get`*NomeProprietà* deve restituire un valore dello stesso tipo. In assenza del metodo `Set`*NomeProprietà*, la proprietà viene contrassegnata come di sola lettura.

- `Set`*PropertyName* e `Get` *PropertyName* devono essere indirizzati direttamente <xref:System.Windows.DependencyObject.GetValue%2A> ai <xref:System.Windows.DependencyObject.SetValue%2A> metodi e sull'oggetto dipendenza di destinazione, rispettivamente. Le finestre di progettazione possono accedere alla proprietà associata eseguendo una chiamata tramite il wrapper del metodo oppure una chiamata diretta all'oggetto dipendenza di destinazione.

Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definire e usare risorse condivise

È possibile includere il controllo nello stesso assembly dell'applicazione oppure inserirlo in un pacchetto in un assembly separato che può essere usato in più applicazioni. Nella maggior parte dei casi, le informazioni di questo argomento si applicano indipendentemente dal metodo usato.  È importante tuttavia notare una differenza.  Quando si inserisce un controllo nello stesso assembly di un'applicazione, è possibile aggiungere risorse globali al file App.xaml. Tuttavia, a un assembly che contiene solo controlli non è <xref:System.Windows.Application> associato un oggetto, pertanto non è disponibile un file app. XAML.

Quando un'applicazione cerca una risorsa, la ricerca viene effettuata a tre livelli nell'ordine seguente:

1. Livello dell'elemento.

   Il sistema inizia dall'elemento che fa riferimento alla risorsa, quindi esegue la ricerca delle risorse dell'elemento padre logico continuando fino a raggiungere l'elemento radice.

2. Livello dell'applicazione.

   Risorse definite dall' <xref:System.Windows.Application> oggetto.

3. Livello del tema.

   I dizionari a livello di tema vengono archiviati in una sottocartella denominata Themes.  I file nella cartella Themes corrispondono ai temi.  Potrebbero ad esempio essere presenti Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml e così via.  Può esserci anche un file denominato generic.xaml.  Quando il sistema cerca una risorsa a livello di tema, la ricerca viene effettuata prima nel file specifico del tema e poi nel file generic.xaml.

Quando il controllo si trova in un assembly separato dall'applicazione, è necessario inserire le risorse globali a livello di elemento o a livello di tema. Entrambi i metodi offrono alcuni vantaggi.

#### <a name="defining-resources-at-the-element-level"></a>Definizione delle risorse a livello di elemento

È possibile definire le risorse condivise a livello di elemento creando un dizionario risorse personalizzato e unendolo al dizionario risorse del controllo.  Quando si usa questo metodo, è possibile assegnare un nome qualsiasi al file di risorse, che può trovarsi nella stessa cartella dei controlli. Le risorse a livello di elemento possono anche usare semplici stringhe come chiavi. Nell'esempio seguente viene creato <xref:System.Windows.Media.LinearGradientBrush> un file di risorse denominato Dictionary1. XAML.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Una volta definito il dizionario, è necessario unirlo al dizionario risorse del controllo.  A tale scopo, è possibile usare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o il codice.

L'esempio seguente unisce un dizionario risorse usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Lo svantaggio di questo approccio consiste nel fatto che <xref:System.Windows.ResourceDictionary> un oggetto viene creato ogni volta che vi si fa riferimento.  Se, ad esempio, nella libreria sono presenti 10 controlli personalizzati e si uniscono i dizionari risorse condivise per ogni controllo usando XAML, si creeranno 10 <xref:System.Windows.ResourceDictionary> oggetti identici.  È possibile evitare questo problema creando una classe statica che unisce le risorse nel codice e restituisce l'oggetto risultante <xref:System.Windows.ResourceDictionary>.

Nell'esempio seguente viene creata una classe che restituisce un <xref:System.Windows.ResourceDictionary>oggetto condiviso.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

L'esempio seguente unisce la risorsa condivisa con le risorse di un controllo personalizzato nel costruttore del controllo prima di chiamare `InitializeComponent`.  Poiché è una proprietà statica <xref:System.Windows.ResourceDictionary> , viene creato una sola volta. `SharedDictionaryManager.SharedDictionary` Poiché il dizionario risorse è stato unito prima di chiamare `InitializeComponent`, le risorse sono disponibili per il controllo nel relativo file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definizione delle risorse a livello di tema

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di creare risorse per diversi temi di Windows.  L'autore di un controllo può definire una risorsa per un tema specifico in modo da modificare l'aspetto del controllo a seconda del tema in uso. Ad esempio, l'aspetto di un <xref:System.Windows.Controls.Button> oggetto nel tema di Windows classico (il tema predefinito per Windows 2000) è diverso da <xref:System.Windows.Controls.Button> un nel tema Windows Luna (il tema predefinito per <xref:System.Windows.Controls.Button> Windows XP) perché usa un diverso <xref:System.Windows.Controls.ControlTemplate> per ogni tema.

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

Quando si inserisce un <xref:System.Windows.Controls.ControlTemplate> oggetto in uno qualsiasi dei file del dizionario risorse specifici del tema, è necessario creare un costruttore statico per il controllo e <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> chiamare il metodo <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>su, come illustrato nell'esempio seguente.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definizione delle chiavi e relativo riferimento per le risorse del tema

Quando si definisce una risorsa a livello di elemento, è possibile assegnare una stringa come chiave e accedere alla risorsa tramite la stringa. Quando si definisce una risorsa a livello di tema, è necessario usare <xref:System.Windows.ComponentResourceKey> come chiave.  L'esempio seguente definisce una risorsa in generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Nell'esempio seguente viene fatto riferimento alla risorsa specificando <xref:System.Windows.ComponentResourceKey> come chiave.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Indicazione del percorso delle risorse del tema

Per trovare le risorse per un controllo, l'applicazione host deve sapere che l'assembly contiene risorse specifiche del controllo. È possibile eseguire questa operazione aggiungendo l' <xref:System.Windows.ThemeInfoAttribute> oggetto all'assembly che contiene il controllo. Dispone di una <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> proprietà che specifica il percorso delle risorse generiche e una <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> proprietà che specifica il percorso delle risorse specifiche del tema. <xref:System.Windows.ThemeInfoAttribute>

Nell'esempio seguente le <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> proprietà e <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> vengono impostate su per <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>specificare che le risorse generiche e specifiche del tema si trovano nello stesso assembly del controllo.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Vedere anche

- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md)
- [Personalizzazione dei controlli](control-customization.md)
