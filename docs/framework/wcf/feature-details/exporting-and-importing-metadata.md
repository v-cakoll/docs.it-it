---
title: Esportazione e importazione di metadati
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], exporting and importing
ms.assetid: 614a75bb-e0b0-4c95-b6d8-02cb5e5ddb38
ms.openlocfilehash: f07a1a10529aa1615bb00a0f3faeca9cb249aa64
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595531"
---
# <a name="exporting-and-importing-metadata"></a>Esportazione e importazione di metadati
In Windows Communication Foundation (WCF) l'esportazione dei metadati è il processo di descrizione degli endpoint di servizio e di proiezione in una rappresentazione parallela standardizzata che i client possono usare per comprendere come usare il servizio. L'importazione dei metadati del servizio è il processo di generazione di istanze o parti di <xref:System.ServiceModel.Description.ServiceEndpoint> dai metadati del servizio.  
  
## <a name="exporting-metadata"></a>Esportazione dei metadati  
 Per esportare metadati da istanze di <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>, utilizzare un'implementazione della classe astratta <xref:System.ServiceModel.Description.MetadataExporter>. Il <xref:System.ServiceModel.Description.WsdlExporter> tipo è l'implementazione della <xref:System.ServiceModel.Description.MetadataExporter> classe astratta inclusa in WCF.  
  
 Il tipo <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> genera metadati Web Services Description Language (WSDL) con allegate espressioni di criteri incapsulate in un'istanza di <xref:System.ServiceModel.Description.MetadataSet>. È possibile utilizzare un'istanza di <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> per esportare in modo iterativo metadati per oggetti <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Description.ServiceEndpoint>. È inoltre possibile esportare una raccolta di oggetti <xref:System.ServiceModel.Description.ServiceEndpoint> e associarli a un nome del servizio specifico.  
  
> [!NOTE]
> `WsdlExporter` può essere utilizzato solo per esportare metadati da istanze `ContractDescription` che contengono informazioni di tipo Common Language Runtime (CLR), ad esempio un'istanza `ContractDescription` creata utilizzando il metodo `ContractDescription.GetContract` o creata come parte di `ServiceDescription` per un'istanza `ServiceHost`. Non è possibile utilizzare `WsdlExporter` per esportare metadati dalle istanze `ContractDescription` importate dai metadati del servizio o create senza informazioni sul tipo.  
  
## <a name="importing-metadata"></a>Importazione dei metadati  
  
### <a name="importing-wsdl-documents"></a>Importazione di documenti WSDL  
 Per importare metadati del servizio in WCF, utilizzare un'implementazione della <xref:System.ServiceModel.Description.MetadataImporter> classe astratta. Il <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> tipo è l'implementazione della <xref:System.ServiceModel.Description.MetadataImporter> classe astratta inclusa in WCF. Il tipo <xref:System.ServiceModel.Description.WsdlImporter> importa metadati WSDL insieme ai relativi criteri allegati. Questi elementi vengono quindi raggruppati in un oggetto <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Il tipo <xref:System.ServiceModel.Description.WsdlImporter> consente di controllare il modo in cui importare i metadati. È possibile importare tutti gli endpoint, tutte le associazioni o tutti i contratti. È possibile importare tutti gli endpoint associati a un servizio WSDL, a un'associazione o a un tipo di porta specifici. È inoltre possibile importare l'endpoint per una porta WSDL specifica, l'associazione per un'associazione WSDL specifica o il contratto per un tipo di porta WSDL specifico.  
  
 <xref:System.ServiceModel.Description.WsdlImporter> espone anche una proprietà <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A> che consente di specificare un set di contratti che non è necessario importare. <xref:System.ServiceModel.Description.WsdlImporter> utilizza i contratti nella proprietà <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A> anziché importare un contratto con lo stesso nome completo dai metadati.  
  
### <a name="importing-policies"></a>Importazione di criteri  
 Il tipo <xref:System.ServiceModel.Description.WsdlImporter> raccoglie le espressioni di criteri allegate ai soggetti di messaggio, operazione ed endpoint, quindi utilizza le implementazioni <xref:System.ServiceModel.Description.IPolicyImportExtension> nella raccolta <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> per importare le espressioni di criteri.  
  
 La logica di importazione del criterio gestisce automaticamente i riferimenti del criterio alle espressioni di criteri nello stesso documento WSDL ed è identificata da un attributo `wsu:Id` o `xml:id`. La logica di importazione del criterio protegge le applicazioni da riferimenti del criterio circolari limitando la dimensione di un'espressione di criteri a 4096 nodi, in cui un nodo è uno degli elementi seguenti: `wsp:Policy`, `wsp:All`, `wsp:ExactlyOne`, `wsp:policyReference`.  
  
 La logica di importazione del criterio normalizza inoltre automaticamente le espressioni di criteri. Espressioni di criteri annidate e l'attributo `wsp:Optional` non sono normalizzati. Il quantità di elaborazione di normalizzazione eseguita è limitata a 4096 passaggi, in cui ogni passaggio produce un'asserzione di criteri, o un elemento figlio di un elemento `wsp:ExactlyOne`.  
  
 Il tipo <xref:System.ServiceModel.Description.WsdlImporter> tenta un massimo di 32 combinazioni di alternative di criteri allegate ai diversi soggetti di criterio WSDL. Se nessuna combinazione viene importata correttamente, viene utilizzata la prima combinazione per costruire un'associazione personalizzata parziale.  
  
## <a name="error-handling"></a>Gestione degli errori  
 Entrambi i tipi <xref:System.ServiceModel.Description.MetadataExporter> e <xref:System.ServiceModel.Description.MetadataImporter> espongono una proprietà `Errors` che può contenere una raccolta di messaggi di errore e di avviso riscontrati rispettivamente durante i processi di esportazione e di importazione, che possono essere utilizzati durante l'implementazione degli strumenti.  
  
 Il tipo <xref:System.ServiceModel.Description.WsdlImporter> di norma genera un'eccezione per un'eccezione intercettata durante il processo di importazione e aggiunge un errore corrispondente alla propria proprietà `Errors`. I metodi <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> e <xref:System.ServiceModel.Description.WsdlImporter.ImportEndpoints%2A>, tuttavia, non generano queste eccezioni, pertanto è necessario controllare la proprietà `Errors` per stabilire se si sono verificati problemi durante la chiamata di questi metodi.  
  
 Il tipo <xref:System.ServiceModel.Description.WsdlExporter> esegue il rethrow di qualsiasi eccezione intercettata durante il processo di esportazione. Queste eccezioni non vengono acquisite come errori nella proprietà `Errors`. Quando <xref:System.ServiceModel.Description.WsdlExporter> genera un'eccezione, si trova in uno stato di errore e non può essere riutilizzato. <xref:System.ServiceModel.Description.WsdlExporter> aggiunge avvisi alla sua proprietà `Errors` quando non è possibile esportare un'operazione perché utilizza azioni con caratteri jolly e quando vengono riscontrati nomi di associazioni duplicati.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Importare metadati negli endpoint di servizio](how-to-import-metadata-into-service-endpoints.md)  
 Descrive come importare i metadati scaricati in oggetti di descrizione.  
  
 [Procedura: esportare metadati dagli endpoint del servizio](how-to-export-metadata-from-service-endpoints.md)  
 Descrive come esportare oggetti di descrizione in metadati.  
  
 [ServiceDescription e riferimento a WSDL](servicedescription-and-wsdl-reference.md)  
 Descrive il mapping tra gli oggetti di descrizione e WSDL.  
  
 [Procedura: usare Svcutil.exe per esportare metadati dal codice del servizio compilato](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)  
 Descrive l'utilizzo di Svcutil.exe per esportare metadati per servizi, contratti e tipi di dati in assembly compilati:  
  
 [Informazioni di riferimento sullo schema del contratto di dati](data-contract-schema-reference.md)  
 Descrive il sottoinsieme dell'XML Schema (XSD) utilizzato da <xref:System.Runtime.Serialization.DataContractSerializer> per descrivere i tipi Common Language Runtime (CLR) per la serializzazione XML.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel.Description.WsdlExporter>  
  
 <xref:System.ServiceModel.Description.WsdlImporter>  
  
## <a name="see-also"></a>Vedere anche

- [Esportazione di metadati personalizzati per un'estensione WCF](../extending/exporting-custom-metadata-for-a-wcf-extension.md)
- [Importazione di metadati personalizzati per un'estensione WCF](../extending/importing-custom-metadata-for-a-wcf-extension.md)
