---
title: Più endpoint su un solo ListenUri
ms.date: 03/30/2017
ms.assetid: 911ffad4-4d47-4430-b7c2-79192ce6bcbd
ms.openlocfilehash: 8e26cc18ed35c446dda120c678dd7e879c756c0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183476"
---
# <a name="multiple-endpoints-at-a-single-listenuri"></a>Più endpoint su un solo ListenUri
In questo esempio viene descritto un servizio che ospita più endpoint in un solo `ListenUri`. Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Come illustrato nell'esempio [Multiple Endpoints,](../../../../docs/framework/wcf/samples/multiple-endpoints.md) un servizio può ospitare più endpoint, ognuno con indirizzi diversi ed eventualmente anche associazioni diverse. Questo esempio mostra che è possibile ospitare più endpoint sullo stesso indirizzo. Questo esempio illustra anche le differenze tra i due tipi di indirizzi che un endpoint del servizio possiede: `EndpointAddress` e `ListenUri`.  
  
 `EndpointAddress` è l'indirizzo logico del servizio. È l'indirizzo cui vengono inviati i messaggi SOAP. `ListenUri` è l'indirizzo fisico del servizio. Ha una porta e indirizza le informazioni laddove l'endpoint del servizio effettivamente è in ascolto per i messaggi sul computer corrente. Nella maggior parte dei casi, non è necessario che questi indirizzi siano differenti; quando un `ListenUri` non è specificato in modo esplicito, imposta come valore predefinito l'URI dell'`EndpointAddress` dell'endpoint. In alcuni casi, è utile per distinguerli, ad esempio durante la configurazione di un router che potrebbe accettare messaggi indirizzati a vari servizi diversi.  
  
## <a name="service"></a>Service  
 Il servizio in questo esempio ha due contratti, `ICalculator` e `IEcho`. Oltre all'endpoint `IMetadataExchange` consueto, sono tre gli endpoint dell'applicazione, come mostra il codice seguente.  
  
```xml  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.ICalculator"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:OtherEcho"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
```  
  
 Tutti e tre gli endpoint sono ospitati sullo stesso `ListenUri` e utilizzano la stessa `binding`- endpoint sullo stesso `ListenUri` devono avere la stessa associazione, perché condividono un solo stack di canali che ascolta i messaggi su quell'indirizzo fisico del computer. L' `address` di ogni endpoint è un URN; sebbene in genere gli indirizzi rappresentano posizioni fisiche, infatti l'indirizzo può essere qualsiasi tipo di URI, perché l'indirizzo viene utilizzato per far corrispondere e filtrare scopi come è dimostrato in questo esempio.  
  
 Poiché tutti e tre `ListenUri`gli endpoint condividono lo stesso , quando arriva un messaggio, Windows Communication Foundation (WCF) deve decidere a quale endpoint è destinato il messaggio. Ogni endpoint ha un filtro messaggi composto di due parti: il filtro dell'indirizzo e il filtro del contratto. Il filtro dell'indirizzo adegua `To` del messaggio SOAP all'indirizzo dell'endpoint del servizio. Ad esempio, solo i messaggi con indirizzo `To "Urn:OtherEcho"` sono candidati per il terzo endpoint di questo servizio. Il filtro del contratto associa le azioni associate alle operazioni di un particolare contratto. Ad esempio, messaggi con l'azione `IEcho`. `Echo` fa corrispondere i filtri del contratto del secondo e del terzo endpoint di questo servizio, perché entrambi quegli endpoint ospitano il contratto `IEcho`.  
  
 Così la combinazione di filtro dell'indirizzo e filtro del contratto rende possibile il routing di ogni messaggio che arriva al `ListenUri` di questo servizio all'endpoint corretto. Il terzo endpoint è differente dagli altri due perché accetta messaggi inviati a un indirizzo diverso dagli altri endpoint. I primo e secondo endpoint sono diversi uno dall'altro sulla base dei contratti (azione del messaggio in arrivo).  
  
## <a name="client"></a>Client  
 Nel momento in cui gli endpoint del server hanno due indirizzi diversi, anche gli endpoint client hanno due indirizzi. Su server e client, viene chiamato l'indirizzo logico `EndpointAddress`. Ma mentre l'indirizzo fisico è chiamato `ListenUri` nel server, sul client l'indirizzo fisico è chiamato `Via`.  
  
 Come nel server, per impostazione predefinita, questi due indirizzi sono gli stessi. Per specificare una `Via` sul client diversa dall'indirizzo dell'endpoint viene utilizzato `ClientViaBehavior`:  
  
```csharp  
Uri via = new Uri("http://localhost/ServiceModelSamples/service.svc");  
CalculatorClient calcClient = new CalculatorClient();  
calcClient.ChannelFactory.Endpoint.Behaviors.Add(  
        new ClientViaBehavior(via));  
```  
  
 Come al solito, l'indirizzo proviene dal file di configurazione client, generato da Svcutil.exe. `Via` (che corrisponde a `ListenUri` del servizio) non viene visualizzato nei metadati del servizio e così queste informazioni devono essere comunicate al client fuori banda (proprio come l'indirizzo dei metadati del servizio).  
  
 Il client in questo esempio invia messaggi a ognuno dei tre endpoint dell'applicazione del server, per dimostrare che può comunicare con (e distinguere tra) i tre endpoint, anche se tutti hanno la stessa `Via`.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Per un'esecuzione a più computer, è necessario sostituire localhost nel file Client.cs con il nome del computer del servizio.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpointsSingleUri`  
