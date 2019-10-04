---
title: 'Procedura: Proteggere endpoint di metadati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: ee64e53f49e15059c91982f2e64879b9f4c76d78
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834683"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="343c4-102">Procedura: Proteggere endpoint di metadati</span><span class="sxs-lookup"><span data-stu-id="343c4-102">How to: Secure Metadata Endpoints</span></span>

<span data-ttu-id="343c4-103">È possibile che i metadati di un servizio contengano informazioni riservate sull'applicazione che un utente malintenzionato potrebbe sfruttare.</span><span class="sxs-lookup"><span data-stu-id="343c4-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="343c4-104">Gli utenti del servizio, inoltre, potrebbero richiedere un meccanismo protetto per ottenere metadati sul servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="343c4-105">È talvolta necessario, quindi, pubblicare i metadati utilizzando un endpoint protetto.</span><span class="sxs-lookup"><span data-stu-id="343c4-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>

<span data-ttu-id="343c4-106">Gli endpoint dei metadati sono generalmente protetti utilizzando i meccanismi di sicurezza standard definiti in Windows Communication Foundation (WCF) per la protezione degli endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="343c4-106">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="343c4-107">Per altre informazioni, vedere [Panoramica della sicurezza](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="343c4-107">For more information, see [Security Overview](security-overview.md).</span></span>

<span data-ttu-id="343c4-108">In questo argomento vengono esaminati i passaggi che consentono di creare un endpoint protetto mediante un certificato SSL (Secure Sockets Layer) o, in altri termini, un endpoint HTTPS.</span><span class="sxs-lookup"><span data-stu-id="343c4-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="343c4-109">Per creare un endpoint di metadati HTTPS GET protetto nel codice</span><span class="sxs-lookup"><span data-stu-id="343c4-109">To create a secure HTTPS GET metadata endpoint in code</span></span>

1. <span data-ttu-id="343c4-110">Configurare una porta con un certificato X.509 appropriato.</span><span class="sxs-lookup"><span data-stu-id="343c4-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="343c4-111">Il certificato deve provenire da un'autorità attendibile e deve presentare l'utilizzo previsto "autorizzazione del servizio".</span><span class="sxs-lookup"><span data-stu-id="343c4-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="343c4-112">È necessario utilizzare lo strumento HttpCfg.exe per allegare il certificato alla porta.</span><span class="sxs-lookup"><span data-stu-id="343c4-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="343c4-113">Vedere [How to: Configurare una porta con un certificato SSL @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="343c4-113">See [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="343c4-114">Il soggetto del certificato o il DNS (Domain Name System) deve corrispondere al nome del computer.</span><span class="sxs-lookup"><span data-stu-id="343c4-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="343c4-115">È fondamentale perché uno dei primi passaggi eseguiti dal meccanismo HTTPS consiste nel verificare che il certificato sia emesso allo stesso URI (Uniform Resource Identifier) dell'indirizzo dal quale è richiamato.</span><span class="sxs-lookup"><span data-stu-id="343c4-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>

2. <span data-ttu-id="343c4-116">Creare una nuova istanza della classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="343c4-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>

3. <span data-ttu-id="343c4-117">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> della classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> su `true`.</span><span class="sxs-lookup"><span data-stu-id="343c4-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>

4. <span data-ttu-id="343c4-118">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> su un URL appropriato.</span><span class="sxs-lookup"><span data-stu-id="343c4-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="343c4-119">Se si specifica un indirizzo assoluto, l'URL deve iniziare con lo schema "https://".</span><span class="sxs-lookup"><span data-stu-id="343c4-119">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="343c4-120">Se si specifica un indirizzo relativo, è necessario fornire un indirizzo di base HTTPS per l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="343c4-121">Se questa proprietà non è impostata, l'indirizzo predefinito è "" o direttamente l'indirizzo di base HTTPS per il servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

5. <span data-ttu-id="343c4-122">Aggiungere l'istanza alla raccolta di comportamenti restituito dalla proprietà <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> della classe <xref:System.ServiceModel.Description.ServiceDescription>, come indicato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="343c4-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="343c4-123">Per creare un endpoint di metadati HTTPS GET protetto nella configurazione</span><span class="sxs-lookup"><span data-stu-id="343c4-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>

1. <span data-ttu-id="343c4-124">Aggiungere un elemento [> \<behaviors](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) all'elemento [\<system. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) del file di configurazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-124">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>

2. <span data-ttu-id="343c4-125">Aggiungere un elemento [> \<serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento [\<behaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="343c4-125">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

3. <span data-ttu-id="343c4-126">Aggiungere un elemento [> \<behavior](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) all'elemento `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="343c4-126">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>

4. <span data-ttu-id="343c4-127">Impostare l'attributo `name` dell'elemento `<behavior>` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="343c4-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="343c4-128">L'attributo `name` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="343c4-128">The `name` attribute is required.</span></span> <span data-ttu-id="343c4-129">Nell'esempio seguente viene utilizzato il valore `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="343c4-129">The example below uses the value `mySvcBehavior`.</span></span>

5. <span data-ttu-id="343c4-130">Aggiungere un [> \<serviceMetadata](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) all'elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="343c4-130">Add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>

6. <span data-ttu-id="343c4-131">Impostare l'attributo `httpsGetEnabled` dell'elemento `<serviceMetadata>` su `true`.</span><span class="sxs-lookup"><span data-stu-id="343c4-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>

7. <span data-ttu-id="343c4-132">Impostare l'attributo `httpsGetUrl` dell'elemento `<serviceMetadata>` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="343c4-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="343c4-133">Se si specifica un indirizzo assoluto, l'URL deve iniziare con lo schema "https://".</span><span class="sxs-lookup"><span data-stu-id="343c4-133">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="343c4-134">Se si specifica un indirizzo relativo, è necessario fornire un indirizzo di base HTTPS per l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="343c4-135">Se questa proprietà non è impostata, l'indirizzo predefinito è "" o direttamente l'indirizzo di base HTTPS per il servizio.</span><span class="sxs-lookup"><span data-stu-id="343c4-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

8. <span data-ttu-id="343c4-136">Per utilizzare il comportamento con un servizio, impostare l'attributo `behaviorConfiguration` dell'elemento [> \<Service](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) sul valore dell'attributo Name dell'elemento Behavior.</span><span class="sxs-lookup"><span data-stu-id="343c4-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="343c4-137">Nella configurazione seguente viene illustrato un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="343c4-137">The following configuration code shows a complete example.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a><span data-ttu-id="343c4-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="343c4-138">Example</span></span>

<span data-ttu-id="343c4-139">Nell'esempio seguente viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> e viene aggiunto un endpoint.</span><span class="sxs-lookup"><span data-stu-id="343c4-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="343c4-140">Il codice crea quindi un'istanza della classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> e imposta le proprietà per creare un punto dello scambio di metadati protetto.</span><span class="sxs-lookup"><span data-stu-id="343c4-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="343c4-141">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="343c4-141">Compiling the Code</span></span>

<span data-ttu-id="343c4-142">Nel codice di esempio vengono utilizzati gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="343c4-142">The code example uses the following namespaces:</span></span>

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="343c4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="343c4-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- <span data-ttu-id="343c4-144">[Procedura: Configurare una porta con un certificato SSL @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="343c4-144">[How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)</span></span>
- [<span data-ttu-id="343c4-145">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="343c4-145">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="343c4-146">Considerazioni sulla sicurezza con i metadati</span><span class="sxs-lookup"><span data-stu-id="343c4-146">Security Considerations with Metadata</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
- [<span data-ttu-id="343c4-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="343c4-147">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
