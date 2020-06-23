---
title: Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)
description: Informazioni sull'utilità ServiceModel Metadata, che genera codice del modello del servizio WFC da documenti di metadati e documenti di metadati dal codice del modello di servizio.
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], building
- endpoints [WCF]
- Svcutil.exe
- clients [WCF], consuming services
ms.assetid: 1abf3d9f-b420-46f1-b628-df238751f308
ms.openlocfilehash: 9f8e8e0239f8f8cd149bc6e8b1d7921124731087
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245947"
---
# <a name="servicemodel-metadata-utility-tool-svcutilexe"></a>Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)

Lo strumento ServiceModel Metadata Utility Tool viene usato per generare codice del modello di servizio da documenti di metadati e documenti di metadati dal codice del modello di servizio.

## <a name="svcutilexe"></a>SvcUtil.exe

Lo strumento ServiceModel Metadata Utility Tool si trova nel percorso di installazione Windows SDK, in particolare *%Programmi%\Microsoft SDKs\Windows\v6.0\Bin*.

### <a name="functionalities"></a>Funzionalità

Nella tabella seguente sono riepilogate le varie funzionalità fornite da questo strumento e l'argomento corrispondente in cui viene illustrata la modalità di utilizzo:

|Attività|Argomento|
|----------|-----------|
|Consente di generare codice dai servizi in esecuzione o dai documenti di metadati statici.|[Generazione di un client WCF dai metadati del servizio](./feature-details/generating-a-wcf-client-from-service-metadata.md)|
|Consente di esportare documenti di metadati da codice compilato.|[Procedura: usare Svcutil.exe per esportare metadati dal codice del servizio compilato](./feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)|
|Consente di convalidare codice di servizio compilato.|[Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato](./feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)|
|Consente di scaricare documenti di metadati dai servizi in esecuzione.|[Procedura: usare Svcutil.exe per scaricare documenti di metadati](./feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)|
|Consente di generare codice di serializzazione.|[Procedura: migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)|

> [!CAUTION]
> Svcutil sovrascrive i file esistenti su un disco se i nomi specificati come parametri sono identici. Questo può includere file di codice, di configurazione o di metadati. Per evitare questo problema durante la generazione di codice e file di configurazione, usare l' `/mergeConfig` opzione.
>
> Inoltre, le `/r` Opzioni e `/ct` per i tipi di riferimento sono per la generazione di contratti dati. Questi commutatori non funzionano in caso di utilizzo di XmlSerializer.

### <a name="timeout"></a>Timeout

Lo strumento ha un timeout di cinque minuti durante il recupero dei metadati. Questo timeout si applica solo al recupero di metadati sulla rete. Non si applica a qualsiasi elaborazione dei metadati.

### <a name="multi-targeting"></a>Multitargeting

Lo strumento non supporta il multitargeting. Se si desidera generare un artefatto .NET 4 da *svcutil.exe*, utilizzare l' *svcutil.exe* da .NET 4 SDK. Per generare un artefatto .NET 3.5, utilizzare l'eseguibile nell'SDK di .NET 3.5.

### <a name="accessing-wsdl-documents"></a>Accesso ai documenti WSDL

Quando si utilizza Svcutil per accedere a un documento WSDL che presenti un riferimento al servizio token di sicurezza (STS), Svcutil effettua una chiamata di WS-MetadataExchange a STS. Tuttavia, il servizio può esporre il proprio documento WSDL utilizzando sia WS-MetadataExchange, sia HTTP GET. Pertanto, se il servizio STS ha esposto solo il documento WSDL utilizzando HTTP GET, un client scritto in WinFX avrà esito negativo. Per i client scritti in .NET Framework 3,5, Svcutil tenta di utilizzare sia WS-MetadataExchange che HTTP GET per ottenere il file WSDL di STS.

## <a name="using-svcutilexe"></a>Utilizzo di SvcUtil.exe

### <a name="common-usages"></a>Utilizzi comuni

La tabella seguente illustra alcune opzioni di uso comune per questo strumento:

|Opzione|Descrizione|
|------------|-----------------|
|/Directory\<directory>|Directory nella quale creare file.<br /><br /> Impostazione predefinita: directory corrente.<br /><br /> Forma abbreviata: `/d`|
|/help|Visualizza la sintassi e le opzioni dei comandi dello strumento.<br /><br /> Forma abbreviata: `/?`|
|/noLogo|Eliminare le informazioni di copyright e il messaggio di avvio.|
|/svcutilConfig:\<configFile>|Consente di specificare un file di configurazione personalizzato da utilizzare in sostituzione del file App.config. Questo file può essere utilizzato per registrare estensioni system.serviceModel senza alterare il file di configurazione dello strumento.|
|/target:\<output type>|Consente di specificare l’output che verrà generato dallo strumento.<br /><br /> I valori validi sono codice, metadati o xmlSerializer.<br /><br /> Forma abbreviata: `/t`|

### <a name="code-generation"></a>Generazione di codice

Lo strumento Svcutil.exe è in grado di generare codice per contratti di servizio, client e tipi di dati dai documenti di metadati. Questi documenti di metadati possono essere salvati in modo permanente o recuperati online. Il recupero online segue il protocollo WS-Metadata Exchange o il protocollo DISCO (per i dettagli vedere la sezione Download dei metadati).

È possibile utilizzare lo strumento *SvcUtil.exe* per generare contratti di servizio e dati basati su un documento WSDL predefinito. Utilizzare l'opzione /serviceContract e specificare un URL o un percorso di file in cui il documento WSDL possa essere scaricato o trovato. In questo modo vengono generati i contratti di servizio e dati definiti nel documento WSDL che possono quindi essere utilizzati per implementare un servizio di reclamo. Per altre informazioni, vedere [procedura: recuperare metadati e implementare un servizio conforme](./feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md).

Per un servizio con un endpoint BasicHttpContextBinding, *Svcutil.exe* genera un BasicHttpBinding con l' `allowCookies` attributo impostato su `true` . I cookie vengono utilizzati come contesto sul server. Se si desidera gestire il contesto sul client quando il servizio utilizza cookie, è possibile modificare la configurazione per utilizzare un elemento di associazione del contesto.

> [!CAUTION]
> Lo strumento Svcutil.exe consente di generare il client in base al WSDL o al file dei criteri ricevuto dal servizio. Il nome dell'entità utente (UPN) viene generato concatenando il nome utente " \@ " e un nome di dominio completo (FQDN). Per utenti registrati su Active Directory, questo formato non è tuttavia valido e l’UPN generato dallo strumento provoca un errore di autenticazione Kerberos con il messaggio di errore che “Tentativo di accesso non riuscito”. Per risolvere questo problema è necessario correggere manualmente il file client generato da questo strumento.

`svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>`

|Argomento|Descrizione|
|--------------|-----------------|
|`epr`|Percorso di un file XML contenente un EndpointReference WS-Addressing per un endpoint di servizio che supporta WS-MetadataExchange. Per ulteriori informazioni, vedere la sezione Download dei metadati.|
|`metadataDocumentPath`|Percorso di un documento di metadati (*WSDL* o *xsd*) che contiene il contratto da importare nel codice (con estensione WSDL, XSD, wspolicy o wsmex).<br /><br /> Lo strumento Svcutil consente di importare e includere quando si specifica un URL remoto per metadati. Tuttavia, se si desidera elaborare file di metadati sul file system locale, è necessario specificare tutti i file di questo argomento. In questo modo, è possibile utilizzare Svcutil in un ambiente di compilazione dove non è possibile avere dipendenze della rete. Per questo argomento è possibile usare caratteri jolly (*. xsd, \* . WSDL).|
|`url`|URL a un endpoint di servizio che fornisce metadati o a un documento di metadati ospitato online. Per ulteriori informazioni sulla modalità di recupero di questi documenti, vedere la sezione Download dei metadati.|

|Opzione|Descrizione|
|------------|-----------------|
|/async|Genera firme di metodi sincrone e asincrone.<br /><br /> Impostazione predefinita: generare solo firme di metodi sincrone.<br /><br /> Forma abbreviata: `/a`|
|CollectionType\<type>|Specifica il tipo di raccolta elenco per un client WCF.<br/><br /> Impostazione predefinita: il tipo di raccolta è System. Array. <br /><br /> Forma abbreviata: `/ct`|
|/config:\<configFile>|Specifica il nome file per il file di configurazione generato.<br /><br /> Impostazione predefinita: output.config|
|/dataContractOnly|Genera solo codice per tipi di contratto dati. I tipi di contratto di servizio non vengono generati.<br /><br /> Per questa opzione è necessario specificare soltanto file di metadati locali.<br /><br /> Forma abbreviata: `/dconly`|
|/enableDataBinding|Implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> su tutti i tipi di contratto dati per consentire il data binding.<br /><br /> Forma abbreviata: `/edb`|
|/excludeType:\<type>|Specifica un nome tipo completo o un nome completo del tipo dell’assembly da escludere dai tipi di contratto a cui si fa riferimento.<br /><br /> Se si utilizza questo commutatore insieme con `/r` di DLL distinte, viene fatto riferimento al nome completo della classe XSD.<br /><br /> Forma abbreviata: `/et`|
|/importXmlTypes|Configura il serializzatore DataContract per l'importazione di tipi diversi da DataContract come tipi IXmlSerializable.|
|/internal|Genera classi contrassegnate come interne. Impostazione predefinita: generare soltanto classi pubbliche.<br /><br /> Forma abbreviata: `/i`|
|/Language\<language>|Specifica il linguaggio di programmazione da utilizzare per la generazione del codice. È necessario specificare un nome di linguaggio registrato nel file di Machine.config o il nome completo di una classe che eredita da <xref:System.CodeDom.Compiler.CodeDomProvider> .<br /><br /> Values: c#, cs, csharp, vb, visualbasic, c++, cpp<br /><br /> Impostazione predefinita: csharp<br /><br /> Forma abbreviata: `/l`|
|/mergeConfig|Incorpora la configurazione generata in un file esistente, anziché sovrascrivere il file esistente.|
|/messageContract|Genera tipi di contratto di messaggio.<br /><br /> Forma abbreviata: `/mc`|
|/namespace\<string,string>|Specifica un mapping da WSDL o XML Schema targetNamespace a uno spazio dei nomi CLR. Con ' \* ' per targetNamespace viene eseguito il mapping di tutti i targetNamespace senza un mapping esplicito a tale spazio dei nomi CLR.<br /><br /> Per assicurarsi che il nome del contratto di messaggio non entri in conflitto con il nome dell'operazione, è necessario qualificare il riferimento al tipo con `::` o verificare che i nomi siano univoci.<br /><br /> Impostazione predefinita: derivata dallo spazio dei nomi di destinazione del documento dello schema per i Contratti dati. Lo spazio dei nomi predefinito viene utilizzato per tutti gli altri tipi generati.<br /><br /> Forma breve: `/n` **Nota:** quando si generano tipi da usare con XmlSerializer, è supportato un solo mapping dello spazio dei nomi. Tutti i tipi generati saranno nello spazio dei nomi predefinito o nello spazio dei nomi specificato da "*".|
|/noConfig|Non genera file di configurazione.|
|/noStdLib|Non fare riferimento a librerie standard.<br /><br /> Impostazione predefinita: viene fatto riferimento a Mscorlib.dll e System.servicemodel.dll.|
|/out\<file>|Specifica il nome del file per il codice generato.<br /><br /> Impostazione predefinita: derivata dal nome della definizione di WSDL, dal nome del servizio WSDL o dallo spazio dei nomi di destinazione di uno degli schemi.<br /><br /> Forma abbreviata: `/o`|
|/Reference\<file path>|Fa riferimento a tipi nell'assembly specificato. Quando si generano client, utilizzare questa opzione per specificare assembly che potrebbero contenere tipi che rappresentano i metadati importati.<br /><br /> Non è possibile specificare contratti di messaggio e tipi <xref:System.Xml.Serialization.XmlSerializer> utilizzando questo commutatore.<br /><br /> Se <xref:System.DateTimeOffset> fa riferimento, viene utilizzato questo tipo invece di generare un tipo nuovo. Se l'applicazione viene scritta usando .NET Framework 3,5, SvcUtil.exe automaticamente i riferimenti <xref:System.DateTimeOffset> .<br /><br /> Forma abbreviata: `/r`|
|/serializable|Genera classi contrassegnate con Attributo serializzabile.<br /><br /> Forma abbreviata: `/s`|
|/serviceContract|Genera codice solo per i contratti di servizio. La classe e la configurazione client non verranno generate.<br /><br /> Forma abbreviata: `/sc`|
|/serializer:Auto|Selezionare automaticamente il serializzatore. Questa operazione tenta di utilizzare il serializzatore dei contratti dati e utilizza XmlSerializer se questa operazione ha esito negativo.<br /><br /> Forma abbreviata: `/ser`|
|/serializer:DataContractSerializer|Genera tipi di dati che utilizzano DataContract Serializer per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:DataContractSerializer`|
|/serializer:XmlSerializer|Genera tipi di dati che utilizzano <xref:System.Xml.Serialization.XmlSerializer> per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:XmlSerializer`|
|/targetClientVersion|Specificare la versione di .NET Framework destinazione dell'applicazione. I valori validi sono `Version30` e `Version35`. Il valore predefinito è `Version30`.<br /><br /> Forma abbreviata: `/tcv`<br /><br /> `Version30`: Usare `/tcv:Version30` se si genera codice per i client che usano WinFX.<br /><br /> `Version35`: Usare `/tcv:Version35` se si sta generando codice per i client che usano .NET Framework 3,5. Se si utilizza `/tcv:Version35` con il commutatore `/async`, vengono generati entrambi metodi asincroni sia basati su eventi che su delegati/callback. Viene inoltre abilitato il supporto per dataset abilitati da LINQ e <xref:System.DateTimeOffset>.|
|/wrapped|Controlla se viene utilizzata una combinazione di maiuscole e minuscole speciale per i documenti in stile document-literal con parametri sottoposti a wrapping. Utilizzare l'opzione **/wrapped** con lo strumento [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per specificare la normale combinazione di maiuscole e minuscole.|

> [!NOTE]
> Quando l'associazione al servizio è una delle associazioni fornite dal sistema (vedere le [associazioni fornite dal sistema](system-provided-bindings.md)) e la <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> proprietà è impostata su `None` o `Sign` , Svcutil genera un file di configurazione utilizzando l' [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) elemento anziché l'elemento previsto fornito dal sistema. Ad esempio, se il servizio utilizza l'elemento `<wsHttpBinding>` con `ProtectionLevel` impostato su `Sign`, la configurazione generata ha `<customBinding>` nella sezione delle associazioni anziché `<wsHttpBinding>`. Per ulteriori informazioni sul livello di protezione, vedere informazioni sul [livello](understanding-protection-level.md)di protezione.

### <a name="metadata-export"></a>Esportazione dei metadati

Svcutil.exe è in grado di esportare metadati per servizi, contratti e tipi di dati in assembly compilati. Per esportare metadati per un servizio, è necessario utilizzare l'opzione `/serviceName` per specificare il servizio che si desidera esportare. Per esportare tutti i tipi di contratto dati all'interno di un assembly, utilizzare l'opzione `/dataContractOnly`. Per impostazione predefinita, i metadati vengono esportati per tutti i contratti di servizio negli assembly di input.

`svcutil.exe [/t:metadata] [/serviceName:<serviceConfigName>] [/dataContractOnly] <assemblyPath>*`

|Argomento|Descrizione|
|--------------|-----------------|
|`assemblyPath`|Specifica il percorso per un assembly contenente servizi, contratti o tipi di contratto dati da esportare. È possibile utilizzare caratteri jolly della riga di comando standard per fornire più file come input.|

|Opzione|Descrizione|
|------------|-----------------|
|ServiceName\<serviceConfigName>|Specifica il nome della configurazione di un servizio da esportare. Se viene utilizzata questa opzione, deve essere passato come input un assembly eseguibile con un file di configurazione associato. Svcutil.exe esegue la ricerca in tutti i file di configurazione associati per la configurazione del servizio. Se i file di configurazione contengono qualsiasi tipo di estensione, gli assembly contenenti questi tipi devono essere in GAC o devono essere forniti in modo esplicito utilizzando l'opzione `/reference`.|
|/Reference\<file path>|Aggiunge l'assembly specificato al set di assembly utilizzato per la risoluzione di riferimenti del tipo. Se si sta esportando o convalidando un servizio che utilizza estensioni di terzi (Comportamenti, Associazioni e BindingElements) registrate in configurazione, utilizzare questa opzione per ricercare assembly di estensione che non si trovano in GAC.<br /><br /> Forma abbreviata: `/r`|
|/dataContractOnly|Opera soltanto su tipi di contratto dati. I contratti di servizio non vengono elaborati.<br /><br /> Per questa opzione è necessario specificare soltanto file di metadati locali.<br /><br /> Forma abbreviata: `/dconly`|
|/excludeType:\<type>|Specifica il nome completo o il nome completo dell’assembly del tipo da escludere dall’esportazione. Questa opzione può essere utilizzata quando si esportano metadati per un servizio o un set di contratti di servizio per escludere tipi dall'esportazione. Non è possibile utilizzare questa opzione con l'opzione `/dconly`.<br /><br /> Quando si ha un solo assembly contenente più servizi che utilizzano classi separate con lo nome XSD, è necessario specificare il nome del servizio anziché il nome della classe XSD per questo commutatore.<br /><br /> Non vengono supportati tipi XSD o tipi di contratto dati.<br /><br /> Forma abbreviata: `/et`|

### <a name="service-validation"></a>Convalida del servizio

È possibile utilizzare la convalida per rilevare errori in implementazioni del servizio senza ospitare il servizio. È necessario utilizzare l'opzione `/serviceName` per indicare il servizio che si desidera convalidare.

`svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*`

|Argomento|Descrizione|
|--------------|-----------------|
|`assemblyPath`|Specifica il percorso per un assembly contenente tipi di contratto di servizio da convalidare. L'assembly deve avere un file di configurazione associato per fornire la configurazione del servizio. È possibile utilizzare caratteri jolly della riga di comando standard per fornire più assembly.|

|Opzione|Descrizione|
|------------|-----------------|
|/validate|Convalida un'implementazione del servizio specificata dall'opzione `/serviceName`. Se viene utilizzata questa opzione, deve essere passato come input un assembly eseguibile con un file di configurazione associato.<br /><br /> Forma abbreviata: `/v`|
|ServiceName\<serviceConfigName>|Specifica il nome della configurazione di un servizio da convalidare. Svcutil.exe esegue la ricerca in tutti i file di configurazione associati di tutti gli assembly di input per la configurazione del servizio. Se i file di configurazione contengono qualsiasi tipo di estensione, gli assembly contenenti questi tipi devono essere in GAC o devono essere forniti in modo esplicito utilizzando l'opzione `/reference`.|
|/Reference\<file path>|Aggiunge l'assembly specificato al set di assembly utilizzato per la risoluzione di riferimenti del tipo. Se si sta esportando o convalidando un servizio che utilizza estensioni di terzi (Comportamenti, Associazioni e BindingElements) registrate in configurazione, utilizzare questa opzione per ricercare assembly di estensione che non si trovano in GAC.<br /><br /> Forma abbreviata: `/r`|
|/dataContractOnly|Opera soltanto su tipi di contratto dati. I contratti di servizio non vengono elaborati.<br /><br /> Per questa opzione è necessario specificare soltanto file di metadati locali.<br /><br /> Forma abbreviata: `/dconly`|
|/excludeType:\<type>|Specifica il nome completo o il nome completo dell’assembly del tipo da escludere dalla convalida.<br /><br /> Forma abbreviata: `/et`|

### <a name="metadata-download"></a>Download dei metadati

È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali. Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`. In caso contrario, viene generato il codice client. Per schemi URL HTTP e HTTPS, Svcutil.exe tenta di recuperare i metadati mediante WS-Metadata Exchange e DISCO. Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-Metadata Exchange.

Svcutil genera le richieste di metadati seguenti simultaneamente per recuperare metadati.

- Richiesta MEX (WS-Transfer) all'indirizzo fornito

- Richiesta MEX all'indirizzo fornito con /mex accodati

- Richiesta DISCO (utilizzo di DiscoveryClientProtocol da ASMX) all'indirizzo fornito.

Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings> per generare richieste MEX. Per configurare l'associazione utilizzata per WS-Metadata Exchange è necessario definire un endpoint client in configurazione che utilizza il contratto IMetadataExchange. Ciò può essere definito nel file di configurazione di Svcutil.exe o in un altro file di configurazione specificato utilizzando l'opzione `/svcutilConfig`.

`svcutil.exe /t:metadata  <url>* | <epr>`

|Argomento|Descrizione|
|--------------|-----------------|
|`url`|URL a un endpoint di servizio che fornisce metadati o a un documento di metadati ospitato online.|
|`epr`|Percorso di un file XML contenente un EndpointReference WS-Addressing per un endpoint di servizio che supporta WS-MetadataExchange.|

### <a name="xmlserializer-type-generation"></a>Generazione del tipo XmlSerializer

I servizi e le applicazioni client che utilizzano tipi di dati serializzabili tramite <xref:System.Xml.Serialization.XmlSerializer> generano e compilano il codice di serializzazione per tali dati in fase di esecuzione, il che può rallentare le prestazioni all'avvio.

> [!NOTE]
> Un codice di serializzazione pregenerato può essere utilizzato solamente nelle applicazioni client e non nei servizi.

Svcutil.exe può generare il codice di serializzazione C# necessario dagli assembly compilati per l’applicazione, migliorando le prestazioni all'avvio per queste applicazioni. Per ulteriori informazioni, vedere [procedura: migliorare il tempo di avvio delle applicazioni client WCF utilizzando XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

> [!NOTE]
> Svcutil.exe genera soltanto codice per tipi utilizzati dai Contratti di Servizio che si trovano negli assembly di input.

`svcutil.exe /t:xmlSerializer  <assemblyPath>*`

|Argomento|Descrizione|
|--------------|-----------------|
|`assemblyPath`|Specifica il percorso per un assembly contenente tipi di contratto di servizio. I tipi di serializzazione vengono generati per tutti i tipi serializzabili in Xml in ogni contratto.|

|Opzione|Descrizione|
|------------|-----------------|
|/Reference\<file path>|Aggiunge l'assembly specificato al set di assembly utilizzato per la risoluzione di riferimenti del tipo.<br /><br /> Forma abbreviata: `/r`|
|/excludeType:\<type>|Specifica il nome completo o il nome completo dell’assembly del tipo da escludere dall’esportazione o convalida.<br /><br /> Forma abbreviata: `/et`|
|/out\<file>|Specifica il nome file per il codice generato. Questa opzione è ignorata quando più assembly vengono passati come input allo strumento.<br /><br /> Impostazione predefinita: derivata dal nome dell'assembly.<br /><br /> Forma abbreviata: `/o`|
|/UseSerializerForFaults|Specifica che per la lettura e la scrittura degli errori deve essere utilizzato <xref:System.Xml.Serialization.XmlSerializer> anziché l'oggetto predefinito <xref:System.Runtime.Serialization.DataContractSerializer>.|

## <a name="examples"></a>Esempi

Il comando seguente consente di generare il codice client da un servizio in esecuzione o da documenti di metadati online.

`svcutil http://service/metadataEndpoint`

Il comando seguente consente di generare il codice client da documenti di metadati locali.

`svcutil *.wsdl *.xsd /language:C#`

Il comando seguente consente di generare tipi di contratto dati in Visual Basic dai documenti di schema locali.

`svcutil /dconly *.xsd /language:VB`

Il comando seguente consente di scaricare i documenti di metadati da servizi in esecuzione.

`svcutil /t:metadata http://service/metadataEndpoint`

Il comando seguente consente di generare i documenti di metadati per contratti di servizio tipi associati in un assembly.

`svcutil myAssembly.dll`

Il comando seguente consente di generare documenti di metadati per un servizio e tutti i contratti di servizio e tipi di dati associati in un assembly.

`svcutil myServiceHost.exe /serviceName:myServiceName`

Il comando seguente consente di generare documenti di metadati per tipi di dati in un assembly.

`svcutil myServiceHost.exe /dconly`

Il comando seguente consente di verificare l’host del servizio.

`svcutil /validate /serviceName:myServiceName myServiceHost.exe`

Il comando seguente consente di generare tipi di serializzazione per i tipi <xref:System.Xml.Serialization.XmlSerializer> utilizzati da qualsiasi contratto di servizio nell'assembly.

`svcutil /t:xmlserializer myContractLibrary.exe`

## <a name="maximum-nametable-character-count-quota"></a>Quota per il numero massimo di caratteri della tabella dei nomi.

Quando si utilizza svcutil per generare metadati per un servizio, è possibile che venga visualizzato il messaggio seguente:

Errore: non è stato possibile ottenere i metadati dalla `http://localhost:8000/somesservice/mex` quota del numero massimo di caratteri NameTable (16384) durante la lettura dei dati XML. La tabella dei nomi è una struttura dati utilizzata per memorizzare le stringhe trovate durante l'elaborazione dei dati XML. Documenti XML lunghi con nomi di elementi, nomi di attributi e valori di attributi non ripetuti possono comportare il superamento della quota. Tale quota può essere incrementata modificando la proprietà MaxNameTableCharCount dell'oggetto XmlDictionaryReaderQuotas utilizzato durante la creazione del lettore XML.

Questo errore può essere causato dalla restituzione di un file WSDL di grandi dimensioni da parte di un servizio quando vengono richiesti i relativi metadati. Il problema deriva dal superamento della quota di caratteri per lo strumento svcutil.exe. Questo valore viene impostato per contribuire a impedire attacchi di tipo Denial of Service (DoS). Questa quota può essere aumentata specificando il seguente file di configurazione per svcutil.

Nel file di configurazione seguente viene mostrato come impostare le quote del lettore per svcutil

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <customBinding>
                <binding name="MyBinding">
                    <textMessageEncoding>
                        <readerQuotas maxDepth="2147483647" maxStringContentLength="2147483647"
                            maxArrayLength="2147483647" maxBytesPerRead="2147483647" maxNameTableCharCount="2147483647" />
                    </textMessageEncoding>
                    <httpTransport maxReceivedMessageSize="2147483647" maxBufferSize="2147483647" />
                </binding>
            </customBinding>
        </bindings>
        <client>
            <endpoint binding="customBinding" bindingConfiguration="MyBinding"
                contract="IMetadataExchange"
                name="http" />
        </client>
    </system.serviceModel>
</configuration>
```

Creare un nuovo file denominato svcutil.exe.config e copiarvi il codice XML di esempio. Posizionare il file nella stessa directory in cui si trova svcutil.exe. Alla successiva esecuzione di svcutil.exe, verranno utilizzate le nuove impostazioni.

## <a name="security-concerns"></a>Problemi di sicurezza

È necessario utilizzare l'elenco di controllo di accesso (ACL) appropriato per proteggere la cartella di installazione di Svcutil.exe, Svcutil.config e i file ai quali fa riferimento `/svcutilConfig`. Ciò può impedire la registrazione ed esecuzione di codice dannoso.

Inoltre, per ridurre al minimo le probabilità che la sicurezza venga compromessa, è consigliabile non aggiungere estensioni non attendibili che facciano parte del sistema o utilizzare provider di codice non attendibili con Svcutil.exe.

Infine, non è necessario utilizzare lo strumento al livello intermedio dell'applicazione, in quanto ciò può provocare l’attacco Denial of Service al processo corrente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Procedura: Creare un client](how-to-create-a-wcf-client.md)
