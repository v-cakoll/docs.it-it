---
title: Protezione del trasporto con l'autenticazione di Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
author: BrucePerlerMS
ms.openlocfilehash: babafe369ee9f5c9261e3b5c8bc749d3d1d39ec4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079864"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="c7bb7-102">Protezione del trasporto con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="c7bb7-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="c7bb7-103">Lo scenario seguente viene illustrato un client Windows Communication Foundation (WCF) e un servizio protetti dalla protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="c7bb7-104">Per altre informazioni sulla programmazione, vedere [procedura: proteggere un servizio con le credenziali di Windows](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb7-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="c7bb7-105">Un servizio Web intranet consente di visualizzare informazioni sulle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="c7bb7-106">Il client è un'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-106">The client is a Windows Form application.</span></span> <span data-ttu-id="c7bb7-107">L'applicazione è distribuita in un dominio in cui la protezione è affidata a un controller Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 <span data-ttu-id="c7bb7-108">![Sicurezza del trasporto con autenticazione di Windows](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span><span class="sxs-lookup"><span data-stu-id="c7bb7-108">![Transport security with Windows authentication](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span></span>  
  
|<span data-ttu-id="c7bb7-109">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="c7bb7-109">Characteristic</span></span>|<span data-ttu-id="c7bb7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7bb7-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c7bb7-111">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7bb7-111">Security Mode</span></span>|<span data-ttu-id="c7bb7-112">Trasporto</span><span class="sxs-lookup"><span data-stu-id="c7bb7-112">Transport</span></span>|  
|<span data-ttu-id="c7bb7-113">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="c7bb7-113">Interoperability</span></span>|<span data-ttu-id="c7bb7-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="c7bb7-114">WCF only</span></span>|  
|<span data-ttu-id="c7bb7-115">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="c7bb7-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="c7bb7-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="c7bb7-116">Authentication (Client)</span></span>|<span data-ttu-id="c7bb7-117">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="c7bb7-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="c7bb7-118">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="c7bb7-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="c7bb7-119">Integrità</span><span class="sxs-lookup"><span data-stu-id="c7bb7-119">Integrity</span></span>|<span data-ttu-id="c7bb7-120">Sì</span><span class="sxs-lookup"><span data-stu-id="c7bb7-120">Yes</span></span>|  
|<span data-ttu-id="c7bb7-121">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="c7bb7-121">Confidentiality</span></span>|<span data-ttu-id="c7bb7-122">Sì</span><span class="sxs-lookup"><span data-stu-id="c7bb7-122">Yes</span></span>|  
|<span data-ttu-id="c7bb7-123">Trasporto</span><span class="sxs-lookup"><span data-stu-id="c7bb7-123">Transport</span></span>|<span data-ttu-id="c7bb7-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="c7bb7-124">NET.TCP</span></span>|  
|<span data-ttu-id="c7bb7-125">Binding</span><span class="sxs-lookup"><span data-stu-id="c7bb7-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="c7bb7-126">Servizio</span><span class="sxs-lookup"><span data-stu-id="c7bb7-126">Service</span></span>  
 <span data-ttu-id="c7bb7-127">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c7bb7-128">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7bb7-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c7bb7-129">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="c7bb7-130">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c7bb7-131">Codice</span><span class="sxs-lookup"><span data-stu-id="c7bb7-131">Code</span></span>  
 <span data-ttu-id="c7bb7-132">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="c7bb7-133">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c7bb7-133">Configuration</span></span>  
 <span data-ttu-id="c7bb7-134">Per configurare l'endpoint del servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"   
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="c7bb7-135">Client</span><span class="sxs-lookup"><span data-stu-id="c7bb7-135">Client</span></span>  
 <span data-ttu-id="c7bb7-136">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c7bb7-137">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7bb7-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c7bb7-138">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="c7bb7-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="c7bb7-139">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="c7bb7-140">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="c7bb7-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c7bb7-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="c7bb7-142">Codice</span><span class="sxs-lookup"><span data-stu-id="c7bb7-142">Code</span></span>  
 <span data-ttu-id="c7bb7-143">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-143">The following code creates the client.</span></span> <span data-ttu-id="c7bb7-144">L'associazione è configurata per utilizzare la protezione della modalità trasporto, con il trasporto TCP e il tipo di credenziale client impostato su Windows.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="c7bb7-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c7bb7-145">Configuration</span></span>  
 <span data-ttu-id="c7bb7-146">Per creare il client, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="c7bb7-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"   
                binding="netTcpBinding"            
                bindingConfiguration="NetTcpBinding_ICalculator"   
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7bb7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7bb7-147">See Also</span></span>  
 [<span data-ttu-id="c7bb7-148">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7bb7-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="c7bb7-149">Procedura: Proteggere un servizio con credenziali di Windows</span><span class="sxs-lookup"><span data-stu-id="c7bb7-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)  
 [<span data-ttu-id="c7bb7-150">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="c7bb7-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
