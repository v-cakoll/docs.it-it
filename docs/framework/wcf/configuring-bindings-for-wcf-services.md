---
title: Configurazione di associazioni per i servizi Windows Communication Foundation
description: Informazioni sulla configurazione delle associazioni in fase di distribuzione per un'applicazione WCF modificando gli elementi nel sistema. Elemento ServiceModel.
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: a2bb396e65722726e54cd315e931eea933386659
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247628"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="48dfe-103">Configurazione di associazioni per i servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="48dfe-103">Configuring Bindings for Windows Communication Foundation Services</span></span>
<span data-ttu-id="48dfe-104">Durante la creazione di un'applicazione, è spesso necessario assegnare all'amministratore il compito di prendere alcune decisioni dopo la distribuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-104">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="48dfe-105">Non è in alcun modo possibile, ad esempio, conoscere in anticipo l'indirizzo di un servizio, o URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="48dfe-105">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="48dfe-106">Anziché inserire un indirizzo nel codice, è preferibile consentire che questa operazione venga eseguita da un amministratore dopo la creazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-106">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="48dfe-107">Questa flessibilità viene realizzata attraverso la configurazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-107">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48dfe-108">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) con l' `/config` opzione per creare rapidamente file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="48dfe-109">Sezioni principali</span><span class="sxs-lookup"><span data-stu-id="48dfe-109">Major Sections</span></span>  
 <span data-ttu-id="48dfe-110">Lo schema di configurazione Windows Communication Foundation (WCF) include le tre sezioni principali seguenti ( `serviceModel` , `bindings` e `services` ):</span><span class="sxs-lookup"><span data-stu-id="48dfe-110">The Windows Communication Foundation (WCF) configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a><span data-ttu-id="48dfe-111">Elementi ServiceModel</span><span class="sxs-lookup"><span data-stu-id="48dfe-111">ServiceModel Elements</span></span>  
 <span data-ttu-id="48dfe-112">È possibile utilizzare la sezione delimitata dall' `system.ServiceModel` elemento per configurare un tipo di servizio con uno o più endpoint, nonché le impostazioni per un servizio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-112">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="48dfe-113">Ogni endpoint può essere quindi configurato con un indirizzo, un contratto e un'associazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-113">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> <span data-ttu-id="48dfe-114">Per ulteriori informazioni sugli endpoint, vedere [Cenni preliminari sulla creazione di endpoint](endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dfe-114">For more information about endpoints, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="48dfe-115">Se non è specificato alcun endpoint, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="48dfe-115">If no endpoints are specified, the runtime adds default endpoints.</span></span> <span data-ttu-id="48dfe-116">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="48dfe-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="48dfe-117">Un'associazione specifica trasporti (HTTP, TCP, pipe, Accodamento messaggi) e protocolli (sicurezza, affidabilità, flussi delle transazioni) e consiste in elementi, ognuno dei quali specifica un aspetto del modo in cui un endpoint comunica con l'esterno.</span><span class="sxs-lookup"><span data-stu-id="48dfe-117">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="48dfe-118">Se ad esempio si specifica l'elemento, viene [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) indicato di utilizzare http come trasporto per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="48dfe-118">For example, specifying the [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="48dfe-119">Ciò consente di associare l'endpoint in fase di esecuzione quando il servizio che utilizza l'endpoint è aperto.</span><span class="sxs-lookup"><span data-stu-id="48dfe-119">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="48dfe-120">Le associazioni sono di due tipi: predefinite e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="48dfe-120">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="48dfe-121">Le associazioni predefinite contengono combinazioni utili di elementi utilizzati in scenari comuni.</span><span class="sxs-lookup"><span data-stu-id="48dfe-121">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="48dfe-122">Per un elenco di tipi di binding predefiniti forniti da WCF, vedere [associazioni fornite dal sistema](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="48dfe-122">For a list of predefined binding types that WCF provides, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="48dfe-123">Se nessuna raccolta di associazioni predefinite presenta la combinazione corretta delle funzionalità necessarie per un'applicazione di servizio, è possibile costruire associazioni personalizzate che soddisfino i requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-123">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> <span data-ttu-id="48dfe-124">Per ulteriori informazioni sulle associazioni personalizzate, vedere [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="48dfe-124">For more information about custom bindings, see [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="48dfe-125">Nei quattro esempi seguenti vengono illustrate le configurazioni di binding più comuni utilizzate per la configurazione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="48dfe-125">The following four examples illustrate the most common binding configurations used for setting up a WCF service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="48dfe-126">Specificare un tipo di associazione per un endpoint</span><span class="sxs-lookup"><span data-stu-id="48dfe-126">Specifying an Endpoint to Use a Binding Type</span></span>  
 <span data-ttu-id="48dfe-127">Nel primo esempio viene illustrato come specificare un endpoint configurato con un indirizzo, un contratto e un'associazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-127">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 <span data-ttu-id="48dfe-128">In questo esempio l'attributo `name` indica il tipo di servizio per il quale è destinata la configurazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-128">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="48dfe-129">Quando si crea un servizio nel codice con il contratto `HelloWorld`, viene inizializzato con tutti gli endpoint definiti nella configurazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-129">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="48dfe-130">Se l'assembly implementa solo un contratto di servizio, l' `name` attributo può essere omesso perché il servizio utilizza l'unico tipo disponibile.</span><span class="sxs-lookup"><span data-stu-id="48dfe-130">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="48dfe-131">L'attributo accetta una stringa che deve presentarsi nel formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="48dfe-131">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="48dfe-132">L'attributo `address` specifica l'URI utilizzato dagli altri endpoint per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-132">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="48dfe-133">L'URI può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="48dfe-133">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="48dfe-134">Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto utilizzato nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="48dfe-134">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="48dfe-135">Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="48dfe-135">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="48dfe-136">L'attributo `contract` specifica il contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="48dfe-136">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="48dfe-137">Il tipo di implementazione del servizio deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="48dfe-137">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="48dfe-138">Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="48dfe-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="48dfe-139">L'attributo `binding` seleziona un'associazione predefinita o personalizzata da utilizzare per lo specifico endpoint.</span><span class="sxs-lookup"><span data-stu-id="48dfe-139">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="48dfe-140">Un endpoint che non seleziona in modo esplicito un'associazione utilizza l'associazione predefinita, ovvero `BasicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="48dfe-140">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="48dfe-141">Modifica di un'associazione predefinita</span><span class="sxs-lookup"><span data-stu-id="48dfe-141">Modifying a Predefined Binding</span></span>  
 <span data-ttu-id="48dfe-142">Nell'esempio seguente un'associazione predefinita viene modificata.</span><span class="sxs-lookup"><span data-stu-id="48dfe-142">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="48dfe-143">Può quindi essere utilizzata per configurare qualsiasi endpoint nel servizio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-143">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="48dfe-144">L'associazione viene modificata impostando il valore della proprietà <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> su 1 secondo.</span><span class="sxs-lookup"><span data-stu-id="48dfe-144">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="48dfe-145">Si noti che la proprietà restituisce un oggetto <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="48dfe-145">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="48dfe-146">L'associazione alterata si trova nella sezione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="48dfe-146">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="48dfe-147">L'associazione alterata può a questo punto essere utilizzata durante la creazione di qualsiasi endpoint impostando l'attributo `binding` nell'elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="48dfe-147">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48dfe-148">Se si assegna un determinato nome all'associazione, `bindingConfiguration` specificato nell'endpoint del servizio deve corrispondere ad esso.</span><span class="sxs-lookup"><span data-stu-id="48dfe-148">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="48dfe-149">Configurare un comportamento da applicare a un servizio</span><span class="sxs-lookup"><span data-stu-id="48dfe-149">Configuring a Behavior to Apply to a Service</span></span>  
 <span data-ttu-id="48dfe-150">Nell'esempio seguente viene configurato un comportamento specifico per il tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="48dfe-150">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="48dfe-151">L' `ServiceMetadataBehavior` elemento viene utilizzato per abilitare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per eseguire una query sul servizio e generare documenti Web Services Description Language (WSDL) dai metadati.</span><span class="sxs-lookup"><span data-stu-id="48dfe-151">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48dfe-152">Se si assegna un determinato nome al comportamento, `behaviorConfiguration` specificato nella sezione del servizio o dell'endpoint deve corrispondere ad esso.</span><span class="sxs-lookup"><span data-stu-id="48dfe-152">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />
    </behavior>  
</behaviors>  
<services>  
    <service
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 <span data-ttu-id="48dfe-153">La configurazione precedente consente a un client di chiamare e di ottenere i metadati del servizio "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="48dfe-153">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="48dfe-154">Specificare un servizio con due endpoint che utilizzano valori di associazione diversi</span><span class="sxs-lookup"><span data-stu-id="48dfe-154">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  
 <span data-ttu-id="48dfe-155">Nell'ultimo esempio sono configurati due endpoint per il tipo di servizio `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="48dfe-155">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="48dfe-156">Ogni endpoint usa un attributo personalizzato diverso `bindingConfiguration` dello stesso tipo di binding (ogni modifica di `basicHttpBinding` ).</span><span class="sxs-lookup"><span data-stu-id="48dfe-156">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="48dfe-157">È possibile ottenere lo stesso comportamento utilizzando la configurazione predefinita mediante l'aggiunta di una sezione `protocolMapping` e la configurazione delle associazioni, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="48dfe-157">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48dfe-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48dfe-158">See also</span></span>

- [<span data-ttu-id="48dfe-159">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="48dfe-159">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="48dfe-160">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="48dfe-160">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [<span data-ttu-id="48dfe-161">Cenni preliminari sulla creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="48dfe-161">Endpoint Creation Overview</span></span>](endpoint-creation-overview.md)
- [<span data-ttu-id="48dfe-162">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="48dfe-162">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
