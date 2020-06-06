---
title: <endpoint> di <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855315"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="c3a6b-102">\<endpoint> di \<client></span><span class="sxs-lookup"><span data-stu-id="c3a6b-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="c3a6b-103">Specifica proprietà di contratto, associazione e indirizzo dell'endpoint del canale usato dai client per connettersi agli endpoint del servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="c3a6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3a6b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3a6b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3a6b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c3a6b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3a6b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3a6b-107">Attributes</span></span>  
  
|<span data-ttu-id="c3a6b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c3a6b-108">Attribute</span></span>|<span data-ttu-id="c3a6b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a6b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3a6b-110">address</span><span class="sxs-lookup"><span data-stu-id="c3a6b-110">address</span></span>|<span data-ttu-id="c3a6b-111">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="c3a6b-112">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="c3a6b-113">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-113">The default is an empty string.</span></span> <span data-ttu-id="c3a6b-114">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="c3a6b-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3a6b-115">behaviorConfiguration</span></span>|<span data-ttu-id="c3a6b-116">Stringa che contiene il nome del comportamento da usare per creare un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="c3a6b-117">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="c3a6b-118">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="c3a6b-119">binding</span><span class="sxs-lookup"><span data-stu-id="c3a6b-119">binding</span></span>|<span data-ttu-id="c3a6b-120">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="c3a6b-121">Stringa che indica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="c3a6b-122">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="c3a6b-123">Il tipo viene registrato in base al nome di sezione invece che al nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="c3a6b-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3a6b-124">bindingConfiguration</span></span>|<span data-ttu-id="c3a6b-125">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-125">Optional.</span></span> <span data-ttu-id="c3a6b-126">Stringa che contiene il nome della configurazione di associazione da usare quando viene creata un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="c3a6b-127">La configurazione di associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="c3a6b-128">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="c3a6b-129">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="c3a6b-130">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="c3a6b-131">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="c3a6b-132">contract</span><span class="sxs-lookup"><span data-stu-id="c3a6b-132">contract</span></span>|<span data-ttu-id="c3a6b-133">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="c3a6b-134">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="c3a6b-135">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="c3a6b-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3a6b-136">endpointConfiguration</span></span>|<span data-ttu-id="c3a6b-137">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="c3a6b-138">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="c3a6b-139">kind</span><span class="sxs-lookup"><span data-stu-id="c3a6b-139">kind</span></span>|<span data-ttu-id="c3a6b-140">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="c3a6b-141">Il tipo deve essere registrato nella `<extensions>` sezione o in Machine. config. Se non viene specificato alcun valore, viene creato un endpoint del canale comune.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="c3a6b-142">name</span><span class="sxs-lookup"><span data-stu-id="c3a6b-142">name</span></span>|<span data-ttu-id="c3a6b-143">Attributo stringa facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-143">Optional string attribute.</span></span> <span data-ttu-id="c3a6b-144">L'attributo identifica in modo univoco un endpoint per un dato contratto.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="c3a6b-145">È possibile definire più client per un determinato tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="c3a6b-146">Ogni definizione deve essere differenziata da un nome di configurazione univoco.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="c3a6b-147">Se questo attributo viene omesso, l'endpoint corrispondente viene usato come endpoint predefinito associato al tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="c3a6b-148">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="c3a6b-149">L'attributo `name` di un'associazione viene usato per l'esportazione della definizione tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3a6b-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3a6b-150">Child Elements</span></span>  
  
|<span data-ttu-id="c3a6b-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3a6b-151">Element</span></span>|<span data-ttu-id="c3a6b-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a6b-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="c3a6b-153">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="c3a6b-154">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3a6b-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3a6b-155">Parent Elements</span></span>  
  
|<span data-ttu-id="c3a6b-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3a6b-156">Element</span></span>|<span data-ttu-id="c3a6b-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a6b-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="c3a6b-158">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c3a6b-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3a6b-159">Example</span></span>  
 <span data-ttu-id="c3a6b-160">Di seguito è riportato un esempio di configurazione dell'endpoint di un canale.</span><span class="sxs-lookup"><span data-stu-id="c3a6b-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="c3a6b-161">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c3a6b-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="c3a6b-162">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="c3a6b-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c3a6b-163">Client</span><span class="sxs-lookup"><span data-stu-id="c3a6b-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
