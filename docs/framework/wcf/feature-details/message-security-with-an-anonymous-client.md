---
title: Protezione dei messaggi con un client anonimo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: fccdd021e392e6c37615a9091ce13f0e94167246
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212010"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="607a6-102">Protezione dei messaggi con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="607a6-102">Message Security with an Anonymous Client</span></span>

<span data-ttu-id="607a6-103">Nello scenario seguente vengono illustrati un client e un servizio protetti dalla sicurezza dei messaggi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="607a6-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="607a6-104">Tra gli obiettivi di progettazione c'è quello di usare la sicurezza dei messaggi invece che la sicurezza del trasporto, così che in futuro sia possibile supportare un modello basato su attestazioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="607a6-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="607a6-105">Per ulteriori informazioni sull'utilizzo di attestazioni avanzate per l'autorizzazione, vedere [gestione di attestazioni e autorizzazioni con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="607a6-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="607a6-106">Per un'applicazione di esempio, vedere la pagina relativa alla [sicurezza dei messaggi anonima](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="607a6-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>

<span data-ttu-id="607a6-107">![Sicurezza dei messaggi con un client anonimo](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="607a6-107">![Message security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>

|<span data-ttu-id="607a6-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="607a6-108">Characteristic</span></span>|<span data-ttu-id="607a6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="607a6-109">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="607a6-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="607a6-110">Security Mode</span></span>|<span data-ttu-id="607a6-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="607a6-111">Message</span></span>|
|<span data-ttu-id="607a6-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="607a6-112">Interoperability</span></span>|<span data-ttu-id="607a6-113">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="607a6-113">WCF only</span></span>|
|<span data-ttu-id="607a6-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="607a6-114">Authentication (Server)</span></span>|<span data-ttu-id="607a6-115">La negoziazione iniziale richiede l'autenticazione server, ma non l'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="607a6-115">Initial negotiation requires server authentication, but not client authentication</span></span>|
|<span data-ttu-id="607a6-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="607a6-116">Authentication (Client)</span></span>|<span data-ttu-id="607a6-117">nessuna</span><span class="sxs-lookup"><span data-stu-id="607a6-117">None</span></span>|
|<span data-ttu-id="607a6-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="607a6-118">Integrity</span></span>|<span data-ttu-id="607a6-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="607a6-119">Yes, using shared security context</span></span>|
|<span data-ttu-id="607a6-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="607a6-120">Confidentiality</span></span>|<span data-ttu-id="607a6-121">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="607a6-121">Yes, using shared security context</span></span>|
|<span data-ttu-id="607a6-122">Transport</span><span class="sxs-lookup"><span data-stu-id="607a6-122">Transport</span></span>|<span data-ttu-id="607a6-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="607a6-123">HTTP</span></span>|

## <a name="service"></a><span data-ttu-id="607a6-124">Servizio</span><span class="sxs-lookup"><span data-stu-id="607a6-124">Service</span></span>

<span data-ttu-id="607a6-125">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="607a6-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="607a6-126">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="607a6-126">Do one of the following:</span></span>

- <span data-ttu-id="607a6-127">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="607a6-127">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="607a6-128">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="607a6-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="607a6-129">Codice</span><span class="sxs-lookup"><span data-stu-id="607a6-129">Code</span></span>

<span data-ttu-id="607a6-130">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="607a6-130">The following code shows how to create a service endpoint that uses message security.</span></span>

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a><span data-ttu-id="607a6-131">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="607a6-131">Configuration</span></span>

<span data-ttu-id="607a6-132">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="607a6-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="607a6-133">L'elemento di comportamento del servizio viene usato per specificare un certificato che viene usato per autenticare il servizio sul client.</span><span class="sxs-lookup"><span data-stu-id="607a6-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="607a6-134">L'elemento servizio deve specificare il comportamento usando l'attributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="607a6-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="607a6-135">L'elemento associazione specifica che il tipo di credenziale client è `None`, consentendo ai client anonimi di usare il servizio.</span><span class="sxs-lookup"><span data-stu-id="607a6-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>

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

## <a name="client"></a><span data-ttu-id="607a6-136">Client</span><span class="sxs-lookup"><span data-stu-id="607a6-136">Client</span></span>

<span data-ttu-id="607a6-137">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="607a6-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="607a6-138">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="607a6-138">Do one of the following:</span></span>

- <span data-ttu-id="607a6-139">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="607a6-139">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="607a6-140">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="607a6-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="607a6-141">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="607a6-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="607a6-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="607a6-142">For example:</span></span>

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="607a6-143">Codice</span><span class="sxs-lookup"><span data-stu-id="607a6-143">Code</span></span>

<span data-ttu-id="607a6-144">Nel codice seguente viene creata un'istanza del client.</span><span class="sxs-lookup"><span data-stu-id="607a6-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="607a6-145">L'associazione usa la protezione in modalità messaggio e il tipo di credenziale client è impostato su Nessuno.</span><span class="sxs-lookup"><span data-stu-id="607a6-145">The binding uses message mode security, and the client credential type is set to none.</span></span>

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a><span data-ttu-id="607a6-146">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="607a6-146">Configuration</span></span>

<span data-ttu-id="607a6-147">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="607a6-147">The following code configures the client.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="607a6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="607a6-148">See also</span></span>

- [<span data-ttu-id="607a6-149">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="607a6-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="607a6-150">Sicurezza delle applicazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="607a6-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)
- [<span data-ttu-id="607a6-151">Sicurezza dei messaggi anonima</span><span class="sxs-lookup"><span data-stu-id="607a6-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)
- [<span data-ttu-id="607a6-152">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="607a6-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- <span data-ttu-id="607a6-153">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="607a6-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
