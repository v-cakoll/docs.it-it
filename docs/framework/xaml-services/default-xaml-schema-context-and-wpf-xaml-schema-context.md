---
title: Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: f29d9eb481903b06ee1f35424baeb055a396b7c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663254"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
Un contesto dello schema XAML è un'entità concettuale che può fregiarsi come una produzione XAML che usa un vocabolario XAML specifico interagisce con l'oggetto di comportamento, tra cui come vengono risolti mapping dei tipi, come gli assembly vengono caricati, come determinato reader e writer di scrittura le impostazioni vengono interpretate. Questo argomento descrive le funzionalità di servizi XAML di .NET Framework e il contesto dello schema XAML predefinito associato, che si basa sul sistema di tipi CLR. Questo argomento descrive anche il contesto dello schema XAML utilizzato per WPF.  
  
## <a name="default-xaml-schema-context"></a>Contesto dello Schema XAML predefinito  
 Servizi XAML di .NET framework sia implementa e utilizza un contesto di schema XAML predefinito. Il comportamento del contesto dello schema XAML predefinito non è sempre completamente visibile nell'API del <xref:System.Xaml.XamlSchemaContext> classe. Tuttavia, in molti casi il comportamento che influenza il contesto dello schema XAML predefinito è osservabile tramite l'API comuni del sistema di tipi XAML, ad esempio i membri del <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType>, o tramite le API esposte su reader XAML e writer XAML che usano contesto dello schema XAML predefinito.  
  
 È possibile creare un <xref:System.Xaml.XamlSchemaContext> che incapsula il comportamento predefinito chiamando il <xref:System.Xaml.XamlSchemaContext> costruttore. Verrà creato in modo esplicito il contesto dello schema XAML predefinito. Stesso contesto dello schema XAML predefinito viene creato in modo implicito, se si inizializza un writer XAML tramite le API che non accettano in modo esplicito o un lettore XAML un <xref:System.Xaml.XamlSchemaContext> parametro di input.  
  
 Contesto dello schema XAML predefinito si basa sulla reflection CLR per il relativo comportamento di mapping di tipo. Inclusa l'analisi CLR definizione <xref:System.Type>ed elementi correlati <xref:System.Reflection.PropertyInfo> o <xref:System.Reflection.MethodInfo>. Inoltre, attribuzione di CLR tipi o membri viene usato per immettere le specifiche per il tipo XAML o informazioni sul membro XAML che usa il tipo di supporto di CLR. Contesto dello schema XAML predefinito non richiede le tecniche di estensione del sistema di tipi, ad esempio il `Invoker` pattern, perché le informazioni necessarie sono disponibili dal sistema di tipi CLR.  
  
 Per la logica di caricamento di assembly, il contesto dello schema XAML predefinito si basa principalmente su qualsiasi valore di assembly specificati nel mapping dello spazio dei nomi XAML. Inoltre, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> può indicare un assembly da caricare, per gli scenari, ad esempio il caricamento di tipi interni.  
  
## <a name="wpf-xaml-schema-context"></a>Contesto dello Schema XAML WPF  
 Il contesto dello schema XAML WPF è descritto in questo argomento, poiché l'implementazione WPF offre un'interessante illustrazione dei tipi di funzionalità che possono essere introdotti implementando un contesto dello schema XAML non predefinito. Inoltre, il concetto di contesto dello schema XAML non viene trattato in modo considerevole nella documentazione di WPF che punta WPF XAML; il comportamento che il contesto dello schema XAML consente solo potrebbe essere completamente comprensibile se integrata con la descrizione di come funziona il contesto dello schema XAML predefinito. Il contesto dello schema XAML WPF implementa il comportamento seguente.  
  
 **Esegue l'override di ricerca:** WPF offre alcuni modelli di contenuto per XAML in cui sono presenti proprietà di contenuto XAML che funzionano senza avere <xref:System.Windows.Markup.ContentPropertyAttribute> con attributi. <xref:System.Xaml.XamlType.LookupContentProperty%2A> le sostituzioni per WPF implementano questo comportamento.  
  
 **Differimento per le espressioni di WPF:** WPF include diverse classi di espressioni che rinviano un valore fino a quando non è disponibile un contesto di runtime. Inoltre, espansione del modello è un comportamento di runtime che si basa sulle tecniche di rinvio.  
  
 **Digitare le ottimizzazioni di ricerca di sistema:** WPF offre un esteso XAML vocabolario e l'oggetto modello, tra cui le definizioni dei membri di classe di base che ereditano da centinaia di classi definita in WPF. Inoltre, WPF stesso viene distribuito tra diversi assembly. WPF consente di ottimizzare la ricerca del relativo tipo utilizzando le tabelle di ricerca e altre tecniche. Ciò fornisce miglioramenti delle prestazioni tramite il contesto dello schema XAML predefinito e la ricerca del relativo tipo basati su CLR. Nei casi in cui tipi non sono disponibili in una tabella di ricerca, il comportamento Usa tecniche di contesto dello schema XAML che sono simili per il contesto dello schema XAML predefinito.  
  
 **Estensione XamlType e XamlMember:** WPF consente di estendere i concetti di proprietà con proprietà di dipendenza e concetti relativi a eventi con gli eventi indirizzati. Per comprendere questi concetti maggiore visibilità per le operazioni di elaborazione di XAML, WPF offre <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>e aggiunge le proprietà interne che presentano proprietà di dipendenza e le caratteristiche di eventi indirizzati.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Accesso al contesto dello Schema XAML WPF  
 Se si usa tecniche XAML che si basano su WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> o <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, il contesto dello schema XAML WPF è già in uso su tali reader XAML e le implementazioni del writer XAML.  
  
 Se si utilizza altri reader XAML o le implementazioni del writer XAML che non si inizializza con il contesto dello schema XAML WPF, potrebbe essere in grado di ottenere il contesto dello schema da un lavoro WPF XAML <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. È quindi possibile usare questo valore come inizializzazione di un'altra API che usano un <xref:System.Xaml.XamlSchemaContext>. Ad esempio, è possibile chiamare <xref:System.Xaml.XamlXmlReader.%23ctor%2A> per l'inizializzazione e passare il contesto dello schema XAML WPF. In alternativa, è possibile usare il contesto dello schema XAML WPF per le operazioni di sistema di tipo XAML. Potrebbe trattarsi di inizializzazione della costruzione di un <xref:System.Xaml.XamlType> oppure <xref:System.Xaml.XamlMember>, o la chiamata <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Si noti che se si accede alcuni aspetti di XAML WPF da un puro prospettive di flusso di nodi XAML, alcune delle funzionalità di framework WPF potrebbe non avere ancora eseguito azioni. Ad esempio, i modelli WPF per i controlli non ancora applicati. Pertanto se si accede a una proprietà che, in fase di esecuzione, potrebbe essere popolata con una struttura ad albero visuale completa, è possibile visualizzare solo un valore della proprietà che fa riferimento a un modello. Il contesto del servizio fornito per le estensioni di markup WPF inoltre non può essere accurato se fornite da una situazione non di runtime e può generare eccezioni quando si tenta di scrivere un oggetto grafico.  
  
## <a name="xaml-and-assembly-loading"></a>XAML e il caricamento di Assembly  
 Assembly caricato per XAML e dei servizi XAML di .NET Framework si integra con il concetto definito da CLR di <xref:System.AppDomain>. Un contesto dello schema XAML interpreta la modalità di caricare gli assembly o trovare i tipi in fase di esecuzione o in fase di progettazione, in base all'utilizzo di <xref:System.AppDomain> e ad altri fattori. La logica è leggermente diversa a seconda che il XAML sia XAML loose per un reader XAML, viene compilato in una DLL da XAML `XamlBuildTask`, o viene generato BAML da WPF `PresentationBuildTask`.  
  
 Il contesto dello schema XAML per WPF si integra con il modello applicazione WPF, che a sua volta utilizza <xref:System.AppDomain> e da altri fattori che sono dettagli di implementazione WPF.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>Lettore XAML di input (XAML loose)  
  
1. Il contesto dello schema XAML esegue l'iterazione attraverso la <xref:System.AppDomain> dell'applicazione, alla ricerca di un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dalla più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly viene utilizzato per la risoluzione.  
  
2. In caso contrario, una delle seguenti tecniche basate su CLR <xref:System.Reflection.Assembly> API vengono utilizzati per caricare un assembly:  
  
    - Se il nome è qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
    - Se ha esito negativo del passaggio precedente, usare il nome breve e token di chiave pubblica se presente, da chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    - Se il nome non qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` viene usato per Windows Communication Foundation (WCF) e Windows Workflow Foundation.  
  
 Si noti che fa riferimento all'assembly tramite `XamlBuildTask` sono sempre completi.  
  
1. Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
2. Se ha esito negativo del passaggio precedente, usare il nome breve e token di chiave pubblica se presente, da chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Esistono due aspetti legati al caricamento di assembly per BAML: il caricamento dell'assembly iniziale che contiene il BAML come componente e il caricamento di assembly di supporto di tipo per qualsiasi tipo fa riferimento la produzione BAML.  
  
##### <a name="assembly-load-for-initial-markup"></a>Caricamento dell'assembly per il markup iniziale:  
 Il riferimento all'assembly da cui caricare il markup è sempre non qualificato.  
  
1. Il contesto dello schema XAML WPF esegue l'iterazione attraverso la <xref:System.AppDomain> dell'applicazione WPF, alla ricerca di un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dalla più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly viene utilizzato per la risoluzione.  
  
2. Se ha esito negativo del passaggio precedente, usare il nome breve e token di chiave pubblica se presente, da chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Riferimenti agli assembly dai tipi BAML:  
 I riferimenti ad assembly per i tipi utilizzati nell'ambiente di produzione BAML sono sempre completamente qualificati, come output dell'attività di compilazione.  
  
1. Il contesto dello schema XAML WPF esegue l'iterazione attraverso la <xref:System.AppDomain> dell'applicazione WPF, alla ricerca di un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dalla più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly viene utilizzato per la risoluzione.  
  
2. In caso contrario, una delle tecniche descritte di seguito viene usata per caricare un assembly:  
  
    - Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
    - Se un nome breve e combinazione token pubblico corrispondente all'assembly che è stato caricato il BAML da, usare tale assembly.  
  
    - Usare nome breve e token di chiave pubblica per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
