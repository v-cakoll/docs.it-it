---
title: <endpoint> di <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855315"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="60d2a-102">\<> endpoint di \<> client</span><span class="sxs-lookup"><span data-stu-id="60d2a-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="60d2a-103">Specifica proprietà di contratto, associazione e indirizzo dell'endpoint del canale usato dai client per connettersi agli endpoint del servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="60d2a-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="60d2a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60d2a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60d2a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="60d2a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="60d2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="60d2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="60d2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> endpoint**</span><span class="sxs-lookup"><span data-stu-id="60d2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d2a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60d2a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60d2a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="60d2a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="60d2a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="60d2a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60d2a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="60d2a-111">Attributes</span></span>  
  
|<span data-ttu-id="60d2a-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="60d2a-112">Attribute</span></span>|<span data-ttu-id="60d2a-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="60d2a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60d2a-114">Address</span><span class="sxs-lookup"><span data-stu-id="60d2a-114">address</span></span>|<span data-ttu-id="60d2a-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="60d2a-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="60d2a-116">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="60d2a-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="60d2a-117">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="60d2a-117">The default is an empty string.</span></span> <span data-ttu-id="60d2a-118">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="60d2a-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="60d2a-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="60d2a-119">behaviorConfiguration</span></span>|<span data-ttu-id="60d2a-120">Stringa che contiene il nome del comportamento da usare per creare un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="60d2a-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="60d2a-121">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="60d2a-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="60d2a-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="60d2a-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="60d2a-123">binding</span><span class="sxs-lookup"><span data-stu-id="60d2a-123">binding</span></span>|<span data-ttu-id="60d2a-124">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="60d2a-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="60d2a-125">Stringa che indica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="60d2a-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="60d2a-126">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="60d2a-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="60d2a-127">Il tipo viene registrato in base al nome di sezione invece che al nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="60d2a-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="60d2a-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="60d2a-128">bindingConfiguration</span></span>|<span data-ttu-id="60d2a-129">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="60d2a-129">Optional.</span></span> <span data-ttu-id="60d2a-130">Stringa che contiene il nome della configurazione di associazione da usare quando viene creata un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="60d2a-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="60d2a-131">La configurazione di associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="60d2a-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="60d2a-132">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="60d2a-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="60d2a-133">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="60d2a-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="60d2a-134">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="60d2a-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="60d2a-135">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="60d2a-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="60d2a-136">contract</span><span class="sxs-lookup"><span data-stu-id="60d2a-136">contract</span></span>|<span data-ttu-id="60d2a-137">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="60d2a-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="60d2a-138">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="60d2a-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="60d2a-139">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="60d2a-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="60d2a-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="60d2a-140">endpointConfiguration</span></span>|<span data-ttu-id="60d2a-141">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="60d2a-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="60d2a-142">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="60d2a-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="60d2a-143">kind</span><span class="sxs-lookup"><span data-stu-id="60d2a-143">kind</span></span>|<span data-ttu-id="60d2a-144">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="60d2a-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="60d2a-145">Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del canale comune.</span><span class="sxs-lookup"><span data-stu-id="60d2a-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="60d2a-146">name</span><span class="sxs-lookup"><span data-stu-id="60d2a-146">name</span></span>|<span data-ttu-id="60d2a-147">Attributo stringa facoltativo.</span><span class="sxs-lookup"><span data-stu-id="60d2a-147">Optional string attribute.</span></span> <span data-ttu-id="60d2a-148">L'attributo identifica in modo univoco un endpoint per un dato contratto.</span><span class="sxs-lookup"><span data-stu-id="60d2a-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="60d2a-149">È possibile definire più client per un determinato tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="60d2a-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="60d2a-150">Ogni definizione deve essere differenziata da un nome di configurazione univoco.</span><span class="sxs-lookup"><span data-stu-id="60d2a-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="60d2a-151">Se questo attributo viene omesso, l'endpoint corrispondente viene usato come endpoint predefinito associato al tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="60d2a-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="60d2a-152">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="60d2a-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="60d2a-153">L'attributo `name` di un'associazione viene usato per l'esportazione della definizione tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="60d2a-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60d2a-154">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="60d2a-154">Child Elements</span></span>  
  
|<span data-ttu-id="60d2a-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="60d2a-155">Element</span></span>|<span data-ttu-id="60d2a-156">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="60d2a-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60d2a-157">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="60d2a-157">\<headers></span></span>](headers.md)|<span data-ttu-id="60d2a-158">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60d2a-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="60d2a-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="60d2a-159">\<identity></span></span>](identity.md)|<span data-ttu-id="60d2a-160">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="60d2a-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60d2a-161">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="60d2a-161">Parent Elements</span></span>  
  
|<span data-ttu-id="60d2a-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="60d2a-162">Element</span></span>|<span data-ttu-id="60d2a-163">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="60d2a-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60d2a-164">\<client></span><span class="sxs-lookup"><span data-stu-id="60d2a-164">\<client></span></span>](client.md)|<span data-ttu-id="60d2a-165">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="60d2a-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="60d2a-166">Esempio</span><span class="sxs-lookup"><span data-stu-id="60d2a-166">Example</span></span>  
 <span data-ttu-id="60d2a-167">Di seguito è riportato un esempio di configurazione dell'endpoint di un canale.</span><span class="sxs-lookup"><span data-stu-id="60d2a-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="60d2a-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60d2a-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="60d2a-169">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="60d2a-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="60d2a-170">Client</span><span class="sxs-lookup"><span data-stu-id="60d2a-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
