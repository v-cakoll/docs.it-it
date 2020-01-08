---
title: Sicurezza del trasporto con un client anonimo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: c3e44c87dfa70ac3a7acc5a83ac596efc22b6155
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344750"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="38d62-102">Sicurezza del trasporto con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="38d62-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="38d62-103">In questo scenario Windows Communication Foundation (WCF) viene utilizzata la sicurezza del trasporto (HTTPS) per garantire la riservatezza e l'integrità.</span><span class="sxs-lookup"><span data-stu-id="38d62-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="38d62-104">È necessario che il server sia autenticato con un certificato SSL (Secure Sockets Layer) e che il client ritenga attendibile il certificato del server.</span><span class="sxs-lookup"><span data-stu-id="38d62-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="38d62-105">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="38d62-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="38d62-106">Per un'applicazione di esempio, vedere la pagina relativa alla [sicurezza del trasporto WS](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="38d62-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="38d62-107">Per ulteriori informazioni sulla sicurezza del trasporto, vedere [Panoramica della sicurezza del trasporto](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="38d62-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="38d62-108">Per ulteriori informazioni sull'utilizzo di un certificato con un servizio, vedere [utilizzo dei certificati](working-with-certificates.md) e [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="38d62-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Utilizzo della sicurezza del trasporto con un client anonimo](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="38d62-110">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="38d62-110">Characteristic</span></span>|<span data-ttu-id="38d62-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38d62-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="38d62-112">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="38d62-112">Security Mode</span></span>|<span data-ttu-id="38d62-113">Transport</span><span class="sxs-lookup"><span data-stu-id="38d62-113">Transport</span></span>|
|<span data-ttu-id="38d62-114">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="38d62-114">Interoperability</span></span>|<span data-ttu-id="38d62-115">Con i servizi Web e i client esistenti</span><span class="sxs-lookup"><span data-stu-id="38d62-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="38d62-116">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="38d62-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="38d62-117">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="38d62-117">Authentication (Client)</span></span>|<span data-ttu-id="38d62-118">Sì</span><span class="sxs-lookup"><span data-stu-id="38d62-118">Yes</span></span><br /><br /> <span data-ttu-id="38d62-119">Livello applicazione (nessun supporto WCF)</span><span class="sxs-lookup"><span data-stu-id="38d62-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="38d62-120">Integrità</span><span class="sxs-lookup"><span data-stu-id="38d62-120">Integrity</span></span>|<span data-ttu-id="38d62-121">Sì</span><span class="sxs-lookup"><span data-stu-id="38d62-121">Yes</span></span>|
|<span data-ttu-id="38d62-122">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="38d62-122">Confidentiality</span></span>|<span data-ttu-id="38d62-123">Sì</span><span class="sxs-lookup"><span data-stu-id="38d62-123">Yes</span></span>|
|<span data-ttu-id="38d62-124">Transport</span><span class="sxs-lookup"><span data-stu-id="38d62-124">Transport</span></span>|<span data-ttu-id="38d62-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38d62-125">HTTPS</span></span>|
|<span data-ttu-id="38d62-126">Associazione</span><span class="sxs-lookup"><span data-stu-id="38d62-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="38d62-127">Servizio</span><span class="sxs-lookup"><span data-stu-id="38d62-127">Service</span></span>

<span data-ttu-id="38d62-128">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="38d62-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="38d62-129">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="38d62-129">Do one of the following:</span></span>

- <span data-ttu-id="38d62-130">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="38d62-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="38d62-131">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="38d62-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="38d62-132">Codice</span><span class="sxs-lookup"><span data-stu-id="38d62-132">Code</span></span>

<span data-ttu-id="38d62-133">Nel codice seguente viene illustrato come creare un endpoint utilizzando la protezione del trasporto:</span><span class="sxs-lookup"><span data-stu-id="38d62-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="38d62-134">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="38d62-134">Configuration</span></span>

<span data-ttu-id="38d62-135">Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="38d62-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="38d62-136">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="38d62-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="38d62-137">Client</span><span class="sxs-lookup"><span data-stu-id="38d62-137">Client</span></span>

<span data-ttu-id="38d62-138">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="38d62-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="38d62-139">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="38d62-139">Do one of the following:</span></span>

- <span data-ttu-id="38d62-140">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="38d62-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="38d62-141">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="38d62-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="38d62-142">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="38d62-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="38d62-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38d62-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="38d62-144">Codice</span><span class="sxs-lookup"><span data-stu-id="38d62-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="38d62-145">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="38d62-145">Configuration</span></span>

<span data-ttu-id="38d62-146">Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="38d62-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38d62-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d62-147">See also</span></span>

- [<span data-ttu-id="38d62-148">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="38d62-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="38d62-149">Sicurezza del trasporto WS</span><span class="sxs-lookup"><span data-stu-id="38d62-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="38d62-150">Panoramica della sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="38d62-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="38d62-151">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="38d62-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
