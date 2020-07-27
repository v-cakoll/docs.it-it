---
title: Proprietà di dipendenza personalizzate
description: Informazioni sui passaggi per implementare una proprietà in Windows Presentation Foundation e sulle opzioni per migliorare le prestazioni, l'usabilità o la versatilità della proprietà.
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
ms.openlocfilehash: b082340afb8b1a814fc5923126aa58183d43bc01
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168146"
---
# <a name="custom-dependency-properties"></a>Proprietà di dipendenza personalizzate

Questo argomento descrive le ragioni per cui sviluppatori di applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e autori di componenti potrebbero decidere di creare una proprietà di dipendenza personalizzata e illustra i passaggi dell'implementazione oltre ad alcune opzioni di implementazione in grado di migliorare le prestazioni, l'usabilità o la versatilità della proprietà.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Prerequisiti

In questo argomento si presuppongono la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer di proprietà di dipendenza esistenti nelle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>Che cos'è una proprietà di dipendenza?

È possibile abilitare ciò che altrimenti sarebbe una proprietà Common Language Runtime (CLR) per supportare lo stile, la data binding, l'ereditarietà, le animazioni e i valori predefiniti implementando tale proprietà come proprietà di dipendenza. Le proprietà di dipendenza sono proprietà registrate con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà chiamando il <xref:System.Windows.DependencyProperty.Register%2A> Metodo (o <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> ) e supportate da un <xref:System.Windows.DependencyProperty> campo dell'identificatore. Le proprietà di dipendenza possono essere utilizzate solo dai <xref:System.Windows.DependencyObject> tipi, ma <xref:System.Windows.DependencyObject> sono piuttosto elevate nella [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gerarchia di classi, quindi la maggior parte delle classi disponibili in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può supportare le proprietà di dipendenza. Per altre informazioni sulle proprietà di dipendenza e alcune delle terminologie e delle convenzioni usate per descriverle in questo SDK, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Esempio di proprietà di dipendenza

Tra molti altri esempi di proprietà di dipendenza implementate nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classi sono incluse la <xref:System.Windows.Controls.Control.Background%2A> proprietà, la proprietà <xref:System.Windows.FrameworkElement.Width%2A> e la <xref:System.Windows.Controls.TextBox.Text%2A> Proprietà. Ogni proprietà di dipendenza esposta da una classe dispone di un campo statico pubblico corrispondente di tipo <xref:System.Windows.DependencyProperty> esposto nella stessa classe. Si tratta dell'identificatore per la proprietà di dipendenza. L'identificatore viene denominato mediante la seguente convenzione: nome della proprietà di dipendenza seguito dalla stringa `Property`. Ad esempio, il <xref:System.Windows.DependencyProperty> campo identificatore corrispondente per la <xref:System.Windows.Controls.Control.Background%2A> proprietà è <xref:System.Windows.Controls.Control.BackgroundProperty> . L'identificatore archivia le informazioni sulla proprietà di dipendenza mentre è stata registrata e l'identificatore viene quindi usato in un secondo momento per altre operazioni che coinvolgono la proprietà di dipendenza, ad esempio la chiamata a <xref:System.Windows.DependencyObject.SetValue%2A> .

Come indicato nella [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md), tutte le proprietà di dipendenza in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (eccetto la maggior parte delle proprietà associate) sono anche proprietà CLR a causa dell'implementazione "wrapper". Pertanto, dal codice, è possibile ottenere o impostare le proprietà di dipendenza chiamando funzioni di accesso CLR che definiscono i wrapper nello stesso modo in cui si utilizzeranno altre proprietà CLR. In qualità di consumer di proprietà di dipendenza stabilite, in genere non si utilizzano i <xref:System.Windows.DependencyObject> metodi <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> , che rappresentano il punto di connessione al sistema di proprietà sottostante. Piuttosto, l'implementazione esistente delle proprietà CLR avrà già chiamato <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> all'interno delle `get` `set` implementazioni del wrapper e della proprietà, usando il campo dell'identificatore in modo appropriato. Se l'implementazione di una proprietà di dipendenza personalizzata viene eseguita in modo autonomo, il wrapper verrà definito in modo simile.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>Quando implementare una proprietà di dipendenza

Quando si implementa una proprietà in una classe, purché la classe derivi da <xref:System.Windows.DependencyObject> , è possibile eseguire il backup della proprietà con un <xref:System.Windows.DependencyProperty> identificatore e quindi impostarla come proprietà di dipendenza. Trasformare una proprietà in una proprietà di dipendenza non sempre è necessario o appropriato e dipende dalle esigenze dello scenario. Talvolta è opportuno usare la tecnica normale che consiste nel supportare la proprietà con un campo privato. Tuttavia, se si vuole che la proprietà supporti una o più delle seguenti funzionalità [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario implementarla come proprietà di dipendenza:

- Si vuole che la proprietà possa essere impostata in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

- Si vuole che la proprietà supporti il data binding. Per altre informazioni sulle proprietà di dipendenza di data binding, vedere [Eseguire l'associazione delle proprietà di due controlli](../data/how-to-bind-the-properties-of-two-controls.md).

- Si vuole che la proprietà possa essere impostata con un riferimento di risorsa dinamica. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

- Si vuole ereditare un valore di proprietà automaticamente da un elemento padre nell'albero degli elementi. In questo caso, eseguire la registrazione con il <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metodo, anche se si crea anche un wrapper di proprietà per l'accesso a CLR. Per altre informazioni, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

- Si vuole che la proprietà sia animata. Per altre informazioni, vedere [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).

- Si vuole che il sistema di proprietà segnali quando il valore precedente della proprietà è stato modificato da azioni intraprese dal sistema di proprietà, dall'ambiente o dall'utente oppure tramite la lettura e l'uso degli stili. Se si usano i metadati della proprietà, la proprietà può specificare un metodo di callback che verrà richiamato ogni volta il sistema di proprietà determina che il valore della proprietà è stato modificato definitivamente. Un concetto correlato è la coercizione del valore di proprietà. Per altre informazioni, vedere [Callback e convalida delle proprietà di dipendenza](dependency-property-callbacks-and-validation.md).

- Si vogliono usare convenzioni di metadati definite usate anche dai processi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ad esempio la segnalazione dell'eventualità che la modifica di un valore di proprietà richieda che il sistema di layout ricomponga gli elementi visivi di un elemento. Oppure si vogliono usare override di metadati in modo che le classi derivate possano modificare caratteristiche basate sui metadati quali il valore predefinito.

- Si desidera che le proprietà di un controllo personalizzato ricevano il supporto di progettazione WPF di Visual Studio, ad esempio la modifica della finestra **Proprietà** . Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).

Quando si esaminano questi scenari, è necessario considerare anche se è possibile realizzare lo scenario eseguendo l'override dei metadati di una proprietà di dipendenza esistente, piuttosto che implementando una proprietà completamente nuova. La praticità di un override di metadati dipende dallo scenario e dalla somiglianza di tale scenario con l'implementazione nelle proprietà di dipendenza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti e nelle classi. Per altre informazioni sull'override dei metadati nelle proprietà esistenti, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Elenco di controllo per la definizione di una proprietà di dipendenza

La definizione di una proprietà di dipendenza include quattro concetti distinti. Questi concetti non rappresentano necessariamente passaggi rigidi di una procedura, in quanto alcuni di questi finiscono per essere combinati come singole righe di codice nell'implementazione:

- (Facoltativo) Creare metadati di proprietà per la proprietà di dipendenza.

- Registrare il nome della proprietà con il sistema di proprietà, specificando un tipo di proprietario e il tipo del valore di proprietà. Se usati, specificare anche i metadati della proprietà.

- Definire un <xref:System.Windows.DependencyProperty> identificatore come `public` `static` `readonly` campo nel tipo di proprietario.

- Definire una proprietà "wrapper" CLR il cui nome corrisponda al nome della proprietà di dipendenza. Implementare le funzioni di accesso e della proprietà "wrapper" CLR `get` `set` per connettersi alla proprietà di dipendenza che la esegue.

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registrazione della proprietà nel sistema di proprietà

Affinché la proprietà sia una proprietà di dipendenza, è necessario registrarla in una tabella gestita dal sistema di proprietà e assegnarle un identificatore univoco usato come qualificatore per le successive operazioni del sistema di proprietà. Queste operazioni possono essere operazioni interne o il codice che chiama le API del sistema di proprietà. Per registrare la proprietà, è necessario chiamare il <xref:System.Windows.DependencyProperty.Register%2A> metodo all'interno del corpo della classe (all'interno della classe, ma all'esterno di qualsiasi definizione di membro). Il campo identificatore viene anche fornito dalla <xref:System.Windows.DependencyProperty.Register%2A> chiamata al metodo come valore restituito. Il motivo per cui la <xref:System.Windows.DependencyProperty.Register%2A> chiamata viene eseguita al di fuori delle altre definizioni dei membri è perché si usa questo valore restituito per assegnare e creare un `public` `static` `readonly` campo di tipo <xref:System.Windows.DependencyProperty> come parte della classe. Questo campo diventa l'identificatore per la proprietà di dipendenza.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Convenzioni di denominazione delle proprietà di dipendenza

Esistono convenzioni di denominazione definite relative alle proprietà di dipendenza che è necessario seguire in tutte le circostanze tranne in casi eccezionali.

La proprietà di dipendenza stessa avrà un nome di base, "AquariumGraphic", come in questo esempio, fornito come primo parametro di <xref:System.Windows.DependencyProperty.Register%2A> . Tale nome deve essere univoco all'interno di ogni tipo di registrazione. Le proprietà di dipendenza ereditate tramite tipi di base sono considerate già parte del tipo di registrazione. I nomi delle proprietà ereditate non possono essere registrati nuovamente. Tuttavia, esiste una tecnica per aggiungere una classe come proprietario di una proprietà di dipendenza persino quando quella proprietà di dipendenza non è ereditata. Per informazioni dettagliate, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).

Quando si crea il campo dell'identificatore, denominare questo campo con il nome della proprietà registrata, più il suffisso `Property`. Questo campo è l'identificatore della proprietà di dipendenza e verrà usato in un secondo momento come input per le <xref:System.Windows.DependencyObject.SetValue%2A> chiamate e <xref:System.Windows.DependencyObject.GetValue%2A> che verranno effettuate nei wrapper, da qualsiasi altro codice che accede alla proprietà tramite il proprio codice, da qualsiasi accesso al codice esterno consentito, dal sistema di proprietà e potenzialmente dai [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processori.

> [!NOTE]
> La definizione della proprietà di dipendenza nel corpo della classe costituisce l'implementazione tipica, ma è anche possibile definire una proprietà di dipendenza nel costruttore statico della classe. Questo approccio potrebbe essere utile nel caso in cui siano necessarie più righe di codice per inizializzare la proprietà di dipendenza.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementazione del "wrapper"

L'implementazione del wrapper deve chiamare <xref:System.Windows.DependencyObject.GetValue%2A> nell' `get` implementazione di e <xref:System.Windows.DependencyObject.SetValue%2A> nell' `set` implementazione (la chiamata di registrazione originale e il campo vengono visualizzati anche per maggiore chiarezza).

In tutte le circostanze eccezionali, le implementazioni del wrapper devono eseguire <xref:System.Windows.DependencyObject.GetValue%2A> rispettivamente le <xref:System.Windows.DependencyObject.SetValue%2A> azioni e. La ragione è discussa nell'argomento [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).

Tutte le proprietà di dipendenza pubbliche esistenti fornite nelle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usano questo semplice modello di implementazione del wrapper. La maggior parte della complessità della modalità di funzionamento delle proprietà di dipendenza è dovuta a un comportamento intrinseco del sistema di proprietà oppure è implementata tramite altri concetti quali la coercizione o i callback di modifica della proprietà mediante i metadati della proprietà.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

Anche in questo caso, per convenzione, il nome della proprietà wrapper deve corrispondere al nome scelto e specificato come primo parametro della <xref:System.Windows.DependencyProperty.Register%2A> chiamata che ha registrato la proprietà. Se la proprietà non segue la convenzione, non necessariamente vengono disabilitati tutti i possibili usi, ma si riscontreranno vari problemi rilevanti:

- Determinati aspetti di stili e modelli non funzioneranno.

- La maggior parte degli strumenti e delle finestre di progettazione devono basarsi sulle convenzioni di denominazione per serializzare correttamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o per fornire assistenza relativamente all'ambiente della finestra di progettazione a livello di singola proprietà.

- L'implementazione corrente del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricatore ignora completamente i wrapper e si basa sulla convenzione di denominazione durante l'elaborazione dei valori di attributo. Per altre informazioni, vedere [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Metadati della proprietà per una nuova proprietà di dipendenza

Quando si registra una proprietà di dipendenza, la registrazione tramite il sistema di proprietà crea un oggetto dei metadati che archivia le caratteristiche della proprietà. Molte di queste caratteristiche hanno impostazioni predefinite che vengono impostate se la proprietà è registrata con le firme semplici di <xref:System.Windows.DependencyProperty.Register%2A> . Altre firme di <xref:System.Windows.DependencyProperty.Register%2A> consentono di specificare i metadati desiderati durante la registrazione della proprietà. I metadati più comuni per le proprietà di dipendenza consistono nel fornire a tali proprietà un valore predefinito che viene applicato alle nuove istanze che usano la proprietà.

Se si crea una proprietà di dipendenza esistente in una classe derivata di <xref:System.Windows.FrameworkElement> , è possibile usare la classe di metadati più specializzata <xref:System.Windows.FrameworkPropertyMetadata> invece della classe di base <xref:System.Windows.PropertyMetadata> . Il costruttore per la <xref:System.Windows.FrameworkPropertyMetadata> classe presenta diverse firme in cui è possibile specificare diverse caratteristiche dei metadati in combinazione. Se si desidera specificare solo il valore predefinito, utilizzare la firma che accetta un solo parametro di tipo <xref:System.Object> . Passare il parametro dell'oggetto come valore predefinito specifico del tipo per la proprietà (il valore predefinito fornito deve corrispondere al tipo specificato come `propertyType` parametro nella <xref:System.Windows.DependencyProperty.Register%2A> chiamata).

Per <xref:System.Windows.FrameworkPropertyMetadata> , è anche possibile specificare i flag di opzione dei metadati per la proprietà. Questi flag vengono convertiti in proprietà discrete nei metadati della proprietà dopo la registrazione e usati per comunicare determinate istruzioni condizionali agli altri processi quali il motore di layout.

#### <a name="setting-appropriate-metadata-flags"></a>Impostazione dei flag di metadati appropriati

- Se la proprietà o le modifiche del relativo valore influiscono su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e in particolare influiscono sul modo in cui il sistema di layout deve ridimensionare o eseguire il rendering dell'elemento in una pagina, impostare uno o più dei flag seguenti: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure> , <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange> , <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender> .

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>indica che una modifica a questa proprietà richiede una modifica al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rendering in cui l'oggetto contenitore potrebbe richiedere più o meno spazio all'interno dell'elemento padre. Ad esempio, è necessario impostare questo flag per una proprietà "Width".

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>indica che una modifica a questa proprietà richiede una modifica al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rendering che in genere non richiede una modifica nello spazio dedicato, ma indica che il posizionamento all'interno dello spazio è stato modificato. Ad esempio, è necessario impostare questo flag per una proprietà "Alignment".

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>indica che si è verificata un'altra modifica che non influirà sul layout e sulla misura, ma richiede un altro rendering. Un esempio potrebbe essere una proprietà che modifica un colore di un elemento esistente, ad esempio "Background".

  - Questi flag vengono spesso usati come protocollo nei metadati per le implementazioni di override del sistema di proprietà o per i callback del layout. Ad esempio, è possibile che si disponga di un <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> callback che chiamerà <xref:System.Windows.UIElement.InvalidateArrange%2A> se una proprietà dell'istanza segnala una modifica del valore e ha <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> come `true` nei relativi metadati.

- Alcune proprietà possono influire sulle caratteristiche di rendering dell'elemento padre contenitore, in modo maggiore rispetto alle modifiche nelle dimensioni necessarie indicate in precedenza. Un esempio è la <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> proprietà usata nel modello di documento dinamico, in cui le modifiche apportate a tale proprietà possono modificare il rendering complessivo del documento dinamico che contiene il paragrafo. Usare <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> o <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> per identificare casi simili nelle proprietà.

- Per impostazione predefinita, le proprietà di dipendenza supportano il data binding. È possibile disabilitare intenzionalmente il data binding per i casi in cui non esiste uno scenario realistico per il data binding o nei quali le prestazioni del data binding per un oggetto di grandi dimensioni viene considerata un problema.

- Per impostazione predefinita, data binding <xref:System.Windows.Data.Binding.Mode%2A> per le proprietà di dipendenza viene impostato sul valore predefinito <xref:System.Windows.Data.BindingMode.OneWay> . È sempre possibile modificare l'associazione in modo che sia per <xref:System.Windows.Data.BindingMode.TwoWay> ogni istanza dell'associazione. per informazioni dettagliate, vedere [specificare la direzione del binding](../data/how-to-specify-the-direction-of-the-binding.md). Tuttavia, come autore della proprietà di dipendenza, è possibile scegliere di fare in modo che la proprietà usi la <xref:System.Windows.Data.BindingMode.TwoWay> modalità di associazione per impostazione predefinita. Un esempio di una proprietà di dipendenza esistente è <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType> . lo scenario per questa proprietà è che la <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> logica di impostazione e la composizione di <xref:System.Windows.Controls.MenuItem> interagiscono con lo stile del tema predefinito. La <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> logica della proprietà usa data binding in modo nativo per mantenere lo stato della proprietà in base alle altre proprietà di stato e alle chiamate al metodo. Un'altra proprietà di esempio associata <xref:System.Windows.Data.BindingMode.TwoWay> per impostazione predefinita è <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> .

- È anche possibile abilitare l'ereditarietà delle proprietà in una proprietà di dipendenza personalizzata impostando il <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> flag. L'ereditarietà della proprietà è utile per uno scenario in cui gli elementi padre e gli elementi figlio hanno una proprietà in comune e avrebbe senso per gli elementi figlio avere quel particolare valore di proprietà impostato sullo stesso valore impostato dall'elemento padre. Una proprietà ereditabile di esempio è <xref:System.Windows.FrameworkElement.DataContext%2A> , che viene usata per le operazioni di associazione per abilitare lo scenario Master-Detail importante per la presentazione dei dati. Rendendo <xref:System.Windows.FrameworkElement.DataContext%2A> ereditabili, tutti gli elementi figlio ereditano anche quel contesto dati. A causa dell'ereditarietà del valore della proprietà, è possibile specificare un contesto dati alla radice della pagina o dell'applicazione e non è necessario specificarlo di nuovo per i binding in tutti i possibili elementi figlio. <xref:System.Windows.FrameworkElement.DataContext%2A>è anche un buon esempio per illustrare che l'ereditarietà esegue l'override del valore predefinito, ma può sempre essere impostata localmente su un particolare elemento figlio. per informazioni dettagliate, vedere [usare il modello Master-Details con dati gerarchici](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). L'ereditarietà del valore della proprietà può incidere negativamente sulle prestazioni e pertanto deve essere usata sporadicamente. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

- Impostare il <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> flag per indicare se la proprietà di dipendenza deve essere rilevata o utilizzata dai servizi di journaling di navigazione. Un esempio è la <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> Proprietà. qualsiasi elemento selezionato in un controllo di selezione deve essere reso permanente quando viene spostata la cronologia del journaling.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura

È possibile definire una proprietà di dipendenza di sola lettura. Tuttavia, gli scenari in base ai quali è possibile definire la proprietà come proprietà di sola lettura sono piuttosto diversi, allo stesso modo della procedura per registrare queste proprietà con il sistema di proprietà e di quella per esporre l'identificatore. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Proprietà di dipendenza di tipo raccolta

Le proprietà di dipendenza di tipo di raccolta presentano alcuni problemi di implementazione aggiuntivi che è opportuno considerare. Per altri dettagli, vedere [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Considerazioni sulla sicurezza delle proprietà di dipendenza

Le proprietà di dipendenza devono essere dichiarate come proprietà pubbliche. I campi dell'identificatore delle proprietà di dipendenza devono essere dichiarati come campi statici pubblici. Anche se si tenta di dichiarare altri livelli di accesso (ad esempio protected), è sempre possibile accedere a una proprietà di dipendenza tramite l'identificatore in combinazione con le API del sistema di proprietà. Anche un campo dell'identificatore protetto è potenzialmente accessibile a causa della creazione di report dei metadati o delle API di determinazione del valore che fanno parte del sistema di proprietà, ad esempio <xref:System.Windows.LocalValueEnumerator> . Per altre informazioni, vedere [Sicurezza delle proprietà di dipendenza](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Proprietà di dipendenza e costruttori di classi

Esiste un principio generale nella programmazione del codice gestito (spesso applicato mediante strumenti di analisi del codice quale FxCop) in base al quale i costruttori di classi non devono chiamare metodi virtuali. Il motivo sta nel fatto che i costruttori possono essere chiamati come inizializzazione di base di un costruttore di classe derivato, pertanto l'uso del metodo virtuale tramite il costruttore potrebbe avvenire a uno stato incompleto dell'inizializzazione dell'istanza di oggetto in corso di creazione. Quando si deriva da una classe che deriva già da <xref:System.Windows.DependencyObject> , è necessario tenere presente che il sistema di proprietà stesso chiama ed espone internamente i metodi virtuali. Tali metodi virtuali sono parte dei servizi del sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'esecuzione dell'override dei metodi consente alle classi derivate di partecipare alla determinazione del valore. Per evitare eventuali problemi con l'inizializzazione del runtime, è consigliabile evitare di impostare valori della proprietà di dipendenza all'interno dei costruttori di classi, a meno che non si segua un modello del costruttore molto specifico. Per altri dettagli, vedere [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Panoramica della creazione di controlli](../controls/control-authoring-overview.md)
- [Proprietà di dipendenza di tipo raccolta](collection-type-dependency-properties.md)
- [Sicurezza delle proprietà di dipendenza](dependency-property-security.md)
- [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md)
- [Modelli di costruttore sicuri per DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
