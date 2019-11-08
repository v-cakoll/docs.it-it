---
title: <security> di <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736443"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="927a0-102">\<> di sicurezza di \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="927a0-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="927a0-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="927a0-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="927a0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="927a0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="927a0-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="927a0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="927a0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="927a0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="927a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetNamedPipeBinding**](netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="927a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="927a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="927a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="927a0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="927a0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="927a0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="927a0-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="927a0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="927a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="927a0-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="927a0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="927a0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="927a0-113">Attributes</span></span>  
  
|<span data-ttu-id="927a0-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="927a0-114">Attribute</span></span>|<span data-ttu-id="927a0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="927a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="927a0-116">modalità</span><span class="sxs-lookup"><span data-stu-id="927a0-116">mode</span></span>|<span data-ttu-id="927a0-117">Specifica il tipo di sicurezza applicata a questa associazione.</span><span class="sxs-lookup"><span data-stu-id="927a0-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="927a0-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="927a0-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="927a0-119">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="927a0-119">-   None: This disables security.</span></span><br /><span data-ttu-id="927a0-120">-Transport: la sicurezza viene fornita utilizzando la sicurezza basata sul trasporto sottostante.</span><span class="sxs-lookup"><span data-stu-id="927a0-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="927a0-121">Con questa modalità è possibile controllare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="927a0-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="927a0-122">-Il valore predefinito è Transport.</span><span class="sxs-lookup"><span data-stu-id="927a0-122">-   The default value is Transport.</span></span> <span data-ttu-id="927a0-123">L'attributo è di tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="927a0-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="927a0-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="927a0-124">Child Elements</span></span>  
  
|<span data-ttu-id="927a0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="927a0-125">Element</span></span>|<span data-ttu-id="927a0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="927a0-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="927a0-127">transport</span><span class="sxs-lookup"><span data-stu-id="927a0-127">transport</span></span>|<span data-ttu-id="927a0-128">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="927a0-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="927a0-129">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="927a0-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="927a0-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="927a0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="927a0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="927a0-131">Element</span></span>|<span data-ttu-id="927a0-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="927a0-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="927a0-133">binding</span><span class="sxs-lookup"><span data-stu-id="927a0-133">binding</span></span>|<span data-ttu-id="927a0-134">Elemento di associazione della [> NetNamedPipeBinding del\<](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="927a0-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="927a0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="927a0-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="927a0-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="927a0-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="927a0-137">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="927a0-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="927a0-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="927a0-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="927a0-139">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="927a0-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="927a0-140">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="927a0-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="927a0-141">\<binding ></span><span class="sxs-lookup"><span data-stu-id="927a0-141">\<binding></span></span>](bindings.md)
