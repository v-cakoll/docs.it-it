---
title: '&lt;security&gt; di &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
author: BrucePerlerMS
ms.openlocfilehash: eee4cc13b5181caa4449c3ad6ebc5247cc7e0f1a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424259"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="fc0a7-102">&lt;security&gt; di &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fc0a7-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="fc0a7-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="fc0a7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc0a7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc0a7-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="fc0a7-105">\<bindings></span></span>  
<span data-ttu-id="fc0a7-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="fc0a7-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="fc0a7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fc0a7-107">\<binding></span></span>  
<span data-ttu-id="fc0a7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fc0a7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0a7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc0a7-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc0a7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fc0a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fc0a7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc0a7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fc0a7-112">Attributes</span></span>  
  
|<span data-ttu-id="fc0a7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fc0a7-113">Attribute</span></span>|<span data-ttu-id="fc0a7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc0a7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc0a7-115">modalità</span><span class="sxs-lookup"><span data-stu-id="fc0a7-115">mode</span></span>|<span data-ttu-id="fc0a7-116">Specifica il tipo di sicurezza applicata a questa associazione.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="fc0a7-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="fc0a7-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fc0a7-118">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-118">-   None: This disables security.</span></span><br /><span data-ttu-id="fc0a7-119">-Transport: Sicurezza viene fornita utilizzando la sicurezza basata sul trasporto sottostante.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="fc0a7-120">Con questa modalità è possibile controllare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="fc0a7-121">-Il valore predefinito è il trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-121">-   The default value is Transport.</span></span> <span data-ttu-id="fc0a7-122">L'attributo è di tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc0a7-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fc0a7-123">Child Elements</span></span>  
  
|<span data-ttu-id="fc0a7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc0a7-124">Element</span></span>|<span data-ttu-id="fc0a7-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc0a7-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc0a7-126">transport</span><span class="sxs-lookup"><span data-stu-id="fc0a7-126">transport</span></span>|<span data-ttu-id="fc0a7-127">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="fc0a7-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fc0a7-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc0a7-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fc0a7-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fc0a7-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc0a7-130">Element</span></span>|<span data-ttu-id="fc0a7-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc0a7-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc0a7-132">binding</span><span class="sxs-lookup"><span data-stu-id="fc0a7-132">binding</span></span>|<span data-ttu-id="fc0a7-133">L'elemento di associazione del [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="fc0a7-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc0a7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc0a7-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="fc0a7-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="fc0a7-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fc0a7-136">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="fc0a7-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fc0a7-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="fc0a7-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fc0a7-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="fc0a7-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fc0a7-139">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fc0a7-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fc0a7-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="fc0a7-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
