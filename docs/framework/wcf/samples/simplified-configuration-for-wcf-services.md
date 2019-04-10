---
title: Configurazione semplificata per servizi WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 47af8dcba35ba31f25597c946596b0cbcac93b4d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304259"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="bbfbe-102">Configurazione semplificata per servizi WCF</span><span class="sxs-lookup"><span data-stu-id="bbfbe-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="bbfbe-103">In questo esempio viene illustrato come implementare e configurare un servizio tipico e un client tramite Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bbfbe-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="bbfbe-104">Questo esempio è la base per tutti gli altri esempi di tecnologia di base.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="bbfbe-105">Questo servizio, che espone un endpoint per comunicare con il servizio, utilizza la configurazione semplificata in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbfbe-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="bbfbe-106">Prima di [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], l'endpoint viene in genere definito in un file di configurazione (Web.config), come mostrato nel codice di configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="bbfbe-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], l'elemento `<service>` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="bbfbe-108">Quando un servizio non definisce alcun endpoint, al servizio viene aggiunto un endpoint per ogni indirizzo di base e contratto implementato.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="bbfbe-109">L'indirizzo di base viene aggiunto al nome del contratto per determinare l'endpoint e l'associazione è determinata dallo schema dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="bbfbe-110">Nell'esempio di codice seguente viene illustrato un file di configurazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="bbfbe-111">In base alla configurazione, è possibile accedere al servizio `http://localhost/servicemodelsamples/service.svc` da un client sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="bbfbe-112">Affinché i client presenti nei computer remoti accedano al servizio, è necessario specificare un nome di dominio completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="bbfbe-113">Per impostazione predefinita, il servizio non espone metadati.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="bbfbe-114">In quanto tale, il servizio attiva il comportamento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="bbfbe-115">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="bbfbe-115">To use this sample</span></span>  
  
1. <span data-ttu-id="bbfbe-116">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bbfbe-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bbfbe-117">Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bbfbe-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bbfbe-118">Eseguire l'esempio attenendosi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbfbe-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="bbfbe-119">Fare clic il **Service** del progetto e selezionare **imposta come progetto di avvio**, quindi premere **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="bbfbe-120">Attendere l'output della console che conferma che il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="bbfbe-121">Fare clic il **Client** del progetto e selezionare **imposta come progetto di avvio**, quindi premere **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bbfbe-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bbfbe-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bbfbe-124">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bbfbe-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bbfbe-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="bbfbe-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfbe-126">See also</span></span>

- [<span data-ttu-id="bbfbe-127">Gestione</span><span class="sxs-lookup"><span data-stu-id="bbfbe-127">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)
- [<span data-ttu-id="bbfbe-128">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="bbfbe-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
