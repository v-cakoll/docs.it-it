---
title: Protezione dei messaggi con un client di certificato
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
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
caps.latest.revision: "16"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e778b48b3ff00c3053992f8e754f674cd7705ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="f7118-102">Protezione dei messaggi con un client di certificato</span><span class="sxs-lookup"><span data-stu-id="f7118-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="f7118-103">Nello scenario seguente sono illustrati un client e un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protetti tramite la protezione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="f7118-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured using message security mode.</span></span> <span data-ttu-id="f7118-104">Sia il client che il servizio sono autenticati mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="f7118-104">Both the client and the service are authenticated with certificates.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f7118-105">[Protezione applicazione distribuita](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="f7118-105"> [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="f7118-106">Per un'applicazione di esempio, vedere [certificato di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="f7118-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="f7118-107">![Client con certificato](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="f7118-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="f7118-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="f7118-108">Characteristic</span></span>|<span data-ttu-id="f7118-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7118-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f7118-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f7118-110">Security Mode</span></span>|<span data-ttu-id="f7118-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f7118-111">Message</span></span>|  
|<span data-ttu-id="f7118-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f7118-112">Interoperability</span></span>|<span data-ttu-id="f7118-113">Solo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7118-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="f7118-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="f7118-114">Authentication (Server)</span></span>|<span data-ttu-id="f7118-115">Utilizzo del certificato del servizio</span><span class="sxs-lookup"><span data-stu-id="f7118-115">Using service certificate</span></span>|  
|<span data-ttu-id="f7118-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="f7118-116">Authentication (Client)</span></span>|<span data-ttu-id="f7118-117">Utilizzo del certificato client</span><span class="sxs-lookup"><span data-stu-id="f7118-117">Using client certificate</span></span>|  
|<span data-ttu-id="f7118-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="f7118-118">Integrity</span></span>|<span data-ttu-id="f7118-119">Sì</span><span class="sxs-lookup"><span data-stu-id="f7118-119">Yes</span></span>|  
|<span data-ttu-id="f7118-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="f7118-120">Confidentiality</span></span>|<span data-ttu-id="f7118-121">Sì</span><span class="sxs-lookup"><span data-stu-id="f7118-121">Yes</span></span>|  
|<span data-ttu-id="f7118-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="f7118-122">Transport</span></span>|<span data-ttu-id="f7118-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="f7118-123">HTTP</span></span>|  
|<span data-ttu-id="f7118-124">Binding</span><span class="sxs-lookup"><span data-stu-id="f7118-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="f7118-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="f7118-125">Service</span></span>  
 <span data-ttu-id="f7118-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="f7118-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f7118-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7118-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f7118-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="f7118-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f7118-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7118-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f7118-130">Codice</span><span class="sxs-lookup"><span data-stu-id="f7118-130">Code</span></span>  
 <span data-ttu-id="f7118-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto.</span><span class="sxs-lookup"><span data-stu-id="f7118-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="f7118-132">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f7118-132">Configuration</span></span>  
 <span data-ttu-id="f7118-133">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="f7118-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCerficiateClient"   
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="f7118-134">Client</span><span class="sxs-lookup"><span data-stu-id="f7118-134">Client</span></span>  
 <span data-ttu-id="f7118-135">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="f7118-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f7118-136">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7118-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f7118-137">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="f7118-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f7118-138">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7118-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f7118-139">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="f7118-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f7118-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f7118-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f7118-141">Codice</span><span class="sxs-lookup"><span data-stu-id="f7118-141">Code</span></span>  
 <span data-ttu-id="f7118-142">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="f7118-142">The following code creates the client.</span></span> <span data-ttu-id="f7118-143">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="f7118-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="f7118-144">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f7118-144">Configuration</span></span>  
 <span data-ttu-id="f7118-145">Nella configurazione seguente il certificato client è specificato utilizzando un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7118-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="f7118-146">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f7118-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="f7118-147">Viene inoltre utilizzato un <`identity`> per specificare un sistema DNS (Domain Name) dell'identità del server previste.</span><span class="sxs-lookup"><span data-stu-id="f7118-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f7118-148">identità, vedere [autenticazione e identità del servizio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f7118-148"> identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7118-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7118-149">See Also</span></span>  
 [<span data-ttu-id="f7118-150">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f7118-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f7118-151">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f7118-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f7118-152">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="f7118-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="f7118-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="f7118-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
