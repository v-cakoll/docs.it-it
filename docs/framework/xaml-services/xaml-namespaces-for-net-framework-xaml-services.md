---
title: Spazi dei nomi XAML per i servizi XAML di .NET Framework
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 842cfb31e21c59bb886ccd266d19c40c64557519
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566795"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Spazi dei nomi XAML per i servizi XAML di .NET Framework
Uno spazio dei nomi XAML è un concetto che espande la definizione di uno spazio dei nomi XML. Simile a uno spazio dei nomi XML, è possibile definire lo spazio dei nomi XAML mediante un `xmlns` attributo nel markup. Spazi dei nomi XAML sono rappresentati anche nel flusso del nodo XAML e altre API dei servizi XAML. In questo argomento viene definito il concetto di spazio dei nomi XAML e viene descritto come gli spazi dei nomi XAML possono essere definiti e usati da contesti dello schema XAML e altri aspetti di servizi XAML di .NET Framework.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Namespace XML e XAML Namespace  
 Uno spazio dei nomi XAML è uno spazio dei nomi XML specializzato, così come XAML è un tipo specializzato di XML che utilizza il formato XML di base per il markup. Nel markup, si dichiara uno spazio dei nomi XAML e il relativo mapping a un `xmlns` attributo applicato a un elemento. Il `xmlns` dichiarazione può essere effettuata allo stesso elemento dichiarato nello spazio dei nomi XAML. Una dichiarazione dello spazio dei nomi XAML apportata a un elemento è valida per tale elemento, tutti gli attributi di tale elemento e tutti gli elementi figlio di tale elemento. Gli attributi è possono utilizzare gli spazi dei nomi XAML che non è uguale all'elemento che contiene l'attributo, purché il nome dell'attributo stesso fa riferimento il prefisso come parte del nome dell'attributo nel markup.  
  
 La distinzione di uno spazio dei nomi XAML e uno spazio dei nomi XML è che uno spazio dei nomi XML può essere utilizzato per fare riferimento a uno schema, o può essere usato per distinguere semplicemente le entità. Per XAML, i tipi e i membri utilizzati in XAML devono essere risolte in tipi di supporto e i concetti dello schema XML non si applicano anche a questa funzionalità. Lo spazio dei nomi XAML contiene informazioni che il contesto dello schema XAML deve essere disponibile per eseguire il mapping di tipo.  
  
## <a name="xaml-namespace-components"></a>Componenti Namespace XAML  
 La definizione di spazio dei nomi XAML include due componenti: un prefisso e un identificatore. Ognuno di questi componenti sono presenti quando uno spazio dei nomi XAML viene dichiarato nel markup o definito nel sistema di tipi XAML.  
  
 Il prefisso può essere qualsiasi stringa consentita per il [W3C gli spazi dei nomi nella specifica XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735) . Per convenzione, i prefissi sono in genere molto breve stringhe, poiché il prefisso viene ripetuto più volte in un file di markup tipico. Determinati spazi dei nomi XAML che devono essere utilizzati in più implementazioni XAML usare prefissi convenzionali particolari. Ad esempio nomi XAML del linguaggio XAML sono in genere mappati utilizzando il prefisso `x`. È possibile definire uno spazio dei nomi XAML predefinito, in cui il prefisso non è fornito nella definizione di ma è rappresentato come una stringa vuota se è definito o richiesto.NET Framework XAML servizi API. In genere, lo spazio dei nomi XAML predefinito viene deliberatamente scelto per alzare di livello una quantità ingrandita omissione prefisso di tag da una tecnologia implementano XAML, scenari e vocabolari.  
  
 L'identificatore può essere qualsiasi stringa consentita per il [W3C gli spazi dei nomi nella specifica XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735). Per convenzione, gli identificatori per spazi dei nomi XML o spazi dei nomi XAML sono spesso specificati in formato URI, in genere come un URI assoluto di protocollo qualificato. Spesso, le informazioni di versione che definiscono un determinato vocabolario XAML sono implicite come parte della stringa di percorso. Spazi dei nomi XAML aggiungere una convenzione di identificatore aggiuntivo oltre convenzione dell'URI di XML. Per spazi dei nomi XAML, l'identificatore comunica le informazioni necessarie per un contesto dello schema XAML per risolvere i tipi che vengono specificati come elementi in tale spazio dei nomi XAML o per risolvere gli attributi ai membri.  
  
 Ai fini della comunicazione di informazioni per un contesto dello schema XAML, l'identificatore per uno spazio dei nomi XAML può essere ancora in formato URI. Tuttavia, in questo caso l'URI viene dichiarato come un identificatore corrispondente in un determinato assembly o un elenco di assembly. Questa operazione viene eseguita negli assembly attribuendo l'assembly con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Questo metodo per identificare lo spazio dei nomi XAML e supporto di un comportamento di risoluzione basato su CLR tipi in assembly con attributi è supportato dal contesto dello schema XAML predefinito nei servizi XAML di .NET Framework. Più in generale, è possibile utilizzare questa convenzione per i casi in cui il contesto dello schema XAML incorpori CLR o dipende dal contesto dello schema XAML predefinito, che è necessario per leggere gli attributi CLR dagli assembly CLR.  
  
 Spazi dei nomi XAML può essere identificato da una convenzione che comunica a uno spazio dei nomi CLR e un assembly di definizione dei tipi. Questa convenzione viene utilizzata nei casi in cui non <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attribuzione presente nell'assembly che contengono i tipi. Questa convenzione è potenzialmente più complessa della convenzione dell'URI e ha inoltre la possibilità di creare ambiguità e duplicati, perché esistono diversi modi di fare riferimento a un assembly.  
  
 La forma più elementare di un identificatore che utilizza la convenzione di spazio dei nomi e assembly CLR è il seguente:  
  
 `clr-namespace:` *Nomeclrns* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` e `; assembly=` sono letterali componenti della sintassi.  
  
 *Nomeclrns* è il nome di stringa che identifica uno spazio dei nomi CLR. Il nome della stringa include qualsiasi carattere punto (.) che fornisce suggerimenti sullo spazio dei nomi CLR e relativa relazione con altri spazi dei nomi CLR.  
  
 *assemblyShortName* è il nome della stringa di un assembly che definisce i tipi che sono utili in XAML. I tipi per essere accessibili tramite lo spazio dei nomi dichiarato di XAML sono previste per definire l'assembly e dichiarati specificamente nello spazio dei nomi CLR specificato da *Nomeclrns*. Il nome della stringa equivale in genere le informazioni come riportato da <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 La definizione completa della convenzione di spazio dei nomi e assembly CLR è il seguente:  
  
 `clr-namespace:` *Nomeclrns* `; assembly=` *assemblyName*  
  
 *assemblyName* rappresenta qualsiasi stringa valida come un <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> input. Questa stringa può includere le impostazioni cultura, chiave pubblica o informazioni sulla versione (definizioni di questi concetti sono definite nella Guida di riferimento per <xref:System.Reflection.Assembly>). COFF formato e l'evidenza (usato da altri overload di <xref:System.Reflection.Assembly.Load%2A>) non sono rilevanti per l'assembly XAML durante il caricamento scopi; tutte le informazioni sul caricamento devono essere presentati come una stringa.  
  
 Specifica una chiave pubblica per l'assembly è una tecnica utile per la sicurezza XAML o per rimuovere l'ambiguità possibili che possono essere presenti se gli assembly vengono caricati in base al nome semplice o pre-esistono in un dominio applicazione o di cache. Per ulteriori informazioni, vedere [considerazioni sulla sicurezza in XAML](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Dichiarazioni di Namespace XAML nei servizi XAML di API  
 Nell'API di servizi XAML di una dichiarazione dello spazio dei nomi XAML è rappresentata da un <xref:System.Xaml.NamespaceDeclaration> oggetto. Se si dichiara uno spazio dei nomi XAML nel codice, si chiama il <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> costruttore. Il `ns` e `prefix` parametri vengono specificati come stringhe, mentre l'input da fornire per questi parametri corrisponde alla definizione dell'identificatore dello spazio dei nomi XAML e il prefisso dello spazio dei nomi XAML come specificato in precedenza in questo argomento.  
  
 Se si siano esaminando le informazioni dello spazio dei nomi XAML come parte di un flusso del nodo XAML o tramite un altro accesso al sistema di tipi XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> report l'identificatore dello spazio dei nomi XAML, e <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> segnala il prefisso dello spazio dei nomi XAML.  
  
 In un flusso del nodo XAML, le informazioni dello spazio dei nomi XAML possono apparire come un nodo XAML che precede l'entità a cui viene applicata. Sono inclusi i casi in cui le informazioni dello spazio dei nomi XAML precede il `StartObject` dell'elemento radice XAML. Per altre informazioni, vedere [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Per molti scenari che utilizzano l'API dei servizi XAML di .NET Framework, è necessario esista almeno una dichiarazione di spazio dei nomi XAML e la dichiarazione deve contenere o fare riferimento alle informazioni necessarie per un contesto dello schema XAML. Gli spazi dei nomi XAML devono specificare gli assembly da caricare o la risoluzione dei tipi specifici all'interno di spazi dei nomi e assembly che sono già caricati o noti dal contesto dello schema XAML.  
  
 Per generare un flusso del nodo XAML, informazioni sul tipo XAML deve essere disponibile, tramite il contesto dello schema XAML. Le informazioni sul tipo XAML non può essere determinati senza viene innanzitutto determinato spazio dei nomi XAML rilevante per ogni nodo da creare. A questo punto, non le istanze dei tipi sono state ancora create, ma il contesto dello schema XAML può essere necessario esaminare le informazioni dall'assembly di definizione del tipo di supporto. Ad esempio, per elaborare il markup `<Party><PartyFavor/></Party>`, il contesto dello schema XAML deve essere in grado di determinare il nome e il tipo del `ContentProperty` di `Party`e pertanto deve inoltre conoscere le informazioni dello spazio dei nomi XAML per `Party` e `PartyFavor`. Nel caso di contesto dello schema XAML predefinito, la reflection statica contiene gran parte delle informazioni sul sistema di tipi XAML che è necessario per generare i nodi di tipo XAML nel flusso del nodo.  
  
 Per generare un oggetto grafico da un flusso del nodo XAML, le dichiarazioni dello spazio dei nomi XAML devono esistere per ogni prefisso XAML utilizzati nel codice originale e registrati nel flusso del nodo XAML. A questo punto, vengono create istanze e si verifica il comportamento di mapping dei tipi true.  
  
 Se è necessario per il popolamento preliminare delle informazioni dello spazio dei nomi XAML, in casi in cui lo spazio dei nomi XAML si intende utilizzare contesto dello schema XAML non è definito nel codice, è possibile usare una tecnica di consiste nel dichiarare le dichiarazioni dello spazio dei nomi XML nel <xref:System.Xml.XmlParserContext> per un <xref:System.Xml.XmlReader>. Utilizzare quindi che <xref:System.Xml.XmlReader> come input per un costruttore di reader XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Due altre API che sono importanti per lo spazio dei nomi XAML gestisce nei servizi XAML di .NET Framework sono gli attributi <xref:System.Windows.Markup.XmlnsDefinitionAttribute> e <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Questi attributi si applicano agli assembly. <xref:System.Windows.Markup.XmlnsDefinitionAttribute> viene utilizzato da un contesto dello schema XAML di interpretare le dichiarazioni dello spazio dei nomi XAML che include un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute> viene utilizzato dagli strumenti che generano XAML in modo che un determinato spazio dei nomi XAML può essere serializzato con un prefisso stimabile. Per ulteriori informazioni, vedere [Related di attributi CLR per tipi personalizzati e le librerie](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni su strutture e concetti del flusso del nodo XAML](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
