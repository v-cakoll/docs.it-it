---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 69f3c70514fc2bcab1b4ef6a45036de98d1af7b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936516"
---
# <a name="service"></a><span data-ttu-id="0e4e1-101">\<> del servizio</span><span class="sxs-lookup"><span data-stu-id="0e4e1-101">\<service></span></span>
<span data-ttu-id="0e4e1-102">L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0e4e1-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="0e4e1-103">Contiene anche endpoint che espongono il servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="0e4e1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e4e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e4e1-105">\<> dei servizi</span><span class="sxs-lookup"><span data-stu-id="0e4e1-105">\<services></span></span>  
<span data-ttu-id="0e4e1-106">\<> del servizio</span><span class="sxs-lookup"><span data-stu-id="0e4e1-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e4e1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e4e1-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e4e1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e4e1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0e4e1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e4e1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e4e1-110">Attributes</span></span>  
  
|<span data-ttu-id="0e4e1-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e4e1-111">Attribute</span></span>|<span data-ttu-id="0e4e1-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0e4e1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e4e1-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e4e1-113">behaviorConfiguration</span></span>|<span data-ttu-id="0e4e1-114">Stringa che contiene il nome del comportamento da usare per creare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="0e4e1-115">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="0e4e1-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="0e4e1-117">name</span><span class="sxs-lookup"><span data-stu-id="0e4e1-117">name</span></span>|<span data-ttu-id="0e4e1-118">Attributo stringa obbligatorio che specifica il tipo del servizio per cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="0e4e1-119">Questa impostazione deve corrispondere a un tipo valido.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="0e4e1-120">Il formato deve essere `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e4e1-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e4e1-121">Child Elements</span></span>  
  
|<span data-ttu-id="0e4e1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e4e1-122">Element</span></span>|<span data-ttu-id="0e4e1-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e4e1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e4e1-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="0e4e1-124">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="0e4e1-125">Raccolta di elementi `endpoint` che espongono questo servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="0e4e1-126">\<host></span><span class="sxs-lookup"><span data-stu-id="0e4e1-126">\<host></span></span>](host.md)|<span data-ttu-id="0e4e1-127">Specifica l'host dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="0e4e1-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e4e1-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e4e1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="0e4e1-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e4e1-130">Element</span></span>|<span data-ttu-id="0e4e1-131">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0e4e1-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e4e1-132">\<services></span><span class="sxs-lookup"><span data-stu-id="0e4e1-132">\<services></span></span>](services.md)|<span data-ttu-id="0e4e1-133">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e4e1-134">Note</span><span class="sxs-lookup"><span data-stu-id="0e4e1-134">Remarks</span></span>  
 <span data-ttu-id="0e4e1-135">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="0e4e1-136">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="0e4e1-137">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="0e4e1-138">Questa sezione e il relativo contenuto definiscono il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="0e4e1-139">L'elemento `behaviorConfiguration` è anche facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="0e4e1-140">Identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="0e4e1-141">Il comportamento specificato in questo attributo deve collegarsi a un comportamento nell'ambito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="0e4e1-142">Ogni servizio espone uno o più endpoint, i quali sono provvisti di un proprio indirizzo e associazione.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="0e4e1-143">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="0e4e1-144">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="0e4e1-145">L'attributo `name` descrive la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="0e4e1-146">L'attributo `bindingConfiguration` definisce quale configurazione viene usata tra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="0e4e1-147">In una sezione di associazione è possibile definire diverse configurazioni.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e4e1-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e4e1-148">Example</span></span>  
 <span data-ttu-id="0e4e1-149">Di seguito è riportato un esempio di una configurazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="0e4e1-149">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e4e1-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e4e1-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="0e4e1-151">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="0e4e1-151">Configuring Services</span></span>](../../../wcf/configuring-services.md)
