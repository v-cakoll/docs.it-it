---
title: Classi XAML e personalizzate per WPF
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: a1de1ee80d1f88b0c0a7adfb75b96353b6861d97
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371892"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>Classi XAML e personalizzate per WPF
Il linguaggio XAML implementato nei framework [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] supporta la possibilità di definire classi o strutture personalizzate in qualsiasi linguaggio [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e quindi di accedere a tali classi o strutture tramite markup XAML. All'interno dello stesso file di markup è possibile usare una combinazione di tipi definiti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e di tipi personalizzati, in genere tramite mapping dei tipi personalizzati al prefisso di uno spazio dei nomi XAML. Questo argomento descrive i requisiti che una classe personalizzata deve soddisfare perché sia utilizzabile come elemento XAML.  
  
 
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## <a name="custom-classes-in-applications-or-assemblies"></a>Classi personalizzate in applicazioni o assembly  
 È possibile definire classi personalizzate da usare in XAML in due modi distinti: all'interno del code-behind o di altro codice che generi l'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] primaria o come classe di un assembly separato, ad esempio un eseguibile o una DLL usata come libreria di classi. Ognuno di questi approcci presenta vantaggi e svantaggi specifici.  
  
-   Il vantaggio della creazione di una libreria di classi consiste nella possibilità di condividere tutte queste classi personalizzate tra un gran numero di applicazioni diverse. Una libreria separata, poi, rende più semplice il controllo delle versioni delle applicazioni in caso di problemi e facilita la creazione di classi destinate a fungere da elementi radice di una pagina XAML.  
  
-   Il vantaggio di poter definire classi personalizzate all'interno dell'applicazione consiste nel fatto che si tratta di una tecnica relativamente leggera in grado di ridurre al minimo i problemi di distribuzione e test che si riscontrano quando, oltre al file eseguibile dell'applicazione principale, si introducono assembly separati.  
  
-   Che le classi personalizzate vengano definite all'interno dello stesso assembly o in un assembly diverso, perché siano utilizzabili come elementi in XAML è necessario effettuarne il mapping tra lo spazio dei nomi CLR e quello XML. Vedere [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>Requisiti per una classe personalizzata come elemento XAML  
 Perché sia possibile crearne un'istanza come elemento oggetto, la classe deve soddisfare i requisiti seguenti:  
  
-   Deve essere pubblica e supportare un costruttore pubblico senza parametri predefinito. Per alcune note riguardanti le strutture, vedere la sezione seguente.  
  
-   La classe personalizzata non deve essere una classe annidata. Le classi annidate e il punto presente nella relativa sintassi di utilizzo CLR generale interferiscono con altre funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e/o di XAML, ad esempio le proprietà collegate.  
  
 Oltre ad abilitare la sintassi degli elementi oggetto, la definizione dell'oggetto abilita la sintassi degli elementi proprietà per tutte le altre proprietà pubbliche che accettano tale oggetto come tipo valore. Ciò è dovuto al fatto che è ora possibile creare un'istanza dell'oggetto come elemento oggetto e inserirla come valore dell'elemento di tale proprietà.  
  
### <a name="structures"></a>Strutture  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è sempre possibile costruire in XAML strutture definite come tipi personalizzati. Ciò è dovuto al fatto che i compilatori [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] creano in modo implicito un costruttore predefinito per una struttura che inizializza tutte le proprietà sui corrispondenti valori predefiniti. In alcuni casi il comportamento predefinito relativo alla costruzione e/o all'utilizzo degli elementi oggetto per una struttura non è consigliabile. Ciò può essere dovuto al fatto che la struttura ha lo scopo di inserire valori e, dal punto di vista concettuale, di funzionare come un'unione, mentre i valori contenuti potrebbero essere interpretabili come reciprocamente esclusivi. Pertanto, non è possibile impostare alcuna delle proprietà della struttura. Oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esempio di tale struttura viene <xref:System.Windows.GridLength>. In genere, tali strutture devono implementare un convertitore di tipi che consenta di esprimere i valori sotto forma di attributo tramite convenzioni di stringa che creano interpretazioni o modalità diverse dei valori della struttura. La struttura deve anche esporre un comportamento simile per la costruzione del codice tramite un costruttore non predefinito.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Requisiti per le proprietà di classi personalizzate come attributi XAML  
 Le proprietà devono fare riferimento a un tipo per valore (ad esempio una primitiva) oppure usare per il tipo una classe che abbia un costruttore predefinito o un convertitore di tipi dedicato al quale un processore XAML possa accedere. Nell'implementazione CLR XAML, i processori XAML individuano tali convertitori tramite il supporto nativo per le primitive di linguaggio o tramite l'applicazione di <xref:System.ComponentModel.TypeConverterAttribute> a un tipo o membro nelle definizioni dei tipi di supporto  
  
 In alternativa, la proprietà può fare riferimento a un tipo di una classe astratta oppure a un'interfaccia. Per le classi astratte o le interfacce, l'aspettativa per l'analisi XAML è che il valore della proprietà debba essere popolato con istanze di classi pratiche che implementano l'interfaccia oppure con istanze di tipi che derivano dalla classe astratta.  
  
 In una classe astratta è possibile dichiarare le proprietà, ma queste possono essere impostate solo per le classi pratiche che derivano dalla classe astratta. Questo perché la creazione dell'elemento oggetto per la classe richiede sempre un costruttore predefinito pubblico per la classe stessa.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>Sintassi degli attributi abilitata per TypeConverter  
 Se si fornisce un convertitore di tipi dedicato con attributi a livello di classe, la conversione di un tipo abilita la sintassi degli attributi per tutte le proprietà per le quali è necessario creare un'istanza del tipo in questione. Un convertitore di tipi non consente l'utilizzo degli elementi oggetto del tipo, che è consentito solo dalla presenza di un costruttore predefinito per il tipo. In genere, pertanto, le proprietà abilitate dal convertitore di tipi possono essere usate nella sintassi delle proprietà solo se il tipo stesso supporta anche la sintassi degli elementi oggetto. Eccezione: è possibile specificare la sintassi di elementi proprietà, ma l'elemento proprietà deve contenere una stringa. Che l'utilizzo della realtà è essenzialmente equivalente a un utilizzo della sintassi di attributo e tale utilizzo non è comune a meno che non è necessario per una gestione più efficace gli spazi vuoti del valore dell'attributo. L'utilizzo degli elementi proprietà riportato di seguito, ad esempio, accetta una stringa e l'equivalente dell'utilizzo dell'attributo:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Esempi di proprietà in cui è consentita la sintassi degli attributi ma la sintassi degli elementi di proprietà che contiene un elemento dell'oggetto non è consentito tramite XAML sono varie proprietà che accettano il <xref:System.Windows.Input.Cursor> tipo. Il <xref:System.Windows.Input.Cursor> classe dispone di un convertitore di tipi dedicato <xref:System.Windows.Input.CursorConverter>, ma non espone un costruttore predefinito, in modo che il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà può essere impostata solo tramite sintassi degli attributi malgrado l'effettivo <xref:System.Windows.Input.Cursor> tipo è un tipo riferimento.  
  
### <a name="per-property-type-converters"></a>Convertitori di tipi per proprietà  
 In alternativa, la proprietà stessa può dichiarare un convertitore di tipi a livello di proprietà. In questo modo un "minilinguaggio" che crea istanze di oggetti del tipo di proprietà inline, elaborando i valori stringa in ingresso dell'attributo come input per un <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> operazione basata sul tipo appropriato. In genere questa operazione viene eseguita per fornire una funzione di accesso pratica e non come unico mezzo per consentire l'impostazione di una proprietà in XAML. È anche possibile, tuttavia, usare convertitori di tipi per gli attributi nei quali si vogliono usare tipi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] che non dispongono né di un costruttore predefinito né di un convertitore di tipi con attributi. Gli esempi dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API vengono determinate proprietà che accettano il <xref:System.Globalization.CultureInfo> tipo. In questo caso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzato in Microsoft .NET Framework esistenti <xref:System.Globalization.CultureInfo> tipo per meglio soddisfare gli scenari di migrazione e compatibilità che sono stati usati nelle versioni precedenti di Framework, ma il <xref:System.Globalization.CultureInfo> tipo non supportava le necessarie i costruttori o conversione di tipi a livello di tipo perché sia utilizzabile come valore della proprietà XAML direttamente.  
  
 Ogni volta che si espone una proprietà con utilizzo in XAML, in particolare se l'utente è un autore di controlli, è consigliabile supportare tale proprietà con una proprietà di dipendenza. Questo è particolarmente vero se si usa esistente [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] implementazione del processore XAML, in quanto è possibile migliorare le prestazioni usando <xref:System.Windows.DependencyProperty> il backup. Una proprietà di dipendenza espone le funzionalità del sistema di proprietà relative alla proprietà in questione che gli utenti si aspettano da una proprietà accessibile tramite XAML, ad esempio funzionalità quali l'animazione, il data binding e il supporto degli stili. Per altre informazioni, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Scrittura e assegnazione di un convertitore di tipi  
 In alcuni casi sarà necessario scrivere una classe personalizzata <xref:System.ComponentModel.TypeConverter> derivata per fornire la conversione di tipo per il tipo di proprietà. Per istruzioni sulle modalità di derivazione e creare un convertitore di tipi in grado di supportare gli utilizzi XAML e come applicare la <xref:System.ComponentModel.TypeConverterAttribute>, vedere [TypeConverter e XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Requisiti per la sintassi degli attributi del gestore eventi XAML per gli eventi di una classe personalizzata  
 Perché sia utilizzabile come evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], l'evento deve essere esposto come pubblico in una classe che supporta un costruttore predefinito o in una classe astratta in cui l'evento è accessibile per le classi derivate. Per poter essere comodamente utilizzato come un evento indirizzato, il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento deve implementare in modo esplicito `add` e `remove` metodi che aggiungono e rimuovono gestori per il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] firma dell'evento e inoltrare tali gestori per il <xref:System.Windows.UIElement.AddHandler%2A>e <xref:System.Windows.UIElement.RemoveHandler%2A> metodi. Questi metodi aggiungono o rimuovono i gestori dall'archivio dei gestori degli eventi indirizzati per l'istanza a cui l'evento è associato.  
  
> [!NOTE]
>  È possibile registrare direttamente i gestori eventi indirizzati tramite <xref:System.Windows.UIElement.AddHandler%2A>e per evitare deliberatamente di definire un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] evento che espone l'evento indirizzato. Questa operazione non è in genere consigliata. In questo caso, infatti, per l'evento non è abilitata la sintassi degli attributi XAML per il collegamento di gestori e nella classe risultante il codice XAML relativo alle caratteristiche del tipo è meno chiaro.  
  
<a name="Collection_Properties"></a>   
## <a name="writing-collection-properties"></a>Scrittura delle proprietà delle raccolte  
 Le proprietà che accettano un tipo di raccolta hanno una sintassi XAML che consente di specificare gli oggetti da aggiungere alla raccolta. Questa sintassi presenta due funzionalità di rilievo.  
  
-   Nella sintassi dell'elemento oggetto non è necessario specificare l'oggetto che rappresenta l'oggetto Collection. Ogni volta che in XAML si specifica una proprietà che accetta un tipo di raccolta, tale tipo di raccolta è implicito.  
  
-   Gli elementi figlio della proprietà della raccolta nel markup vengono elaborati in modo che diventino membri della raccolta. In genere l'accesso del codice ai membri di una raccolta avviene tramite metodi di elenco o dizionario, ad esempio `Add`, oppure tramite un indicizzatore. Ma la sintassi XAML non supporta metodi o indicizzatori (eccezione: XAML 2009 può supportare i metodi, ma l'utilizzo di XAML 2009 limita i possibili utilizzi di WPF; visualizzare [funzionalità del linguaggio XAML 2009](../../xaml-services/xaml-2009-language-features.md)). Le raccolte sono ovviamente un requisito molto comune per la creazione di un albero di elementi. È quindi necessario individuare il modo più adatto per popolarle in XAML dichiarativo. Pertanto, gli elementi figlio di una proprietà della raccolta vengono elaborati aggiungendoli alla raccolta che rappresenta il valore del tipo della proprietà.  
  
 La definizione di proprietà di raccolta per l'implementazione dei servizi XAML di .NET Framework e quindi anche per il processore XAML di WPF è la seguente. Il tipo della proprietà deve soddisfare una delle condizioni seguenti:  
  
-   Implementa <xref:System.Collections.IList>.  
  
-   Implements <xref:System.Collections.IDictionary> o l'interfaccia equivalente generica (<xref:System.Collections.Generic.IDictionary%602>).  
  
-   Deriva da <xref:System.Array> (per altre informazioni sulle matrici in XAML, vedere [estensione di Markup X:Array](../../xaml-services/x-array-markup-extension.md).)  
  
-   Implements <xref:System.Windows.Markup.IAddChild> (un'interfaccia definita da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]).  
  
 In CLR ognuno di questi tipi dispone di un metodo `Add`, usato dal processore XAML per aggiungere elementi alla raccolta sottostante durante la creazione dell'oggetto grafico.  
  
> [!NOTE]
>  Il tipo generico `List` e `Dictionary` interfacce (<xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602>) non sono supportate per il rilevamento della raccolta dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processore XAML. Tuttavia, è possibile usare la <xref:System.Collections.Generic.List%601> classe come classe di base, perché implementa <xref:System.Collections.IList> direttamente, o <xref:System.Collections.Generic.Dictionary%602> come classe di base, perché implementa <xref:System.Collections.IDictionary> direttamente.  
  
 Quando si dichiara una proprietà che accetta una raccolta, prestare attenzione alla modalità di inizializzazione del valore di questa proprietà nelle nuove istanze del tipo. Se non si implementa la proprietà come proprietà di dipendenza, è adeguato che la proprietà usi un campo sottostante che chiami il costruttore del tipo della raccolta. Se la proprietà è una proprietà di dipendenza, potrebbe essere necessario inizializzare la proprietà della raccolta come parte del costruttore del tipo predefinito. Ciò è dovuto al fatto che il valore predefinito di una proprietà di dipendenza proviene dai metadati e in genere è necessario evitare che il valore iniziale di una proprietà di una raccolta corrisponda a una raccolta condivisa statica. Deve esistere un'istanza della raccolta per ogni istanza del tipo che la contiene. Per altre informazioni, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).  
  
 Per la proprietà della raccolta è possibile implementare un tipo di raccolta personalizzato. A causa del trattamento implicito della proprietà della raccolta, per usare il tipo di raccolta personalizzato in XAML non è necessario che il tipo disponga di un costruttore predefinito. Se si vuole, tuttavia, è possibile specificare un costruttore predefinito per il tipo di raccolta. Questo modo di procedere può risultare utile. È infatti possibile dichiarare in modo esplicito una raccolta come elemento oggetto solo se si specifica un costruttore predefinito. Alcuni autori di markup interpretano la dichiarazione esplicita di una raccolta come una questione di stile di markup. Un costruttore predefinito, poi, può semplificare i requisiti di inizializzazione quando si creano nuovi oggetti che usano il tipo di raccolta come valore della proprietà.  
  
<a name="XAMLCONtent"></a>   
## <a name="declaring-xaml-content-properties"></a>Dichiarazione di proprietà di contenuto XAML  
 Nel linguaggio XAML è definito il concetto di proprietà di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ogni classe utilizzabile nella sintassi per gli oggetti può avere una sola proprietà di contenuto XAML. Per dichiarare una proprietà per proprietà di contenuto XAML per la classe, applicare il <xref:System.Windows.Markup.ContentPropertyAttribute> come parte della definizione di classe. Specificare il nome della proprietà del contenuto XAML desiderata come il <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> nell'attributo. La proprietà viene specificata sotto forma di stringa in base al nome, non come un costrutto di reflection, ad esempio <xref:System.Reflection.PropertyInfo>.  
  
 È possibile specificare una proprietà di raccolta come proprietà del contenuto XAML. Il risultato è un utilizzo di tale proprietà in cui l'elemento oggetto può avere uno o più elementi figlio, senza alcun tag di elementi oggetto Collection o di elementi proprietà. Questi elementi vengono considerati come valore per la proprietà del contenuto XAML e vengono aggiunti all'istanza della raccolta sottostante.  
  
 Alcune proprietà del contenuto XAML esistenti usano il tipo di proprietà di `Object`. In questo modo un XAML contenuti i valori delle proprietà che può accettare primitivi, ad esempio un <xref:System.String> , nonché un valore dell'oggetto di riferimento. Se si segue questo modello, il tipo usato è responsabile della determinazione del tipo, nonché della gestione dei tipi possibili. Il motivo tipico per un <xref:System.Object> contenuto tipo deve supportare sia un modo semplice, ovvero l'aggiunta di contenuto dell'oggetto sotto forma di stringa (che riceve un trattamento di presentazione predefinito) o che in modo avanzati dell'aggiunta dell'oggetto contenuto che consente di specificare una presentazione non predefinito o dati aggiuntivi.  
  
<a name="Serializing"></a>   
## <a name="serializing-xaml"></a>Serializzazione di XAML  
 Per alcuni scenari, ad esempio per gli autori di controlli, è anche necessario assicurarsi che qualsiasi rappresentazione di oggetti per cui può essere creata un'istanza in XAML possa anche essere serializzata di nuovo nel markup XAML equivalente. I requisiti di serializzazione non sono descritti in questo argomento. Vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md) e [Struttura ad albero e serializzazione degli elementi](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
- [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md)
