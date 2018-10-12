---
title: Client e servizio Intranet non protetti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
author: BrucePerlerMS
ms.openlocfilehash: e09f7c8483e1a3ca330bbee995c2d59f9005f207
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122754"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="93319-102">Client e servizio Intranet non protetti</span><span class="sxs-lookup"><span data-stu-id="93319-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="93319-103">La figura seguente illustra un semplice servizio Windows Communication Foundation (WCF) sviluppato per fornire informazioni su una rete privata protetta a un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="93319-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="93319-104">Sicurezza non è necessaria perché i dati sono di importanza bassa, la rete è considerata naturalmente protetta o sicurezza viene fornita tramite un livello sottostante l'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="93319-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 <span data-ttu-id="93319-105">![Uno scenario di servizio e client non sicuri Intranet](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="93319-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="93319-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="93319-106">Characteristic</span></span>|<span data-ttu-id="93319-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93319-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="93319-108">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="93319-108">Security Mode</span></span>|<span data-ttu-id="93319-109">None</span><span class="sxs-lookup"><span data-stu-id="93319-109">None</span></span>|  
|<span data-ttu-id="93319-110">Trasporto</span><span class="sxs-lookup"><span data-stu-id="93319-110">Transport</span></span>|<span data-ttu-id="93319-111">TCP</span><span class="sxs-lookup"><span data-stu-id="93319-111">TCP</span></span>|  
|<span data-ttu-id="93319-112">Binding</span><span class="sxs-lookup"><span data-stu-id="93319-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="93319-113">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="93319-113">Interoperability</span></span>|<span data-ttu-id="93319-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="93319-114">WCF only</span></span>|  
|<span data-ttu-id="93319-115">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="93319-115">Authentication</span></span>|<span data-ttu-id="93319-116">None</span><span class="sxs-lookup"><span data-stu-id="93319-116">None</span></span>|  
|<span data-ttu-id="93319-117">Integrità</span><span class="sxs-lookup"><span data-stu-id="93319-117">Integrity</span></span>|<span data-ttu-id="93319-118">None</span><span class="sxs-lookup"><span data-stu-id="93319-118">None</span></span>|  
|<span data-ttu-id="93319-119">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="93319-119">Confidentiality</span></span>|<span data-ttu-id="93319-120">None</span><span class="sxs-lookup"><span data-stu-id="93319-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="93319-121">Servizio</span><span class="sxs-lookup"><span data-stu-id="93319-121">Service</span></span>  
 <span data-ttu-id="93319-122">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="93319-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="93319-123">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93319-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="93319-124">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="93319-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="93319-125">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="93319-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="93319-126">Codice</span><span class="sxs-lookup"><span data-stu-id="93319-126">Code</span></span>  
 <span data-ttu-id="93319-127">Il codice seguente illustra come creare un endpoint senza protezione.</span><span class="sxs-lookup"><span data-stu-id="93319-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="93319-128">Configurazione</span><span class="sxs-lookup"><span data-stu-id="93319-128">Configuration</span></span>  
 <span data-ttu-id="93319-129">Il codice seguente imposta lo stesso endpoint usando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="93319-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="93319-130">Client</span><span class="sxs-lookup"><span data-stu-id="93319-130">Client</span></span>  
 <span data-ttu-id="93319-131">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="93319-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="93319-132">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93319-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="93319-133">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="93319-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="93319-134">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="93319-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="93319-135">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="93319-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="93319-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93319-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="93319-137">Codice</span><span class="sxs-lookup"><span data-stu-id="93319-137">Code</span></span>  
 <span data-ttu-id="93319-138">Il codice seguente viene illustrato un client WCF di base che accede a un endpoint non protetto usando il protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="93319-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="93319-139">Configurazione</span><span class="sxs-lookup"><span data-stu-id="93319-139">Configuration</span></span>  
 <span data-ttu-id="93319-140">Il codice di configurazione seguente è relativo al client:</span><span class="sxs-lookup"><span data-stu-id="93319-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93319-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93319-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="93319-142">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="93319-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="93319-143">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="93319-143">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
