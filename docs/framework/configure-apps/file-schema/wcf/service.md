---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197958"
---
# <a name="service"></a><span data-ttu-id="df9ce-101">\<service></span><span class="sxs-lookup"><span data-stu-id="df9ce-101">\<service></span></span>
<span data-ttu-id="df9ce-102">L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="df9ce-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="df9ce-103">Contiene anche endpoint che espongono il servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="df9ce-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="df9ce-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="df9ce-105">\<services></span><span class="sxs-lookup"><span data-stu-id="df9ce-105">\<services></span></span>  
<span data-ttu-id="df9ce-106">\<service></span><span class="sxs-lookup"><span data-stu-id="df9ce-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9ce-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df9ce-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df9ce-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="df9ce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df9ce-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="df9ce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df9ce-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="df9ce-110">Attributes</span></span>  
  
|<span data-ttu-id="df9ce-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="df9ce-111">Attribute</span></span>|<span data-ttu-id="df9ce-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df9ce-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df9ce-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="df9ce-113">behaviorConfiguration</span></span>|<span data-ttu-id="df9ce-114">Stringa che contiene il nome del comportamento da usare per creare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="df9ce-115">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="df9ce-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="df9ce-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="df9ce-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="df9ce-117">name</span><span class="sxs-lookup"><span data-stu-id="df9ce-117">name</span></span>|<span data-ttu-id="df9ce-118">Attributo stringa obbligatorio che specifica il tipo del servizio per cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="df9ce-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="df9ce-119">Questa impostazione deve corrispondere a un tipo valido.</span><span class="sxs-lookup"><span data-stu-id="df9ce-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="df9ce-120">Il formato deve essere</span><span class="sxs-lookup"><span data-stu-id="df9ce-120">The format should be</span></span> `Namespace.Class.`|  
  
### <a name="child-elements"></a><span data-ttu-id="df9ce-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="df9ce-121">Child Elements</span></span>  
  
|<span data-ttu-id="df9ce-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="df9ce-122">Element</span></span>|<span data-ttu-id="df9ce-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df9ce-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df9ce-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="df9ce-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="df9ce-125">Raccolta di elementi `endpoint` che espongono questo servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="df9ce-126">\<host></span><span class="sxs-lookup"><span data-stu-id="df9ce-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="df9ce-127">Specifica l'host dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="df9ce-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="df9ce-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df9ce-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="df9ce-129">Parent Elements</span></span>  
  
|<span data-ttu-id="df9ce-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="df9ce-130">Element</span></span>|<span data-ttu-id="df9ce-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df9ce-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df9ce-132">\<services></span><span class="sxs-lookup"><span data-stu-id="df9ce-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="df9ce-133">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="df9ce-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df9ce-134">Note</span><span class="sxs-lookup"><span data-stu-id="df9ce-134">Remarks</span></span>  
 <span data-ttu-id="df9ce-135">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="df9ce-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="df9ce-136">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="df9ce-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="df9ce-137">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="df9ce-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="df9ce-138">Questa sezione e il relativo contenuto definiscono il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="df9ce-139">L'elemento `behaviorConfiguration` è anche facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df9ce-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="df9ce-140">Identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="df9ce-141">Il comportamento specificato in questo attributo deve collegarsi a un comportamento nell'ambito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="df9ce-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="df9ce-142">Ogni servizio espone uno o più endpoint, i quali sono provvisti di un proprio indirizzo e associazione.</span><span class="sxs-lookup"><span data-stu-id="df9ce-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="df9ce-143">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="df9ce-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="df9ce-144">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="df9ce-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="df9ce-145">L'attributo `name` descrive la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="df9ce-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="df9ce-146">L'attributo `bindingConfiguration` definisce quale configurazione viene usata tra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="df9ce-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="df9ce-147">In una sezione di associazione è possibile definire diverse configurazioni.</span><span class="sxs-lookup"><span data-stu-id="df9ce-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df9ce-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="df9ce-148">Example</span></span>  
 <span data-ttu-id="df9ce-149">Di seguito è riportato un esempio di una configurazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="df9ce-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="df9ce-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df9ce-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="df9ce-151">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="df9ce-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
