---
title: Protezione dei messaggi con certificati reciproci
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
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3d5e598fea118eb340b965d605f5fdeb9c479a4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="805be-102">Protezione dei messaggi con certificati reciproci</span><span class="sxs-lookup"><span data-stu-id="805be-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="805be-103">Nello scenario seguente sono illustrati un client e un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protetti tramite la protezione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="805be-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message security mode.</span></span> <span data-ttu-id="805be-104">Il client e il servizio sono autenticati mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="805be-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="805be-105">Questo scenario è interoperativo perché utilizza WS-Security con la specifica X.509 Certificate Token Profile.</span><span class="sxs-lookup"><span data-stu-id="805be-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="805be-106">Nello scenario non viene eseguita la negoziazione del certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="805be-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="805be-107">È necessario che il certificato del servizio venga fornito al client prima di qualsiasi comunicazione.</span><span class="sxs-lookup"><span data-stu-id="805be-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="805be-108">Il certificato del server può essere distribuito con l'applicazione o fornito in una comunicazione fuori banda.</span><span class="sxs-lookup"><span data-stu-id="805be-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="805be-109">![Messaggio di sicurezza con certificati reciproci](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="805be-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="805be-110">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="805be-110">Characteristic</span></span>|<span data-ttu-id="805be-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="805be-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="805be-112">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="805be-112">Security Mode</span></span>|<span data-ttu-id="805be-113">Messaggio</span><span class="sxs-lookup"><span data-stu-id="805be-113">Message</span></span>|  
|<span data-ttu-id="805be-114">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="805be-114">Interoperability</span></span>|<span data-ttu-id="805be-115">Sì, con WS-Security e client e servizi compatibili con X.509 Certificate Token Profile.</span><span class="sxs-lookup"><span data-stu-id="805be-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="805be-116">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="805be-116">Authentication</span></span>|<span data-ttu-id="805be-117">Autenticazione reciproca del server e del client.</span><span class="sxs-lookup"><span data-stu-id="805be-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="805be-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="805be-118">Integrity</span></span>|<span data-ttu-id="805be-119">Sì</span><span class="sxs-lookup"><span data-stu-id="805be-119">Yes</span></span>|  
|<span data-ttu-id="805be-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="805be-120">Confidentiality</span></span>|<span data-ttu-id="805be-121">Sì</span><span class="sxs-lookup"><span data-stu-id="805be-121">Yes</span></span>|  
|<span data-ttu-id="805be-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="805be-122">Transport</span></span>|<span data-ttu-id="805be-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="805be-123">HTTP</span></span>|  
|<span data-ttu-id="805be-124">Binding</span><span class="sxs-lookup"><span data-stu-id="805be-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="805be-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="805be-125">Service</span></span>  
 <span data-ttu-id="805be-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="805be-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="805be-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="805be-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="805be-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="805be-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="805be-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="805be-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="805be-130">Codice</span><span class="sxs-lookup"><span data-stu-id="805be-130">Code</span></span>  
 <span data-ttu-id="805be-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="805be-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="805be-132">Il servizio richiede un certificato per identificarsi.</span><span class="sxs-lookup"><span data-stu-id="805be-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="805be-133">Configurazione</span><span class="sxs-lookup"><span data-stu-id="805be-133">Configuration</span></span>  
 <span data-ttu-id="805be-134">Per creare lo stesso servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="805be-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"   
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="805be-135">Client</span><span class="sxs-lookup"><span data-stu-id="805be-135">Client</span></span>  
 <span data-ttu-id="805be-136">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="805be-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="805be-137">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="805be-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="805be-138">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="805be-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="805be-139">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="805be-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="805be-140">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="805be-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="805be-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="805be-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="805be-142">Codice</span><span class="sxs-lookup"><span data-stu-id="805be-142">Code</span></span>  
 <span data-ttu-id="805be-143">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="805be-143">The following code creates the client.</span></span> <span data-ttu-id="805be-144">La modalità di sicurezza è impostata su Message e il tipo di credenziale client è impostato su Certificate.</span><span class="sxs-lookup"><span data-stu-id="805be-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="805be-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="805be-145">Configuration</span></span>  
 <span data-ttu-id="805be-146">Il codice seguente consente di configurare il client.</span><span class="sxs-lookup"><span data-stu-id="805be-146">The following configures the client.</span></span> <span data-ttu-id="805be-147">Un certificato client deve essere specificato utilizzando il [ \<clientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="805be-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="805be-148">Inoltre, il certificato del servizio viene specificato usando il [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="805be-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"   
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="805be-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="805be-149">See Also</span></span>  
 [<span data-ttu-id="805be-150">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="805be-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="805be-151">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="805be-151">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)  
 [<span data-ttu-id="805be-152">Procedura: creare e installare i certificati temporanei in WCF per la sicurezza del trasporto durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="805be-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=244264)
