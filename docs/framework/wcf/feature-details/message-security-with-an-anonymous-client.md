---
title: Protezione dei messaggi con un client anonimo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: 058163c96bba036c3183695bf986b4d0424271ac
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595219"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="871f0-102">Protezione dei messaggi con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="871f0-102">Message Security with an Anonymous Client</span></span>

<span data-ttu-id="871f0-103">Nello scenario seguente vengono illustrati un client e un servizio protetti dalla sicurezza dei messaggi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="871f0-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="871f0-104">Tra gli obiettivi di progettazione c'è quello di usare la sicurezza dei messaggi invece che la sicurezza del trasporto, così che in futuro sia possibile supportare un modello basato su attestazioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="871f0-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="871f0-105">Per ulteriori informazioni sull'utilizzo di attestazioni avanzate per l'autorizzazione, vedere [gestione di attestazioni e autorizzazioni con il modello di identità](managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="871f0-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="871f0-106">Per un'applicazione di esempio, vedere la pagina relativa alla [sicurezza dei messaggi anonima](../samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="871f0-106">For a sample application, see [Message Security Anonymous](../samples/message-security-anonymous.md).</span></span>

<span data-ttu-id="871f0-107">![Sicurezza dei messaggi con un client anonimo](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="871f0-107">![Message security with an anonymous client](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>

|<span data-ttu-id="871f0-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="871f0-108">Characteristic</span></span>|<span data-ttu-id="871f0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="871f0-109">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="871f0-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="871f0-110">Security Mode</span></span>|<span data-ttu-id="871f0-111">Message</span><span class="sxs-lookup"><span data-stu-id="871f0-111">Message</span></span>|
|<span data-ttu-id="871f0-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="871f0-112">Interoperability</span></span>|<span data-ttu-id="871f0-113">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="871f0-113">WCF only</span></span>|
|<span data-ttu-id="871f0-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="871f0-114">Authentication (Server)</span></span>|<span data-ttu-id="871f0-115">La negoziazione iniziale richiede l'autenticazione server, ma non l'autenticazione client</span><span class="sxs-lookup"><span data-stu-id="871f0-115">Initial negotiation requires server authentication, but not client authentication</span></span>|
|<span data-ttu-id="871f0-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="871f0-116">Authentication (Client)</span></span>|<span data-ttu-id="871f0-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="871f0-117">None</span></span>|
|<span data-ttu-id="871f0-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="871f0-118">Integrity</span></span>|<span data-ttu-id="871f0-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="871f0-119">Yes, using shared security context</span></span>|
|<span data-ttu-id="871f0-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="871f0-120">Confidentiality</span></span>|<span data-ttu-id="871f0-121">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="871f0-121">Yes, using shared security context</span></span>|
|<span data-ttu-id="871f0-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="871f0-122">Transport</span></span>|<span data-ttu-id="871f0-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="871f0-123">HTTP</span></span>|

## <a name="service"></a><span data-ttu-id="871f0-124">Service</span><span class="sxs-lookup"><span data-stu-id="871f0-124">Service</span></span>

<span data-ttu-id="871f0-125">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="871f0-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="871f0-126">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="871f0-126">Do one of the following:</span></span>

- <span data-ttu-id="871f0-127">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="871f0-127">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="871f0-128">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="871f0-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="871f0-129">Codice</span><span class="sxs-lookup"><span data-stu-id="871f0-129">Code</span></span>

<span data-ttu-id="871f0-130">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="871f0-130">The following code shows how to create a service endpoint that uses message security.</span></span>

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a><span data-ttu-id="871f0-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="871f0-131">Configuration</span></span>

<span data-ttu-id="871f0-132">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="871f0-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="871f0-133">L'elemento di comportamento del servizio viene usato per specificare un certificato che viene usato per autenticare il servizio sul client.</span><span class="sxs-lookup"><span data-stu-id="871f0-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="871f0-134">L'elemento servizio deve specificare il comportamento usando l'attributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="871f0-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="871f0-135">L'elemento associazione specifica che il tipo di credenziale client è `None`, consentendo ai client anonimi di usare il servizio.</span><span class="sxs-lookup"><span data-stu-id="871f0-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>

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

## <a name="client"></a><span data-ttu-id="871f0-136">Client</span><span class="sxs-lookup"><span data-stu-id="871f0-136">Client</span></span>

<span data-ttu-id="871f0-137">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="871f0-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="871f0-138">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="871f0-138">Do one of the following:</span></span>

- <span data-ttu-id="871f0-139">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="871f0-139">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="871f0-140">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="871f0-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="871f0-141">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="871f0-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="871f0-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="871f0-142">For example:</span></span>

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="871f0-143">Codice</span><span class="sxs-lookup"><span data-stu-id="871f0-143">Code</span></span>

<span data-ttu-id="871f0-144">Nel codice seguente viene creata un'istanza del client.</span><span class="sxs-lookup"><span data-stu-id="871f0-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="871f0-145">L'associazione usa la protezione in modalità messaggio e il tipo di credenziale client è impostato su Nessuno.</span><span class="sxs-lookup"><span data-stu-id="871f0-145">The binding uses message mode security, and the client credential type is set to none.</span></span>

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a><span data-ttu-id="871f0-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="871f0-146">Configuration</span></span>

<span data-ttu-id="871f0-147">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="871f0-147">The following code configures the client.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="871f0-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="871f0-148">See also</span></span>

- [<span data-ttu-id="871f0-149">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="871f0-149">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="871f0-150">Protezione delle applicazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="871f0-150">Distributed Application Security</span></span>](distributed-application-security.md)
- [<span data-ttu-id="871f0-151">Sicurezza dei messaggi anonima</span><span class="sxs-lookup"><span data-stu-id="871f0-151">Message Security Anonymous</span></span>](../samples/message-security-anonymous.md)
- [<span data-ttu-id="871f0-152">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="871f0-152">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- <span data-ttu-id="871f0-153">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="871f0-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
