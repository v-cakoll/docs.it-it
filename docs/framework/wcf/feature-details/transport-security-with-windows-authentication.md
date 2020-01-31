---
title: Protezione del trasporto con l'autenticazione di Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 6392ea0f17596406a8671a039bd78777d9e11e42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742652"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="cd50b-102">Protezione del trasporto con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="cd50b-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="cd50b-103">Nello scenario seguente vengono illustrati un client e un servizio Windows Communication Foundation (WCF) protetti dalla sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="cd50b-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="cd50b-104">Per altre informazioni sulla programmazione, vedere [procedura: proteggere un servizio con credenziali di Windows](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="cd50b-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="cd50b-105">Un servizio Web intranet consente di visualizzare informazioni sulle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="cd50b-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="cd50b-106">Il client è un'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cd50b-106">The client is a Windows Form application.</span></span> <span data-ttu-id="cd50b-107">L'applicazione è distribuita in un dominio in cui la protezione è affidata a un controller Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cd50b-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Sicurezza del trasporto con l'autenticazione di Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="cd50b-109">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="cd50b-109">Characteristic</span></span>|<span data-ttu-id="cd50b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd50b-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cd50b-111">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cd50b-111">Security Mode</span></span>|<span data-ttu-id="cd50b-112">Transport</span><span class="sxs-lookup"><span data-stu-id="cd50b-112">Transport</span></span>|  
|<span data-ttu-id="cd50b-113">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd50b-113">Interoperability</span></span>|<span data-ttu-id="cd50b-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="cd50b-114">WCF only</span></span>|  
|<span data-ttu-id="cd50b-115">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="cd50b-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="cd50b-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="cd50b-116">Authentication (Client)</span></span>|<span data-ttu-id="cd50b-117">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="cd50b-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="cd50b-118">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="cd50b-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="cd50b-119">Integrità</span><span class="sxs-lookup"><span data-stu-id="cd50b-119">Integrity</span></span>|<span data-ttu-id="cd50b-120">Sì</span><span class="sxs-lookup"><span data-stu-id="cd50b-120">Yes</span></span>|  
|<span data-ttu-id="cd50b-121">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="cd50b-121">Confidentiality</span></span>|<span data-ttu-id="cd50b-122">Sì</span><span class="sxs-lookup"><span data-stu-id="cd50b-122">Yes</span></span>|  
|<span data-ttu-id="cd50b-123">Transport</span><span class="sxs-lookup"><span data-stu-id="cd50b-123">Transport</span></span>|<span data-ttu-id="cd50b-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="cd50b-124">NET.TCP</span></span>|  
|<span data-ttu-id="cd50b-125">Associazione</span><span class="sxs-lookup"><span data-stu-id="cd50b-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="cd50b-126">Servizio</span><span class="sxs-lookup"><span data-stu-id="cd50b-126">Service</span></span>  
 <span data-ttu-id="cd50b-127">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="cd50b-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="cd50b-128">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="cd50b-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="cd50b-129">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="cd50b-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="cd50b-130">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="cd50b-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cd50b-131">Codice</span><span class="sxs-lookup"><span data-stu-id="cd50b-131">Code</span></span>  
 <span data-ttu-id="cd50b-132">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cd50b-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="cd50b-133">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="cd50b-133">Configuration</span></span>  
 <span data-ttu-id="cd50b-134">Per configurare l'endpoint del servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="cd50b-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="cd50b-135">Client</span><span class="sxs-lookup"><span data-stu-id="cd50b-135">Client</span></span>  
 <span data-ttu-id="cd50b-136">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="cd50b-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="cd50b-137">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="cd50b-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="cd50b-138">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="cd50b-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="cd50b-139">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="cd50b-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="cd50b-140">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="cd50b-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="cd50b-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cd50b-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="cd50b-142">Codice</span><span class="sxs-lookup"><span data-stu-id="cd50b-142">Code</span></span>  
 <span data-ttu-id="cd50b-143">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="cd50b-143">The following code creates the client.</span></span> <span data-ttu-id="cd50b-144">L'associazione è configurata per utilizzare la protezione della modalità trasporto, con il trasporto TCP e il tipo di credenziale client impostato su Windows.</span><span class="sxs-lookup"><span data-stu-id="cd50b-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="cd50b-145">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="cd50b-145">Configuration</span></span>  
 <span data-ttu-id="cd50b-146">Per creare il client, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="cd50b-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd50b-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd50b-147">See also</span></span>

- [<span data-ttu-id="cd50b-148">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="cd50b-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="cd50b-149">Procedura: Proteggere un servizio con credenziali di Windows</span><span class="sxs-lookup"><span data-stu-id="cd50b-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="cd50b-150">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cd50b-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
