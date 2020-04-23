---
title: XAML Namespaces for .NET XAML Services
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071843"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>XAML Namespaces for .NET XAML Services
Uno spazio dei nomi XAML è un concetto che si espande sulla definizione di uno spazio dei nomi XML. Analogamente a uno spazio dei nomi `xmlns` XML, è possibile definire uno spazio dei nomi XAML usando un attributo nel markup. Gli spazi dei nomi XAML sono rappresentati anche nel flusso del nodo XAML e in altre API dei servizi XAML. Questo argomento definisce il concetto di spazio dei nomi XAML e descrive come gli spazi dei nomi XAML possono essere definiti e vengono usati dai contesti dello schema XAML e da altri aspetti dei servizi XAML di .NET.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML Namespace and XAML Namespace  
 Uno spazio dei nomi XAML è uno spazio dei nomi XML specializzato, proprio come XAML è una forma specializzata di XML e usa il formato XML di base per il markup. Nel markup, dichiari uno spazio dei `xmlns` nomi XAML e il relativo mapping tramite un attributo applicato a un elemento. La `xmlns` dichiarazione può essere effettuata allo stesso elemento in cui è dichiarato lo spazio dei nomi XAML. Una dichiarazione dello spazio dei nomi XAML effettuata a un elemento è valida per tale elemento, tutti gli attributi di tale elemento e tutti gli elementi figlio di tale elemento. Gli attributi possono usare uno spazio dei nomi XAML diverso dall'elemento che contiene l'attributo, purché il nome dell'attributo stesso faccia riferimento al prefisso come parte del nome dell'attributo nel markup.  
  
 La distinzione tra uno spazio dei nomi XAML e uno spazio dei nomi XML consiste nel fatto che uno spazio dei nomi XML può essere usato per fare riferimento a uno schema o semplicemente per differenziare le entità. Per XAML, i tipi e i membri usati in XAML devono essere risolti in tipi di supporto e i concetti dello schema XML non si applicano bene a questa funzionalità. Lo spazio dei nomi XAML contiene informazioni che il contesto dello schema XAML deve avere disponibile per eseguire questo mapping dei tipi.  
  
## <a name="xaml-namespace-components"></a>Componenti dello spazio dei nomi XAMLXAML Namespace Components  
 La definizione dello spazio dei nomi XAML include due componenti: un prefisso e un identificatore. Ognuno di questi componenti è presente quando uno spazio dei nomi XAML viene dichiarato nel markup o definito nel sistema di tipi XAML.  
  
 Il prefisso può essere qualsiasi stringa come consentito dagli spazi [dei nomi W3C nella specifica XML 1.0](https://www.w3.org/TR/REC-xml-names/). Per convenzione, i prefissi sono in genere stringhe brevi, perché il prefisso viene ripetuto più volte in un tipico file di markup. Alcuni spazi dei nomi XAML che devono essere usati in più implementazioni XAML usano prefissi convenzionali specifici. Ad esempio, lo spazio dei nomi XAML `x`del linguaggio XAML viene in genere mappato utilizzando il prefisso . È possibile definire uno spazio dei nomi XAML predefinito, in cui il prefisso non è specificato nella definizione, ma viene rappresentato come una stringa vuota se definito o sottoposto a query by.NETAPI dei servizi XAML. In genere, lo spazio dei nomi XAML predefinito viene scelto deliberatamente per promuovere una quantità massima di markup che omette il prefisso da una tecnologia di implementazione XAML e i relativi scenari e vocabolari.  
  
 L'identificatore può essere qualsiasi stringa come consentito dagli spazi [dei nomi W3C nella specifica XML 1.0](https://www.w3.org/TR/REC-xml-names/). Per convenzione, gli identificatori per gli spazi dei nomi XML o XAML vengono spesso forniti in formato URI, in genere come URI assoluto qualificato dal protocollo. Spesso, le informazioni sulla versione che definiscono un vocabolario XAML specifico sono implicite come parte della stringa di percorso. Gli spazi dei nomi XAML aggiungono una convenzione di identificatore aggiuntiva oltre la convenzione DELL'URI XML. Per gli spazi dei nomi XAML, l'identificatore comunica le informazioni necessarie per un contesto dello schema XAML per risolvere i tipi specificati come elementi in tale spazio dei nomi XAML o per risolvere gli attributi nei membri.  
  
 Ai fini della comunicazione di informazioni a un contesto dello schema XAML, l'identificatore per uno spazio dei nomi XAML potrebbe essere ancora in formato URI. Tuttavia, in questo caso l'URI viene dichiarato anche come identificatore corrispondente in un determinato assembly o elenco di assembly. Questa operazione viene eseguita negli <xref:System.Windows.Markup.XmlnsDefinitionAttribute>assiemi attribuendo all'assembly con . Questo metodo di identificazione dello spazio dei nomi XAML e supporto di un comportamento di risoluzione dei tipi basato su CLR nell'assembly con attributi è supportato dal contesto dello schema XAML predefinito nei servizi XAML di .NET. Più in generale, questa convenzione può essere utilizzata per i casi in cui il contesto dello schema XAML incorpora CLR o è basato sul contesto dello schema XAML predefinito, necessario per leggere gli attributi CLR dagli assembly CLR.  
  
 Gli spazi dei nomi XAML possono anche essere identificati da una convenzione che comunica uno spazio dei nomi CLR e un assembly di definizione dei tipi. Questa convenzione viene utilizzata <xref:System.Windows.Markup.XmlnsDefinitionAttribute> nei casi in cui non esiste alcuna attribuzione negli assembly che contengono tipi. Questa convenzione è potenzialmente più complessa rispetto alla convenzione URI e ha anche il potenziale per ambiguità e duplicazione, perché esistono diversi modi di fare riferimento a un assembly.  
  
 La forma più semplice di un identificatore che utilizza lo spazio dei nomi CLR e la convenzione dell'assembly è la seguente:  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:`e `; assembly=` sono componenti letterali della sintassi.  
  
 *clrnsName* è il nome della stringa che identifica uno spazio dei nomi CLR. Questo nome di stringa include tutti i caratteri punto interni (.) che forniscono suggerimenti sullo spazio dei nomi CLR e la relativa relazione con altri spazi dei nomi CLR.
  
 *assemblyShortName* è il nome di stringa di un assembly che definisce i tipi utili in XAML. I tipi a cui accedere tramite lo spazio dei nomi XAML dichiarato devono essere definiti dall'assembly e dichiarati all'interno dello spazio dei nomi CLR specificato da *clrnsName*. Questo nome di stringa è in <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>genere parallelo alle informazioni riportate da .  
  
 Di seguito è riportata una definizione più completa dello spazio dei nomi CLR e della convenzione dell'assembly:  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName* rappresenta qualsiasi stringa valida <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> come input. Questa stringa può includere informazioni sulle impostazioni cultura, sulla chiave pubblica o <xref:System.Reflection.Assembly>sulla versione (le definizioni di questi concetti sono definite nell'argomento di riferimento per ). Il formato cOFF e l'evidenza <xref:System.Reflection.Assembly.Load%2A>(utilizzati da altri overload di ) non sono rilevanti per scopi di caricamento di assembly XAML; tutte le informazioni sul carico devono essere presentate come una stringa.  
  
 Specificare una chiave pubblica per l'assembly è una tecnica utile per la sicurezza XAML o per rimuovere possibili ambiguità che possono esistere se gli assembly vengono caricati con un nome semplice o preesistere in una cache o in un dominio applicazione. Per altre informazioni, vedere [Considerazioni sulla sicurezza XAML](security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML Namespace Declarations in the XAML Services API  
 Nell'API dei servizi XAML, una dichiarazione dello spazio dei nomi XAML è rappresentata da un <xref:System.Xaml.NamespaceDeclaration> oggetto. Se si dichiara uno spazio dei nomi <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> XAML nel codice, chiamare il costruttore. I `ns` `prefix` parametri e vengono specificati come stringhe e l'input da fornire per questi parametri corrisponde alla definizione dell'identificatore dello spazio dei nomi XAML e del prefisso dello spazio dei nomi XAML come fornito in precedenza in questo argomento.  
  
 Se si esaminano le informazioni sullo spazio dei nomi XAML come parte <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> di un flusso <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> del nodo XAML o tramite altri accessi al sistema di tipi XAML, si segnala l'identificatore dello spazio dei nomi XAML e viene segnalato il prefisso dello spazio dei nomi XAML.  
  
 In un flusso del nodo XAML, le informazioni sullo spazio dei nomi XAML possono essere visualizzate come un nodo XAML che precede l'entità a cui si applica. Sono inclusi i casi in cui `StartObject` le informazioni sullo spazio dei nomi XAML precedono l'elemento radice XAML. Per altre informazioni, vedere [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Per molti scenari che usano l'API dei servizi XAML .NET, è prevista l'esistenza di almeno una dichiarazione dello spazio dei nomi XAML e la dichiarazione deve contenere o fare riferimento alle informazioni richieste da un contesto dello schema XAML. Gli spazi dei nomi XAML devono specificare gli assembly da caricare o facilitare la risoluzione di tipi specifici all'interno di spazi dei nomi e assembly già caricati o noti dal contesto dello schema XAML.  
  
 Per generare un flusso del nodo XAML, le informazioni sul tipo XAML devono essere disponibili, tramite il contesto dello schema XAML. Le informazioni sul tipo XAML non possono essere determinate senza prima determinare lo spazio dei nomi XAML pertinente per ogni nodo da creare. A questo punto, non viene ancora creata alcuna istanza di tipi, ma il contesto dello schema XAML potrebbe essere necessario cercare informazioni dall'assembly di definizione e dal tipo di supporto. Per elaborare il markup, `<Party><PartyFavor/></Party>`ad esempio, il contesto dello schema XAML `ContentProperty` `Party`deve essere in grado di determinare `Party` `PartyFavor`il nome e il tipo di , pertanto è necessario conoscere anche le informazioni sullo spazio dei nomi XAML per e . Nel caso del contesto dello schema XAML predefinito, la reflection statica segnala gran parte delle informazioni sul sistema di tipi XAML necessarie per generare nodi di tipo XAML nel flusso del nodo.  
  
 Per generare un oggetto grafico da un flusso del nodo XAML, le dichiarazioni dello spazio dei nomi XAML devono esistere per ogni prefisso XAML usato nel markup originale e registrato nel flusso del nodo XAML. A questo punto, vengono create istanze e si verifica un vero e proprio comportamento di mapping dei tipi.  
  
 Se è necessario prepopolare le informazioni sullo spazio dei nomi XAML, nei casi in cui lo spazio dei nomi XAML che si <xref:System.Xml.XmlParserContext> intende <xref:System.Xml.XmlReader>utilizzare il contesto dello schema XAML non è definito nel markup, una tecnica che è possibile utilizzare consiste nel dichiarare le dichiarazioni dello spazio dei nomi XML in per un oggetto . Utilizzarelo <xref:System.Xml.XmlReader> quindi come input per un <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>costruttore del lettore XAML o .  
  
 Altre due API rilevanti per la gestione dello spazio dei <xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsPrefixAttribute>nomi XAML nei servizi XAML .NET sono gli attributi e i file . Questi attributi si applicano agli assembly. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>viene utilizzato da un contesto dello schema XAML per interpretare qualsiasi dichiarazione dello spazio dei nomi XAML che include un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute>viene utilizzato dagli strumenti che generano XAML in modo che un determinato spazio dei nomi XAML possa essere serializzato con un prefisso prevedibile. Per ulteriori informazioni, vedere [Attributi CLR correlati a XAML per tipi e librerie personalizzati](clr-attributes-with-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
