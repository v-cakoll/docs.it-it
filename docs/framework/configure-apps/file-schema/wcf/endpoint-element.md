---
title: Elemento &lt;endpoint&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c466d7f7f00d7fd2358f0d5d71c0b705f316f66f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltendpointgt-element"></a><span data-ttu-id="06a03-102">Elemento &lt;endpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="06a03-102">&lt;endpoint&gt; element</span></span>
<span data-ttu-id="06a03-103">Specifica le proprietà di associazione, contratto e indirizzo di endpoint del servizio usato per esporre servizi.</span><span class="sxs-lookup"><span data-stu-id="06a03-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="06a03-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="06a03-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="06a03-105">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="06a03-105">\<service></span></span>  
<span data-ttu-id="06a03-106">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="06a03-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a03-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06a03-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration="String"   isSystemEndpoint="Boolean"   kind="String"   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06a03-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="06a03-108">Attributes and Elements</span></span>  
 <span data-ttu-id="06a03-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="06a03-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06a03-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="06a03-110">Attributes</span></span>  
  
|<span data-ttu-id="06a03-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="06a03-111">Attribute</span></span>|<span data-ttu-id="06a03-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06a03-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06a03-113">address</span><span class="sxs-lookup"><span data-stu-id="06a03-113">address</span></span>|<span data-ttu-id="06a03-114">Stringa che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a03-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="06a03-115">L'indirizzo può essere specificato come indirizzo assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="06a03-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="06a03-116">Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto usato nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="06a03-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="06a03-117">Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a03-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="06a03-118">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="06a03-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="06a03-119">behaviorConfiguration</span></span>|<span data-ttu-id="06a03-120">Stringa che contiene il nome del comportamento da usare nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a03-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="06a03-121">associazione</span><span class="sxs-lookup"><span data-stu-id="06a03-121">binding</span></span>|<span data-ttu-id="06a03-122">Attributo stringa obbligatorio che specifica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="06a03-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="06a03-123">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="06a03-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="06a03-124">Il tipo viene registrato dal nome di sezione, anziché dal nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="06a03-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="06a03-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="06a03-125">bindingConfiguration</span></span>|<span data-ttu-id="06a03-126">Stringa che specifica il nome dell'associazione da usare quando viene creata l'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a03-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="06a03-127">Il nome dell'associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="06a03-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="06a03-128">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="06a03-129">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="06a03-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="06a03-130">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="06a03-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="06a03-131">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="06a03-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="06a03-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="06a03-132">bindingName</span></span>|<span data-ttu-id="06a03-133">Stringa che specifica il nome completo e univoco dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="06a03-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="06a03-134">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="06a03-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="06a03-135">bindingNamespace</span></span>|<span data-ttu-id="06a03-136">Stringa che specifica il nome completo e univoco dello spazio dei nomi dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="06a03-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="06a03-137">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="06a03-138">contratto</span><span class="sxs-lookup"><span data-stu-id="06a03-138">contract</span></span>|<span data-ttu-id="06a03-139">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a03-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="06a03-140">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="06a03-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="06a03-141">Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="06a03-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="06a03-142">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="06a03-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="06a03-143">endpointConfiguration</span></span>|<span data-ttu-id="06a03-144">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="06a03-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="06a03-145">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="06a03-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="06a03-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="06a03-146">isSystemEndpoint</span></span>|<span data-ttu-id="06a03-147">Valore booleano che specifica se un endpoint è un endpoint di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="06a03-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="06a03-148">kind</span><span class="sxs-lookup"><span data-stu-id="06a03-148">kind</span></span>|<span data-ttu-id="06a03-149">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="06a03-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="06a03-150">Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del servizio comune.</span><span class="sxs-lookup"><span data-stu-id="06a03-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="06a03-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="06a03-151">listenUriMode</span></span>|<span data-ttu-id="06a03-152">Specifica il modo in cui il trasporto considera l'elemento `ListenUri` fornito sul quale è in ascolto il servizio.</span><span class="sxs-lookup"><span data-stu-id="06a03-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="06a03-153">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="06a03-153">Valid values are</span></span><br /><br /> <span data-ttu-id="06a03-154">-Esplicita</span><span class="sxs-lookup"><span data-stu-id="06a03-154">-   Explicit</span></span><br /><span data-ttu-id="06a03-155">-Univoco</span><span class="sxs-lookup"><span data-stu-id="06a03-155">-   Unique</span></span><br /><br /> <span data-ttu-id="06a03-156">Il valore predefinito è Explicit.</span><span class="sxs-lookup"><span data-stu-id="06a03-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="06a03-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="06a03-157">listenUri</span></span>|<span data-ttu-id="06a03-158">Stringa che specifica l'URI sul quale è in ascolto l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="06a03-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="06a03-159">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="06a03-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="06a03-160">name</span><span class="sxs-lookup"><span data-stu-id="06a03-160">name</span></span>|<span data-ttu-id="06a03-161">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="06a03-161">Optional attribute.</span></span> <span data-ttu-id="06a03-162">Stringa che specifica il nome dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="06a03-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="06a03-163">Il valore predefinito è costituito dalla concatenazione del nome dell'associazione e del nome della descrizione del contratto.</span><span class="sxs-lookup"><span data-stu-id="06a03-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="06a03-164">È possibile che i servizi siano dotati di più endpoint, quindi l'attributo `name` dell'endpoint si differenzia dal nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="06a03-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06a03-165">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="06a03-165">Child Elements</span></span>  
  
|<span data-ttu-id="06a03-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="06a03-166">Element</span></span>|<span data-ttu-id="06a03-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06a03-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06a03-168">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="06a03-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="06a03-169">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="06a03-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="06a03-170">\<identità ></span><span class="sxs-lookup"><span data-stu-id="06a03-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="06a03-171">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="06a03-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06a03-172">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="06a03-172">Parent Elements</span></span>  
  
|<span data-ttu-id="06a03-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="06a03-173">Element</span></span>|<span data-ttu-id="06a03-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06a03-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06a03-175">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="06a03-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="06a03-176">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="06a03-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="06a03-177">Esempio</span><span class="sxs-lookup"><span data-stu-id="06a03-177">Example</span></span>  
 <span data-ttu-id="06a03-178">Di seguito è riportato un esempio di configurazione dell'endpoint di un servizio.</span><span class="sxs-lookup"><span data-stu-id="06a03-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06a03-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a03-179">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [<span data-ttu-id="06a03-180">Endpoint: Indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="06a03-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="06a03-181">Procedura: creare un Endpoint del servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="06a03-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
