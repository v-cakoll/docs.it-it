---
title: Protezione dei messaggi con un client di certificato
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
caps.latest.revision: 16
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 6e31c7a9e53e8b918661c0c6c544e697e2a772e6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="082b0-102">Protezione dei messaggi con un client di certificato</span><span class="sxs-lookup"><span data-stu-id="082b0-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="082b0-103">Nello scenario seguente sono illustrati un client e un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protetti tramite la protezione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="082b0-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured using message security mode.</span></span> <span data-ttu-id="082b0-104">Sia il client che il servizio sono autenticati mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="082b0-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="082b0-105">Per altre informazioni, vedere [protezione di applicazione distribuita](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="082b0-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="082b0-106">Per un'applicazione di esempio, vedere [certificato di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="082b0-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="082b0-107">![Client con certificato](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="082b0-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="082b0-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="082b0-108">Characteristic</span></span>|<span data-ttu-id="082b0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="082b0-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="082b0-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="082b0-110">Security Mode</span></span>|<span data-ttu-id="082b0-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="082b0-111">Message</span></span>|  
|<span data-ttu-id="082b0-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="082b0-112">Interoperability</span></span>|<span data-ttu-id="082b0-113">Solo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="082b0-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="082b0-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="082b0-114">Authentication (Server)</span></span>|<span data-ttu-id="082b0-115">Utilizzo del certificato del servizio</span><span class="sxs-lookup"><span data-stu-id="082b0-115">Using service certificate</span></span>|  
|<span data-ttu-id="082b0-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="082b0-116">Authentication (Client)</span></span>|<span data-ttu-id="082b0-117">Utilizzo del certificato client</span><span class="sxs-lookup"><span data-stu-id="082b0-117">Using client certificate</span></span>|  
|<span data-ttu-id="082b0-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="082b0-118">Integrity</span></span>|<span data-ttu-id="082b0-119">Sì</span><span class="sxs-lookup"><span data-stu-id="082b0-119">Yes</span></span>|  
|<span data-ttu-id="082b0-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="082b0-120">Confidentiality</span></span>|<span data-ttu-id="082b0-121">Sì</span><span class="sxs-lookup"><span data-stu-id="082b0-121">Yes</span></span>|  
|<span data-ttu-id="082b0-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="082b0-122">Transport</span></span>|<span data-ttu-id="082b0-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="082b0-123">HTTP</span></span>|  
|<span data-ttu-id="082b0-124">Binding</span><span class="sxs-lookup"><span data-stu-id="082b0-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="082b0-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="082b0-125">Service</span></span>  
 <span data-ttu-id="082b0-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="082b0-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="082b0-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="082b0-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="082b0-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="082b0-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="082b0-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="082b0-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="082b0-130">Codice</span><span class="sxs-lookup"><span data-stu-id="082b0-130">Code</span></span>  
 <span data-ttu-id="082b0-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto.</span><span class="sxs-lookup"><span data-stu-id="082b0-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="082b0-132">Configurazione</span><span class="sxs-lookup"><span data-stu-id="082b0-132">Configuration</span></span>  
 <span data-ttu-id="082b0-133">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="082b0-133">The following configuration can be used instead of the code.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="082b0-134">Client</span><span class="sxs-lookup"><span data-stu-id="082b0-134">Client</span></span>  
 <span data-ttu-id="082b0-135">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="082b0-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="082b0-136">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="082b0-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="082b0-137">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="082b0-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="082b0-138">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="082b0-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="082b0-139">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="082b0-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="082b0-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="082b0-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="082b0-141">Codice</span><span class="sxs-lookup"><span data-stu-id="082b0-141">Code</span></span>  
 <span data-ttu-id="082b0-142">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="082b0-142">The following code creates the client.</span></span> <span data-ttu-id="082b0-143">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="082b0-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="082b0-144">Configurazione</span><span class="sxs-lookup"><span data-stu-id="082b0-144">Configuration</span></span>  
 <span data-ttu-id="082b0-145">Nella configurazione seguente il certificato client è specificato utilizzando un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="082b0-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="082b0-146">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="082b0-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="082b0-147">Viene inoltre utilizzato un <`identity`> per specificare un sistema DNS (Domain Name) dell'identità del server previste.</span><span class="sxs-lookup"><span data-stu-id="082b0-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="082b0-148">Per ulteriori informazioni sull'identità, vedere [identità del servizio e l'autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="082b0-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="082b0-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="082b0-149">See Also</span></span>  
 [<span data-ttu-id="082b0-150">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="082b0-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="082b0-151">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="082b0-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="082b0-152">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="082b0-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="082b0-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="082b0-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
