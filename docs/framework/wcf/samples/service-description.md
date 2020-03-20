---
title: Descrizione del servizio
ms.date: 03/30/2017
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
ms.openlocfilehash: d77797ed2871f2211ff142e2f45c160a92632138
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144086"
---
# <a name="service-description"></a>Descrizione del servizio
L'esempio Descrizione del servizio illustra come un servizio può recuperare le informazioni di descrizione del servizio nella fase di esecuzione. L'esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), con un'operazione di servizio aggiuntiva definita per restituire informazioni descrittive sul servizio. Le informazioni restituite elencano indirizzi di base e gli endpoint del servizio. Il servizio fornisce queste informazioni utilizzando le classi <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> e <xref:System.ServiceModel.Description.ServiceDescription>.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio utilizza una versione modificata del contratto della calcolatrice chiamata `IServiceDescriptionCalculator`. Il contratto definisce un'operazione del servizio aggiuntiva denominata `GetServiceDescriptionInfo` che restituisce una stringa su più righe al client che descrive l'indirizzo o gli indirizzi di base e l'endpoint o gli endpoint del servizio.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 Il codice di implementazione per `GetServiceDescriptionInfo` utilizza la classe<xref:System.ServiceModel.Description.ServiceDescription> per elencare gli endpoint del servizio. Poiché gli endpoint del servizio possono avere indirizzi relativi, elenca per primi gli indirizzi di base del servizio. Per ottenere tutte di queste informazioni il codice recupera il contesto dell'operazione utilizzando <xref:System.ServiceModel.OperationContext.Current%2A>. La classe <xref:System.ServiceModel.ServiceHost> e l'oggetto <xref:System.ServiceModel.Description.ServiceDescription> sono recuperati dal contesto dell'operazione. Per elencare gli endpoint di base del servizio il codice scorre la raccolta <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> dell'host del servizio. Per elencare gli endpoint del servizio il codice scorre la raccolta degli endpoint della descrizione del servizio.  
  
```csharp
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 Quando si esegue l'esempio, le operazioni della calcolatrice, e in seguito le informazioni del servizio, vengono restituite dall'operazione `GetServiceDescriptionInfo`. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
