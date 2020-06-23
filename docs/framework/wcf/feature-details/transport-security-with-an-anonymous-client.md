---
title: Sicurezza del trasporto con un client anonimo
description: Esaminare questo scenario WCF, che utilizza la sicurezza del trasporto per autenticare un server utilizzando un certificato considerato attendibile dal client. Il client non è autenticato.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 08cfb8c1a5581f17a251224430018764bed80b0f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245011"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="7a1aa-104">Sicurezza del trasporto con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="7a1aa-104">Transport security with an anonymous client</span></span>

<span data-ttu-id="7a1aa-105">In questo scenario Windows Communication Foundation (WCF) viene utilizzata la sicurezza del trasporto (HTTPS) per garantire la riservatezza e l'integrità.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-105">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="7a1aa-106">È necessario che il server sia autenticato con un certificato SSL (Secure Sockets Layer) e che il client ritenga attendibile il certificato del server.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-106">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="7a1aa-107">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-107">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="7a1aa-108">Per un'applicazione di esempio, vedere la pagina relativa alla [sicurezza del trasporto WS](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="7a1aa-108">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="7a1aa-109">Per ulteriori informazioni sulla sicurezza del trasporto, vedere [Panoramica della sicurezza del trasporto](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7a1aa-109">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="7a1aa-110">Per ulteriori informazioni sull'utilizzo di un certificato con un servizio, vedere [utilizzo dei certificati](working-with-certificates.md) e [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="7a1aa-110">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Utilizzo della sicurezza del trasporto con un client anonimo](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="7a1aa-112">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7a1aa-112">Characteristic</span></span>|<span data-ttu-id="7a1aa-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a1aa-113">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="7a1aa-114">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7a1aa-114">Security Mode</span></span>|<span data-ttu-id="7a1aa-115">Trasporto</span><span class="sxs-lookup"><span data-stu-id="7a1aa-115">Transport</span></span>|
|<span data-ttu-id="7a1aa-116">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7a1aa-116">Interoperability</span></span>|<span data-ttu-id="7a1aa-117">Con i servizi Web e i client esistenti</span><span class="sxs-lookup"><span data-stu-id="7a1aa-117">With existing Web services and clients</span></span>|
|<span data-ttu-id="7a1aa-118">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="7a1aa-118">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="7a1aa-119">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="7a1aa-119">Authentication (Client)</span></span>|<span data-ttu-id="7a1aa-120">Sì</span><span class="sxs-lookup"><span data-stu-id="7a1aa-120">Yes</span></span><br /><br /> <span data-ttu-id="7a1aa-121">Livello applicazione (nessun supporto WCF)</span><span class="sxs-lookup"><span data-stu-id="7a1aa-121">Application level (no WCF support)</span></span>|
|<span data-ttu-id="7a1aa-122">Integrità</span><span class="sxs-lookup"><span data-stu-id="7a1aa-122">Integrity</span></span>|<span data-ttu-id="7a1aa-123">Sì</span><span class="sxs-lookup"><span data-stu-id="7a1aa-123">Yes</span></span>|
|<span data-ttu-id="7a1aa-124">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="7a1aa-124">Confidentiality</span></span>|<span data-ttu-id="7a1aa-125">Sì</span><span class="sxs-lookup"><span data-stu-id="7a1aa-125">Yes</span></span>|
|<span data-ttu-id="7a1aa-126">Trasporto</span><span class="sxs-lookup"><span data-stu-id="7a1aa-126">Transport</span></span>|<span data-ttu-id="7a1aa-127">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7a1aa-127">HTTPS</span></span>|
|<span data-ttu-id="7a1aa-128">Binding</span><span class="sxs-lookup"><span data-stu-id="7a1aa-128">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="7a1aa-129">Service</span><span class="sxs-lookup"><span data-stu-id="7a1aa-129">Service</span></span>

<span data-ttu-id="7a1aa-130">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-130">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7a1aa-131">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a1aa-131">Do one of the following:</span></span>

- <span data-ttu-id="7a1aa-132">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-132">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="7a1aa-133">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-133">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="7a1aa-134">Codice</span><span class="sxs-lookup"><span data-stu-id="7a1aa-134">Code</span></span>

<span data-ttu-id="7a1aa-135">Nel codice seguente viene illustrato come creare un endpoint utilizzando la protezione del trasporto:</span><span class="sxs-lookup"><span data-stu-id="7a1aa-135">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="7a1aa-136">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7a1aa-136">Configuration</span></span>

<span data-ttu-id="7a1aa-137">Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-137">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="7a1aa-138">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-138">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="7a1aa-139">Client</span><span class="sxs-lookup"><span data-stu-id="7a1aa-139">Client</span></span>

<span data-ttu-id="7a1aa-140">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-140">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7a1aa-141">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a1aa-141">Do one of the following:</span></span>

- <span data-ttu-id="7a1aa-142">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="7a1aa-142">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="7a1aa-143">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-143">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="7a1aa-144">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-144">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="7a1aa-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7a1aa-145">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="7a1aa-146">Codice</span><span class="sxs-lookup"><span data-stu-id="7a1aa-146">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="7a1aa-147">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7a1aa-147">Configuration</span></span>

<span data-ttu-id="7a1aa-148">Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="7a1aa-148">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7a1aa-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a1aa-149">See also</span></span>

- [<span data-ttu-id="7a1aa-150">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7a1aa-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="7a1aa-151">Sicurezza del trasporto WS</span><span class="sxs-lookup"><span data-stu-id="7a1aa-151">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="7a1aa-152">Panoramica sulla sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="7a1aa-152">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="7a1aa-153">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7a1aa-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
