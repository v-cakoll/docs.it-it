---
title: <endpoint> di <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 2bf59972ff2f75995e94a3c1934e88944d65fcc7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919104"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="968c4-102">\<> endpoint di \<> client</span><span class="sxs-lookup"><span data-stu-id="968c4-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="968c4-103">Specifica proprietà di contratto, associazione e indirizzo dell'endpoint del canale usato dai client per connettersi agli endpoint del servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="968c4-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="968c4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="968c4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="968c4-105">\<client></span><span class="sxs-lookup"><span data-stu-id="968c4-105">\<client></span></span>  
<span data-ttu-id="968c4-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="968c4-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="968c4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="968c4-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="968c4-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="968c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="968c4-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="968c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="968c4-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="968c4-110">Attributes</span></span>  
  
|<span data-ttu-id="968c4-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="968c4-111">Attribute</span></span>|<span data-ttu-id="968c4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="968c4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="968c4-113">Address</span><span class="sxs-lookup"><span data-stu-id="968c4-113">address</span></span>|<span data-ttu-id="968c4-114">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="968c4-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="968c4-115">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="968c4-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="968c4-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="968c4-116">The default is an empty string.</span></span> <span data-ttu-id="968c4-117">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="968c4-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="968c4-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="968c4-118">behaviorConfiguration</span></span>|<span data-ttu-id="968c4-119">Stringa che contiene il nome del comportamento da usare per creare un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="968c4-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="968c4-120">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="968c4-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="968c4-121">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="968c4-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="968c4-122">binding</span><span class="sxs-lookup"><span data-stu-id="968c4-122">binding</span></span>|<span data-ttu-id="968c4-123">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="968c4-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="968c4-124">Stringa che indica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="968c4-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="968c4-125">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="968c4-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="968c4-126">Il tipo viene registrato in base al nome di sezione invece che al nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="968c4-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="968c4-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="968c4-127">bindingConfiguration</span></span>|<span data-ttu-id="968c4-128">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="968c4-128">Optional.</span></span> <span data-ttu-id="968c4-129">Stringa che contiene il nome della configurazione di associazione da usare quando viene creata un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="968c4-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="968c4-130">La configurazione di associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="968c4-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="968c4-131">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="968c4-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="968c4-132">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="968c4-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="968c4-133">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="968c4-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="968c4-134">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="968c4-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="968c4-135">contract</span><span class="sxs-lookup"><span data-stu-id="968c4-135">contract</span></span>|<span data-ttu-id="968c4-136">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="968c4-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="968c4-137">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="968c4-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="968c4-138">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="968c4-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="968c4-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="968c4-139">endpointConfiguration</span></span>|<span data-ttu-id="968c4-140">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="968c4-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="968c4-141">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="968c4-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="968c4-142">kind</span><span class="sxs-lookup"><span data-stu-id="968c4-142">kind</span></span>|<span data-ttu-id="968c4-143">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="968c4-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="968c4-144">Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del canale comune.</span><span class="sxs-lookup"><span data-stu-id="968c4-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="968c4-145">name</span><span class="sxs-lookup"><span data-stu-id="968c4-145">name</span></span>|<span data-ttu-id="968c4-146">Attributo stringa facoltativo.</span><span class="sxs-lookup"><span data-stu-id="968c4-146">Optional string attribute.</span></span> <span data-ttu-id="968c4-147">L'attributo identifica in modo univoco un endpoint per un dato contratto.</span><span class="sxs-lookup"><span data-stu-id="968c4-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="968c4-148">È possibile definire più client per un determinato tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="968c4-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="968c4-149">Ogni definizione deve essere differenziata da un nome di configurazione univoco.</span><span class="sxs-lookup"><span data-stu-id="968c4-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="968c4-150">Se questo attributo viene omesso, l'endpoint corrispondente viene usato come endpoint predefinito associato al tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="968c4-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="968c4-151">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="968c4-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="968c4-152">L'attributo `name` di un'associazione viene usato per l'esportazione della definizione tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="968c4-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="968c4-153">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="968c4-153">Child Elements</span></span>  
  
|<span data-ttu-id="968c4-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="968c4-154">Element</span></span>|<span data-ttu-id="968c4-155">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="968c4-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="968c4-156">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="968c4-156">\<headers></span></span>](headers.md)|<span data-ttu-id="968c4-157">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="968c4-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="968c4-158">\<identity></span><span class="sxs-lookup"><span data-stu-id="968c4-158">\<identity></span></span>](identity.md)|<span data-ttu-id="968c4-159">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="968c4-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="968c4-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="968c4-160">Parent Elements</span></span>  
  
|<span data-ttu-id="968c4-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="968c4-161">Element</span></span>|<span data-ttu-id="968c4-162">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="968c4-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="968c4-163">\<client></span><span class="sxs-lookup"><span data-stu-id="968c4-163">\<client></span></span>](client.md)|<span data-ttu-id="968c4-164">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="968c4-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="968c4-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="968c4-165">Example</span></span>  
 <span data-ttu-id="968c4-166">Di seguito è riportato un esempio di configurazione dell'endpoint di un canale.</span><span class="sxs-lookup"><span data-stu-id="968c4-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="968c4-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="968c4-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="968c4-168">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="968c4-168">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="968c4-169">Client</span><span class="sxs-lookup"><span data-stu-id="968c4-169">Clients</span></span>](../../../wcf/feature-details/clients.md)
