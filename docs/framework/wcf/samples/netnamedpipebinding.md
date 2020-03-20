---
title: NetNamedPipeBinding
ms.date: 03/30/2017
helpviewer_keywords:
- Net Profile Named Pipe
ms.assetid: e78e845f-c325-46e2-927d-81616f97f7d5
ms.openlocfilehash: da54a835fd32efe4f53a80701465d2d7d8adba7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183474"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="bda33-102">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="bda33-102">NetNamedPipeBinding</span></span>
<span data-ttu-id="bda33-103">In questo esempio viene descritta l'associazione `netNamedPipeBinding`, che fornisce la comunicazione tra i processi sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="bda33-103">This sample demonstrates the `netNamedPipeBinding` binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="bda33-104">Le named pipe non funzionano tra computer.</span><span class="sxs-lookup"><span data-stu-id="bda33-104">Named pipes do not work across machines.</span></span> <span data-ttu-id="bda33-105">Questo esempio è basato sul servizio di calcolatrice [Introduzione.This sample](../../../../docs/framework/wcf/samples/getting-started-sample.md) is based on The Getting Started calculator service.</span><span class="sxs-lookup"><span data-stu-id="bda33-105">This sample is based on The [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) calculator service.</span></span>  
  
 <span data-ttu-id="bda33-106">In questo esempio, il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="bda33-106">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="bda33-107">Sia il client che il servizio sono applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="bda33-107">Both the client and the service are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bda33-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bda33-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="bda33-109">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="bda33-109">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="bda33-110">Il tipo di associazione viene specificato nell'attributo `binding` dell'endpoint [ \<>](../../configure-apps/file-schema/wcf/endpoint-element.md) o [ \<dell'endpoint> dell'elemento \<>client,](../../configure-apps/file-schema/wcf/endpoint-of-client.md) come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bda33-110">The binding type is specified in the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) or [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element, as shown in the following sample configuration:</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="bda33-111">Nell'esempio precedente è stato illustrato come configurare un endpoint per l'uso dell'associazione `netNamedPipeBinding` con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="bda33-111">The previous sample shows how to configure an endpoint to use the `netNamedPipeBinding` binding with the default settings.</span></span> <span data-ttu-id="bda33-112">Se si desidera configurare l'associazione `netNamedPipeBinding` e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="bda33-112">If you want to configure the `netNamedPipeBinding` binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="bda33-113">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="bda33-113">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          bindingConfiguration="Binding1"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="bda33-114">In questo esempio, la configurazione di associazione si chiama `Binding1` ed è dotata della seguente descrizione:</span><span class="sxs-lookup"><span data-stu-id="bda33-114">In this sample, the binding configuration is named `Binding1` and has the following definition:</span></span>  
  
```xml  
<bindings>  
  <!--   
        Following is the expanded configuration section for a NetNamedPipeBinding.  
        Each property is configured with the default value.  
     -->  
  <netNamedPipeBinding>  
    <binding name="Binding1"
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"  
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"
             maxBufferPoolSize="524288"  
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">  
      <security mode="Transport">  
        <transport protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netNamedPipeBinding>  
</bindings>  
```  
  
 <span data-ttu-id="bda33-115">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="bda33-115">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="bda33-116">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="bda33-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bda33-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="bda33-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bda33-118">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bda33-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bda33-119">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bda33-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bda33-120">Per eseguire l'esempio in una configurazione con un singolo computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bda33-120">To run the sample in a single machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bda33-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bda33-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bda33-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bda33-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bda33-123">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bda33-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bda33-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bda33-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\NamedPipe`  
