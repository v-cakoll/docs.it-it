---
title: Spazi dei nomi XAML per i servizi XAML di .NET Framework
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: dc2c424306b9ebd705f2541266e4b1e3afe94547
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153556"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Spazi dei nomi XAML per i servizi XAML di .NET Framework
Uno spazio dei nomi XAML è un concetto che si espande sulla definizione di uno spazio dei nomi XML. Simile a uno spazio dei nomi XML, è possibile definire un spazio dei nomi XAML utilizzando un `xmlns` attributo nel markup. Gli spazi dei nomi XAML sono rappresentati anche in altre API di servizi XAML e il flusso di nodi XAML. In questo argomento viene definito il concetto di spazio dei nomi XAML e viene descritto come gli spazi dei nomi XAML possono essere definiti e servono da contesti dello schema XAML e altri aspetti di servizi XAML di .NET Framework.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Namespace XML e XAML Namespace  
 Uno spazio dei nomi XAML è uno spazio dei nomi XML specializzato, esattamente come XAML è un formato specifico del linguaggio XML e Usa il formato XML di base per il markup. Nel markup, si dichiara uno spazio dei nomi XAML e il relativo mapping tramite un `xmlns` attributo applicato a un elemento. Il `xmlns` dichiarazione può essere effettuata allo stesso elemento dichiarata all'interno dello spazio dei nomi XAML. Una dichiarazione dello spazio dei nomi XAML apportata a un elemento è valida per tale elemento, tutti gli attributi di tale elemento e tutti gli elementi figlio di quell'elemento. Gli attributi possono usare gli spazi dei nomi XAML che non è quello utilizzato per l'elemento che contiene l'attributo, purché il nome dell'attributo stesso fa riferimento il prefisso come parte del nome dell'attributo nel markup.  
  
 La differenza di uno spazio dei nomi XAML e uno spazio dei nomi XML è che uno spazio dei nomi XML può essere utilizzato per fare riferimento a uno schema, o potrebbe essere usato per distinguere semplicemente le entità. Per XAML, i tipi e i membri utilizzati in XAML devono essere risolte in tipi di supporto e i concetti dello schema XML non si applicano anche a questa funzionalità. Lo spazio dei nomi XAML contiene informazioni che il contesto dello schema XAML deve essere disponibile per poter eseguire il mapping dei tipi.  
  
## <a name="xaml-namespace-components"></a>XAML Namespace componenti  
 La definizione dello spazio dei nomi XAML include due componenti: un prefisso e un identificatore. Ognuno di questi componenti sono presenti quando uno spazio dei nomi XAML viene dichiarato nel markup, o definito nel sistema di tipi XAML.  
  
 Il prefisso può essere qualsiasi stringa consentita per il [spazi dei nomi W3C nella specifica XML 1.0](https://go.microsoft.com/fwlink/?LinkID=161735) . Per convenzione, i prefissi sono stringhe molto breve, perché il prefisso viene ripetuto più volte in un file di markup tipica. Determinati spazi dei nomi XAML che devono essere utilizzati in più implementazioni XAML usare prefissi convenzionali particolari. Ad esempio, spazio dei nomi XAML del linguaggio XAML è in genere mappata utilizzando il prefisso `x`. È possibile definire uno spazio dei nomi XAML predefinito, in cui il prefisso non è specificato nella definizione di ma viene rappresentato come una stringa vuota se definito o richiesto.NET Framework XAML servizi API. In genere, lo spazio dei nomi XAML predefinito viene scelto intenzionalmente per promuovere una quantità ingrandita di omissione di prefisso di markup mediante una tecnologia di implementazione XAML scenari e i relativi vocabolari.  
  
 L'identificatore può essere qualsiasi stringa come consentito dal [spazi dei nomi W3C nella specifica XML 1.0](https://go.microsoft.com/fwlink/?LinkID=161735). Per convenzione, gli identificatori per spazi dei nomi XML o spazi dei nomi XAML sono spesso espressi in formato URI, in genere come un URI assoluto completo di protocollo. Spesso, le informazioni sulla versione che definisce un vocabolario XAML specifico è impliciti come parte della stringa di percorso. Gli spazi dei nomi XAML aggiungere una convenzione identificatore aggiuntivo oltre la convenzione dell'URI di XML. Per gli spazi dei nomi XAML, l'identificatore comunica informazioni necessarie a un contesto dello schema XAML per risolvere i tipi che vengono specificati come elementi in tale spazio dei nomi XAML o per risolvere gli attributi ai membri.  
  
 Ai fini della comunicazione delle informazioni per un contesto dello schema XAML, l'identificatore per uno spazio dei nomi XAML può essere ancora in formato URI. Tuttavia, in questo caso l'URI viene anche dichiarato come un identificatore corrispondente in un determinato assembly o un elenco di assembly. Questa operazione viene eseguita negli assembly attribuendo l'assembly con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Questo metodo di identificazione dello spazio dei nomi XAML e che supportano un comportamento di risoluzione basati su CLR tipo nell'assembly con attributi è supportato dal contesto dello schema XAML predefinito nei servizi XAML di .NET Framework. Più in generale, questa convenzione è utilizzabile per i casi in cui il contesto dello schema XAML incorpora CLR o si basa sul contesto dello schema XAML predefinito, che è necessario per leggere gli attributi CLR dagli assembly CLR.  
  
 Gli spazi dei nomi XAML può essere anche identificato da una convenzione che comunica a uno spazio dei nomi CLR e un assembly di definizione dei tipi. Questa convenzione viene usata nei casi in cui non <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attribuzione esiste negli assembly che contengono i tipi. Questa convenzione è potenzialmente più complessa della convenzione dell'URI e ha anche il rischio di ambiguità e la duplicazione, perché esistono diversi modi di fare riferimento a un assembly.  
  
 La forma più elementare di un identificatore che viene utilizzata la convenzione di spazio dei nomi e assembly CLR è come segue:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` e `; assembly=` letterale componenti della sintassi.  
  
 *Nomeclrns* è il nome di stringa che identifica uno spazio dei nomi CLR. Il nome della stringa include qualsiasi carattere punto (.) che fornisce suggerimenti sullo spazio dei nomi CLR e in relazione agli altri spazi dei nomi CLR.  
  
 *NomeBreveAssembly* è il nome di stringa di un assembly che definisce i tipi che sono utili in XAML. I tipi di essere accessibili tramite lo spazio dei nomi XAML dichiarato dovrebbero essere definiti in assembly e in particolare venga dichiarato nello spazio dei nomi CLR specificato da *Nomeclrns*. Il nome della stringa è parallelo in genere le informazioni come riportato da <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 La definizione completa della convenzione di spazio dei nomi e assembly di CLR è come segue:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* rappresenta qualsiasi stringa valida come un <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> input. Questa stringa può includere le impostazioni cultura, chiave pubblica o le informazioni sulla versione (definizioni di questi concetti sono definite nell'argomento di riferimento per <xref:System.Reflection.Assembly>). Formato COFF formato e l'evidenza (come utilizzato da altri overload di <xref:System.Reflection.Assembly.Load%2A>) non sono rilevanti per scopi di caricamento degli assembly XAML tutte le informazioni sul caricamento deve essere presentati come una stringa.  
  
 Specifica una chiave pubblica per l'assembly è una tecnica utile per la sicurezza XAML o per rimuovere possibili ambiguità che possono esistere se gli assembly vengono caricati in base al nome semplice o pre-esistano in un dominio applicazione o della cache. Per altre informazioni, vedere [XAML Security Considerations](xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Dichiarazioni di Namespace XAML nei servizi XAML di API  
 Nell'API di servizi XAML, una dichiarazione dello spazio dei nomi XAML è rappresentata da un <xref:System.Xaml.NamespaceDeclaration> oggetto. Se si dichiara uno spazio dei nomi XAML nel codice, si chiama il <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> costruttore. Il `ns` e `prefix` parametri vengono specificati come stringhe e l'input per specificare per questi parametri corrisponde alla definizione dell'identificatore dello spazio dei nomi XAML e il prefisso dello spazio dei nomi XAML come indicato in precedenza in questo argomento.  
  
 Se le informazioni dello spazio dei nomi XAML come parte di un flusso di nodi XAML o tramite un altro accesso al sistema di tipi XAML, se si siano esaminando <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> segnala l'identificatore dello spazio dei nomi XAML, e <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> segnala il prefisso dello spazio dei nomi XAML.  
  
 In un flusso di nodi XAML, le informazioni dello spazio dei nomi XAML possono apparire come un nodo XAML che precede l'entità a cui viene applicata. Sono inclusi i casi in cui le informazioni dello spazio dei nomi XAML precede il `StartObject` dell'elemento radice XAML. Per altre informazioni, vedere [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Per molti scenari che usano l'API di servizi XAML di .NET Framework, è necessario almeno una dichiarazione di spazio dei nomi XAML che esista e la dichiarazione deve contenere o fare riferimento alle informazioni necessarie per un contesto dello schema XAML. Gli spazi dei nomi XAML deve specificare gli assembly da caricare o la risoluzione dei tipi specifici all'interno di spazi dei nomi e gli assembly che sono già caricati o noti con il contesto dello schema XAML.  
  
 Per generare un flusso di nodi XAML, le informazioni sul tipo XAML deve essere disponibile, tramite il contesto dello schema XAML. Le informazioni sul tipo XAML non può essere determinati senza prima determinare lo spazio dei nomi XAML pertinente per ogni nodo da creare. A questo punto, non le istanze di tipi sono già state create, ma potrebbe essere necessario il contesto dello schema XAML individuare le informazioni dalla definizione di assembly e tipo di supporto. Ad esempio, per poter elaborare il markup `<Party><PartyFavor/></Party>`, il contesto dello schema XAML deve essere in grado di determinare il nome e il tipo del `ContentProperty` dei `Party`e pertanto deve inoltre conoscere le informazioni dello spazio dei nomi XAML per `Party` e `PartyFavor`. Nel caso il contesto dello schema XAML predefinito, la reflection statica contiene gran parte delle informazioni sul sistema di tipo XAML necessario per generare nodi di tipo XAML nel flusso di nodi.  
  
 Per generare un oggetto grafico da un flusso di nodi XAML, le dichiarazioni dello spazio dei nomi XAML devono esistere per ogni prefisso XAML usati nel markup originale e registrata nel flusso di nodi XAML. A questo punto, vengono create istanze e si verifica il comportamento di mapping dei tipi true.  
  
 Se è necessario per il popolamento preliminare delle informazioni dello spazio dei nomi XAML, nei casi in cui lo spazio dei nomi XAML si intende il contesto dello schema XAML da utilizzare non è definito nel markup, è possibile usare una tecnica consiste nel dichiarare le dichiarazioni dello spazio dei nomi XML nel <xref:System.Xml.XmlParserContext> per un <xref:System.Xml.XmlReader>. Quindi usare tale <xref:System.Xml.XmlReader> come input per un costruttore di reader XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Due altre API che sono rilevanti per spazio dei nomi XAML gestisce nei servizi XAML di .NET Framework sono gli attributi <xref:System.Windows.Markup.XmlnsDefinitionAttribute> e <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Questi attributi si applicano agli assembly. <xref:System.Windows.Markup.XmlnsDefinitionAttribute> usato da un contesto dello schema XAML per interpretare qualsiasi dichiarazione dello spazio dei nomi XAML che include un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute> viene usato dagli strumenti che generano XAML in modo che un determinato spazio dei nomi XAML può essere serializzato con un prefisso prevedibile. Per altre informazioni, vedere [Related attributi CLR per tipi personalizzati e le librerie](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
