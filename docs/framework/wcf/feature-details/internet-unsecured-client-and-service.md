---
title: Client e servizio non protetti in Internet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 7eb640576bc00bc767ba16f8dc4a5d5952a479c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184733"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="8f330-102">Client e servizio non protetti in Internet</span><span class="sxs-lookup"><span data-stu-id="8f330-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="8f330-103">Nella figura seguente viene illustrato un esempio di un servizio e un client e un servizio Windows Communication Foundation (WCF) Windows pubblici e non protetti:The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span><span class="sxs-lookup"><span data-stu-id="8f330-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Screenshot che mostra uno scenario Internet non protetto](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="8f330-105">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="8f330-105">Characteristic</span></span>|<span data-ttu-id="8f330-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f330-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8f330-107">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8f330-107">Security Mode</span></span>|<span data-ttu-id="8f330-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="8f330-108">None</span></span>|  
|<span data-ttu-id="8f330-109">Trasporto</span><span class="sxs-lookup"><span data-stu-id="8f330-109">Transport</span></span>|<span data-ttu-id="8f330-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="8f330-110">HTTP</span></span>|  
|<span data-ttu-id="8f330-111">Associazione</span><span class="sxs-lookup"><span data-stu-id="8f330-111">Binding</span></span>|<span data-ttu-id="8f330-112"><xref:System.ServiceModel.BasicHttpBinding>nel codice o l'elemento [ \<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="8f330-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="8f330-113">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="8f330-113">Interoperability</span></span>|<span data-ttu-id="8f330-114">Con servizi e client di servizi Web esistenti</span><span class="sxs-lookup"><span data-stu-id="8f330-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="8f330-115">Authentication</span><span class="sxs-lookup"><span data-stu-id="8f330-115">Authentication</span></span>|<span data-ttu-id="8f330-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="8f330-116">None</span></span>|  
|<span data-ttu-id="8f330-117">Integrità</span><span class="sxs-lookup"><span data-stu-id="8f330-117">Integrity</span></span>|<span data-ttu-id="8f330-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="8f330-118">None</span></span>|  
|<span data-ttu-id="8f330-119">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="8f330-119">Confidentiality</span></span>|<span data-ttu-id="8f330-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="8f330-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="8f330-121">Service</span><span class="sxs-lookup"><span data-stu-id="8f330-121">Service</span></span>  
 <span data-ttu-id="8f330-122">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="8f330-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8f330-123">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f330-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="8f330-124">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="8f330-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="8f330-125">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="8f330-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8f330-126">Codice</span><span class="sxs-lookup"><span data-stu-id="8f330-126">Code</span></span>  
 <span data-ttu-id="8f330-127">Nel codice seguente viene illustrato come creare un endpoint senza protezione.</span><span class="sxs-lookup"><span data-stu-id="8f330-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="8f330-128">Per impostazione predefinita, nell'elemento <xref:System.ServiceModel.BasicHttpBinding> la modalità di sicurezza è impostata su <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="8f330-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="8f330-129">Service Configuration</span><span class="sxs-lookup"><span data-stu-id="8f330-129">Service Configuration</span></span>  
 <span data-ttu-id="8f330-130">Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8f330-130">The following code sets up the same endpoint using configuration.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="8f330-131">Client</span><span class="sxs-lookup"><span data-stu-id="8f330-131">Client</span></span>  
 <span data-ttu-id="8f330-132">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="8f330-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8f330-133">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f330-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="8f330-134">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="8f330-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="8f330-135">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="8f330-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="8f330-136">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="8f330-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="8f330-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f330-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="8f330-138">Codice</span><span class="sxs-lookup"><span data-stu-id="8f330-138">Code</span></span>  
 <span data-ttu-id="8f330-139">Il codice seguente illustra un client WCF di base che accede a un endpoint non protetto.</span><span class="sxs-lookup"><span data-stu-id="8f330-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="8f330-140">Configurazione del client</span><span class="sxs-lookup"><span data-stu-id="8f330-140">Client Configuration</span></span>  
 <span data-ttu-id="8f330-141">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="8f330-141">The following code configures the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f330-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f330-142">See also</span></span>

- [<span data-ttu-id="8f330-143">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="8f330-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [<span data-ttu-id="8f330-144">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="8f330-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="8f330-145">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8f330-145">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
