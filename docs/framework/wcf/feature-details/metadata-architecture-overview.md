---
title: Panoramica dell'architettura dei metadati
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], overview
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
ms.openlocfilehash: a6bd41fa5aed4c2a22ee7c72087e2da0d7e4ea17
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598853"
---
# <a name="metadata-architecture-overview"></a>Panoramica dell'architettura dei metadati
Windows Communication Foundation (WCF) fornisce un'infrastruttura avanzata per l'esportazione, la pubblicazione, il recupero e l'importazione dei metadati del servizio. I servizi WCF utilizzano i metadati per descrivere come interagire con gli endpoint del servizio in modo che gli strumenti, ad esempio Svcutil. exe, possano generare automaticamente il codice client per accedere al servizio.  
  
 La maggior parte dei tipi che costituiscono l'infrastruttura dei metadati WCF si trova nello <xref:System.ServiceModel.Description> spazio dei nomi.  
  
 WCF usa la <xref:System.ServiceModel.Description.ServiceEndpoint> classe per descrivere gli endpoint in un servizio. È possibile utilizzare WCF per generare metadati per gli endpoint di servizio o per importare metadati del servizio per generare <xref:System.ServiceModel.Description.ServiceEndpoint> istanze di.  
  
 WCF rappresenta i metadati per un servizio come un'istanza del <xref:System.ServiceModel.Description.MetadataSet> tipo, la cui struttura è strettamente legata al formato di serializzazione dei metadati definito in WS-MetadataExchange. Il tipo <xref:System.ServiceModel.Description.MetadataSet> raggruppa i metadati effettivi del servizio, ad esempio i documenti Web Services Description Language (WSDL), i documenti di XML Schema o le espressioni WS-Policy, come raccolta di istanze di <xref:System.ServiceModel.Description.MetadataSection>. Ogni istanza di <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> contiene un sottolinguaggio dei metadati specifici e un identificatore. Una <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> può contenere gli elementi seguenti nella proprietà <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=nameWithType>:  
  
- Metadati non elaborati.  
  
- Istanza di <xref:System.ServiceModel.Description.MetadataReference>.  
  
- Istanza di <xref:System.ServiceModel.Description.MetadataLocation>.  
  
 Le istanze di <xref:System.ServiceModel.Description.MetadataReference?displayProperty=nameWithType> puntano a un altro endpoint di scambio di metadati (MEX) e le istanze di <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=nameWithType> puntano a un documento di metadati utilizzando un URL HTTP. WCF supporta l'utilizzo di documenti WSDL per descrivere endpoint di servizio, contratti di servizio, associazioni, modelli di scambio di messaggi, messaggi e messaggi di errore implementati da un servizio. I tipi di dati utilizzati dal servizio sono descritti nei documenti WSDL utilizzando XML Schema. Per ulteriori informazioni, vedere [importazione ed esportazione di schemi](schema-import-and-export.md). È possibile utilizzare WCF per esportare e importare estensioni WSDL per il comportamento del servizio, i comportamenti del contratto e gli elementi di associazione che estendono la funzionalità di un servizio. Per ulteriori informazioni, vedere [esportazione di metadati personalizzati per un'estensione WCF](../extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-service-metadata"></a>Esportazione di metadati del servizio  
 In WCF l' *esportazione dei metadati* è il processo di descrizione degli endpoint di servizio e di proiezione in una rappresentazione parallela standardizzata che i client possono usare per comprendere come usare il servizio. Per esportare metadati da istanze di <xref:System.ServiceModel.Description.ServiceEndpoint>, utilizzare un'implementazione della classe astratta <xref:System.ServiceModel.Description.MetadataExporter>. Un'implementazione <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> genera metadati che sono incapsulati in un'istanza di <xref:System.ServiceModel.Description.MetadataSet>.  
  
 La classe <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> fornisce un framework per la generazione di espressioni di criteri che descrivono le funzionalità e i requisiti di un'associazione di endpoint e le operazioni, i messaggi e gli errori pertinenti. Queste espressioni di criteri vengono acquisite in un'istanza di <xref:System.ServiceModel.Description.PolicyConversionContext>. Un'implementazione di <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> può quindi collegare tali espressioni di criteri ai metadati che genera.  
  
 <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> chiama ogni <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> che implementa l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension> nell'associazione di un <xref:System.ServiceModel.Description.ServiceEndpoint> durante la generazione di un oggetto <xref:System.ServiceModel.Description.PolicyConversionContext> che deve essere utilizzato dall'implementazione di <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>. È possibile esportare nuove asserzioni di criteri implementando l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension> nelle implementazioni personalizzate del tipo <xref:System.ServiceModel.Channels.BindingElement>.  
  
 Il <xref:System.ServiceModel.Description.WsdlExporter> tipo è l'implementazione della <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> classe astratta inclusa in WCF. Il tipo <xref:System.ServiceModel.Description.WsdlExporter> genera metadati WSDL con allegate le espressioni di criteri.  
  
 Per esportare metadati WSDL personalizzati o estensioni WSDL per i comportamenti degli endpoint, i comportamenti del contratto o elementi di associazione in un endpoint del servizio, è possibile implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension>. <xref:System.ServiceModel.Description.WsdlExporter> cerca in un'istanza <xref:System.ServiceModel.Description.ServiceEndpoint> elementi di associazione, comportamenti dell'operazione, comportamenti del contratto e comportamenti degli endpoint che implementano l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> in fase di generazione del documento WSDL.  
  
## <a name="publishing-service-metadata"></a>Pubblicazione di metadati del servizio  
 I servizi WCF pubblicano i metadati esponendo uno o più endpoint di metadati. La pubblicazione dei metadati del servizio li rende disponibili utilizzando i protocolli standard, ad esempio le richieste MEX e HTTP/GET. Gli endpoint dei metadati sono accomunati ad altri endpoint del servizio dal fatto di avere un indirizzo, un'associazione e un contratto. È possibile aggiungere endpoint dei metadati a un host del servizio nella configurazione o nel codice.  
  
 Per pubblicare endpoint dei metadati per un servizio WCF, è innanzitutto necessario aggiungere al servizio un'istanza del <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamento del servizio. L'aggiunta di un'istanza <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> al servizio aggiunge a quest'ultimo la capacità di pubblicare metadati esponendo uno o più endpoint dei metadati. Dopo aver aggiunto il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, è possibile esporre gli endpoint dei metadati che supportano il protocollo MEX o quelli che rispondono alle richieste HTTP/GET.  
  
 Per aggiungere endpoint dei metadati che utilizzano il protocollo MEX, aggiungere gli endpoint del servizio all'host del servizio che utilizzano il contratto di servizio denominato IMetadataExchange. WCF definisce l' <xref:System.ServiceModel.Description.IMetadataExchange> interfaccia con il nome del contratto di servizio. Gli endpoint WS-MetadataExchange, o gli endpoint MEX, possono utilizzare una delle quattro associazioni predefinite esposte dai metodi factory statici sulla <xref:System.ServiceModel.Description.MetadataExchangeBindings> classe in modo che corrispondano alle associazioni predefinite utilizzate dagli strumenti WCF, ad esempio Svcutil. exe. È inoltre possibile configurare gli endpoint dei metadati MEX utilizzando un'associazione personalizzata.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> utilizza un oggetto <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> per esportare i metadati per tutti gli endpoint nel servizio. Per ulteriori informazioni sull'esportazione di metadati da un servizio, vedere [esportazione e importazione di metadati](exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> aggiunge all'host del servizio un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataExtension> come estensione. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> fornisce l'implementazione per i metadati che pubblicano protocolli. È inoltre possibile utilizzare <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> per ottenere i metadati del servizio in fase di esecuzione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>.  
  
> [!CAUTION]
> Se si aggiunge un endpoint MEX al file di configurazione dell'applicazione e quindi si tenta di aggiungere l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> all'host del servizio nel codice, verrà generata l'eccezione seguente:  
>
> System.InvalidOperationException: Impossibile trovare il nome contratto 'IMetadataExchange' nell'elenco dei contratti implementati dal servizio Service1. Aggiungere un elemento ServiceMetadataBehavior al file di configurazione oppure direttamente a ServiceHost per abilitare il supporto per questo contratto.  
>
> Per risolvere il problema, aggiungere l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al file di configurazione oppure aggiungere sia l'endpoint che l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al codice.  
>
> Per un esempio di aggiunta <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in un file di configurazione dell'applicazione, vedere il [Introduzione](../samples/getting-started-sample.md). Per un esempio di aggiunta di <xref:System.ServiceModel.Description.ServiceMetadataBehavior> nel codice, vedere l'esempio [self-host](../samples/self-host.md) .  

> [!CAUTION]
> Quando si pubblicano metadati per un servizio che espone due contratti di servizio diversi in cui ciascuno contiene un'operazione dello stesso nome viene generata un'eccezione. Se ad esempio è presente un servizio che espone un contratto di servizio denominato ICarService con un'operazione Get(Car c) e lo stesso servizio espone un contratto di servizio denominato IBookService con un'operazione Get(Book b), viene generata un'eccezione o viene visualizzato un messaggio di errore durante la creazione dei metadati del servizio. Per risolvere il problema, effettuare una delle operazioni seguenti:  
>
> - Rinominare una delle operazioni.
> - Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.  
> - Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
## <a name="retrieving-service-metadata"></a>Recupero di metadati del servizio  
 WCF può recuperare i metadati del servizio utilizzando protocolli standardizzati come WS-MetadataExchange e HTTP. Entrambi questi protocolli sono supportati dal tipo <xref:System.ServiceModel.Description.MetadataExchangeClient>. Per recuperare i metadati del servizio, utilizzare il tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> fornendo un indirizzo e un'associazione facoltativa. L'associazione utilizzata da un'istanza <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> può essere una delle associazioni predefinite dalla classe statica <xref:System.ServiceModel.Description.MetadataExchangeBindings>, un'associazione fornita dall'utente o un'associazione caricata dalla configurazione dell'endpoint per il contratto `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> può inoltre risolvere i riferimenti dell'URL HTTP ai metadati utilizzando il tipo <xref:System.Net.HttpWebRequest>.  
  
 Per impostazione predefinita, un'istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> è collegata a una sola istanza di <xref:System.ServiceModel.Channels.ChannelFactoryBase>. È possibile modificare o sostituire l'istanza di <xref:System.ServiceModel.Channels.ChannelFactoryBase> utilizzata da <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> eseguendo l'override del metodo virtuale <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. Analogamente, è possibile modificare o sostituire l'istanza di <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> utilizzata da <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> per le richieste HTTP/GET eseguendo l'override del metodo virtuale <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
 È possibile recuperare i metadati del servizio usando le richieste WS-MetadataExchange o HTTP/GET usando lo strumento Svcutil. exe e passando l'opzione **/target: Metadata** e un indirizzo. Svcutil.exe scarica i metadati all'indirizzo specificato e salva i file su disco. Svcutil.exe utilizza un'istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> internamente e carica una configurazione dell'endpoint MEX (dal file di configurazione dell'applicazione) il cui nome corrisponde allo schema dell'indirizzo passato a Svcutil.exe, se presente. In caso contrario, Svcutil.exe utilizza per impostazione predefinita una delle associazioni definite dal tipo di factory statico <xref:System.ServiceModel.Description.MetadataExchangeBindings>.  
  
## <a name="importing-service-metadata"></a>Importazione di metadati del servizio  
 In WCF l'importazione dei metadati è il processo di generazione di una rappresentazione astratta di un servizio o delle relative parti dei componenti dai relativi metadati. Ad esempio, WCF può importare <xref:System.ServiceModel.Description.ServiceEndpoint> istanze, <xref:System.ServiceModel.Channels.Binding> istanze o <xref:System.ServiceModel.Description.ContractDescription> istanze da un documento WSDL per un servizio. Per importare metadati del servizio in WCF, utilizzare un'implementazione della <xref:System.ServiceModel.Description.MetadataImporter> classe astratta. I tipi che derivano dalla <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> classe implementano il supporto per l'importazione di formati di metadati che sfruttano la logica di importazione WS-Policy in WCF.  
  
 Un'implementazione di <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> raccoglie le espressioni di criteri collegate ai metadati del servizio in un oggetto <xref:System.ServiceModel.Description.PolicyConversionContext>. <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> elabora quindi i criteri come parte dell'importazione dei metadati chiamando le implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension> nella proprietà <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>.  
  
 È possibile aggiungere il supporto per importare nuove asserzioni di criteri in un <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> aggiungendo la propria implementazione dell'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension> alla raccolta <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> in un'istanza <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>. In alternativa, è possibile registrare l'estensione di importazione dei criteri nel file di configurazione dell'applicazione client.  
  
 Il <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> tipo è l'implementazione della <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> classe astratta inclusa in WCF. Il tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> importa metadati WSDL insieme ai relativi criteri allegati. Questi elementi vengono quindi raggruppati in un oggetto <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Per aggiungere il supporto per l'importazione di estensioni WSDL, implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension>, quindi aggiungere tale implementazione alla proprietà <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> nell'istanza di <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>. È inoltre possibile utilizzare il tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> per caricare implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> registrate nel file di configurazione dell'applicazione client.  
  
## <a name="dynamic-bindings"></a>Associazioni dinamiche  
 È possibile aggiornare dinamicamente l'associazione utilizzata per creare un canale per un endpoint del servizio nel caso in cui l'associazione per l'endpoint cambi o si desideri creare un canale per un endpoint che utilizza lo stesso contratto ma ha un'associazione diversa. È possibile utilizzare la <xref:System.ServiceModel.Description.MetadataResolver> classe statica per recuperare e importare metadati in fase di esecuzione per endpoint del servizio che implementano un contratto specifico. È quindi possibile utilizzare gli oggetti <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> importati per creare un client o una channel factory per l'endpoint desiderato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description>
- [Formati dei metadati](metadata-formats.md)
- [Esportazione e importazione di metadati](exporting-and-importing-metadata.md)
- [Pubblicazione di metadati](publishing-metadata.md)
- [Recupero di metadati](retrieving-metadata.md)
- [Uso di metadati](using-metadata.md)
- [Considerazioni sulla sicurezza con metadati](security-considerations-with-metadata.md)
- [Estensione del sistema di metadati](../extending/extending-the-metadata-system.md)
