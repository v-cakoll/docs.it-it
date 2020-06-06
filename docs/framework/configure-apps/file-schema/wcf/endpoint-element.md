---
title: Elemento <endpoint>
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855387"
---
# <a name="endpoint-element"></a><span data-ttu-id="a23dd-102">Elemento \<endpoint></span><span class="sxs-lookup"><span data-stu-id="a23dd-102">\<endpoint> element</span></span>
<span data-ttu-id="a23dd-103">Specifica le proprietà di associazione, contratto e indirizzo di endpoint del servizio usato per esporre servizi.</span><span class="sxs-lookup"><span data-stu-id="a23dd-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="a23dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a23dd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a23dd-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a23dd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a23dd-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a23dd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a23dd-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a23dd-107">Attributes</span></span>  
  
|<span data-ttu-id="a23dd-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="a23dd-108">Attribute</span></span>|<span data-ttu-id="a23dd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a23dd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a23dd-110">address</span><span class="sxs-lookup"><span data-stu-id="a23dd-110">address</span></span>|<span data-ttu-id="a23dd-111">Stringa che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23dd-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="a23dd-112">L'indirizzo può essere specificato come indirizzo assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="a23dd-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="a23dd-113">Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto usato nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="a23dd-114">Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23dd-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="a23dd-115">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="a23dd-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a23dd-116">behaviorConfiguration</span></span>|<span data-ttu-id="a23dd-117">Stringa che contiene il nome del comportamento da usare nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23dd-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="a23dd-118">binding</span><span class="sxs-lookup"><span data-stu-id="a23dd-118">binding</span></span>|<span data-ttu-id="a23dd-119">Attributo stringa obbligatorio che specifica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a23dd-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="a23dd-120">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="a23dd-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="a23dd-121">Il tipo viene registrato dal nome di sezione, anziché dal nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="a23dd-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a23dd-122">bindingConfiguration</span></span>|<span data-ttu-id="a23dd-123">Stringa che specifica il nome dell'associazione da usare quando viene creata l'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23dd-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="a23dd-124">Il nome dell'associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="a23dd-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="a23dd-125">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="a23dd-126">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="a23dd-127">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a23dd-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="a23dd-128">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="a23dd-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="a23dd-129">bindingName</span></span>|<span data-ttu-id="a23dd-130">Stringa che specifica il nome completo e univoco dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="a23dd-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="a23dd-131">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="a23dd-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="a23dd-132">bindingNamespace</span></span>|<span data-ttu-id="a23dd-133">Stringa che specifica il nome completo e univoco dello spazio dei nomi dell'associazione per l'esportazione delle definizioni tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="a23dd-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="a23dd-134">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="a23dd-135">contract</span><span class="sxs-lookup"><span data-stu-id="a23dd-135">contract</span></span>|<span data-ttu-id="a23dd-136">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23dd-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="a23dd-137">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="a23dd-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="a23dd-138">Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="a23dd-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="a23dd-139">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="a23dd-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="a23dd-140">endpointConfiguration</span></span>|<span data-ttu-id="a23dd-141">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="a23dd-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="a23dd-142">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="a23dd-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="a23dd-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="a23dd-143">isSystemEndpoint</span></span>|<span data-ttu-id="a23dd-144">Valore booleano che specifica se un endpoint è un endpoint di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="a23dd-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="a23dd-145">kind</span><span class="sxs-lookup"><span data-stu-id="a23dd-145">kind</span></span>|<span data-ttu-id="a23dd-146">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="a23dd-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="a23dd-147">Il tipo deve essere registrato nella `<extensions>` sezione o in Machine. config. Se non viene specificato alcun valore, viene creato un endpoint del servizio comune.</span><span class="sxs-lookup"><span data-stu-id="a23dd-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="a23dd-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="a23dd-148">listenUriMode</span></span>|<span data-ttu-id="a23dd-149">Specifica il modo in cui il trasporto considera l'elemento `ListenUri` fornito sul quale è in ascolto il servizio.</span><span class="sxs-lookup"><span data-stu-id="a23dd-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="a23dd-150">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="a23dd-150">Valid values are</span></span><br /><br /> <span data-ttu-id="a23dd-151">-Esplicito</span><span class="sxs-lookup"><span data-stu-id="a23dd-151">-   Explicit</span></span><br /><span data-ttu-id="a23dd-152">-Univoco</span><span class="sxs-lookup"><span data-stu-id="a23dd-152">-   Unique</span></span><br /><br /> <span data-ttu-id="a23dd-153">Il valore predefinito è Explicit.</span><span class="sxs-lookup"><span data-stu-id="a23dd-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="a23dd-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="a23dd-154">listenUri</span></span>|<span data-ttu-id="a23dd-155">Stringa che specifica l'URI sul quale è in ascolto l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="a23dd-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="a23dd-156">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a23dd-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="a23dd-157">name</span><span class="sxs-lookup"><span data-stu-id="a23dd-157">name</span></span>|<span data-ttu-id="a23dd-158">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a23dd-158">Optional attribute.</span></span> <span data-ttu-id="a23dd-159">Stringa che specifica il nome dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="a23dd-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="a23dd-160">Il valore predefinito è costituito dalla concatenazione del nome dell'associazione e del nome della descrizione del contratto.</span><span class="sxs-lookup"><span data-stu-id="a23dd-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="a23dd-161">È possibile che i servizi siano dotati di più endpoint, quindi l'attributo `name` dell'endpoint si differenzia dal nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="a23dd-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a23dd-162">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a23dd-162">Child Elements</span></span>  
  
|<span data-ttu-id="a23dd-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="a23dd-163">Element</span></span>|<span data-ttu-id="a23dd-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a23dd-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="a23dd-165">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a23dd-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="a23dd-166">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="a23dd-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a23dd-167">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a23dd-167">Parent Elements</span></span>  
  
|<span data-ttu-id="a23dd-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="a23dd-168">Element</span></span>|<span data-ttu-id="a23dd-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a23dd-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="a23dd-170">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="a23dd-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a23dd-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="a23dd-171">Example</span></span>  
 <span data-ttu-id="a23dd-172">Di seguito è riportato un esempio di configurazione dell'endpoint di un servizio.</span><span class="sxs-lookup"><span data-stu-id="a23dd-172">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a23dd-173">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a23dd-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="a23dd-174">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="a23dd-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="a23dd-175">Procedura: creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="a23dd-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
