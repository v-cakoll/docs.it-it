---
title: Proprietà di dipendenza personalizzate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
ms.openlocfilehash: e4117d7add2a34d6d989d9222e7688361cf6b379
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646359"
---
# <a name="custom-dependency-properties"></a>Proprietà di dipendenza personalizzate

Questo argomento descrive le ragioni per cui sviluppatori di applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e autori di componenti potrebbero decidere di creare una proprietà di dipendenza personalizzata e illustra i passaggi dell'implementazione oltre ad alcune opzioni di implementazione in grado di migliorare le prestazioni, l'usabilità o la versatilità della proprietà.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Prerequisiti

In questo argomento si presuppongono la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer di proprietà di dipendenza esistenti nelle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>Che cos'è una proprietà di dipendenza?

È possibile abilitare quella che altrimenti sarebbe una proprietà CLR (Common Language Runtime) per supportare l'applicazione di stili, l'associazione dati, l'ereditarietà, le animazioni e i valori predefiniti implementandola come proprietà di dipendenza. Le proprietà di dipendenza sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà registrate <xref:System.Windows.DependencyProperty.Register%2A> con il <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>sistema di proprietà <xref:System.Windows.DependencyProperty> chiamando il metodo (o ) e supportate da un campo dell'identificatore. Le proprietà di dipendenza <xref:System.Windows.DependencyObject> possono essere <xref:System.Windows.DependencyObject> usate solo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dai tipi, ma sono piuttosto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elevate nella gerarchia delle classi, pertanto la maggior parte delle classi disponibili in può supportare le proprietà di dipendenza. Per ulteriori informazioni sulle proprietà di dipendenza e su alcuni termini e convenzioni usati per descriverle in questo SDK, vedere [Cenni](dependency-properties-overview.md)preliminari sulle proprietà di dipendenza .

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Esempio di proprietà di dipendenza

Esempi di proprietà di dipendenza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementate <xref:System.Windows.Controls.Control.Background%2A> nelle <xref:System.Windows.FrameworkElement.Width%2A> classi includono, <xref:System.Windows.Controls.TextBox.Text%2A> tra gli altri, la proprietà, la proprietà e la proprietà. Ogni proprietà di dipendenza esposta da una classe <xref:System.Windows.DependencyProperty> dispone di un campo statico pubblico corrispondente di tipo esposto nella stessa classe. Si tratta dell'identificatore per la proprietà di dipendenza. L'identificatore viene denominato mediante la seguente convenzione: nome della proprietà di dipendenza seguito dalla stringa `Property`. Ad esempio, <xref:System.Windows.DependencyProperty> il campo <xref:System.Windows.Controls.Control.Background%2A> dell'identificatore corrispondente per la proprietà è <xref:System.Windows.Controls.Control.BackgroundProperty>. L'identificatore archivia le informazioni sulla proprietà di dipendenza come è stata registrata e l'identificatore <xref:System.Windows.DependencyObject.SetValue%2A>viene quindi utilizzato in un secondo momento per altre operazioni che coinvolgono la proprietà di dipendenza, ad esempio la chiamata .

Come indicato in [Dependency Properties Overview](dependency-properties-overview.md), [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tutte le proprietà di dipendenza in (ad eccezione della maggior parte delle proprietà associate) sono anche proprietà CLR a causa dell'implementazione "wrapper". Pertanto, dal codice, è possibile ottenere o impostare le proprietà di dipendenza chiamando le funzioni di accesso CLR che definiscono i wrapper nello stesso modo in cui si utilizzerebbero altre proprietà CLR. Come consumer di proprietà di dipendenza stabilite, <xref:System.Windows.DependencyObject> <xref:System.Windows.DependencyObject.GetValue%2A> in <xref:System.Windows.DependencyObject.SetValue%2A>genere non si utilizzano i metodi e , che sono il punto di connessione al sistema di proprietà sottostante. Piuttosto, l'implementazione esistente delle proprietà <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> CLR `get` avrà già chiamato e all'interno delle implementazioni del wrapper e `set` della proprietà, utilizzando il campo identificatore in modo appropriato. Se l'implementazione di una proprietà di dipendenza personalizzata viene eseguita in modo autonomo, il wrapper verrà definito in modo simile.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>Quando implementare una proprietà di dipendenza

Quando si implementa una proprietà in una classe, <xref:System.Windows.DependencyObject>purché la classe derivi <xref:System.Windows.DependencyProperty> da , è possibile eseguire il backup della proprietà con un identificatore e quindi renderla una proprietà di dipendenza. Trasformare una proprietà in una proprietà di dipendenza non sempre è necessario o appropriato e dipende dalle esigenze dello scenario. Talvolta è opportuno usare la tecnica normale che consiste nel supportare la proprietà con un campo privato. Tuttavia, se si vuole che la proprietà supporti una o più delle seguenti funzionalità [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario implementarla come proprietà di dipendenza:

- Si vuole che la proprietà possa essere impostata in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

- Si vuole che la proprietà supporti il data binding. Per altre informazioni sulle proprietà di dipendenza di data binding, vedere [Eseguire l'associazione delle proprietà di due controlli](../data/how-to-bind-the-properties-of-two-controls.md).

- Si vuole che la proprietà possa essere impostata con un riferimento di risorsa dinamica. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

- Si vuole ereditare un valore di proprietà automaticamente da un elemento padre nell'albero degli elementi. In questo caso, <xref:System.Windows.DependencyProperty.RegisterAttached%2A> eseguire la registrazione con il metodo , anche se si crea anche un wrapper di proprietà per l'accesso CLR. Per altre informazioni, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

- Si vuole che la proprietà sia animata. Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](../graphics-multimedia/animation-overview.md)

- Si vuole che il sistema di proprietà segnali quando il valore precedente della proprietà è stato modificato da azioni intraprese dal sistema di proprietà, dall'ambiente o dall'utente oppure tramite la lettura e l'uso degli stili. Se si usano i metadati della proprietà, la proprietà può specificare un metodo di callback che verrà richiamato ogni volta il sistema di proprietà determina che il valore della proprietà è stato modificato definitivamente. Un concetto correlato è la coercizione del valore di proprietà. Per altre informazioni, vedere [Callback e convalida delle proprietà di dipendenza](dependency-property-callbacks-and-validation.md).

- Si vogliono usare convenzioni di metadati definite usate anche dai processi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ad esempio la segnalazione dell'eventualità che la modifica di un valore di proprietà richieda che il sistema di layout ricomponga gli elementi visivi di un elemento. Oppure si vogliono usare override di metadati in modo che le classi derivate possano modificare caratteristiche basate sui metadati quali il valore predefinito.

- Si desidera che le proprietà di un controllo personalizzato ricevano il supporto di Progettazione WPF di Visual Studio, ad esempio la modifica della finestra **Proprietà.You** want properties of a custom control to receive Visual Studio WPF Designer support, such as Properties window editing. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).

Quando si esaminano questi scenari, è necessario considerare anche se è possibile realizzare lo scenario eseguendo l'override dei metadati di una proprietà di dipendenza esistente, piuttosto che implementando una proprietà completamente nuova. La praticità di un override di metadati dipende dallo scenario e dalla somiglianza di tale scenario con l'implementazione nelle proprietà di dipendenza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti e nelle classi. Per altre informazioni sull'override dei metadati nelle proprietà esistenti, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Elenco di controllo per la definizione di una proprietà di dipendenza

La definizione di una proprietà di dipendenza include quattro concetti distinti. Questi concetti non rappresentano necessariamente passaggi rigidi di una procedura, in quanto alcuni di questi finiscono per essere combinati come singole righe di codice nell'implementazione:

- (Facoltativo) Creare metadati di proprietà per la proprietà di dipendenza.

- Registrare il nome della proprietà con il sistema di proprietà, specificando un tipo di proprietario e il tipo del valore di proprietà. Se usati, specificare anche i metadati della proprietà.

- Definire <xref:System.Windows.DependencyProperty> un identificatore come `public` `static` `readonly` campo nel tipo di proprietario.

- Definire una proprietà "wrapper" CLR il cui nome corrisponde al nome della proprietà di dipendenza. Implementare la proprietà "wrapper" CLR `get` e `set` le funzioni di accesso per connettersi con la proprietà di dipendenza che la supporta.

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registrazione della proprietà nel sistema di proprietà

Affinché la proprietà sia una proprietà di dipendenza, è necessario registrarla in una tabella gestita dal sistema di proprietà e assegnarle un identificatore univoco usato come qualificatore per le successive operazioni del sistema di proprietà. Queste operazioni possono essere operazioni interne o le API del sistema di proprietà che chiamano il codice. Per registrare la proprietà, chiamare il <xref:System.Windows.DependencyProperty.Register%2A> metodo all'interno del corpo della classe (all'interno della classe, ma all'esterno di qualsiasi definizione di membro). Il campo dell'identificatore <xref:System.Windows.DependencyProperty.Register%2A> viene fornito anche dalla chiamata al metodo, come valore restituito. Il motivo <xref:System.Windows.DependencyProperty.Register%2A> per cui la chiamata viene eseguita all'esterno di `public` `static` `readonly` altre definizioni di membro è perché si utilizza questo valore restituito per assegnare e creare un campo di tipo <xref:System.Windows.DependencyProperty> come parte della classe. Questo campo diventa l'identificatore per la proprietà di dipendenza.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Convenzioni di denominazione delle proprietà di dipendenza

Esistono convenzioni di denominazione definite relative alle proprietà di dipendenza che è necessario seguire in tutte le circostanze tranne in casi eccezionali.

La proprietà di dipendenza stessa avrà un nome di base, "AquariumGraphic", <xref:System.Windows.DependencyProperty.Register%2A>come in questo esempio, che viene fornito come primo parametro di . Tale nome deve essere univoco all'interno di ogni tipo di registrazione. Le proprietà di dipendenza ereditate tramite tipi di base sono considerate già parte del tipo di registrazione. I nomi delle proprietà ereditate non possono essere registrati nuovamente. Tuttavia, esiste una tecnica per aggiungere una classe come proprietario di una proprietà di dipendenza persino quando quella proprietà di dipendenza non è ereditata. Per informazioni dettagliate, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).

Quando si crea il campo dell'identificatore, denominare questo campo con il nome della proprietà registrata, più il suffisso `Property`. Questo campo è l'identificatore per la proprietà di dipendenza e <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyObject.GetValue%2A> verrà utilizzato in un secondo momento come input per le chiamate e effettuate nei wrapper, da qualsiasi altro accesso [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di codice alla proprietà tramite il proprio codice, da qualsiasi accesso al codice esterno consentito, dal sistema di proprietà e potenzialmente dai processori.

> [!NOTE]
> La definizione della proprietà di dipendenza nel corpo della classe costituisce l'implementazione tipica, ma è anche possibile definire una proprietà di dipendenza nel costruttore statico della classe. Questo approccio potrebbe essere utile nel caso in cui siano necessarie più righe di codice per inizializzare la proprietà di dipendenza.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementazione del "wrapper"

L'implementazione <xref:System.Windows.DependencyObject.GetValue%2A> del `get` wrapper deve <xref:System.Windows.DependencyObject.SetValue%2A> chiamare `set` nell'implementazione e nell'implementazione (la chiamata di registrazione originale e il campo sono illustrati anche qui per chiarezza).

In tutte le circostanze tranne in casi <xref:System.Windows.DependencyObject.GetValue%2A> eccezionali, le implementazioni del wrapper devono eseguire solo le azioni e . <xref:System.Windows.DependencyObject.SetValue%2A> La ragione è discussa nell'argomento [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).

Tutte le proprietà di dipendenza pubbliche esistenti fornite nelle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usano questo semplice modello di implementazione del wrapper. La maggior parte della complessità della modalità di funzionamento delle proprietà di dipendenza è dovuta a un comportamento intrinseco del sistema di proprietà oppure è implementata tramite altri concetti quali la coercizione o i callback di modifica della proprietà mediante i metadati della proprietà.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

Anche in questo caso, per convenzione, il nome della proprietà wrapper deve <xref:System.Windows.DependencyProperty.Register%2A> essere uguale al nome scelto e fornito come primo parametro della chiamata che ha registrato la proprietà. Se la proprietà non segue la convenzione, non necessariamente vengono disabilitati tutti i possibili usi, ma si riscontreranno vari problemi rilevanti:

- Determinati aspetti di stili e modelli non funzioneranno.

- La maggior parte degli strumenti e delle finestre di progettazione devono basarsi sulle convenzioni di denominazione per serializzare correttamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o per fornire assistenza relativamente all'ambiente della finestra di progettazione a livello di singola proprietà.

- L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] corrente del caricatore ignora completamente i wrapper e si basa sulla convenzione di denominazione durante l'elaborazione dei valori degli attributi. Per altre informazioni, vedere [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Metadati della proprietà per una nuova proprietà di dipendenza

Quando si registra una proprietà di dipendenza, la registrazione tramite il sistema di proprietà crea un oggetto dei metadati che archivia le caratteristiche della proprietà. Molte di queste caratteristiche hanno valori predefiniti che vengono impostati <xref:System.Windows.DependencyProperty.Register%2A>se la proprietà è registrata con le semplici firme di . Altre firme di consentono di <xref:System.Windows.DependencyProperty.Register%2A> specificare i metadati desiderati durante la registrazione della proprietà. I metadati più comuni per le proprietà di dipendenza consistono nel fornire a tali proprietà un valore predefinito che viene applicato alle nuove istanze che usano la proprietà.

Se si crea una proprietà di dipendenza esistente <xref:System.Windows.FrameworkElement>in una classe derivata <xref:System.Windows.FrameworkPropertyMetadata> di , <xref:System.Windows.PropertyMetadata> è possibile utilizzare la classe di metadati più specializzata anziché la classe base. Il costruttore <xref:System.Windows.FrameworkPropertyMetadata> per la classe dispone di diverse firme in cui è possibile specificare varie caratteristiche dei metadati in combinazione. Se si desidera specificare solo il valore predefinito, utilizzare <xref:System.Object>la firma che accetta un singolo parametro di tipo . Passare tale parametro dell'oggetto come valore predefinito specifico del tipo per la `propertyType` proprietà (il valore predefinito fornito deve essere il tipo fornito come parametro nella <xref:System.Windows.DependencyProperty.Register%2A> chiamata).

Per <xref:System.Windows.FrameworkPropertyMetadata>, è anche possibile specificare i flag di opzione dei metadati per la proprietà. Questi flag vengono convertiti in proprietà discrete nei metadati della proprietà dopo la registrazione e usati per comunicare determinate istruzioni condizionali agli altri processi quali il motore di layout.

#### <a name="setting-appropriate-metadata-flags"></a>Impostazione dei flag di metadati appropriati

- Se la proprietà (o le modifiche [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]del relativo valore) influisce sul valore di , e in particolare influisce sul <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>modo <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>in cui il sistema di layout deve ridimensionare o eseguire il rendering dell'elemento in una pagina, impostare uno o più dei seguenti flag: , , .

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>indica che una modifica a questa [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proprietà richiede una modifica al rendering in cui l'oggetto contenitore potrebbe richiedere più o meno spazio all'interno dell'oggetto padre. Ad esempio, è necessario impostare questo flag per una proprietà "Width".

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>indica che una modifica a questa [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proprietà richiede una modifica al rendering che in genere non richiede una modifica nello spazio dedicato, ma indica che il posizionamento all'interno dello spazio è cambiato. Ad esempio, è necessario impostare questo flag per una proprietà "Alignment".

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>indica che si è verificata un'altra modifica che non influirà sul layout e sulla misura, ma richiede un altro rendering. Un esempio potrebbe essere una proprietà che modifica un colore di un elemento esistente, ad esempio "Background".

  - Questi flag vengono spesso usati come protocollo nei metadati per le implementazioni di override del sistema di proprietà o per i callback del layout. Ad esempio, si <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> potrebbe avere <xref:System.Windows.UIElement.InvalidateArrange%2A> un callback che chiamerà se qualsiasi <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> `true` proprietà dell'istanza segnala una modifica del valore e ha come nei relativi metadati.

- Alcune proprietà possono influire sulle caratteristiche di rendering dell'elemento padre contenitore, in modo maggiore rispetto alle modifiche nelle dimensioni necessarie indicate in precedenza. Un esempio <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> è la proprietà utilizzata nel modello di documento dinamico, in cui le modifiche apportate a tale proprietà possono modificare il rendering complessivo del documento dinamico che contiene il paragrafo. Utilizzare <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> o identificare casi simili nelle proprie proprietà.

- Per impostazione predefinita, le proprietà di dipendenza supportano il data binding. È possibile disabilitare intenzionalmente il data binding per i casi in cui non esiste uno scenario realistico per il data binding o nei quali le prestazioni del data binding per un oggetto di grandi dimensioni viene considerata un problema.

- Per impostazione <xref:System.Windows.Data.Binding.Mode%2A> predefinita, l'associazione <xref:System.Windows.Data.BindingMode.OneWay>dati per le proprietà di dipendenza ha per impostazione predefinita . È sempre possibile modificare <xref:System.Windows.Data.BindingMode.TwoWay> l'associazione in modo che sia per ogni istanza di associazione. Per informazioni dettagliate, vedere [Specificare la direzione dell'associazione](../data/how-to-specify-the-direction-of-the-binding.md). Ma come autore della proprietà di dipendenza, è <xref:System.Windows.Data.BindingMode.TwoWay> possibile scegliere di rendere la proprietà utilizzare la modalità di associazione per impostazione predefinita. Un esempio di una proprietà <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>di dipendenza esistente è ; lo scenario per questa <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> proprietà è che la <xref:System.Windows.Controls.MenuItem> logica di impostazione e la composizione di interagire con lo stile di tema predefinito. La <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> logica della proprietà utilizza l'associazione dati in modo nativo per mantenere lo stato della proprietà in base ad altre proprietà di stato e chiamate al metodo. Un'altra proprietà <xref:System.Windows.Data.BindingMode.TwoWay> di esempio <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>che esegue l'associazione per impostazione predefinita è .

- È anche possibile abilitare l'ereditarietà <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> della proprietà in una proprietà di dipendenza personalizzata impostando il flag. L'ereditarietà della proprietà è utile per uno scenario in cui gli elementi padre e gli elementi figlio hanno una proprietà in comune e avrebbe senso per gli elementi figlio avere quel particolare valore di proprietà impostato sullo stesso valore impostato dall'elemento padre. Un esempio di <xref:System.Windows.FrameworkElement.DataContext%2A>proprietà ereditabile è , utilizzata per le operazioni di associazione per abilitare l'importante scenario master-dettagli per la presentazione dei dati. Rendendo <xref:System.Windows.FrameworkElement.DataContext%2A> ereditabili anche tutti gli elementi figlio ereditano tale contesto dati. A causa dell'ereditarietà del valore della proprietà, è possibile specificare un contesto dati alla radice della pagina o dell'applicazione e non è necessario specificarlo di nuovo per i binding in tutti i possibili elementi figlio. <xref:System.Windows.FrameworkElement.DataContext%2A>è anche un buon esempio per illustrare che l'ereditarietà esegue l'override del valore predefinito, ma può sempre essere impostata localmente su qualsiasi elemento figlio specifico. Per informazioni dettagliate, consultate [Utilizzare il modello Master-Details con dati gerarchici.](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) L'ereditarietà del valore della proprietà può incidere negativamente sulle prestazioni e pertanto deve essere usata sporadicamente. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

- Impostare <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> il flag per indicare se la proprietà di dipendenza deve essere rilevata o utilizzata dai servizi di inserimento nel journal di navigazione. Un esempio <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> è la proprietà ; qualsiasi elemento selezionato in un controllo di selezione deve essere mantenuto quando si esplora la cronologia di inserimento nel journal.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura

È possibile definire una proprietà di dipendenza di sola lettura. Tuttavia, gli scenari in base ai quali è possibile definire la proprietà come proprietà di sola lettura sono piuttosto diversi, allo stesso modo della procedura per registrare queste proprietà con il sistema di proprietà e di quella per esporre l'identificatore. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Proprietà di dipendenza di tipo raccolta

Le proprietà di dipendenza di tipo di raccolta presentano alcuni problemi di implementazione aggiuntivi che è opportuno considerare. Per altri dettagli, vedere [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Considerazioni sulla sicurezza delle proprietà di dipendenza

Le proprietà di dipendenza devono essere dichiarate come proprietà pubbliche. I campi dell'identificatore delle proprietà di dipendenza devono essere dichiarati come campi statici pubblici. Anche se si tenta di dichiarare altri livelli di accesso, ad esempio protected, è sempre possibile accedere a una proprietà di dipendenza tramite l'identificatore in combinazione con le API del sistema di proprietà. Anche un campo dell'identificatore protetto è potenzialmente accessibile a causa della creazione <xref:System.Windows.LocalValueEnumerator>di report sui metadati o delle API di determinazione del valore che fanno parte del sistema di proprietà, ad esempio . Per altre informazioni, vedere [Sicurezza delle proprietà di dipendenza](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Proprietà di dipendenza e costruttori di classi

Esiste un principio generale nella programmazione del codice gestito (spesso applicato mediante strumenti di analisi del codice quale FxCop) in base al quale i costruttori di classi non devono chiamare metodi virtuali. Il motivo sta nel fatto che i costruttori possono essere chiamati come inizializzazione di base di un costruttore di classe derivato, pertanto l'uso del metodo virtuale tramite il costruttore potrebbe avvenire a uno stato incompleto dell'inizializzazione dell'istanza di oggetto in corso di creazione. Quando si deriva da qualsiasi classe <xref:System.Windows.DependencyObject>che deriva già da , è necessario tenere presente che il sistema di proprietà stesso chiama ed espone internamente i metodi virtuali. Tali metodi virtuali sono parte dei servizi del sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'esecuzione dell'override dei metodi consente alle classi derivate di partecipare alla determinazione del valore. Per evitare eventuali problemi con l'inizializzazione del runtime, è consigliabile evitare di impostare valori della proprietà di dipendenza all'interno dei costruttori di classi, a meno che non si segua un modello del costruttore molto specifico. Per altri dettagli, vedere [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Panoramica della creazione di controlli](../controls/control-authoring-overview.md)
- [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md)
- [Sicurezza delle proprietà di dipendenza](dependency-property-security.md)
- [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md)
- [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
