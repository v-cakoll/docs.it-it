---
title: Configurazione semplificata per servizi WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: d303d298ca45504968b4b37bd2835381b7e2eee5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094904"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="1a894-102">Configurazione semplificata per servizi WCF</span><span class="sxs-lookup"><span data-stu-id="1a894-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="1a894-103">In questo esempio viene illustrato come implementare e configurare un servizio e un client tipici utilizzando Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1a894-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1a894-104">Questo esempio è la base per tutti gli altri esempi di tecnologia di base.</span><span class="sxs-lookup"><span data-stu-id="1a894-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="1a894-105">Questo servizio, che espone un endpoint per la comunicazione con il servizio, usa la configurazione semplificata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1a894-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="1a894-106">Prima del .NET Framework 4, l'endpoint viene in genere definito in un file di configurazione (Web. config), come illustrato nell'esempio di codice di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="1a894-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
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
  
 <span data-ttu-id="1a894-107">In .NET Framework 4, l'elemento `<service>` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1a894-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="1a894-108">Quando un servizio non definisce alcun endpoint, al servizio viene aggiunto un endpoint per ogni indirizzo di base e contratto implementato.</span><span class="sxs-lookup"><span data-stu-id="1a894-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="1a894-109">L'indirizzo di base viene aggiunto al nome del contratto per determinare l'endpoint e l'associazione è determinata dallo schema dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1a894-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="1a894-110">Nell'esempio di codice seguente viene illustrato un file di configurazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="1a894-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="1a894-111">Come configurato, è possibile accedere al servizio `http://localhost/servicemodelsamples/service.svc` da un client nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="1a894-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="1a894-112">Affinché i client presenti nei computer remoti accedano al servizio, è necessario specificare un nome di dominio completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="1a894-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="1a894-113">Per impostazione predefinita, il servizio non espone metadati.</span><span class="sxs-lookup"><span data-stu-id="1a894-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="1a894-114">In quanto tale, il servizio attiva il comportamento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1a894-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
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
  
### <a name="to-use-this-sample"></a><span data-ttu-id="1a894-115">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="1a894-115">To use this sample</span></span>  
  
1. <span data-ttu-id="1a894-116">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1a894-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1a894-117">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1a894-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1a894-118">Eseguire l'esempio attenendosi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a894-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="1a894-119">Fare clic con il pulsante destro del mouse sul progetto di **servizio** e selezionare **Imposta come progetto di avvio**, quindi premere **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="1a894-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="1a894-120">Attendere l'output della console che conferma che il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1a894-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="1a894-121">Fare clic con il pulsante destro del mouse sul progetto **client** e selezionare **Imposta come progetto di avvio**, quindi premere **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="1a894-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a894-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1a894-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1a894-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1a894-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="1a894-124">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1a894-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1a894-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1a894-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="1a894-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a894-126">See also</span></span>

- <span data-ttu-id="1a894-127">[Esempi di gestione di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1a894-127">[AppFabric Management Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="1a894-128">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="1a894-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
