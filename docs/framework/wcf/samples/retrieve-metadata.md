---
title: Recupero di metadati
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 4763686485dfe97844fad78cf0bb279113c0ce08
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594608"
---
# <a name="retrieve-metadata"></a>Recupero di metadati
Questo esempio dimostra come implementare un client che recupera dinamicamente metadati da un servizio per scegliere un endpoint con il quale comunicare. Questo esempio è basato sul [Introduzione](getting-started-sample.md). Il servizio è stato modificato per esporre due endpoint, un endpoint all'indirizzo di base usando l' `basicHttpBinding` associazione e un endpoint sicuro in {*BaseAddress*}/Secure usando l' `wsHttpBinding` associazione. Anziché configurare il client con gli indirizzi e le associazioni dell'endpoint, il client recupera dinamicamente i metadati per il servizio usando la classe <xref:System.ServiceModel.Description.MetadataExchangeClient> e quindi importa i metadati come un <xref:System.ServiceModel.Description.ServiceEndpointCollection> usando la classe <xref:System.ServiceModel.Description.WsdlImporter>.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 L'applicazione client usa l'elemento <xref:System.ServiceModel.Description.ServiceEndpointCollection> importato per creare i client che devono comunicare con il servizio. L'applicazione client scorre ciascun endpoint recuperato e comunica con ogni endpoint che implementa il contratto `ICalculator`. L'indirizzo e l'associazione appropriati vengono forniti con l'endpoint recuperato in modo che il client venga configurato per comunicare con ciascun endpoint, come illustrato nel codice di esempio seguente.  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 La finestra della console client visualizza le operazioni inviate a ciascuno degli endpoint indicando il percorso dell'indirizzo e nome di associazione.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
