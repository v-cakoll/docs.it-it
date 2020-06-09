---
title: Client tipizzati
ms.date: 03/30/2017
ms.assetid: 62c40e8f-e9b4-4b1a-939a-93c37393d343
ms.openlocfilehash: fe10a967a184666ad17f3ef93ecb3c4cffce46c7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591187"
---
# <a name="typed-client"></a>Client tipizzati
Nell'esempio viene illustrato come ottenere informazioni da un client tipizzato generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice. In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 La proprietà `Endpoint` del client consente l'accesso alle informazioni sull'endpoint del servizio con cui il client sta comunicando, inclusi indirizzo, informazioni sull'associazione e sul contratto. La proprietà `InnerChannel` del client è un'istanza di <xref:System.ServiceModel.IClientChannel> che consente l'accesso a informazioni sul canale sottostante, ad esempio stato e ID di sessione.  
  
```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
...  
Console.WriteLine("Client - endpoint:  " + client.Endpoint.Address);  
Console.WriteLine("Client - binding:  " + client.Endpoint.Binding.Name);  
Console.WriteLine("Client - contract: " + client.Endpoint.Contract.Name);  
  
IClientChannel channel = client.InnerChannel;  
Console.WriteLine("Client channel - state: " + channel.State);  
Console.WriteLine("Client channel - session identifier: " + channel.SessionId);  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Client - endpoint:  http://localhost/servicemodelsamples/service.svc  
Client - binding:  WSHttpBinding  
Client - contract: ICalculator  
Client channel - state: Opened  
Client channel - session identifier: urn:uuid:ae16fbc4-2964-4e87-9fb1-c5aa78fc567e  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\TypedClient`  
