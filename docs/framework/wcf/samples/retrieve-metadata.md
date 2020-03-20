---
title: Recupero di metadati
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 9b1adf4ed2a09625ca19016f531936002fff757d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183385"
---
# <a name="retrieve-metadata"></a>Recupero di metadati
Questo esempio dimostra come implementare un client che recupera dinamicamente metadati da un servizio per scegliere un endpoint con il quale comunicare. Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md). Il servizio è stato modificato per esporre due endpoint, `basicHttpBinding` ovvero un endpoint all'indirizzo di base tramite l'associazione, e un endpoint sicuro in corrispondenza del valore di indirizzo di*base,* ovvero l'associazione. `wsHttpBinding` Anziché configurare il client con gli indirizzi e le associazioni dell'endpoint, il client recupera dinamicamente i metadati per il servizio usando la classe <xref:System.ServiceModel.Description.MetadataExchangeClient> e quindi importa i metadati come un <xref:System.ServiceModel.Description.ServiceEndpointCollection> usando la classe <xref:System.ServiceModel.Description.WsdlImporter>.  
  
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
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione della soluzione in C, C, o Visual Basic .NET, seguire le istruzioni riportate in [Compilazione degli esempi](../../../../docs/framework/wcf/samples/building-the-samples.md)di Windows Communication Foundation .  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
