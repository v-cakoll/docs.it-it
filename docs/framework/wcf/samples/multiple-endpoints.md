---
title: "Più endpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Multiple EndPoints
ms.assetid: 8f0c2e1f-9aee-41c2-8301-c72b7f664412
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 87846ca624b557f39bcb61d467a270779f399f6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="multiple-endpoints"></a><span data-ttu-id="6b8b6-102">Più endpoint</span><span class="sxs-lookup"><span data-stu-id="6b8b6-102">Multiple Endpoints</span></span>
<span data-ttu-id="6b8b6-103">L'esempio Più endpoint mostra come configurare più endpoint in un servizio e come comunicare con ogni endpoint a partire da un client.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-103">The Multiple Endpoints sample demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span> <span data-ttu-id="6b8b6-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6b8b6-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="6b8b6-105">La configurazione del servizio è stata modificata per definire due endpoint che supportano il contratto `ICalculator`, ma ognuno con un indirizzo diverso e una diversa associazione.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-105">The service configuration has been modified to define two endpoints that support the `ICalculator` contract, but each at a different address using a different binding.</span></span> <span data-ttu-id="6b8b6-106">La configurazione client e il codice sono stati modificati per comunicare con entrambi gli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-106">The client configuration and code have been modified to communicate with both of the service endpoints.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b8b6-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6b8b6-108">Il file Web.config del servizio è stato modificato per definire due endpoint che supportano entrambi il contratto `ICalculator`, ma ognuno con un indirizzo diverso e una diversa associazione.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-108">The service Web.config file has been modified to define two endpoints, each supporting the same `ICalculator` contract, but at different addresses using different bindings.</span></span> <span data-ttu-id="6b8b6-109">Il primo endpoint viene definito all'indirizzo di base utilizzando un'associazione `basicHttpBinding` che non ha sicurezza attivata.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-109">The first endpoint is defined at the base address using a `basicHttpBinding` binding, which does not have security enabled.</span></span> <span data-ttu-id="6b8b6-110">Il secondo endpoint viene definito in {baseaddress}/secure utilizzando un'associazione `wsHttpBinding`, protetta per impostazione predefinita, utilizzando WS-Security con autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-110">The second endpoint is defined at {baseaddress}/secure using a `wsHttpBinding` binding, which is secure by default, using WS-Security with Windows authentication.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- This endpoint is exposed at the base address provided by host:  
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- secure endpoint exposed at {base address}/secure:  
       http://localhost/servicemodelsamples/service.svc/secure -->  
  <endpoint address="secure"  
            binding="wsHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="6b8b6-111">Entrambi gli endpoint vengono configurati sul client.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-111">Both endpoints are also configured on the client.</span></span> <span data-ttu-id="6b8b6-112">A questi endpoint vengono assegnati dei nomi così che il chiamante può passare il nome dell'endpoint desiderato nel costruttore del client.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-112">These endpoints are given names so that the caller can pass the desired endpoint name into the constructor of the client.</span></span>  
  
```xml  
<client>  
  <!-- Passing "basic" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="basic"  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="basicHttpBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- Passing "secure" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="secure"  
address="http://localhost/servicemodelsamples/service.svc/secure"   
            binding="wsHttpBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
```  
  
 <span data-ttu-id="6b8b6-113">Il client utilizza entrambi gli endpoint come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-113">The client uses both endpoints as shown in the following code.</span></span>  
  
```  
static void Main()  
{  
    // Create a client to the basic endpoint configuration.  
    CalculatorClient client = new CalculatorClient("basic");  
    Console.WriteLine("Communicate with basic endpoint.");  
    // call operations  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    // Create a client to the secure endpoint configuration.  
    client = new CalculatorClient("secure");  
    Console.WriteLine("Communicate with secure endpoint.");  
    // Call operations.  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="6b8b6-114">Quando si esegue il client, vengono visualizzate interazioni con entrambi gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-114">When you run the client, interactions with both endpoints are displayed.</span></span>  
  
```  
Communicate with basic endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Communicate with secure endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6b8b6-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6b8b6-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6b8b6-116">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b8b6-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6b8b6-117">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b8b6-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6b8b6-118">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b8b6-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b8b6-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6b8b6-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6b8b6-121">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b8b6-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b8b6-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6b8b6-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpoints`  
  
## <a name="see-also"></a><span data-ttu-id="6b8b6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b8b6-123">See Also</span></span>
