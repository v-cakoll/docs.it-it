---
title: Protezione dei messaggi con un client di certificato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7aad53e9c6d5708bceca9831264c112f885fb889
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732514"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="41f1e-102">Protezione dei messaggi con un client di certificato</span><span class="sxs-lookup"><span data-stu-id="41f1e-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="41f1e-103">Lo scenario seguente viene illustrato un client Windows Communication Foundation (WCF) e un servizio protetti tramite la modalità sicurezza messaggio.</span><span class="sxs-lookup"><span data-stu-id="41f1e-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="41f1e-104">Sia il client che il servizio sono autenticati mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="41f1e-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="41f1e-105">Per altre informazioni, vedere [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="41f1e-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="41f1e-106">Per un'applicazione di esempio, vedere [certificato di sicurezza dei messaggi](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="41f1e-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="41f1e-107">![Client con certificato](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="41f1e-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="41f1e-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="41f1e-108">Characteristic</span></span>|<span data-ttu-id="41f1e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41f1e-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="41f1e-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="41f1e-110">Security Mode</span></span>|<span data-ttu-id="41f1e-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="41f1e-111">Message</span></span>|  
|<span data-ttu-id="41f1e-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="41f1e-112">Interoperability</span></span>|<span data-ttu-id="41f1e-113">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="41f1e-113">WCF only</span></span>|  
|<span data-ttu-id="41f1e-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="41f1e-114">Authentication (Server)</span></span>|<span data-ttu-id="41f1e-115">Utilizzo del certificato del servizio</span><span class="sxs-lookup"><span data-stu-id="41f1e-115">Using service certificate</span></span>|  
|<span data-ttu-id="41f1e-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="41f1e-116">Authentication (Client)</span></span>|<span data-ttu-id="41f1e-117">Utilizzo del certificato client</span><span class="sxs-lookup"><span data-stu-id="41f1e-117">Using client certificate</span></span>|  
|<span data-ttu-id="41f1e-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="41f1e-118">Integrity</span></span>|<span data-ttu-id="41f1e-119">Sì</span><span class="sxs-lookup"><span data-stu-id="41f1e-119">Yes</span></span>|  
|<span data-ttu-id="41f1e-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="41f1e-120">Confidentiality</span></span>|<span data-ttu-id="41f1e-121">Sì</span><span class="sxs-lookup"><span data-stu-id="41f1e-121">Yes</span></span>|  
|<span data-ttu-id="41f1e-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="41f1e-122">Transport</span></span>|<span data-ttu-id="41f1e-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="41f1e-123">HTTP</span></span>|  
|<span data-ttu-id="41f1e-124">Binding</span><span class="sxs-lookup"><span data-stu-id="41f1e-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="41f1e-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="41f1e-125">Service</span></span>  
 <span data-ttu-id="41f1e-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="41f1e-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="41f1e-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41f1e-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="41f1e-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="41f1e-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="41f1e-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="41f1e-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41f1e-130">Codice</span><span class="sxs-lookup"><span data-stu-id="41f1e-130">Code</span></span>  
 <span data-ttu-id="41f1e-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto.</span><span class="sxs-lookup"><span data-stu-id="41f1e-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="41f1e-132">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41f1e-132">Configuration</span></span>  
 <span data-ttu-id="41f1e-133">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="41f1e-133">The following configuration can be used instead of the code.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="41f1e-134">Client</span><span class="sxs-lookup"><span data-stu-id="41f1e-134">Client</span></span>  
 <span data-ttu-id="41f1e-135">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="41f1e-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="41f1e-136">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41f1e-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="41f1e-137">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="41f1e-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="41f1e-138">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="41f1e-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="41f1e-139">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="41f1e-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="41f1e-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41f1e-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="41f1e-141">Codice</span><span class="sxs-lookup"><span data-stu-id="41f1e-141">Code</span></span>  
 <span data-ttu-id="41f1e-142">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="41f1e-142">The following code creates the client.</span></span> <span data-ttu-id="41f1e-143">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="41f1e-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="41f1e-144">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41f1e-144">Configuration</span></span>  
 <span data-ttu-id="41f1e-145">Nella configurazione seguente il certificato client è specificato utilizzando un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="41f1e-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="41f1e-146">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="41f1e-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="41f1e-147">Il codice utilizza inoltre un <`identity`> elemento per specificare un sistema DNS (Domain Name) dell'identità server prevista.</span><span class="sxs-lookup"><span data-stu-id="41f1e-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="41f1e-148">Per altre informazioni sull'identità, vedere [identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="41f1e-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41f1e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41f1e-149">See Also</span></span>  
 [<span data-ttu-id="41f1e-150">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="41f1e-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="41f1e-151">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="41f1e-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="41f1e-152">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="41f1e-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="41f1e-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="41f1e-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
