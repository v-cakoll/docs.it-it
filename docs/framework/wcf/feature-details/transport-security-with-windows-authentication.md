---
title: Protezione del trasporto con l'autenticazione di Windows
description: Esaminare questo scenario, che mostra un client/servizio WCF protetto dalla sicurezza di Windows. In questo esempio un servizio Intranet Visualizza le informazioni sulle risorse umane.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: b6134d4cbdff0c1adea704a7f3aaff7e40fd75ec
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244764"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="95d46-104">Protezione del trasporto con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="95d46-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="95d46-105">Nello scenario seguente vengono illustrati un client e un servizio Windows Communication Foundation (WCF) protetti dalla sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="95d46-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="95d46-106">Per altre informazioni sulla programmazione, vedere [procedura: proteggere un servizio con credenziali di Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="95d46-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="95d46-107">Un servizio Web intranet consente di visualizzare informazioni sulle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="95d46-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="95d46-108">Il client è un'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="95d46-108">The client is a Windows Form application.</span></span> <span data-ttu-id="95d46-109">L'applicazione è distribuita in un dominio in cui la protezione è affidata a un controller Kerberos.</span><span class="sxs-lookup"><span data-stu-id="95d46-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Sicurezza del trasporto con l'autenticazione di Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="95d46-111">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="95d46-111">Characteristic</span></span>|<span data-ttu-id="95d46-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95d46-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="95d46-113">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="95d46-113">Security Mode</span></span>|<span data-ttu-id="95d46-114">Trasporto</span><span class="sxs-lookup"><span data-stu-id="95d46-114">Transport</span></span>|  
|<span data-ttu-id="95d46-115">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="95d46-115">Interoperability</span></span>|<span data-ttu-id="95d46-116">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="95d46-116">WCF only</span></span>|  
|<span data-ttu-id="95d46-117">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="95d46-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="95d46-118">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="95d46-118">Authentication (Client)</span></span>|<span data-ttu-id="95d46-119">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="95d46-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="95d46-120">Sì (utilizza l'autenticazione integrata di Windows)</span><span class="sxs-lookup"><span data-stu-id="95d46-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="95d46-121">Integrità</span><span class="sxs-lookup"><span data-stu-id="95d46-121">Integrity</span></span>|<span data-ttu-id="95d46-122">Sì</span><span class="sxs-lookup"><span data-stu-id="95d46-122">Yes</span></span>|  
|<span data-ttu-id="95d46-123">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="95d46-123">Confidentiality</span></span>|<span data-ttu-id="95d46-124">Sì</span><span class="sxs-lookup"><span data-stu-id="95d46-124">Yes</span></span>|  
|<span data-ttu-id="95d46-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="95d46-125">Transport</span></span>|<span data-ttu-id="95d46-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="95d46-126">NET.TCP</span></span>|  
|<span data-ttu-id="95d46-127">Binding</span><span class="sxs-lookup"><span data-stu-id="95d46-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="95d46-128">Service</span><span class="sxs-lookup"><span data-stu-id="95d46-128">Service</span></span>  
 <span data-ttu-id="95d46-129">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="95d46-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="95d46-130">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95d46-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="95d46-131">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="95d46-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="95d46-132">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="95d46-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="95d46-133">Codice</span><span class="sxs-lookup"><span data-stu-id="95d46-133">Code</span></span>  
 <span data-ttu-id="95d46-134">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="95d46-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="95d46-135">Configurazione</span><span class="sxs-lookup"><span data-stu-id="95d46-135">Configuration</span></span>  
 <span data-ttu-id="95d46-136">Per configurare l'endpoint del servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="95d46-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="95d46-137">Client</span><span class="sxs-lookup"><span data-stu-id="95d46-137">Client</span></span>  
 <span data-ttu-id="95d46-138">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="95d46-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="95d46-139">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95d46-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="95d46-140">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="95d46-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="95d46-141">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="95d46-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="95d46-142">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="95d46-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="95d46-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="95d46-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="95d46-144">Codice</span><span class="sxs-lookup"><span data-stu-id="95d46-144">Code</span></span>  
 <span data-ttu-id="95d46-145">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="95d46-145">The following code creates the client.</span></span> <span data-ttu-id="95d46-146">L'associazione è configurata per utilizzare la protezione della modalità trasporto, con il trasporto TCP e il tipo di credenziale client impostato su Windows.</span><span class="sxs-lookup"><span data-stu-id="95d46-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="95d46-147">Configurazione</span><span class="sxs-lookup"><span data-stu-id="95d46-147">Configuration</span></span>  
 <span data-ttu-id="95d46-148">Per creare il client, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="95d46-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95d46-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95d46-149">See also</span></span>

- [<span data-ttu-id="95d46-150">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="95d46-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="95d46-151">Procedura: Proteggere un servizio con credenziali di Windows</span><span class="sxs-lookup"><span data-stu-id="95d46-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="95d46-152">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="95d46-152">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
