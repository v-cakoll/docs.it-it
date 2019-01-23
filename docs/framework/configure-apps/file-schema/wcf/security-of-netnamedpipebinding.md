---
title: '&lt;security&gt; di &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: bef644094de06939c6948a50888f7f7f9d3e9a7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524611"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="02962-102">&lt;security&gt; di &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="02962-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="02962-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="02962-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="02962-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02962-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02962-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="02962-105">\<bindings></span></span>  
<span data-ttu-id="02962-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="02962-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="02962-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="02962-107">\<binding></span></span>  
<span data-ttu-id="02962-108">\<security></span><span class="sxs-lookup"><span data-stu-id="02962-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02962-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02962-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02962-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02962-110">Attributes and Elements</span></span>  
 <span data-ttu-id="02962-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02962-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02962-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="02962-112">Attributes</span></span>  
  
|<span data-ttu-id="02962-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="02962-113">Attribute</span></span>|<span data-ttu-id="02962-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02962-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02962-115">modalità</span><span class="sxs-lookup"><span data-stu-id="02962-115">mode</span></span>|<span data-ttu-id="02962-116">Specifica il tipo di sicurezza applicata a questa associazione.</span><span class="sxs-lookup"><span data-stu-id="02962-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="02962-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="02962-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="02962-118">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="02962-118">-   None: This disables security.</span></span><br /><span data-ttu-id="02962-119">-Transport: La sicurezza viene fornita utilizzando la sicurezza basata sul trasporto sottostante.</span><span class="sxs-lookup"><span data-stu-id="02962-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="02962-120">Con questa modalità è possibile controllare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="02962-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="02962-121">-Il valore predefinito è il trasporto.</span><span class="sxs-lookup"><span data-stu-id="02962-121">-   The default value is Transport.</span></span> <span data-ttu-id="02962-122">L'attributo è di tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="02962-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02962-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02962-123">Child Elements</span></span>  
  
|<span data-ttu-id="02962-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="02962-124">Element</span></span>|<span data-ttu-id="02962-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02962-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02962-126">transport</span><span class="sxs-lookup"><span data-stu-id="02962-126">transport</span></span>|<span data-ttu-id="02962-127">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="02962-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="02962-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="02962-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02962-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02962-129">Parent Elements</span></span>  
  
|<span data-ttu-id="02962-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="02962-130">Element</span></span>|<span data-ttu-id="02962-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02962-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02962-132">binding</span><span class="sxs-lookup"><span data-stu-id="02962-132">binding</span></span>|<span data-ttu-id="02962-133">L'elemento di associazione del [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="02962-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02962-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02962-134">See also</span></span>
- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="02962-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="02962-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="02962-136">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="02962-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="02962-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="02962-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="02962-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="02962-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02962-139">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="02962-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="02962-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="02962-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
