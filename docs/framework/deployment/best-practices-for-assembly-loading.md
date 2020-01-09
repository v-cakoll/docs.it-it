---
title: Procedure consigliate per il caricamento di assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies,binding
- LoadFrom method
- default load context
- TypeLoadException class,causes
- assembly loading errors
- load contexts
- assemblies,loading
- LoadWithPartialName method
- load-from context
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
ms.openlocfilehash: d1b6c2cd9f96a4acf48cbced48a86bc3e3409562
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716581"
---
# <a name="best-practices-for-assembly-loading"></a>Procedure consigliate per il caricamento di assembly
Questo articolo illustra come evitare problemi di identità del tipo che possono causare eccezioni <xref:System.InvalidCastException>, <xref:System.MissingMethodException> e altri errori. Nell'articolo vengono discussi i seguenti suggerimenti:  
  
- [Esaminare i vantaggi e gli svantaggi dei contesti di caricamento](#load_contexts)  
  
- [Evitare l'associazione di nomi di assembly parziali](#avoid_partial_names)  
  
- [Evitare il caricamento di un assembly in più contesti](#avoid_loading_into_multiple_contexts)  
  
- [Evitare il caricamento di più versioni di un assembly nello stesso contesto](#avoid_loading_multiple_versions)  
  
- [Considerare il passaggio al contesto di caricamento predefinito](#switch_to_default)  
  
 Il primo suggerimento [Esaminare i vantaggi e gli svantaggi dei contesti di caricamento](#load_contexts) fornisce informazioni di base per le altre indicazioni, che dipendono dalla conoscenza dei contesti di caricamento.  
  
<a name="load_contexts"></a>   
## <a name="understand-the-advantages-and-disadvantages-of-load-contexts"></a>Esaminare i vantaggi e gli svantaggi dei contesti di caricamento  
 All'interno di un dominio dell'applicazione gli assembly possono essere caricati in uno dei tre contesti disponibili o essere caricati senza contesto:  
  
- Il contesto di caricamento di default contiene gli assembly rilevati mediante l'esecuzione di probe nella Global Assembly Cache, nello store di assembly dell'host se il runtime è gestito tramite host (ad esempio in SQL Server) e in <xref:System.AppDomainSetup.ApplicationBase%2A> e <xref:System.AppDomainSetup.PrivateBinPath%2A> nel dominio dell'applicazione. La maggior parte degli overload del metodo <xref:System.Reflection.Assembly.Load%2A> carica gli assembly in questo contesto.  
  
- Il contesto di origine del caricamento contiene assembly caricati da percorsi nei quali il caricatore non esegue ricerche. Ad esempio i componenti aggiuntivi potrebbero essere installati in una directory che non si trova nel percorso dell'applicazione. <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType> e <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> sono esempi di metodi che vengono caricati in base al percorso.  
  
- Il contesto Reflection-Only contiene assembly caricati con i metodi <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> e <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>. Il codice in questo contesto non può essere eseguito, pertanto non viene discusso in questo argomento. Per altre informazioni, vedere [Procedura: Caricare assembly nel contesto Reflection-Only](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
- Se un assembly dinamico temporaneo è stato generato tramite reflection emit non è presente in nessun contesto. Inoltre la maggior parte degli assembly caricati con il metodo <xref:System.Reflection.Assembly.LoadFile%2A> vengono caricati senza contesto mentre gli assembly caricati da matrici di byte vengono caricati senza contesto a meno che la loro identità, dopo l'applicazione dei criteri, non stabilisca che si trovano nella Global Assembly Cache.  
  
 I contesti di esecuzione presentano vantaggi e svantaggi, illustrati nelle sezioni seguenti.  
  
### <a name="default-load-context"></a>Contesto di caricamento predefinito  
 Quando gli assembly vengono caricati nel contesto di caricamento predefinito le relative dipendenze vengono caricate automaticamente. Le dipendenze caricate nel contesto di caricamento predefinito vengono rilevate automaticamente per gli assembly che si trovano in tale contesto o nel contesto di origine del caricamento. Il caricamento tramite identità dell'assembly aumenta la stabilità delle applicazioni impedendo l'uso di versioni sconosciute degli assembly. Vedere la sezione [Evitare l'associazione di nomi di assembly parziali](#avoid_partial_names).  
  
 L'uso del contesto di caricamento predefinito presenta i seguenti svantaggi:  
  
- Le dipendenze caricate in altri contesti non sono disponibili.  
  
- Non è possibile caricare assembly da percorsi esterni al percorso di esecuzione del probe nel contesto di caricamento predefinito.  
  
### <a name="load-from-context"></a>Contesto di origine del caricamento  
 Il contesto di origine del caricamento consente di caricare un assembly da un percorso esterno al percorso dell'applicazione e pertanto non incluso nell'esecuzione del probe. Consente il rilevamento e il caricamento delle dipendenze da tale percorso, perché le informazioni del percorso sono gestite dal contesto. Inoltre gli assembly in questo contesto possono usare le dipendenze caricate nel contesto di caricamento predefinito.  
  
 Il caricamento di assembly con il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o uno degli altri metodi di caricamento in base al percorso presenta i seguenti svantaggi:  
  
- Se è già caricato un assembly con la stessa identità <xref:System.Reflection.Assembly.LoadFrom%2A> restituisce l'assembly caricato anche se è stato specificato un percorso diverso.  
  
- Se un assembly viene caricato con <xref:System.Reflection.Assembly.LoadFrom%2A> e successivamente un assembly nel contesto di caricamento predefinito tenta di caricare lo stesso assembly in base al nome visualizzato, il tentativo di caricamento non riesce. Questa situazione può verificarsi quando un assembly è deserializzato.  
  
- Se un assembly viene caricato con <xref:System.Reflection.Assembly.LoadFrom%2A> e il percorso di esecuzione del probe include un assembly con la stessa identità ma situato in un percorso diverso possono verificarsi eccezioni <xref:System.InvalidCastException>, <xref:System.MissingMethodException> o altri comportamenti imprevisti.  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A> richiede <xref:System.Security.Permissions.FileIOPermissionAccess.Read?displayProperty=nameWithType> e <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery?displayProperty=nameWithType> o <xref:System.Net.WebPermission> per il percorso specificato.  
  
- Se esiste un'immagine nativa per l'assembly tale immagine non viene usata.  
  
- L'assembly non può essere caricato come modulo indipendente dal dominio.  
  
- Nelle versioni 1.0 e 1.1 di .NET Framework i criteri non vengono applicati.  
  
### <a name="no-context"></a>Nessun contesto  
 Il caricamento senza contesto è l'unica opzione disponibile per gli assembly temporanei generati con reflection emit. Il caricamento senza contesto è l'unico metodo per caricare più assembly con la stessa identità in un unico dominio applicazione. Inoltre evita l'esecuzione del probe.  
  
 Gli assembly caricati da matrici di byte vengono caricati senza contesto a meno che l'identità dell'assembly, stabilita quando vengono applicati i criteri, non corrisponda all'identità di un assembly nella Global Assembly Cache. In tal caso l'assembly viene caricato dalla Global Assembly Cache.  
  
 Il caricamento di assembly senza contesto presenta i seguenti svantaggi:  
  
- Gli altri assembly non possono essere associati agli assembly caricati senza contesto, a meno che non si gestisca l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
- Le dipendenze non vengono caricate automaticamente. È possibile precaricarle senza contesto, precaricarle nel contesto di caricamento predefinito o caricarle tramite la gestione dell'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
- Il caricamento di più assembly con la stessa identità senza contesto può causare problemi di identità del tipo simili a quelli causati dal caricamento di assembly con la stessa identità in più contesti. Vedere [Evitare il caricamento di un assembly in più contesti](#avoid_loading_into_multiple_contexts).  
  
- Se esiste un'immagine nativa per l'assembly tale immagine non viene usata.  
  
- L'assembly non può essere caricato come modulo indipendente dal dominio.  
  
- Nelle versioni 1.0 e 1.1 di .NET Framework i criteri non vengono applicati.  
  
<a name="avoid_partial_names"></a>   
## <a name="avoid-binding-on-partial-assembly-names"></a>Evitare l'associazione di nomi di assembly parziali  
 L'associazione di un nome parziale si verifica quando al caricamento di un assembly si specifica solo una parte del nome visualizzato dell'assembly (<xref:System.Reflection.Assembly.FullName%2A>). Ad esempio è possibile chiamare il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> solo con il nome semplice dell'assembly, omettendo la versione, le impostazioni cultura e il token di chiave pubblica. Oppure è possibile chiamare il metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> il quale prima chiama il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, quindi se questo non individua l'assembly esegue una ricerca nella Global Assembly Cache e carica la versione disponibile più recente dell'assembly.  
  
 L'associazione di nomi parziali può causare numerosi problemi, inclusi i seguenti:  
  
- Il metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> potrebbe caricare un assembly diverso con lo stesso nome semplice. Ad esempio è possibile che due applicazioni installino nella Global Assembly Cache due assembly completamente diversi che hanno lo stesso nome semplice `GraphicsLibrary`.  
  
- L'assembly realmente caricato potrebbe non essere compatibile con le versioni precedenti. Ad esempio se non si specifica la versione potrebbe essere caricata una versione di molto successiva a quella che il programma doveva usare in origine. Le modifiche presenti nella versione successiva potrebbero causare errori nell'applicazione.  
  
- L'assembly realmente caricato potrebbe non essere compatibile con le versioni successive. Ad esempio l'applicazione può essere stata creata e sottoposta a test con la versione più recente di un assembly, ma l'associazione parziale potrebbe caricare una versione di molto anteriore, che non dispone delle funzionalità usate dall'applicazione.  
  
- L'installazione di nuove applicazioni può compromettere il funzionamento delle applicazioni esistenti. Il funzionamento di un'applicazione che usa il metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A> può essere compromesso dall'installazione di una versione più recente e non compatibile di un assembly condiviso.  
  
- Può verificarsi il caricamento imprevisto di dipendenze. Se si caricano due assembly che condividono una dipendenza, il caricamento con associazione parziale può far sì che un assembly usi un componente con il quale non è stato compilato né testato.  
  
 Per i problemi che può causare, il metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A> è stato contrassegnato come obsoleto. Si consiglia di usare il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> e di specificare i nomi visualizzati degli assembly completi. Vedere [Comprendere i vantaggi e gli svantaggi dei contesti di caricamento](#load_contexts) e [Considerare il passaggio al contesto di caricamento predefinito](#switch_to_default).  
  
 Se si vuole usare il metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A> perché semplifica il caricamento degli assembly, tenere presente che l'interruzione del funzionamento dell'applicazione con un messaggio di errore che identifica l'assembly mancante è probabilmente un'esperienza utente migliore all'uso automatico di una versione sconosciuta dell'assembly, che potrebbe causare comportamenti imprevedibili e problemi di sicurezza.  
  
<a name="avoid_loading_into_multiple_contexts"></a>   
## <a name="avoid-loading-an-assembly-into-multiple-contexts"></a>Evitare il caricamento di un assembly in più contesti  
 Il caricamento di un assembly in più contesti può causare problemi di identità del tipo. Quando lo stesso tipo viene caricato dallo stesso assembly in due contesti diversi è come se fossero stati caricati due tipi diversi con lo stesso nome. Se si tenta di eseguire il cast di un tipo all'altro tipo viene generata un'eccezione <xref:System.InvalidCastException> con un messaggio ambiguo indicante che non è possibile eseguire il cast del tipo `MyType` al tipo `MyType`.  
  
 Si supponga ad esempio che l'interfaccia `ICommunicate` venga dichiarata in un assembly `Utility` al quale fa riferimento sia il programma che altri assembly caricati dal programma stesso. Gli altri assembly contengono tipi che implementano l'interfaccia `ICommunicate` e consentono al programma di usarli.  
  
 Si consideri ora cosa accade quando viene eseguito il programma. Gli assembly ai quali fa riferimento il programma vengono caricati nel contesto di caricamento predefinito. Se si carica un assembly di destinazione in base all'identità con il metodo <xref:System.Reflection.Assembly.Load%2A>, l'assembly e le relative dipendenze vengono caricati nel contesto di caricamento predefinito. Sia il programma sia l'assembly di destinazione useranno lo stesso assembly `Utility`.  
  
 Si supponga tuttavia di caricare l'assembly di destinazione in base al percorso del file, usando il metodo <xref:System.Reflection.Assembly.LoadFile%2A>. L'assembly viene caricato senza contesto, pertanto le relative dipendenze non vengono caricate automaticamente. Si potrebbe disporre di un gestore per l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per fornire la dipendenza e caricare l'assembly `Utility` senza contesto mediante il metodo <xref:System.Reflection.Assembly.LoadFile%2A>. Ora quando si crea un'istanza di un tipo incluso nell'assembly di destinazione e si tenta di assegnarla a una variabile di tipo `ICommunicate` viene restituita un'eccezione <xref:System.InvalidCastException> perché il runtime considera le interfacce `ICommunicate` nelle due copie dell'assembly `Utility` come tipi diversi.  
  
 Esistono molti altri scenari in cui un assembly può essere caricato in più contesti. L'approccio migliore consiste nell'evitare conflitti riposizionando l'assembly di destinazione nel percorso dell'applicazione e usando il metodo <xref:System.Reflection.Assembly.Load%2A> con il nome visualizzato completo. L'assembly viene così caricato nel contesto di caricamento predefinito ed entrambi gli assembly usano lo stesso assembly `Utility`.  
  
 Se l'assembly di destinazione deve rimanere al di fuori del percorso dell'applicazione è possibile usare il <xref:System.Reflection.Assembly.LoadFrom%2A> metodo per caricarlo nel contesto di origine del caricamento. Se l'assembly di destinazione è stato compilato con un riferimento all'assembly `Utility` dell'applicazione userà l'assembly `Utility` caricato dall'applicazione nel contesto di caricamento predefinito. Si noti che possono verificarsi problemi se l'assembly di destinazione presenta una dipendenza da una copia dell'assembly `Utility` situata al di fuori del percorso dell'applicazione. Se tale assembly viene caricato nel contesto di origine del caricamento prima che l'applicazione carichi l'assembly `Utility`, il caricamento dell'applicazione avrà esito negativo.  
  
 La sezione [Considerare il passaggio al contesto di caricamento predefinito](#switch_to_default) illustra le alternative all'uso di caricamenti del percorso del file quali <xref:System.Reflection.Assembly.LoadFile%2A> e <xref:System.Reflection.Assembly.LoadFrom%2A>.  
  
<a name="avoid_loading_multiple_versions"></a>   
## <a name="avoid-loading-multiple-versions-of-an-assembly-into-the-same-context"></a>Evitare il caricamento di più versioni di un assembly nello stesso contesto  
 Il caricamento di più versioni di un assembly in un unico contesto di caricamento può causare problemi di identità del tipo. Il fatto che lo stesso tipo venga caricato da due versioni dello stesso assembly equivale al caricamento di due tipi diversi con lo stesso nome. Se si tenta di eseguire il cast di un tipo all'altro tipo viene generata un'eccezione <xref:System.InvalidCastException> con un messaggio ambiguo indicante che non è possibile eseguire il cast del tipo `MyType` al tipo `MyType`.  
  
 Ad esempio il programma potrebbe caricare immediatamente una versione dell'assembly `Utility` e in seguito caricare un altro assembly che carica una versione diversa dell'assembly `Utility`. Oppure un errore di codifica potrebbe far sì che due percorsi di codice diversi dell'applicazione carichino versioni diverse di un assembly.  
  
 Nel contesto di caricamento predefinito questo problema può verificarsi quando si usa il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> e si specificano nomi visualizzati degli assembly completi che includono numeri di versione diversi. Per gli assembly caricati senza contesto, il problema può essere causato dall'uso del metodo <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> per caricare lo stesso assembly da percorsi diversi. Il runtime considera due assembly caricati da percorsi diversi come assembly diversi, anche se le loro identità sono uguali.  
  
 Oltre ai problemi di identità del tipo, più versioni di un assembly possono causare un'eccezione <xref:System.MissingMethodException> se un tipo caricato da una determinata versione dell'assembly viene passato a codice che prevede di ricevere quel tipo da una versione diversa. Ad esempio il codice potrebbe prevedere un metodo aggiunto alla versione successiva.  
  
 Errori più insidiosi possono verificarsi se il comportamento del tipo è cambiato da una versione all'altra. Ad esempio un metodo potrebbe generare un'eccezione imprevista o restituire un valore imprevisto.  
  
 Esaminare attentamente il codice per garantire che sia caricata una sola versione di un assembly. È possibile usare il metodo <xref:System.AppDomain.GetAssemblies%2A?displayProperty=nameWithType> per determinare quali assembly vengono caricati in un determinato momento.  
  
<a name="switch_to_default"></a>   
## <a name="consider-switching-to-the-default-load-context"></a>Considerare il passaggio al contesto di caricamento predefinito  
 Esaminare i modelli di caricamento e distribuzione degli assembly dell'applicazione. È possibile eliminare gli assembly caricati da matrici di byte? È possibile spostare gli assembly nel percorso di esecuzione del probe? Se gli assembly si trovano nella Global Assembly Cache o nel percorso di esecuzione del probe del dominio applicazione (vale a dire <xref:System.AppDomainSetup.ApplicationBase%2A> e <xref:System.AppDomainSetup.PrivateBinPath%2A>) è possibile caricare l'assembly tramite l'identità.  
  
 Se non è possibile inserire tutti gli assembly nel percorso di esecuzione del probe, considerare alternative quali l'uso del modello del componente aggiuntivo di .NET Framework, l'inserimento degli assembly nella Global Assembly Cache o la creazione di domini applicazione.  
  
### <a name="consider-using-the-net-framework-add-in-model"></a>Considerare l'uso del modello del componente aggiuntivo di .NET Framework  
 Se si usa il contesto di origine del caricamento per implementare i componenti aggiuntivi, che in genere non vengono installati nella base dell'applicazione, usare il modello del componente aggiuntivo di .NET Framework. Questo modello fornisce l'isolamento a livello del dominio applicazione o del processo e non richiede alcuna gestione dei domini applicazione da parte dell'utente. Per informazioni sul modello del componente aggiuntivo, vedere [Componenti aggiuntivi ed estensibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
### <a name="consider-using-the-global-assembly-cache"></a>Considerare l'uso della Global Assembly Cache  
 L'inserimento degli assembly nella Global Assembly Cache consente di sfruttare il vantaggio di un percorso dell'assembly condiviso al di fuori della base dell'applicazione, senza rinunciare ai vantaggi del contesto di caricamento predefinito né avere gli svantaggi degli altri contesti.  
  
### <a name="consider-using-application-domains"></a>Considerare l'uso dei domini applicazione  
 Se risulta impossibile distribuire alcuni assembly nel percorso di esecuzione del probe dell'applicazione, considerare la possibilità di creare di un nuovo dominio applicazione per tali assembly. Usare un oggetto <xref:System.AppDomainSetup> per creare il nuovo dominio applicazione e la proprietà <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> per specificare il percorso che contiene gli assembly da caricare. Se è necessario eseguire il probe in più directory, è possibile impostare <xref:System.AppDomainSetup.ApplicationBase%2A> su una directory radice e usare la proprietà <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=nameWithType> per identificare le sottodirectory in cui eseguire il probe. In alternativa è possibile creare più domini applicazione e impostare la proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di ogni dominio sul percorso appropriato per gli assembly.  
  
 Per caricare questi assembly è possibile usare il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>. Dal momento che ora si trovano nel percorso di esecuzione del probe, verranno caricati nel contesto di caricamento predefinito anziché nel contesto di origine del caricamento. Tuttavia è consigliabile passare al metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> e fornire i nomi visualizzati degli assembly completi per assicurare che vengano sempre usate versioni corrette.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>
