---
title: Client e servizio non protetti in Internet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cd7cc9da457424dede6f62ecefca8cee0d94fb88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="90874-102">Client e servizio non protetti in Internet</span><span class="sxs-lookup"><span data-stu-id="90874-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="90874-103">Nell'illustrazione seguente è mostrato un esempio di un client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] pubblico non protetto e di un servizio.</span><span class="sxs-lookup"><span data-stu-id="90874-103">The following illustration shows an example of a public, unsecured [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span>  
  
 <span data-ttu-id="90874-104">![Scenario di sicuri e il servizio Internet non protetto](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span><span class="sxs-lookup"><span data-stu-id="90874-104">![Unsecured Internet cleint and service scenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span></span>  
  
|<span data-ttu-id="90874-105">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="90874-105">Characteristic</span></span>|<span data-ttu-id="90874-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90874-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="90874-107">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="90874-107">Security Mode</span></span>|<span data-ttu-id="90874-108">None</span><span class="sxs-lookup"><span data-stu-id="90874-108">None</span></span>|  
|<span data-ttu-id="90874-109">Trasporto</span><span class="sxs-lookup"><span data-stu-id="90874-109">Transport</span></span>|<span data-ttu-id="90874-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="90874-110">HTTP</span></span>|  
|<span data-ttu-id="90874-111">Binding</span><span class="sxs-lookup"><span data-stu-id="90874-111">Binding</span></span>|<span data-ttu-id="90874-112"><xref:System.ServiceModel.BasicHttpBinding>nel codice, o [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="90874-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="90874-113">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="90874-113">Interoperability</span></span>|<span data-ttu-id="90874-114">Con servizi e client di servizi Web esistenti</span><span class="sxs-lookup"><span data-stu-id="90874-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="90874-115">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="90874-115">Authentication</span></span>|<span data-ttu-id="90874-116">None</span><span class="sxs-lookup"><span data-stu-id="90874-116">None</span></span>|  
|<span data-ttu-id="90874-117">Integrità</span><span class="sxs-lookup"><span data-stu-id="90874-117">Integrity</span></span>|<span data-ttu-id="90874-118">None</span><span class="sxs-lookup"><span data-stu-id="90874-118">None</span></span>|  
|<span data-ttu-id="90874-119">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="90874-119">Confidentiality</span></span>|<span data-ttu-id="90874-120">None</span><span class="sxs-lookup"><span data-stu-id="90874-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="90874-121">Servizio</span><span class="sxs-lookup"><span data-stu-id="90874-121">Service</span></span>  
 <span data-ttu-id="90874-122">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="90874-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="90874-123">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90874-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="90874-124">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="90874-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="90874-125">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="90874-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="90874-126">Codice</span><span class="sxs-lookup"><span data-stu-id="90874-126">Code</span></span>  
 <span data-ttu-id="90874-127">Nel codice seguente viene illustrato come creare un endpoint senza protezione.</span><span class="sxs-lookup"><span data-stu-id="90874-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="90874-128">Per impostazione predefinita, nell'elemento <xref:System.ServiceModel.BasicHttpBinding> la modalità di sicurezza è impostata su <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="90874-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="90874-129">Configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="90874-129">Service Configuration</span></span>  
 <span data-ttu-id="90874-130">Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="90874-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="90874-131">Client</span><span class="sxs-lookup"><span data-stu-id="90874-131">Client</span></span>  
 <span data-ttu-id="90874-132">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="90874-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="90874-133">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90874-133">Do one of the following:</span></span>  
  
-   <span data-ttu-id="90874-134">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="90874-134">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="90874-135">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="90874-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="90874-136">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="90874-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="90874-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90874-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="90874-138">Codice</span><span class="sxs-lookup"><span data-stu-id="90874-138">Code</span></span>  
 <span data-ttu-id="90874-139">Nel codice seguente è mostrato un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di base che accede a un endpoint non protetto.</span><span class="sxs-lookup"><span data-stu-id="90874-139">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="90874-140">Configurazione del client</span><span class="sxs-lookup"><span data-stu-id="90874-140">Client Configuration</span></span>  
 <span data-ttu-id="90874-141">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="90874-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90874-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90874-142">See Also</span></span>  
 [<span data-ttu-id="90874-143">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="90874-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [<span data-ttu-id="90874-144">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="90874-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="90874-145">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="90874-145">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
