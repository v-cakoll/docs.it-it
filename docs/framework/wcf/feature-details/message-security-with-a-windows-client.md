---
title: Protezione dei messaggi con un client Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: dcb311523c6ec41b62f6e69fe6bc7635b9d49708
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595232"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="b10cb-102">Protezione dei messaggi con un client Windows</span><span class="sxs-lookup"><span data-stu-id="b10cb-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="b10cb-103">Questo scenario mostra un client Windows Communication Foundation (WCF) e un server protetti dalla modalità di sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b10cb-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="b10cb-104">Il client e il servizio vengono autenticati utilizzando le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="b10cb-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="b10cb-105">![Sicurezza dei messaggi con un client Windows](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="b10cb-105">![Message security with a Windows client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="b10cb-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="b10cb-106">Characteristic</span></span>|<span data-ttu-id="b10cb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b10cb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b10cb-108">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b10cb-108">Security Mode</span></span>|<span data-ttu-id="b10cb-109">Message</span><span class="sxs-lookup"><span data-stu-id="b10cb-109">Message</span></span>|  
|<span data-ttu-id="b10cb-110">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b10cb-110">Interoperability</span></span>|<span data-ttu-id="b10cb-111">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="b10cb-111">WCF Only</span></span>|  
|<span data-ttu-id="b10cb-112">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="b10cb-112">Authentication (Server)</span></span>|<span data-ttu-id="b10cb-113">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="b10cb-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b10cb-114">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="b10cb-114">Authentication (Client)</span></span>|<span data-ttu-id="b10cb-115">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="b10cb-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b10cb-116">Integrità</span><span class="sxs-lookup"><span data-stu-id="b10cb-116">Integrity</span></span>|<span data-ttu-id="b10cb-117">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="b10cb-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="b10cb-118">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="b10cb-118">Confidentiality</span></span>|<span data-ttu-id="b10cb-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="b10cb-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="b10cb-120">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b10cb-120">Transport</span></span>|<span data-ttu-id="b10cb-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="b10cb-121">NET.TCP</span></span>|  
|<span data-ttu-id="b10cb-122">Binding</span><span class="sxs-lookup"><span data-stu-id="b10cb-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="b10cb-123">Service</span><span class="sxs-lookup"><span data-stu-id="b10cb-123">Service</span></span>  
 <span data-ttu-id="b10cb-124">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b10cb-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b10cb-125">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10cb-125">Do one of the following:</span></span>  
  
- <span data-ttu-id="b10cb-126">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="b10cb-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="b10cb-127">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="b10cb-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b10cb-128">Codice</span><span class="sxs-lookup"><span data-stu-id="b10cb-128">Code</span></span>  
 <span data-ttu-id="b10cb-129">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto con un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="b10cb-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="b10cb-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="b10cb-130">Configuration</span></span>  
 <span data-ttu-id="b10cb-131">Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice:</span><span class="sxs-lookup"><span data-stu-id="b10cb-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="b10cb-132">Client</span><span class="sxs-lookup"><span data-stu-id="b10cb-132">Client</span></span>  
 <span data-ttu-id="b10cb-133">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b10cb-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b10cb-134">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10cb-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="b10cb-135">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="b10cb-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="b10cb-136">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="b10cb-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="b10cb-137">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="b10cb-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="b10cb-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b10cb-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="b10cb-139">Codice</span><span class="sxs-lookup"><span data-stu-id="b10cb-139">Code</span></span>  
 <span data-ttu-id="b10cb-140">Il codice seguente crea un client.</span><span class="sxs-lookup"><span data-stu-id="b10cb-140">The following code creates a client.</span></span> <span data-ttu-id="b10cb-141">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="b10cb-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="b10cb-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="b10cb-142">Configuration</span></span>  
 <span data-ttu-id="b10cb-143">Per impostare le proprietà client viene utilizzata la configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="b10cb-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b10cb-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b10cb-144">See also</span></span>

- [<span data-ttu-id="b10cb-145">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="b10cb-145">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="b10cb-146">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b10cb-146">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
