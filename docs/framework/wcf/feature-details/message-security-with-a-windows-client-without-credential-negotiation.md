---
title: Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: d3b05a1786131a119d516edeba0d6e8e24289f87
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212034"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="96b63-102">Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="96b63-102">Message Security with a Windows Client without Credential Negotiation</span></span>

<span data-ttu-id="96b63-103">Nello scenario seguente vengono illustrati un client e un servizio Windows Communication Foundation (WCF) protetti dal protocollo Kerberos.</span><span class="sxs-lookup"><span data-stu-id="96b63-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>

<span data-ttu-id="96b63-104">Il servizio e il client sono nello stesso dominio o sono entrambi in domini attendibili.</span><span class="sxs-lookup"><span data-stu-id="96b63-104">Both the service and the client are in the same domain or trusted domains.</span></span>

> [!NOTE]
> <span data-ttu-id="96b63-105">La differenza tra questo scenario e la [sicurezza dei messaggi con un client Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) è che questo scenario non negozia le credenziali del servizio con il servizio prima di inviare il messaggio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96b63-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="96b63-106">Inoltre, poiché ciò richiede il protocollo Kerberos, questo scenario richiede un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="96b63-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>

<span data-ttu-id="96b63-107">![Sicurezza del messaggio senza negoziazione delle credenziali](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="96b63-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>

|<span data-ttu-id="96b63-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="96b63-108">Characteristic</span></span>|<span data-ttu-id="96b63-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96b63-109">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="96b63-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="96b63-110">Security Mode</span></span>|<span data-ttu-id="96b63-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="96b63-111">Message</span></span>|
|<span data-ttu-id="96b63-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="96b63-112">Interoperability</span></span>|<span data-ttu-id="96b63-113">Sì, WS-Security con client compatibili con il profilo del token Kerberos</span><span class="sxs-lookup"><span data-stu-id="96b63-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|
|<span data-ttu-id="96b63-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="96b63-114">Authentication (Server)</span></span>|<span data-ttu-id="96b63-115">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="96b63-115">Mutual authentication of the server and client</span></span>|
|<span data-ttu-id="96b63-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="96b63-116">Authentication (Client)</span></span>|<span data-ttu-id="96b63-117">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="96b63-117">Mutual authentication of the server and client</span></span>|
|<span data-ttu-id="96b63-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="96b63-118">Integrity</span></span>|<span data-ttu-id="96b63-119">Sì</span><span class="sxs-lookup"><span data-stu-id="96b63-119">Yes</span></span>|
|<span data-ttu-id="96b63-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="96b63-120">Confidentiality</span></span>|<span data-ttu-id="96b63-121">Sì</span><span class="sxs-lookup"><span data-stu-id="96b63-121">Yes</span></span>|
|<span data-ttu-id="96b63-122">Transport</span><span class="sxs-lookup"><span data-stu-id="96b63-122">Transport</span></span>|<span data-ttu-id="96b63-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="96b63-123">HTTP</span></span>|
|<span data-ttu-id="96b63-124">Associazione</span><span class="sxs-lookup"><span data-stu-id="96b63-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="96b63-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="96b63-125">Service</span></span>

<span data-ttu-id="96b63-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="96b63-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="96b63-127">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="96b63-127">Do one of the following:</span></span>

- <span data-ttu-id="96b63-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="96b63-128">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="96b63-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="96b63-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="96b63-130">Codice</span><span class="sxs-lookup"><span data-stu-id="96b63-130">Code</span></span>

<span data-ttu-id="96b63-131">Il codice seguente crea un endpoint del servizio che usa la sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="96b63-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="96b63-132">Il codice disabilita la negoziazione della credenziale del servizio e la definizione di un token del contesto di sicurezza (SCT, Security Context Token).</span><span class="sxs-lookup"><span data-stu-id="96b63-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>

> [!NOTE]
> <span data-ttu-id="96b63-133">Per usare il tipo di credenziale di Windows senza negoziazione, l'account utente del servizio deve avere accesso al nome dell'entità servizio (SPN, Service Principal Name) registrato con il dominio di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96b63-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="96b63-134">Tale operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="96b63-134">You can do this in two ways:</span></span>

1. <span data-ttu-id="96b63-135">Usare l'account `NetworkService` o `LocalSystem` per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="96b63-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="96b63-136">Poiché questi account hanno accesso al nome SPN del computer stabilito quando il computer viene aggiunto al dominio Active Directory, WCF genera automaticamente l'elemento SPN appropriato all'interno dell'endpoint del servizio nei metadati del servizio (descrizione dei servizi Web Lingua o WSDL.</span><span class="sxs-lookup"><span data-stu-id="96b63-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>

2. <span data-ttu-id="96b63-137">Usare un account di dominio Active Directory arbitrario per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="96b63-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="96b63-138">In questo caso è necessario definire un SPN per questo account di dominio.</span><span class="sxs-lookup"><span data-stu-id="96b63-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="96b63-139">A tale scopo è possibile usare l'utilità Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="96b63-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="96b63-140">Una volta creato il nome SPN per l'account del servizio, configurare WCF per la pubblicazione di tale SPN nei client del servizio tramite i relativi metadati (WSDL).</span><span class="sxs-lookup"><span data-stu-id="96b63-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="96b63-141">Questa operazione viene eseguita impostando l'identità per l'endpoint esposto o tramite un file di configurazione dell'applicazione o tramite codice.</span><span class="sxs-lookup"><span data-stu-id="96b63-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="96b63-142">Nell'esempio seguente l'identità viene pubblicata a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="96b63-142">The following example publishes the identity programmatically.</span></span>

<span data-ttu-id="96b63-143">Per ulteriori informazioni sui nomi SPN, sul protocollo Kerberos e Active Directory, vedere [supplemento tecnico Kerberos per Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="96b63-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span></span> <span data-ttu-id="96b63-144">Per altre informazioni sulle identità degli endpoint, vedere [modalità di autenticazione di SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="96b63-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>

[!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
[!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]

### <a name="configuration"></a><span data-ttu-id="96b63-145">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="96b63-145">Configuration</span></span>

<span data-ttu-id="96b63-146">Invece del codice, è possibile usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="96b63-146">The following configuration can be used instead of the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors />
    <services>
      <service behaviorConfiguration="" name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="KerberosBinding"
                  name="WSHttpBinding_ICalculator"
                  contract="ServiceModel.ICalculator"
                  listenUri="net.tcp://localhost/metadata" >
         <identity>
            <servicePrincipalName value="service_spn_name" />
         </identity>
        </endpoint>
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="KerberosBinding">
          <security>
            <message negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="96b63-147">Client</span><span class="sxs-lookup"><span data-stu-id="96b63-147">Client</span></span>

<span data-ttu-id="96b63-148">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="96b63-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="96b63-149">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="96b63-149">Do one of the following:</span></span>

- <span data-ttu-id="96b63-150">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="96b63-150">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="96b63-151">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="96b63-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="96b63-152">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="96b63-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="96b63-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96b63-153">For example:</span></span>

  [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
  [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="96b63-154">Codice</span><span class="sxs-lookup"><span data-stu-id="96b63-154">Code</span></span>

<span data-ttu-id="96b63-155">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="96b63-155">The following code configures the client.</span></span> <span data-ttu-id="96b63-156">La modalità di sicurezza è impostata su Messaggio e il tipo di credenziale client è impostato su Windows.</span><span class="sxs-lookup"><span data-stu-id="96b63-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="96b63-157">Le proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> e <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> sono impostate su `false`.</span><span class="sxs-lookup"><span data-stu-id="96b63-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="96b63-158">Per usare un tipo di credenziale di Windows senza negoziazione, il client deve essere configurato con il nome di entità servizio dell'account del servizio prima di iniziare la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="96b63-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="96b63-159">Il client usa il nome dell'entità servizio (SPN) per ottenere il token Kerberos per autenticare e proteggere la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="96b63-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="96b63-160">L'esempio seguente mostra come configurare il client con l'SPN del servizio.</span><span class="sxs-lookup"><span data-stu-id="96b63-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="96b63-161">Se si utilizza lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il client, l'SPN del servizio verrà propagato automaticamente al client dai metadati (WSDL) del servizio, se i metadati del servizio contengono tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="96b63-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="96b63-162">Per ulteriori informazioni su come configurare il servizio in modo da includere il relativo nome SPN nei metadati del servizio, vedere la sezione "servizio" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="96b63-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>
>
> <span data-ttu-id="96b63-163">Per ulteriori informazioni sui nomi SPN, Kerberos e Active Directory, vedere [supplemento tecnico Kerberos per Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="96b63-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span></span> <span data-ttu-id="96b63-164">Per ulteriori informazioni sulle identità degli endpoint, vedere [l'](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) argomento relativo alle modalità di autenticazione di SecurityBindingElement.</span><span class="sxs-lookup"><span data-stu-id="96b63-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>

[!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
[!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]

### <a name="configuration"></a><span data-ttu-id="96b63-165">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="96b63-165">Configuration</span></span>

<span data-ttu-id="96b63-166">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="96b63-166">The following code configures the client.</span></span> <span data-ttu-id="96b63-167">Si noti che è necessario impostare l'elemento [\<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) in modo che corrisponda al nome SPN del servizio come registrato per l'account del servizio nel dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96b63-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://localhost/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator">
        <identity>
          <servicePrincipalName value="service_spn_name" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="96b63-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b63-168">See also</span></span>

- [<span data-ttu-id="96b63-169">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="96b63-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="96b63-170">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="96b63-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- <span data-ttu-id="96b63-171">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="96b63-171">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
