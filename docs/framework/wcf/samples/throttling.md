---
title: Limitazione
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, throttling sample
- Throttling Sample [Windows Communication Foundation]
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
ms.openlocfilehash: d41270d63d188443207c78a3c55b469e2bd7b482
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006289"
---
# <a name="throttling"></a><span data-ttu-id="a8b47-102">Limitazione</span><span class="sxs-lookup"><span data-stu-id="a8b47-102">Throttling</span></span>
<span data-ttu-id="a8b47-103">Nell'esempio della limitazione viene illustrato l'utilizzo dei controlli di limitazione.</span><span class="sxs-lookup"><span data-stu-id="a8b47-103">The Throttling sample demonstrates the use of throttling controls.</span></span> <span data-ttu-id="a8b47-104">I controlli di limitazione pongono dei limiti sul numero di chiamate, istanze o sessioni simultanee per impedire l'uso eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="a8b47-104">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span> <span data-ttu-id="a8b47-105">Il comportamento della limitazione viene specificato nelle impostazioni del file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="a8b47-105">Throttling behavior is specified in service configuration file settings.</span></span> <span data-ttu-id="a8b47-106">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="a8b47-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="a8b47-107">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a8b47-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8b47-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a8b47-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a8b47-109">File di configurazione del servizio specifica i controlli di limitazione delle richieste in un [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b47-109">The service configuration file specifies throttling controls in a [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="a8b47-110">In base alla configurazione, il servizio limita il numero massimo di chiamate simultanee a 2 e il numero massimo di istanze simultanee a 10.</span><span class="sxs-lookup"><span data-stu-id="a8b47-110">As configured, the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span>  
  
 <span data-ttu-id="a8b47-111">Per illustrare la limitazione si definisce un periodo di inattività sui metodi del servizio come segue:</span><span class="sxs-lookup"><span data-stu-id="a8b47-111">In order to demonstrate throttling we define a sleep time on the service methods as follows:</span></span>  
  
```csharp
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
```  
  
 <span data-ttu-id="a8b47-112">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="a8b47-112">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a8b47-113">I metodi Add e Subtract vengono eseguiti contemporaneamente, così come i metodi Multiply e Divide, a dimostrazione che non possono essere eseguiti più di 2 metodi contemporaneamente e, quindi, illustrando la limitazione.</span><span class="sxs-lookup"><span data-stu-id="a8b47-113">The Add and Subtract methods are executed concurrently and the Multiply and Divide methods are executed concurrently proving that not more than 2 methods can be executed concurrently thus demonstrating throttling.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a8b47-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a8b47-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a8b47-115">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8b47-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a8b47-116">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8b47-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a8b47-117">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8b47-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8b47-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a8b47-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a8b47-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a8b47-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a8b47-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a8b47-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a8b47-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b47-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
