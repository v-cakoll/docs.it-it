---
title: <endpoint> elemento
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 667086cda010daf51cb92116d636b9b526b4b34b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163410"
---
# <a name="endpoint-element"></a><span data-ttu-id="e3c84-102">\<endpoint > elemento</span><span class="sxs-lookup"><span data-stu-id="e3c84-102">\<endpoint> element</span></span>
<span data-ttu-id="e3c84-103">Specifica le proprietà di associazione, contratto e indirizzo di endpoint del servizio usato per esporre servizi.</span><span class="sxs-lookup"><span data-stu-id="e3c84-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="e3c84-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3c84-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3c84-105">\<service></span><span class="sxs-lookup"><span data-stu-id="e3c84-105">\<service></span></span>  
<span data-ttu-id="e3c84-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e3c84-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c84-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3c84-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3c84-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3c84-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3c84-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3c84-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3c84-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3c84-110">Attributes</span></span>  
  
|<span data-ttu-id="e3c84-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e3c84-111">Attribute</span></span>|<span data-ttu-id="e3c84-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3c84-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3c84-113">indirizzo</span><span class="sxs-lookup"><span data-stu-id="e3c84-113">address</span></span>|<span data-ttu-id="e3c84-114">Stringa che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3c84-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="e3c84-115">L'indirizzo può essere specificato come indirizzo assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="e3c84-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="e3c84-116">Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto usato nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="e3c84-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="e3c84-117">Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3c84-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="e3c84-118">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3c84-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c84-119">behaviorConfiguration</span></span>|<span data-ttu-id="e3c84-120">Stringa che contiene il nome del comportamento da usare nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3c84-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="e3c84-121">binding</span><span class="sxs-lookup"><span data-stu-id="e3c84-121">binding</span></span>|<span data-ttu-id="e3c84-122">Attributo stringa obbligatorio che specifica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e3c84-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="e3c84-123">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="e3c84-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="e3c84-124">Il tipo viene registrato dal nome di sezione, anziché dal nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="e3c84-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="e3c84-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c84-125">bindingConfiguration</span></span>|<span data-ttu-id="e3c84-126">Stringa che specifica il nome dell'associazione da usare quando viene creata l'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3c84-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="e3c84-127">Il nome dell'associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="e3c84-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="e3c84-128">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e3c84-129">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3c84-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="e3c84-130">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e3c84-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="e3c84-131">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e3c84-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="e3c84-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="e3c84-132">bindingName</span></span>|<span data-ttu-id="e3c84-133">Stringa che specifica il nome completo e univoco dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="e3c84-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="e3c84-134">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3c84-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="e3c84-135">bindingNamespace</span></span>|<span data-ttu-id="e3c84-136">Stringa che specifica il nome completo e univoco dello spazio dei nomi dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="e3c84-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="e3c84-137">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3c84-138">contratto</span><span class="sxs-lookup"><span data-stu-id="e3c84-138">contract</span></span>|<span data-ttu-id="e3c84-139">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3c84-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="e3c84-140">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="e3c84-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="e3c84-141">Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="e3c84-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="e3c84-142">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3c84-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c84-143">endpointConfiguration</span></span>|<span data-ttu-id="e3c84-144">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="e3c84-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="e3c84-145">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="e3c84-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="e3c84-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="e3c84-146">isSystemEndpoint</span></span>|<span data-ttu-id="e3c84-147">Valore booleano che specifica se un endpoint è un endpoint di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="e3c84-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="e3c84-148">kind</span><span class="sxs-lookup"><span data-stu-id="e3c84-148">kind</span></span>|<span data-ttu-id="e3c84-149">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="e3c84-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="e3c84-150">Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del servizio comune.</span><span class="sxs-lookup"><span data-stu-id="e3c84-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="e3c84-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="e3c84-151">listenUriMode</span></span>|<span data-ttu-id="e3c84-152">Specifica il modo in cui il trasporto considera l'elemento `ListenUri` fornito sul quale è in ascolto il servizio.</span><span class="sxs-lookup"><span data-stu-id="e3c84-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="e3c84-153">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="e3c84-153">Valid values are</span></span><br /><br /> <span data-ttu-id="e3c84-154">-   Explicit</span><span class="sxs-lookup"><span data-stu-id="e3c84-154">-   Explicit</span></span><br /><span data-ttu-id="e3c84-155">-Univoco</span><span class="sxs-lookup"><span data-stu-id="e3c84-155">-   Unique</span></span><br /><br /> <span data-ttu-id="e3c84-156">Il valore predefinito è Explicit.</span><span class="sxs-lookup"><span data-stu-id="e3c84-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="e3c84-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="e3c84-157">listenUri</span></span>|<span data-ttu-id="e3c84-158">Stringa che specifica l'URI sul quale è in ascolto l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3c84-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="e3c84-159">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3c84-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3c84-160">name</span><span class="sxs-lookup"><span data-stu-id="e3c84-160">name</span></span>|<span data-ttu-id="e3c84-161">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e3c84-161">Optional attribute.</span></span> <span data-ttu-id="e3c84-162">Stringa che specifica il nome dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3c84-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="e3c84-163">Il valore predefinito è costituito dalla concatenazione del nome dell'associazione e del nome della descrizione del contratto.</span><span class="sxs-lookup"><span data-stu-id="e3c84-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="e3c84-164">È possibile che i servizi siano dotati di più endpoint, quindi l'attributo `name` dell'endpoint si differenzia dal nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3c84-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3c84-165">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3c84-165">Child Elements</span></span>  
  
|<span data-ttu-id="e3c84-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3c84-166">Element</span></span>|<span data-ttu-id="e3c84-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3c84-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3c84-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="e3c84-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="e3c84-169">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e3c84-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="e3c84-170">\<identity></span><span class="sxs-lookup"><span data-stu-id="e3c84-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e3c84-171">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="e3c84-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3c84-172">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3c84-172">Parent Elements</span></span>  
  
|<span data-ttu-id="e3c84-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3c84-173">Element</span></span>|<span data-ttu-id="e3c84-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3c84-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3c84-175">\<service></span><span class="sxs-lookup"><span data-stu-id="e3c84-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="e3c84-176">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="e3c84-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3c84-177">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3c84-177">Example</span></span>  
 <span data-ttu-id="e3c84-178">Di seguito è riportato un esempio di configurazione dell'endpoint di un servizio.</span><span class="sxs-lookup"><span data-stu-id="e3c84-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="e3c84-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3c84-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="e3c84-180">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="e3c84-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="e3c84-181">Procedura: Creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="e3c84-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
