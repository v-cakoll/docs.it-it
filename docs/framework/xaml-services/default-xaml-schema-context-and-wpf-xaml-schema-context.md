---
title: Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: 7
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ec5e29ae9022470f8b583dc1b673a0b93040c862
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
Un contesto dello schema XAML è un'entità concettuale che qualifica come una produzione XAML che usa un determinato vocabolario XAML interagisce con l'oggetto di scrittura del comportamento, incluso come risolvere, mapping dei tipi come assembly vengono caricati, come determinato reader e writer le impostazioni vengono interpretate. In questo argomento vengono descritte le funzionalità di servizi XAML di .NET Framework e il contesto dello schema XAML predefinito associato, basato sul sistema di tipi CLR. Questo argomento descrive anche il contesto dello schema XAML che viene utilizzato per WPF.  
  
## <a name="default-xaml-schema-context"></a>Contesto dello Schema XAML predefinito  
 Servizi XAML di .NET framework implementa sia utilizza un contesto di schema XAML predefinito. Il comportamento del contesto dello schema XAML predefinito non è sempre completamente visibile nell'API del <xref:System.Xaml.XamlSchemaContext> classe. Tuttavia, in molti casi il comportamento che influenza il contesto dello schema XAML predefinito è osservabile tramite l'API comuni del sistema di tipi XAML, ad esempio i membri di <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType>, o tramite le API esposte in reader XAML e writer XAML che usano contesto dello schema XAML predefinito.  
  
 È possibile creare un <xref:System.Xaml.XamlSchemaContext> che incapsula le impostazioni predefinite tramite la chiamata di <xref:System.Xaml.XamlSchemaContext> costruttore. Verrà creato in modo esplicito il contesto dello schema XAML predefinito. Contesto dello schema XAML predefinito stesso viene creato in modo implicito, se si inizializza un reader XAML o un writer XAML utilizzando le API che non accettano in modo esplicito un <xref:System.Xaml.XamlSchemaContext> parametro di input.  
  
 Contesto dello schema XAML predefinito si basa sulla reflection CLR per il relativo comportamento di mapping del tipo. Inclusa l'analisi CLR definizione <xref:System.Type>e correlati <xref:System.Reflection.PropertyInfo> o <xref:System.Reflection.MethodInfo>. Inoltre, attribuzione di CLR da tipi o membri verrà utilizzati per compilare le specifiche per tipo XAML o informazioni sui membri XAML che utilizza il tipo di supporto di CLR. Contesto dello schema XAML predefinito non richiede le tecniche di estensione del sistema di tipo, ad esempio il `Invoker` di schema, perché le informazioni necessarie sono disponibili dal sistema di tipi CLR.  
  
 Per la logica di caricamento di assembly, il contesto dello schema XAML predefinito si basa principalmente sui valori di assembly specificati nel mapping dello spazio dei nomi XAML. Inoltre, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> possibile suggerisca un assembly da caricare, per scenari quali il caricamento di tipi interni.  
  
## <a name="wpf-xaml-schema-context"></a>Contesto dello Schema XAML WPF  
 Il contesto dello schema XAML WPF viene descritto in questo argomento, poiché l'implementazione di WPF offre un'interessante illustrazione dei tipi di funzionalità che possono essere introdotti implementando un contesto dello schema XAML non predefinito. Inoltre, il concetto di contesto dello schema XAML non è illustrato molto nella documentazione di WPF che risolve XAML WPF. potrebbe essere completamente comprensibile se integrato con una descrizione del funzionamento di contesto dello schema XAML predefinito solo il comportamento che consente il contesto dello schema XAML. Il contesto dello schema XAML WPF implementa il comportamento seguente.  
  
 **Esegue l'override di ricerca:** WPF include alcuni modelli di contenuto per il codice XAML in cui sono presenti le proprietà del contenuto XAML che funzionano senza avere <xref:System.Windows.Markup.ContentPropertyAttribute> con attributi. <xref:System.Xaml.XamlType.LookupContentProperty%2A> le sostituzioni per WPF implementano tale comportamento.  
  
 **Rinvio per le espressioni di WPF:** WPF include diverse classi di espressioni che rinvia un valore fino a quando non è disponibile un contesto di runtime. Inoltre, l'espansione del modello è un comportamento di runtime che si basa sulle tecniche di esclusione.  
  
 **Digitare le ottimizzazioni di ricerca di sistema:** WPF è disponibile un completo XAML vocabolario e un oggetto modello, incluse le definizioni dei membri di classe di base che ereditano da centinaia di classi WPF definite. Inoltre, WPF stesso viene distribuito tra diversi assembly. WPF consente di ottimizzare la ricerca del tipo utilizzando le tabelle di ricerca e altre tecniche. Questo fornisce miglioramenti delle prestazioni nel contesto dello schema XAML predefinito e la ricerca del relativo tipo basato su CLR. Nei casi in cui non esistono tipi in una tabella di ricerca, il comportamento utilizza tecniche di contesto dello schema XAML che sono simili al contesto dello schema XAML predefinito.  
  
 **Estensione XamlType e XamlMember:** WPF estende i concetti di proprietà con le proprietà di dipendenza e concetti di eventi con eventi indirizzati. Per assegnare a questi concetti maggiore visibilità per le operazioni di elaborazione XAML, WPF estende <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>e aggiunge le proprietà interne che presentano proprietà di dipendenza e caratteristiche evento indirizzato.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Accesso al contesto dello Schema XAML WPF  
 Se si utilizza tecniche XAML basato su WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> o <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, il contesto dello schema XAML di WPF è già in uso su tali reader XAML e le implementazioni del writer XAML.  
  
 Se si usano altri reader XAML o le implementazioni del writer XAML che non si inizializza con il contesto dello schema XAML WPF, è possibile ottenere un utilizzo XAML di WPF contesto dello schema da <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. È quindi possibile utilizzare questo valore come l'inizializzazione di altre API che utilizzano un <xref:System.Xaml.XamlSchemaContext>. Ad esempio, è possibile chiamare <xref:System.Xaml.XamlXmlReader.%23ctor%2A> per l'inizializzazione e passare il contesto dello schema XAML di WPF. In alternativa, è possibile usare il contesto dello schema XAML WPF per le operazioni di sistema di tipo XAML. Potrebbe trattarsi di inizializzazione della costruzione di un <xref:System.Xaml.XamlType> o <xref:System.Xaml.XamlMember>, o la chiamata <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Si noti che se si accede alcuni aspetti di WPF XAML da un pure prospettive di flusso di nodi XAML, alcune delle funzionalità di framework WPF potrebbe non avere ancora eseguito azioni. Ad esempio, i modelli per i controlli WPF non sono ancora applicati. Pertanto se si accede a una proprietà in fase di esecuzione potrebbe essere popolata con una struttura ad albero visivo completa, potrebbero visualizzare solo un valore della proprietà che fa riferimento a un modello. Il contesto del servizio fornito per le estensioni di markup WPF non essere accurato se fornito da una situazione non di runtime e può generare eccezioni quando si tenta di scrivere un oggetto grafico.  
  
## <a name="xaml-and-assembly-loading"></a>XAML e il caricamento di Assembly  
 Assembly caricato per XAML e i servizi XAML di .NET Framework si integra con il concetto definito da CLR di <xref:System.AppDomain>. Un contesto dello schema XAML interpreta la modalità di caricamento di assembly o di ricerca dei tipi in fase di esecuzione o la fase di progettazione, in base all'utilizzo di <xref:System.AppDomain> e ad altri fattori. La logica è leggermente diversa a seconda che il codice XAML sia XAML separato per un reader XAML, viene compilato in una DLL da XAML `XamlBuildTask`, o BAML generato da WPF `PresentationBuildTask`.  
  
 Contesto dello schema XAML per WPF si integra con il modello applicazione WPF, che a sua volta utilizza <xref:System.AppDomain> nonché altri fattori che sono i dettagli di implementazione di WPF.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>Reader XAML di input (XAML separato)  
  
1.  Contesto dello schema XAML scorre il <xref:System.AppDomain> dell'applicazione, cercare un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dal più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly è utilizzato per la risoluzione.  
  
2.  In caso contrario, una delle tecniche seguenti basate su CLR <xref:System.Reflection.Assembly> API vengono utilizzati per caricare un assembly:  
  
    -   Se il nome qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
    -   Se il passaggio precedente ha esito negativo, utilizzare il nome breve e token di chiave pubblica se presente, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    -   Se il nome non qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` viene utilizzato per [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)] e Windows Workflow Foundation.  
  
 Si noti che i riferimenti agli assembly tramite `XamlBuildTask` sono sempre completi.  
  
1.  Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
2.  Se il passaggio precedente ha esito negativo, utilizzare il nome breve e token di chiave pubblica se presente, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Sono disponibili due opzioni per il caricamento di assembly per BAML: il caricamento dell'assembly iniziale che contiene il BAML come componente e il caricamento degli assembly i tipo di backup di tutti i tipi a cui fa riferimento la produzione BAML.  
  
##### <a name="assembly-load-for-initial-markup"></a>Caricamento dell'assembly per il markup iniziale:  
 Il riferimento all'assembly da cui caricare il markup è sempre non qualificato.  
  
1.  Scorre il contesto dello schema XAML WPF di <xref:System.AppDomain> dell'applicazione WPF, ricerca di un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dal più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly è utilizzato per la risoluzione.  
  
2.  Se il passaggio precedente ha esito negativo, utilizzare il nome breve e token di chiave pubblica se presente, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Riferimenti agli assembly dai tipi BAML:  
 Riferimenti agli assembly per i tipi utilizzati nella produzione BAML sono sempre completi, come output dell'attività di compilazione.  
  
1.  Scorre il contesto dello schema XAML WPF di <xref:System.AppDomain> dell'applicazione WPF, ricerca di un assembly già caricato che corrisponde a tutti gli aspetti del nome, a partire dal più recente assembly caricato. Se viene trovata una corrispondenza, l'assembly è utilizzato per la risoluzione.  
  
2.  In caso contrario, una delle tecniche seguenti viene utilizzata per caricare un assembly:  
  
    -   Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sul nome completo.  
  
    -   Se un nome breve + pubblica token combinazione corrisponde all'assembly caricato dal BAML, utilizzare tale assembly.  
  
    -   Utilizzare il nome breve e token di chiave pubblica per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni su strutture e concetti del flusso del nodo XAML](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
