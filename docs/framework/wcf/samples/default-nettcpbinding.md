---
title: Associazione NetTcpBinding predefinita
ms.date: 03/30/2017
helpviewer_keywords:
- Net profile TCP
ms.assetid: e8475fe6-0ecd-407a-8e7e-45860561bb74
ms.openlocfilehash: 6a546a982b7c000e7fb5304daf7eac95d6da7e92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768969"
---
# <a name="default-nettcpbinding"></a><span data-ttu-id="7e687-102">Associazione NetTcpBinding predefinita</span><span class="sxs-lookup"><span data-stu-id="7e687-102">Default NetTcpBinding</span></span>
<span data-ttu-id="7e687-103">Questo esempio dimostra l'uso dell'associazione <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="7e687-103">This sample demonstrates the use of the <xref:System.ServiceModel.NetTcpBinding> binding.</span></span> <span data-ttu-id="7e687-104">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="7e687-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="7e687-105">In questo esempio, il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="7e687-105">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="7e687-106">Sia il client che il servizio sono applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="7e687-106">Both the client and service are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e687-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7e687-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7e687-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7e687-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7e687-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7e687-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7e687-110">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="7e687-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e687-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7e687-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\Default`  
  
 <span data-ttu-id="7e687-112">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="7e687-112">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="7e687-113">Il tipo di associazione è specificato nella `binding` attributo del [ \<endpoint >](../../configure-apps/file-schema/wcf/endpoint-element.md) come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="7e687-113">The binding type is specified in the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="7e687-114">Nell'esempio precedente è stato illustrato come configurare un endpoint per l'uso dell'associazione `netTcpBinding` con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="7e687-114">The previous sample shows how to configure an endpoint to use the `netTcpBinding` binding with the default settings.</span></span> <span data-ttu-id="7e687-115">Se si desidera configurare l'associazione `netTcpBinding` e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="7e687-115">If you want to configure the `netTcpBinding` binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="7e687-116">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7e687-116">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="7e687-117">Nell'esempio seguente la configurazione di associazione viene denominata `Binding1` e viene definita come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e687-117">In this sample, the binding configuration is named `Binding1` and is defined as shown in the following sample configuration.</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    ...  
    <endpoint address=""  
              binding="netTcpBinding"  
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
  
<bindings>  
  <netTcpBinding>  
    <binding name="Binding1"   
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"   
             receiveTimeout="00:10:00"   
             sendTimeout="00:01:00"  
             transactionFlow="false"   
             transferMode="Buffered"   
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"   
             listenBacklog="10"  
             maxBufferPoolSize="524288"   
             maxBufferSize="65536"   
             maxConnections="10"  
             maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32"   
                    maxStringContentLength="8192"   
                    maxArrayLength="16384"  
                    maxBytesPerRead="4096"   
                    maxNameTableCharCount="16384" />  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="7e687-118">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="7e687-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7e687-119">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="7e687-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press ENTER to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7e687-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="7e687-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7e687-121">Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="7e687-121">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="7e687-122">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e687-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="7e687-123">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e687-123">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="7e687-124">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e687-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e687-125">Poiché il server è indipendente, è necessario specificare un'identità nel file App.config del client per eseguire l'esempio in una configurazione tra più computer.</span><span class="sxs-lookup"><span data-stu-id="7e687-125">Because the server is self-hosted, you must specify an identity in the client's App.config file to run the sample in a cross-machine configuration.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name=""  
          address="net.tcp://servername:9000/servicemodelsamples/service"   
          binding="netTcpBinding"   
          contract="Microsoft.ServiceModel.Samples.ICalculator">  
            <identity>  
              <userPrincipalName value = "user_name@service_domain"/>  
            </identity>  
      </endpoint>  
    </client>  
    ```  
