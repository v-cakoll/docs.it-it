---
title: XAML e classi personalizzate
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: 4cd0ba7fa03d2578f4477c3ccf53188fbbea2dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186268"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>Classi XAML e personalizzate per WPF
XAML implementato nei framework CLR (Common Language Runtime) supporta la possibilità di definire una classe o una struttura personalizzata in qualsiasi linguaggio CLR (Common Language Runtime) e quindi di accedere a tale classe utilizzando il markup XAML. All'interno dello stesso file di markup è possibile usare una combinazione di tipi definiti da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e di tipi personalizzati, in genere tramite mapping dei tipi personalizzati al prefisso di uno spazio dei nomi XAML. Questo argomento descrive i requisiti che una classe personalizzata deve soddisfare perché sia utilizzabile come elemento XAML.  

<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>
## <a name="custom-classes-in-applications-or-assemblies"></a>Classi personalizzate in applicazioni o assembly  
 È possibile definire classi personalizzate da usare in XAML in due modi distinti: all'interno del code-behind o di altro codice che generi l'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] primaria o come classe di un assembly separato, ad esempio un eseguibile o una DLL usata come libreria di classi. Ognuno di questi approcci presenta vantaggi e svantaggi specifici.  
  
- Il vantaggio della creazione di una libreria di classi consiste nella possibilità di condividere tutte queste classi personalizzate tra un gran numero di applicazioni diverse. Una libreria separata, poi, rende più semplice il controllo delle versioni delle applicazioni in caso di problemi e facilita la creazione di classi destinate a fungere da elementi radice di una pagina XAML.  
  
- Il vantaggio di poter definire classi personalizzate all'interno dell'applicazione consiste nel fatto che si tratta di una tecnica relativamente leggera in grado di ridurre al minimo i problemi di distribuzione e test che si riscontrano quando, oltre al file eseguibile dell'applicazione principale, si introducono assembly separati.  
  
- Che le classi personalizzate vengano definite all'interno dello stesso assembly o in un assembly diverso, perché siano utilizzabili come elementi in XAML è necessario effettuarne il mapping tra lo spazio dei nomi CLR e quello XML. Vedere [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>Requisiti per una classe personalizzata come elemento XAML  
 Perché sia possibile crearne un'istanza come elemento oggetto, la classe deve soddisfare i requisiti seguenti:  
  
- Deve essere pubblica e supportare un costruttore pubblico senza parametri predefinito. Per alcune note riguardanti le strutture, vedere la sezione seguente.  
  
- La classe personalizzata non deve essere una classe annidata. Le classi annidate e il punto presente nella relativa sintassi di utilizzo CLR generale interferiscono con altre funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e/o di XAML, ad esempio le proprietà collegate.  
  
 Oltre ad abilitare la sintassi degli elementi oggetto, la definizione dell'oggetto abilita la sintassi degli elementi proprietà per tutte le altre proprietà pubbliche che accettano tale oggetto come tipo valore. Ciò è dovuto al fatto che è ora possibile creare un'istanza dell'oggetto come elemento oggetto e inserirla come valore dell'elemento di tale proprietà.  
  
### <a name="structures"></a>Strutture  
 Le strutture definite come tipi personalizzati possono sempre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] essere costruite in XAML in . Ciò è dovuto al fatto che i compilatori CLR creano in modo implicito un costruttore senza parametri per una struttura che inizializza tutti i valori delle proprietà sui valori predefiniti. In alcuni casi il comportamento predefinito relativo alla costruzione e/o all'utilizzo degli elementi oggetto per una struttura non è consigliabile. Ciò può essere dovuto al fatto che la struttura ha lo scopo di inserire valori e, dal punto di vista concettuale, di funzionare come un'unione, mentre i valori contenuti potrebbero essere interpretabili come reciprocamente esclusivi. Pertanto, non è possibile impostare alcuna delle proprietà della struttura. Un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esempio di tale <xref:System.Windows.GridLength>struttura è . In genere, tali strutture devono implementare un convertitore di tipi che consenta di esprimere i valori sotto forma di attributo tramite convenzioni di stringa che creano interpretazioni o modalità diverse dei valori della struttura. La struttura deve inoltre esporre un comportamento simile per la costruzione del codice tramite un costruttore senza parametri.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Requisiti per le proprietà di classi personalizzate come attributi XAML  
 Le proprietà devono fare riferimento a un tipo in base al valore (ad esempio una primitiva) o usare una classe per il tipo che dispone di un costruttore senza parametri o di un convertitore di tipi dedicato a cui può accedere un processore XAML. Nell'implementazione XAML di CLR, i processori XAML trovano tali convertitori tramite il supporto nativo per le primitive del linguaggio o tramite l'applicazione di <xref:System.ComponentModel.TypeConverterAttribute> un tipo o un membro nelle definizioni dei tipi di supporto  
  
 In alternativa, la proprietà può fare riferimento a un tipo di una classe astratta oppure a un'interfaccia. Per le classi astratte o le interfacce, l'aspettativa per l'analisi XAML è che il valore della proprietà debba essere popolato con istanze di classi pratiche che implementano l'interfaccia oppure con istanze di tipi che derivano dalla classe astratta.  
  
 In una classe astratta è possibile dichiarare le proprietà, ma queste possono essere impostate solo per le classi pratiche che derivano dalla classe astratta. Ciò è dovuto al fatto che la creazione dell'elemento oggetto per la classe richiede un costruttore pubblico senza parametri nella classe.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>Sintassi degli attributi abilitata per TypeConverter  
 Se si fornisce un convertitore di tipi dedicato con attributi a livello di classe, la conversione di un tipo abilita la sintassi degli attributi per tutte le proprietà per le quali è necessario creare un'istanza del tipo in questione. Un convertitore di tipi non abilita l'utilizzo di elementi oggetto del tipo. solo la presenza di un costruttore senza parametri per quel tipo consente l'utilizzo di elementi oggetto. In genere, pertanto, le proprietà abilitate dal convertitore di tipi possono essere usate nella sintassi delle proprietà solo se il tipo stesso supporta anche la sintassi degli elementi oggetto. Eccezione: è possibile specificare la sintassi di elementi proprietà, ma l'elemento proprietà deve contenere una stringa. Tale utilizzo è essenzialmente equivalente all'utilizzo della sintassi di un attributo e tale utilizzo non è comune a meno che non sia necessaria una gestione degli spazi vuoti più affidabile del valore dell'attributo. L'utilizzo degli elementi proprietà riportato di seguito, ad esempio, accetta una stringa e l'equivalente dell'utilizzo dell'attributo:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Esempi di proprietà in cui è consentita la sintassi degli attributi, ma la <xref:System.Windows.Input.Cursor> sintassi degli elementi proprietà che contiene un elemento oggetto non è consentita tramite XAML sono varie proprietà che accettano il tipo. La <xref:System.Windows.Input.Cursor> classe dispone di <xref:System.Windows.Input.CursorConverter>un convertitore di tipi dedicato , <xref:System.Windows.FrameworkElement.Cursor%2A> ma non espone un costruttore <xref:System.Windows.Input.Cursor> senza parametri, pertanto la proprietà può essere impostata solo tramite la sintassi degli attributi anche se il tipo effettivo è un tipo di riferimento.  
  
### <a name="per-property-type-converters"></a>Convertitori di tipi per proprietà  
 In alternativa, la proprietà stessa può dichiarare un convertitore di tipi a livello di proprietà. In questo modo viene abilitato un "mini linguaggio" che crea un'istanza di oggetti del <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> tipo della proprietà inline, elaborando i valori stringa in ingresso dell'attributo come input per un'operazione basata sul tipo appropriato. In genere questa operazione viene eseguita per fornire una funzione di accesso pratica e non come unico mezzo per consentire l'impostazione di una proprietà in XAML. Tuttavia, è anche possibile utilizzare convertitori di tipi per gli attributi in cui si desidera utilizzare i tipi CLR esistenti che non forniscono un costruttore senza parametri o un convertitore di tipi con attributi. Esempi dall'API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono alcune <xref:System.Globalization.CultureInfo> proprietà che accettano il tipo. In questo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] caso, usato il <xref:System.Globalization.CultureInfo> tipo Microsoft .NET Framework esistente per indirizzare meglio gli <xref:System.Globalization.CultureInfo> scenari di compatibilità e migrazione usati nelle versioni precedenti dei framework, ma il tipo non supportava i costruttori necessari o la conversione del tipo a livello di tipo per essere utilizzabile direttamente come valore della proprietà XAML.  
  
 Ogni volta che si espone una proprietà con utilizzo in XAML, in particolare se l'utente è un autore di controlli, è consigliabile supportare tale proprietà con una proprietà di dipendenza. Ciò è particolarmente vero [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se si utilizza l'implementazione esistente <xref:System.Windows.DependencyProperty> del processore XAML, perché è possibile migliorare le prestazioni utilizzando il backup. Una proprietà di dipendenza espone le funzionalità del sistema di proprietà relative alla proprietà in questione che gli utenti si aspettano da una proprietà accessibile tramite XAML, ad esempio funzionalità quali l'animazione, il data binding e il supporto degli stili. Per altre informazioni, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Scrittura e assegnazione di un convertitore di tipi  
 In alcuni casi è necessario <xref:System.ComponentModel.TypeConverter> scrivere una classe derivata personalizzata per fornire la conversione del tipo per il tipo di proprietà. Per istruzioni su come derivare e creare un convertitore di tipi <xref:System.ComponentModel.TypeConverterAttribute>in grado di supportare gli utilizzi XAML e su come applicare , vedere [TypeConverters e XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Requisiti per la sintassi degli attributi del gestore eventi XAML per gli eventi di una classe personalizzata  
 Per essere utilizzabile come evento CLR, l'evento deve essere esposto come evento pubblico in una classe che supporta un costruttore senza parametri o in una classe astratta in cui è possibile accedere all'evento nelle classi derivate. Per poter essere utilizzato comodamente come evento indirizzato, `add` l'evento CLR deve implementare metodi e `remove` espliciti, che <xref:System.Windows.UIElement.AddHandler%2A> aggiungono <xref:System.Windows.UIElement.RemoveHandler%2A> e rimuovono gestori per la firma dell'evento CLR e inoltrano tali gestori ai metodi e . Questi metodi aggiungono o rimuovono i gestori dall'archivio dei gestori degli eventi indirizzati per l'istanza a cui l'evento è associato.  
  
> [!NOTE]
> È possibile registrare direttamente i gestori <xref:System.Windows.UIElement.AddHandler%2A>per gli eventi indirizzati utilizzando , e non definire deliberatamente un evento CLR che espone l'evento indirizzato. Questa operazione non è in genere consigliata. In questo caso, infatti, per l'evento non è abilitata la sintassi degli attributi XAML per il collegamento di gestori e nella classe risultante il codice XAML relativo alle caratteristiche del tipo è meno chiaro.  
  
<a name="Collection_Properties"></a>
## <a name="writing-collection-properties"></a>Scrittura delle proprietà delle raccolte  
 Le proprietà che accettano un tipo di raccolta hanno una sintassi XAML che consente di specificare gli oggetti da aggiungere alla raccolta. Questa sintassi presenta due funzionalità di rilievo.  
  
- Nella sintassi dell'elemento oggetto non è necessario specificare l'oggetto che rappresenta l'oggetto Collection. Ogni volta che in XAML si specifica una proprietà che accetta un tipo di raccolta, tale tipo di raccolta è implicito.  
  
- Gli elementi figlio della proprietà della raccolta nel markup vengono elaborati in modo che diventino membri della raccolta. In genere l'accesso del codice ai membri di una raccolta avviene tramite metodi di elenco o dizionario, ad esempio `Add`, oppure tramite un indicizzatore. La sintassi XAML, tuttavia, non supporta metodi o indicizzatori, ad eccezione di XAML 2009, che supporta i metodi. L'uso di XAML 2009, però, limita i possibili utilizzi di WPF. Vedere [Funzionalità del linguaggio XAML 2009](../../../desktop-wpf/xaml-services/xaml-2009-language-features.md). Le raccolte sono ovviamente un requisito molto comune per la creazione di un albero di elementi. È quindi necessario individuare il modo più adatto per popolarle in XAML dichiarativo. Pertanto, gli elementi figlio di una proprietà della raccolta vengono elaborati aggiungendoli alla raccolta che rappresenta il valore del tipo della proprietà.  
  
 La definizione di proprietà di raccolta per l'implementazione dei servizi XAML di .NET Framework e quindi anche per il processore XAML di WPF è la seguente. Il tipo della proprietà deve soddisfare una delle condizioni seguenti:  
  
- Implementa <xref:System.Collections.IList>.  
  
- Implementa <xref:System.Collections.IDictionary> o l'equivalente generico (<xref:System.Collections.Generic.IDictionary%602>).  
  
- Deriva da <xref:System.Array> (per ulteriori informazioni sulle matrici in XAML, vedere [x:Array Markup Extension](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
- Implements <xref:System.Windows.Markup.IAddChild> (un'interfaccia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]definita da ).  
  
 In CLR ognuno di questi tipi dispone di un metodo `Add`, usato dal processore XAML per aggiungere elementi alla raccolta sottostante durante la creazione dell'oggetto grafico.  
  
> [!NOTE]
> Il `List` generico `Dictionary` e<xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602>le interfacce ( e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ) non sono supportati per il rilevamento di raccolte dal processore XAML. Tuttavia, è <xref:System.Collections.Generic.List%601> possibile usare la classe come <xref:System.Collections.IList> classe <xref:System.Collections.Generic.Dictionary%602> base, perché implementa direttamente <xref:System.Collections.IDictionary> o come classe base, perché implementa direttamente.  
  
 Quando si dichiara una proprietà che accetta una raccolta, prestare attenzione alla modalità di inizializzazione del valore di questa proprietà nelle nuove istanze del tipo. Se non si implementa la proprietà come proprietà di dipendenza, è adeguato che la proprietà usi un campo sottostante che chiami il costruttore del tipo della raccolta. Se la proprietà è una proprietà di dipendenza, potrebbe essere necessario inizializzare la proprietà della raccolta come parte del costruttore del tipo predefinito. Ciò è dovuto al fatto che il valore predefinito di una proprietà di dipendenza proviene dai metadati e in genere è necessario evitare che il valore iniziale di una proprietà di una raccolta corrisponda a una raccolta condivisa statica. Deve esistere un'istanza della raccolta per ogni istanza del tipo che la contiene. Per altre informazioni, vedere [Proprietà Dependency personalizzate](custom-dependency-properties.md).  
  
 Per la proprietà della raccolta è possibile implementare un tipo di raccolta personalizzato. A causa del trattamento implicito delle proprietà di raccolta, il tipo di raccolta personalizzata non deve fornire un costruttore senza parametri per poter essere utilizzato in XAML in modo implicito. Tuttavia, è possibile fornire facoltativamente un costruttore senza parametri per il tipo di raccolta. Questo modo di procedere può risultare utile. A meno che non si fornisca un costruttore senza parametri, non è possibile dichiarare in modo esplicito la raccolta come elemento oggetto. Alcuni autori di markup interpretano la dichiarazione esplicita di una raccolta come una questione di stile di markup. Inoltre, un costruttore senza parametri può semplificare i requisiti di inizializzazione quando si creano nuovi oggetti che utilizzano il tipo di raccolta come valore della proprietà.  
  
<a name="XAMLCONtent"></a>
## <a name="declaring-xaml-content-properties"></a>Dichiarazione di proprietà di contenuto XAML  
 Nel linguaggio XAML è definito il concetto di proprietà di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ogni classe utilizzabile nella sintassi per gli oggetti può avere una sola proprietà di contenuto XAML. Per dichiarare una proprietà come proprietà di contenuto <xref:System.Windows.Markup.ContentPropertyAttribute> XAML per la classe, applicare la parte come parte della definizione della classe. Specificare il nome della proprietà <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> di contenuto XAML desiderata come nell'attributo. La proprietà viene specificata come stringa in base al <xref:System.Reflection.PropertyInfo>nome, non come costrutto di reflection, ad esempio .  
  
 È possibile specificare una proprietà di raccolta come proprietà del contenuto XAML. Il risultato è un utilizzo di tale proprietà in cui l'elemento oggetto può avere uno o più elementi figlio, senza alcun tag di elementi oggetto Collection o di elementi proprietà. Questi elementi vengono considerati come valore per la proprietà del contenuto XAML e vengono aggiunti all'istanza della raccolta sottostante.  
  
 Alcune proprietà del contenuto XAML esistenti usano il tipo di proprietà di `Object`. In questo modo una proprietà di contenuto XAML <xref:System.String> che può accettare valori primitivi, ad esempio un e un singolo valore dell'oggetto di riferimento. Se si segue questo modello, il tipo usato è responsabile della determinazione del tipo, nonché della gestione dei tipi possibili. Il motivo <xref:System.Object> tipico di un tipo di contenuto consiste nel supportare sia un semplice mezzo per aggiungere contenuto dell'oggetto come stringa (che riceve un trattamento di presentazione predefinito) sia un mezzo avanzato per aggiungere contenuto dell'oggetto che specifica una presentazione non predefinita o dati aggiuntivi.  
  
<a name="Serializing"></a>
## <a name="serializing-xaml"></a>Serializzazione di XAML  
 Per alcuni scenari, ad esempio per gli autori di controlli, è anche necessario assicurarsi che qualsiasi rappresentazione di oggetti per cui può essere creata un'istanza in XAML possa anche essere serializzata di nuovo nel markup XAML equivalente. I requisiti di serializzazione non sono descritti in questo argomento. Vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md) e [Struttura ad albero e serializzazione degli elementi](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Panoramica della creazione di controlli](../controls/control-authoring-overview.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
- [Caricamento XAML e proprietà di dipendenza](xaml-loading-and-dependency-properties.md)
