---
title: Servizio indipendente
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: a38738c369db3d3f8242bd71ee04a19a669b2cf4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144149"
---
# <a name="self-host"></a>Servizio indipendente
In questo esempio viene illustrato come implementare un servizio indipendente in un'applicazione console. Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md). Il file di configurazione del servizio è stato rinominato da Web.config a App.config ed è stato modificato per configurare un indirizzo di base utilizzato dall'host. Il codice sorgente del servizio è stato modificato per implementare una funzione `Main` statica che crea e apre un host del servizio che fornisce l'indirizzo di base configurato. L'implementazione del servizio è stata modificata per scrivere l'output nella console per ogni operazione. Il client non è stato modificato, a parte la configurazione dell'indirizzo dell'endpoint corretto del servizio.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene implementata una funzione main statica per creare una classe <xref:System.ServiceModel.ServiceHost> per il tipo `CalculatorService` specificato, come illustrato nel codice seguente.  
  
```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 Quando un servizio viene ospitato in IIS (Internet Information Services) o WAS (Windows Process Activation Service), l'indirizzo di base del servizio viene fornito dall'ambiente host. Nel caso di un servizio indipendente, è necessario specificare manualmente l'indirizzo di base. Questa operazione viene `add` eseguita utilizzando l'elemento child di [ \<baseAddresses>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), figlio dell'host [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), [ \<l'elemento](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) figlio del servizio>come illustrato nella configurazione di esempio seguente.  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
