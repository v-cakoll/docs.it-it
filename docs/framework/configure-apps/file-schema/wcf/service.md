---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855014"
---
# \<service>
<span data-ttu-id="04d79-101">L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="04d79-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="04d79-102">Contiene anche endpoint che espongono il servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="04d79-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04d79-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04d79-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04d79-104">Attributes and Elements</span></span>  
 <span data-ttu-id="04d79-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04d79-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04d79-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="04d79-106">Attributes</span></span>  
  
|<span data-ttu-id="04d79-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="04d79-107">Attribute</span></span>|<span data-ttu-id="04d79-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04d79-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04d79-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="04d79-109">behaviorConfiguration</span></span>|<span data-ttu-id="04d79-110">Stringa che contiene il nome del comportamento da usare per creare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="04d79-111">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="04d79-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="04d79-112">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="04d79-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="04d79-113">name</span><span class="sxs-lookup"><span data-stu-id="04d79-113">name</span></span>|<span data-ttu-id="04d79-114">Attributo stringa obbligatorio che specifica il tipo del servizio per cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="04d79-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="04d79-115">Questa impostazione deve corrispondere a un tipo valido.</span><span class="sxs-lookup"><span data-stu-id="04d79-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="04d79-116">Il formato deve essere `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="04d79-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04d79-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04d79-117">Child Elements</span></span>  
  
|<span data-ttu-id="04d79-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="04d79-118">Element</span></span>|<span data-ttu-id="04d79-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04d79-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="04d79-120">Raccolta di elementi `endpoint` che espongono questo servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="04d79-121">Specifica l'host dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="04d79-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="04d79-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04d79-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04d79-123">Parent Elements</span></span>  
  
|<span data-ttu-id="04d79-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="04d79-124">Element</span></span>|<span data-ttu-id="04d79-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04d79-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="04d79-126">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="04d79-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04d79-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="04d79-127">Remarks</span></span>  
 <span data-ttu-id="04d79-128">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04d79-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="04d79-129">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="04d79-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="04d79-130">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="04d79-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="04d79-131">Questa sezione e il relativo contenuto definiscono il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="04d79-132">L'elemento `behaviorConfiguration` è anche facoltativo.</span><span class="sxs-lookup"><span data-stu-id="04d79-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="04d79-133">Identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="04d79-134">Il comportamento specificato in questo attributo deve collegarsi a un comportamento nell'ambito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04d79-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="04d79-135">Ogni servizio espone uno o più endpoint, i quali sono provvisti di un proprio indirizzo e associazione.</span><span class="sxs-lookup"><span data-stu-id="04d79-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="04d79-136">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="04d79-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="04d79-137">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="04d79-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="04d79-138">L'attributo `name` descrive la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="04d79-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="04d79-139">L'attributo `bindingConfiguration` definisce quale configurazione viene usata tra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="04d79-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="04d79-140">In una sezione di associazione è possibile definire diverse configurazioni.</span><span class="sxs-lookup"><span data-stu-id="04d79-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04d79-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="04d79-141">Example</span></span>  
 <span data-ttu-id="04d79-142">Di seguito è riportato un esempio di una configurazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="04d79-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04d79-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="04d79-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="04d79-144">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="04d79-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
