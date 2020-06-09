---
title: Channel Factory
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: 2aa44c4ef274fa548d490b0d8a648457a7b1e03b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600659"
---
# <a name="channel-factory"></a>Channel Factory

In questo esempio viene illustrato in che modo un'applicazione client può creare un canale con la classe <xref:System.ServiceModel.ChannelFactory> anziché un client generato. Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

In questo esempio viene utilizzata la classe <xref:System.ServiceModel.ChannelFactory%601> per creare un canale a un endpoint del servizio. In genere, per creare un canale per un endpoint di servizio si genera un tipo di client con lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) e si crea un'istanza del tipo generato. È anche possibile creare un canale utilizzando la classe <xref:System.ServiceModel.ChannelFactory%601>, come illustrato in questo esempio. Il servizio creato dal codice di esempio seguente è identico al servizio nel [Introduzione](getting-started-sample.md).

```csharp
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
WSHttpBinding binding = new WSHttpBinding();
ChannelFactory<ICalculator> factory = new
                    ChannelFactory<ICalculator>(binding, address);
ICalculator channel = factory.CreateChannel();
```

> [!IMPORTANT]
> Se si esegue questo esempio in uno scenario a più computer, è necessario sostituire "localhost" nel codice precedente con il nome completo del computer che sta eseguendo il servizio. In questo esempio non viene utilizzata la configurazione per impostare l'indirizzo dell'endpoint, pertanto questa operazione deve essere eseguita nel codice.

Quando il canale è stato creato, le operazioni del servizio possono essere richiamate in modo analogo a un client generato.

```csharp
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = channel.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

Per chiudere il canale, è necessario prima eseguirne il cast a un'interfaccia <xref:System.ServiceModel.IClientChannel>. Ciò è necessario in quanto il canale generato viene dichiarato nell'applicazione client utilizzando l'interfaccia `ICalculator` che dispone di metodi quali `Add` e `Subtract` ma non `Close`. Il metodo `Close` ha origine sull'interfaccia <xref:System.ServiceModel.ICommunicationObject>.

```csharp
// Close the channel.
 ((IClientChannel)client).Close();
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare l'applicazione client.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md). Si noti che in questo esempio non viene abilitata la pubblicazione di metadati. Per rigenerare il tipo client, è necessario innanzitutto abilitare la pubblicazione dei metadati per questo esempio.

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

### <a name="to-run-the-sample-cross-machine"></a>Per eseguire l'esempio su più computer

1. Sostituire "localhost" nel codice seguente con il nome completo del computer che sta eseguendo il servizio.

    ```csharp
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
    ```

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`
