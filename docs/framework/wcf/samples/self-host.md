---
title: Servizio indipendente
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: f5c46bc486e03cf86ada3a565a3c282cd81db286
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599945"
---
# <a name="self-host"></a><span data-ttu-id="ac118-102">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="ac118-102">Self-Host</span></span>
<span data-ttu-id="ac118-103">In questo esempio viene illustrato come implementare un servizio indipendente in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="ac118-103">This sample demonstrates how to implement a self-hosted service in a console application.</span></span> <span data-ttu-id="ac118-104">Questo esempio è basato sul [Introduzione](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ac118-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="ac118-105">Il file di configurazione del servizio è stato rinominato da Web.config a App.config ed è stato modificato per configurare un indirizzo di base utilizzato dall'host.</span><span class="sxs-lookup"><span data-stu-id="ac118-105">The service configuration file has been renamed from Web.config to App.config and modified to configure a base address, which the host uses.</span></span> <span data-ttu-id="ac118-106">Il codice sorgente del servizio è stato modificato per implementare una funzione `Main` statica che crea e apre un host del servizio che fornisce l'indirizzo di base configurato.</span><span class="sxs-lookup"><span data-stu-id="ac118-106">The service source code has been modified to implement a static `Main` function that creates and opens a service host that provides the configured base address.</span></span> <span data-ttu-id="ac118-107">L'implementazione del servizio è stata modificata per scrivere l'output nella console per ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="ac118-107">The service implementation has been modified to write output to the console for each operation.</span></span> <span data-ttu-id="ac118-108">Il client non è stato modificato, a parte la configurazione dell'indirizzo dell'endpoint corretto del servizio.</span><span class="sxs-lookup"><span data-stu-id="ac118-108">The client has been unmodified, except for configuring the correct endpoint address of the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac118-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ac118-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac118-110">Nell'esempio viene implementata una funzione main statica per creare una classe <xref:System.ServiceModel.ServiceHost> per il tipo `CalculatorService` specificato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ac118-110">The sample implements a static main function to create a <xref:System.ServiceModel.ServiceHost> for the given `CalculatorService` type, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="ac118-111">Quando un servizio viene ospitato in IIS (Internet Information Services) o WAS (Windows Process Activation Service), l'indirizzo di base del servizio viene fornito dall'ambiente host.</span><span class="sxs-lookup"><span data-stu-id="ac118-111">When a service is hosted in Internet Information Services (IIS) or Windows Process Activation Service (WAS), the base address of the service is provided by the hosting environment.</span></span> <span data-ttu-id="ac118-112">Nel caso di un servizio indipendente, è necessario specificare manualmente l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="ac118-112">In the self-hosted case, you must specify the base address yourself.</span></span> <span data-ttu-id="ac118-113">Questa operazione viene eseguita utilizzando l' `add` elemento, figlio di [\<baseAddresses>](../../configure-apps/file-schema/wcf/baseaddresses.md) , figlio di [\<host>](../../configure-apps/file-schema/wcf/host.md) , figlio di, [\<service>](../../configure-apps/file-schema/wcf/service.md) come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac118-113">This is done using the `add` element, child of [\<baseAddresses>](../../configure-apps/file-schema/wcf/baseaddresses.md), child of [\<host>](../../configure-apps/file-schema/wcf/host.md), child of [\<service>](../../configure-apps/file-schema/wcf/service.md) as demonstrated in the following sample configuration.</span></span>  
  
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
  
 <span data-ttu-id="ac118-114">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="ac118-114">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="ac118-115">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="ac118-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac118-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ac118-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ac118-117">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac118-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ac118-118">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac118-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ac118-119">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac118-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ac118-120">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ac118-120">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac118-121">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ac118-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ac118-122">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="ac118-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac118-123">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ac118-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a><span data-ttu-id="ac118-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac118-124">See also</span></span>

- <span data-ttu-id="ac118-125">[Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ac118-125">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
