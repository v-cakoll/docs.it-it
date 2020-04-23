---
title: Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071864"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
Un contesto dello schema XAML è un'entità concettuale che qualifica il modo in cui una produzione XAML che usa un vocabolario XAML specifico interagisce con il comportamento di scrittura dell'oggetto, incluso il modo in cui il mapping dei tipi viene risolto, come vengono caricati gli assembly, come vengono interpretate determinate impostazioni del lettore e del writer. In questo argomento vengono descritte le funzionalità dei servizi XAML .NET e il contesto dello schema XAML predefinito associato, basato sul sistema di tipi CLR. In questo argomento viene inoltre descritto il contesto dello schema XAML utilizzato per WPFWPF.

## <a name="default-xaml-schema-context"></a>Contesto dello schema XAML predefinitoDefault XAML Schema Context

I servizi XAML .NET implementano e usano un contesto dello schema XAML predefinito. Il comportamento di contesto dello schema XAML predefinito <xref:System.Xaml.XamlSchemaContext> non è sempre completamente visibile nell'API della classe. Tuttavia, in molti casi il comportamento influenzato dal contesto dello schema XAML predefinito è <xref:System.Xaml.XamlMember> osservabile tramite l'API comune del sistema di tipi XAML, ad esempio i membri di o <xref:System.Xaml.XamlType>, o tramite le API esposte nei reader XAML e nei writer XAML che utilizzano il contesto dello schema XAML predefinito.

È possibile <xref:System.Xaml.XamlSchemaContext> creare un che incapsula <xref:System.Xaml.XamlSchemaContext> il comportamento predefinito chiamando il costruttore. In questo modo viene creato in modo esplicito il contesto dello schema XAML predefinito. Lo stesso contesto dello schema XAML predefinito viene creato in modo implicito, se si <xref:System.Xaml.XamlSchemaContext> inizializza un reader XAML o un writer XAML usando API che non accettano in modo esplicito un parametro di input.

Il contesto dello schema XAML predefinito si basa sulla reflection CLR per il comportamento di mapping dei tipi. Ciò include l'esame <xref:System.Reflection.PropertyInfo> <xref:System.Reflection.MethodInfo>della definizione di CLR <xref:System.Type>e correlati o . Inoltre, l'attribuzione CLR su tipi o membri viene utilizzata per compilare le specifiche per le informazioni sul tipo XAML o sui membri XAML che utilizzano il tipo di supporto CLR. Il contesto dello schema XAML predefinito non `Invoker` richiede tecniche di estensione del sistema di tipi, ad esempio il modello, perché le informazioni necessarie sono disponibili nel sistema di tipi CLR.

Per la logica di caricamento dell'assembly, il contesto dello schema XAML predefinito si basa principalmente su qualsiasi valore di assembly fornito nei mapping dello spazio dei nomi XAML. Inoltre, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> può suggerire un assembly da caricare, per scenari come il caricamento di tipi interni.

## <a name="wpf-xaml-schema-context"></a>Contesto dello schema XAML WPFWPF XAML Schema Context

Il contesto dello schema XAML WPF è descritto in questo argomento perché l'implementazione WPF fornisce un'illustrazione interessante dei tipi di funzionalità che possono essere introdotte implementando un contesto dello schema XAML non predefinito. Inoltre, il concetto di contesto dello schema XAML non è illustrato molto nella documentazione WPFWPF che indirizza XAML WPF; il comportamento abilitato dal contesto dello schema XAML potrebbe essere pienamente comprensibile solo se integrato con una discussione sul funzionamento del contesto dello schema XAML predefinito. Il contesto dello schema XAML WPF implementa il comportamento seguente.

**Sostituzioni di ricerca:** WPFWPF include alcuni modelli di contenuto per XAML in <xref:System.Windows.Markup.ContentPropertyAttribute> cui sono presenti proprietà di contenuto XAML che funzionano senza essere attribuite. <xref:System.Xaml.XamlType.LookupContentProperty%2A>gli override per WPFWPF implementano questo comportamento.

**Rinviare le espressioni WPF:Deferral for WPF expressions:** WPFWPF include diverse classi di espressioni che rinviano un valore fino a quando non è disponibile un contesto di runtime. Inoltre, l'espansione del modello è un comportamento di runtime che si basa sulle tecniche di rinvio.

**Ottimizzazioni della ricerca del sistema di tipi:** WPFWPF dispone di un ampio vocabolario XAML e di un modello a oggetti, incluse le definizioni dei membri della classe base che ereditano letteralmente centinaia di classi definite da WPF. Inoltre, WPFWPF stesso è distribuito tra più assembly. WPFWPF ottimizza la ricerca dei tipi usando tabelle di ricerca e altre tecniche. Ciò fornisce miglioramenti delle prestazioni rispetto al contesto dello schema XAML predefinito e alla relativa ricerca di tipi basata su CLR. Nei casi in cui i tipi non esistono in una tabella di ricerca, il comportamento usa tecniche di contesto dello schema XAML simili al contesto dello schema XAML predefinito.

**XamlType e XamlMember estensione:** WPFWPF estende i concetti di proprietà con le proprietà di dipendenza e i concetti di evento con gli eventi indirizzati. Per offrire a questi concetti una maggiore <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>visibilità per le operazioni di elaborazione XAML, WPF extends e , e aggiunge proprietà interne che segnalano le caratteristiche della proprietà di dipendenza e degli eventi indirizzati.

### <a name="accessing-the-wpf-xaml-schema-context"></a>Accesso al contesto dello schema XAML WPFAccessing the WPF XAML Schema Context

Se si usano tecniche XAML basate <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> su <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>WPF o , il contesto dello schema XAML WPF è già in uso in tali implementazioni del reader XAML e del writer XAML.

Se si utilizzano altre implementazioni del reader XAML o del writer XAML che non vengono inizializzate con <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>il contesto dello schema XAML WPF, è possibile ottenere un contesto dello schema XAML WPF funzionante da . È quindi possibile utilizzare questo valore come <xref:System.Xaml.XamlSchemaContext>inizializzazione per altre API che utilizzano un file . Ad esempio, è <xref:System.Xaml.XamlXmlReader.%23ctor%2A> possibile chiamare per l'inizializzazione e passare il contesto dello schema XAML WPF. In alternativa, è possibile usare il contesto dello schema XAML WPF per le operazioni del sistema di tipi XAML. Ciò può includere <xref:System.Xaml.XamlType> l'inizializzazione di costruzione di un oggetto o <xref:System.Xaml.XamlMember>o , o la chiamata <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>a .

Si noti che se si accede a determinati aspetti di XAML WPF da una prospettiva di flusso del nodo XAML puro, alcune delle funzionalità del framework WPF potrebbero non aver ancora agito. Ad esempio, i modelli WPFWPF per i controlli non sono ancora applicati. Pertanto, se si accede a una proprietà che in fase di esecuzione potrebbe essere popolata con una struttura ad albero visuale completa, è possibile visualizzare solo un valore di proprietà che fa riferimento a un modello. Anche il contesto del servizio fornito per le estensioni di markup WPFWPF potrebbe non essere accurato se fornito da una situazione non di runtime e può generare eccezioni quando si tenta di scrivere un oggetto grafico.

## <a name="xaml-and-assembly-loading"></a>Caricamento di XAML e assembly

Il caricamento degli assembly per i servizi XAML xaml <xref:System.AppDomain>e .NET si integra con il concetto definito da CLR di . Un contesto dello schema XAML interpreta come caricare assembly o trovare tipi in <xref:System.AppDomain> fase di esecuzione o in fase di progettazione, in base all'uso di e altri fattori. La logica è leggermente diversa a seconda che il codice XAML sia `XamlBuildTask`separato da XAML per un `PresentationBuildTask`reader XAML, XAML compilato in una DLL da o sia BAML generato da WPF.

Il contesto dello schema XAML per WPFWPF si <xref:System.AppDomain> integra con il modello di applicazione WPFWPF, che a sua volta usa e altri fattori che sono dettagli di implementazione WPFWPF.

#### <a name="xaml-reader-input-loose-xaml"></a>Input del lettore XAML (XAML separato)

01. Il contesto dello schema <xref:System.AppDomain> XAML scorre l'applicazione, cercando un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, tale assieme viene utilizzato per la risoluzione.

02. In caso contrario, per <xref:System.Reflection.Assembly> caricare un assembly viene utilizzata una delle tecniche seguenti in base all'API CLR:

    - Se il nome è qualificato <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> nel mapping, chiamare il nome completo.

    - Se il passaggio precedente ha esito negativo, utilizzare il <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>nome breve (e il token di chiave pubblica se presente) per chiamare .

    - Se il nome non è qualificato <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>nel mapping, chiamare .

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask`viene utilizzato per Windows Communication Foundation (WCF) e Windows Workflow Foundation.

Si noti `XamlBuildTask` che i riferimenti agli assembly tramite sono sempre completi.

1. Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> il nome completo.

2. Se il passaggio precedente ha esito negativo, utilizzare il <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>nome breve (e il token di chiave pubblica se presente) per chiamare .

#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)

Il caricamento dell'assembly per BAML è dovuto a due aspetti: il caricamento dell'assembly iniziale che contiene il BAML come componente e il caricamento degli assembly di backup dei tipi per tutti i tipi a cui fa riferimento la produzione BAML.

##### <a name="assembly-load-for-initial-markup"></a>Caricamento dell'assieme per il markup iniziale:

Il riferimento all'assembly da cui caricare il markup è sempre non qualificato.

1. Il contesto dello schema <xref:System.AppDomain> XAML WPF scorre l'applicazione WPF, cercando un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, tale assieme viene utilizzato per la risoluzione.

2. Se il passaggio precedente ha esito negativo, utilizzare il <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>nome breve (e il token di chiave pubblica se presente) per chiamare .

##### <a name="assembly-references-by-baml-types"></a>Riferimenti agli assembly da tipi BAML:

I riferimenti agli assembly per i tipi utilizzati nella produzione BAML sono sempre completi, come output dell'attività di compilazione.

01. Il contesto dello schema <xref:System.AppDomain> XAML WPF scorre l'applicazione WPF, cercando un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, tale assieme viene utilizzato per la risoluzione.

02. In caso contrario, per caricare un assembly viene utilizzata una delle tecniche seguenti:

    - Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> il nome completo.
  
    - Se una combinazione di nome breve e token di chiave pubblica corrisponde all'assembly da cui è stato caricato il BAML, utilizzare tale assembly.

    - Utilizzare il nome breve, <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>ovvero il token di chiave pubblica, per chiamare .

## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
