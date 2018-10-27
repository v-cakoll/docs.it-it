---
title: Protezione dei messaggi con un client anonimo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: e90eeb787fd2141459dfa67f36fda94036cec94f
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50036801"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="5d57f-102">Protezione dei messaggi con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="5d57f-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="5d57f-103">Lo scenario seguente vengono illustrati un client e servizio protetti dalla protezione dei messaggi di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5d57f-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="5d57f-104">Tra gli obiettivi di progettazione c'è quello di usare la sicurezza dei messaggi invece che la sicurezza del trasporto, così che in futuro sia possibile supportare un modello basato su attestazioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="5d57f-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="5d57f-105">Per altre informazioni sull'uso di attestazioni dettagliate per l'autorizzazione, vedere [gestione di attestazioni e autorizzazioni con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="5d57f-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="5d57f-106">Per un'applicazione di esempio, vedere [sicurezza dei messaggi anonima](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="5d57f-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="5d57f-107">![Messaggio di sicurezza con un client anonimo](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="5d57f-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="5d57f-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="5d57f-108">Characteristic</span></span>|<span data-ttu-id="5d57f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d57f-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5d57f-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d57f-110">Security Mode</span></span>|<span data-ttu-id="5d57f-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5d57f-111">Message</span></span>|  
|<span data-ttu-id="5d57f-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="5d57f-112">Interoperability</span></span>|<span data-ttu-id="5d57f-113">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="5d57f-113">WCF only</span></span>|  
|<span data-ttu-id="5d57f-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="5d57f-114">Authentication (Server)</span></span>|<span data-ttu-id="5d57f-115">La negoziazione iniziale richiede l'autenticazione server, ma non l'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="5d57f-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="5d57f-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="5d57f-116">Authentication (Client)</span></span>|<span data-ttu-id="5d57f-117">None</span><span class="sxs-lookup"><span data-stu-id="5d57f-117">None</span></span>|  
|<span data-ttu-id="5d57f-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="5d57f-118">Integrity</span></span>|<span data-ttu-id="5d57f-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="5d57f-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="5d57f-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="5d57f-120">Confidentiality</span></span>|<span data-ttu-id="5d57f-121">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="5d57f-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="5d57f-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="5d57f-122">Transport</span></span>|<span data-ttu-id="5d57f-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="5d57f-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="5d57f-124">Servizio</span><span class="sxs-lookup"><span data-stu-id="5d57f-124">Service</span></span>  
 <span data-ttu-id="5d57f-125">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="5d57f-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5d57f-126">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d57f-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5d57f-127">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="5d57f-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="5d57f-128">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="5d57f-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d57f-129">Codice</span><span class="sxs-lookup"><span data-stu-id="5d57f-129">Code</span></span>  
 <span data-ttu-id="5d57f-130">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d57f-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="5d57f-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5d57f-131">Configuration</span></span>  
 <span data-ttu-id="5d57f-132">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="5d57f-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="5d57f-133">L'elemento di comportamento del servizio viene usato per specificare un certificato che viene usato per autenticare il servizio sul client.</span><span class="sxs-lookup"><span data-stu-id="5d57f-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="5d57f-134">L'elemento servizio deve specificare il comportamento usando l'attributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="5d57f-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="5d57f-135">L'elemento associazione specifica che il tipo di credenziale client è `None`, consentendo ai client anonimi di usare il servizio.</span><span class="sxs-lookup"><span data-stu-id="5d57f-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="5d57f-136">Client</span><span class="sxs-lookup"><span data-stu-id="5d57f-136">Client</span></span>  
 <span data-ttu-id="5d57f-137">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="5d57f-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5d57f-138">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d57f-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5d57f-139">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="5d57f-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="5d57f-140">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="5d57f-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="5d57f-141">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="5d57f-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="5d57f-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5d57f-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="5d57f-143">Codice</span><span class="sxs-lookup"><span data-stu-id="5d57f-143">Code</span></span>  
 <span data-ttu-id="5d57f-144">Nel codice seguente viene creata un'istanza del client.</span><span class="sxs-lookup"><span data-stu-id="5d57f-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="5d57f-145">L'associazione usa la protezione in modalità messaggio e il tipo di credenziale client è impostato su Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d57f-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="5d57f-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5d57f-146">Configuration</span></span>  
 <span data-ttu-id="5d57f-147">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="5d57f-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d57f-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d57f-148">See Also</span></span>  
 [<span data-ttu-id="5d57f-149">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d57f-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="5d57f-150">Sicurezza delle applicazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="5d57f-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="5d57f-151">Sicurezza dei messaggi anonima</span><span class="sxs-lookup"><span data-stu-id="5d57f-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="5d57f-152">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="5d57f-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5d57f-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="5d57f-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
