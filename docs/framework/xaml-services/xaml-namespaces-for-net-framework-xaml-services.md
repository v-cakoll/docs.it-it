---
title: Spazi dei nomi XAML per i servizi XAML di .NET Framework
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 11bf5d112c64fb0b942decf7635f02b90a98bdeb
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837168"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Spazi dei nomi XAML per i servizi XAML di .NET Framework
Uno spazio dei nomi XAML è un concetto che espande la definizione di uno spazio dei nomi XML. Analogamente a uno spazio dei nomi XML, è possibile definire uno spazio dei nomi XAML usando un attributo `xmlns` nel markup. Gli spazi dei nomi XAML sono anche rappresentati nel flusso di nodi XAML e in altre API dei servizi XAML. In questo argomento viene definito il concetto di spazio dei nomi XAML e viene descritto il modo in cui è possibile definire gli spazi dei nomi XAML e vengono utilizzati dai contesti dello schema XAML e da altri aspetti dei servizi .NET Framework XAML.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Spazio dei nomi XML e spazio dei nomi XAML  
 Uno spazio dei nomi XAML è uno spazio dei nomi XML specializzato, così come XAML è una forma specializzata di XML e utilizza il form XML di base per il markup. Nel markup si dichiara uno spazio dei nomi XAML e il relativo mapping tramite un attributo `xmlns` applicato a un elemento. La dichiarazione di `xmlns` può essere apportata allo stesso elemento in cui è dichiarato lo spazio dei nomi XAML. Una dichiarazione dello spazio dei nomi XAML eseguita per un elemento è valida per l'elemento, tutti gli attributi dell'elemento e tutti gli elementi figlio di tale elemento. Gli attributi possono usare uno spazio dei nomi XAML diverso da quello dell'elemento che contiene l'attributo, purché il nome dell'attributo faccia riferimento al prefisso come parte del nome di attributo nel markup.  
  
 La distinzione tra uno spazio dei nomi XAML e uno spazio dei nomi XML consiste nel fatto che uno spazio dei nomi XML può essere usato per fare riferimento a uno schema oppure può essere usato per distinguere semplicemente le entità. Per XAML, i tipi e i membri usati in XAML devono essere risolti in tipi di supporto e XML Schema concetti non si applicano bene a questa funzionalità. Lo spazio dei nomi XAML contiene informazioni che devono essere disponibili nel contesto dello schema XAML per poter eseguire questo mapping dei tipi.  
  
## <a name="xaml-namespace-components"></a>Componenti dello spazio dei nomi XAML  
 La definizione dello spazio dei nomi XAML è costituita da due componenti: un prefisso e un identificatore. Ognuno di questi componenti è presente quando uno spazio dei nomi XAML viene dichiarato nel markup o definito nel sistema di tipi XAML.  
  
 Il prefisso può essere qualsiasi stringa consentita dalla [specifica W3C Namespaces in XML 1,0](https://www.w3.org/TR/REC-xml-names/) . Per convenzione, i prefissi sono in genere stringhe molto brevi, perché il prefisso viene ripetuto più volte in un file di markup tipico. Alcuni spazi dei nomi XAML progettati per essere utilizzati in più implementazioni XAML utilizzano prefissi convenzionali specifici. Lo spazio dei nomi XAML del linguaggio XAML, ad esempio, viene in genere mappato utilizzando il prefisso `x`. È possibile definire uno spazio dei nomi XAML predefinito, in cui il prefisso non è specificato nella definizione ma è rappresentato come una stringa vuota se è stata definita o sottoposta a query nell'API dei servizi XAML di by.NET Framework. In genere, lo spazio dei nomi XAML predefinito viene scelto intenzionalmente per promuovere una quantità ingrandita di markup che omette il prefisso da una tecnologia di implementazione XAML e dai relativi scenari e vocabolari.  
  
 L'identificatore può essere qualsiasi stringa consentita dalla [specifica W3C Namespaces in XML 1,0](https://www.w3.org/TR/REC-xml-names/). Per convenzione, gli identificatori per gli spazi dei nomi XML o gli spazi dei nomi XAML vengono spesso specificati nel formato URI, in genere come URI assoluto qualificato dal protocollo. Spesso, le informazioni sulla versione che definiscono un particolare vocabolario XAML sono implicite come parte della stringa di percorso. Gli spazi dei nomi XAML aggiungono una convenzione di identificazione aggiuntiva oltre la convenzione dell'URI XML. Per gli spazi dei nomi XAML, l'identificatore comunica le informazioni necessarie per un contesto dello schema XAML per risolvere i tipi specificati come elementi nello spazio dei nomi XAML o per risolvere gli attributi ai membri.  
  
 Per la comunicazione di informazioni a un contesto dello schema XAML, l'identificatore di uno spazio dei nomi XAML potrebbe essere ancora in formato URI. Tuttavia, in questo caso l'URI viene dichiarato anche come identificatore corrispondente in un assembly o un elenco di assembly specifico. Questa operazione viene eseguita negli assembly attribuendo l'assembly con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Questo metodo per identificare lo spazio dei nomi XAML e supportare un comportamento di risoluzione del tipo basato su CLR nell'assembly con attributi è supportato dal contesto dello schema XAML predefinito in .NET Framework servizi XAML. Più in generale, questa convenzione può essere utilizzata per i casi in cui il contesto dello schema XAML incorpora CLR o si basa sul contesto dello schema XAML predefinito, che è necessario per leggere gli attributi CLR dagli assembly CLR.  
  
 Gli spazi dei nomi XAML possono inoltre essere identificati da una convenzione che comunica uno spazio dei nomi CLR e un assembly che definisce il tipo. Questa convenzione viene utilizzata nei casi in cui non esiste alcuna <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attribuzione negli assembly che contengono i tipi. Questa convenzione è potenzialmente più complessa della convenzione dell'URI e può anche causare ambiguità e duplicazione, perché esistono diversi modi per fare riferimento a un assembly.  
  
 La forma più semplice di un identificatore che utilizza lo spazio dei nomi CLR e la convenzione di assembly è la seguente:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` e `; assembly=` sono componenti letterali della sintassi.  
  
 *Nomeclrns* è il nome della stringa che identifica uno spazio dei nomi CLR. Questo nome di stringa include i caratteri punto interni (.) che forniscono suggerimenti sullo spazio dei nomi CLR e la relativa relazione con altri spazi dei nomi CLR.  
  
 *NomeBreveAssembly* è il nome di stringa di un assembly che definisce i tipi utili in XAML. È previsto che i tipi a cui si accede tramite lo spazio dei nomi XAML dichiarato siano definiti dall'assembly e dichiarati in modo specifico all'interno dello spazio dei nomi CLR specificato da *Nomeclrns*. Questo nome di stringa in genere è parallelo alle informazioni segnalate dal <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 Una definizione più completa dello spazio dei nomi CLR e della convenzione degli assembly è la seguente:  
  
 `clr-namespace:` *nomeclrns* `; assembly=` *AssemblyName*  
  
 *AssemblyName* rappresenta qualsiasi stringa valida come input <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>. Questa stringa può includere informazioni sulle impostazioni cultura, sulla chiave pubblica o sulla versione. le definizioni di questi concetti sono definite nell'argomento di riferimento per <xref:System.Reflection.Assembly>. Il formato COFF e l'evidenza (come usato da altri overload di <xref:System.Reflection.Assembly.Load%2A>) non sono rilevanti per il caricamento di assembly XAML; tutte le informazioni sul caricamento devono essere presentate sotto forma di stringa.  
  
 La specifica di una chiave pubblica per l'assembly è una tecnica utile per la sicurezza XAML o per la rimozione di possibili ambiguità che possono esistere se gli assembly vengono caricati con un nome semplice o preesistenti in una cache o in un dominio dell'applicazione. Per altre informazioni, vedere [considerazioni sulla sicurezza di XAML](xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Dichiarazioni dello spazio dei nomi XAML nell'API dei servizi XAML  
 Nell'API dei servizi XAML, una dichiarazione dello spazio dei nomi XAML è rappresentata da un oggetto <xref:System.Xaml.NamespaceDeclaration>. Se si dichiara uno spazio dei nomi XAML nel codice, si chiama il costruttore <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>. I parametri `ns` e `prefix` sono specificati come stringhe e l'input da fornire per questi parametri corrisponde alla definizione dell'identificatore dello spazio dei nomi XAML e del prefisso dello spazio dei nomi XAML come indicato in precedenza in questo argomento.  
  
 Se si esaminano le informazioni dello spazio dei nomi XAML come parte di un flusso di nodi XAML o tramite altri accessi al sistema di tipi XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> segnala l'identificatore dello spazio dei nomi XAML e <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> segnala il prefisso dello spazio dei nomi XAML.  
  
 In un flusso di nodi XAML, le informazioni sullo spazio dei nomi XAML possono apparire come nodo XAML che precede l'entità a cui si riferisce. Sono inclusi i casi in cui le informazioni dello spazio dei nomi XAML precedono il `StartObject` dell'elemento radice XAML. Per altre informazioni, vedere [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Per molti scenari in cui viene utilizzata .NET Framework API dei servizi XAML, deve esistere almeno una dichiarazione dello spazio dei nomi XAML e la dichiarazione deve contenere o fare riferimento alle informazioni richieste da un contesto dello schema XAML. Gli spazi dei nomi XAML devono specificare gli assembly da caricare o facilitare la risoluzione di tipi specifici all'interno di spazi dei nomi e assembly già caricati o noti dal contesto dello schema XAML.  
  
 Per generare un flusso di nodi XAML, è necessario che le informazioni sul tipo XAML siano disponibili tramite il contesto dello schema XAML. Non è possibile determinare le informazioni sul tipo XAML senza prima determinare lo spazio dei nomi XAML pertinente per ogni nodo da creare. A questo punto, non sono ancora state create istanze di tipi, ma il contesto dello schema XAML potrebbe dover cercare informazioni dall'assembly di definizione e dal tipo di supporto. Per elaborare il markup `<Party><PartyFavor/></Party>`, ad esempio, è necessario che il contesto dello schema XAML sia in grado di determinare il nome e il tipo del `ContentProperty` di `Party`e di conseguenza anche le informazioni sullo spazio dei nomi XAML per `Party` e `PartyFavor`. Nel caso del contesto dello schema XAML predefinito, la reflection statica segnala gran parte delle informazioni del sistema di tipi XAML necessarie per generare nodi di tipo XAML nel flusso di nodi.  
  
 Per generare un oggetto grafico da un flusso di nodi XAML, è necessario che esistano dichiarazioni dello spazio dei nomi XAML per ogni prefisso XAML usato nel markup originale e registrato nel flusso di nodi XAML. A questo punto vengono create le istanze e si verifica il comportamento effettivo del mapping dei tipi.  
  
 Se è necessario prepopolare le informazioni dello spazio dei nomi XAML, nei casi in cui lo spazio dei nomi XAML che si intende usare nel contesto dello schema XAML non è definito nel markup, una tecnica che è possibile usare consiste nel dichiarare dichiarazioni dello spazio dei nomi XML nel <xref:System.Xml.XmlParserContext> per un <xref:System.Xml.XmlReader>. Usare quindi tale <xref:System.Xml.XmlReader> come input per un costruttore di reader XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Altre due API rilevanti per la gestione dello spazio dei nomi XAML in .NET Framework i servizi XAML sono gli attributi <xref:System.Windows.Markup.XmlnsDefinitionAttribute> e <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Questi attributi si applicano agli assembly. <xref:System.Windows.Markup.XmlnsDefinitionAttribute> viene usato da un contesto dello schema XAML per interpretare qualsiasi dichiarazione dello spazio dei nomi XAML che include un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute> viene usato dagli strumenti che creano XAML in modo che un particolare spazio dei nomi XAML possa essere serializzato con un prefisso stimabile. Per altre informazioni, vedere [attributi CLR correlati a XAML per tipi e librerie personalizzati](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
