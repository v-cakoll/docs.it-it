---
title: <security> di <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936680"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="98c95-102">\<> di sicurezza \<di NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="98c95-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="98c95-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="98c95-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="98c95-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="98c95-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="98c95-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="98c95-105">\<bindings></span></span>  
<span data-ttu-id="98c95-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="98c95-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="98c95-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="98c95-107">\<binding></span></span>  
<span data-ttu-id="98c95-108">\<security></span><span class="sxs-lookup"><span data-stu-id="98c95-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c95-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98c95-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98c95-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="98c95-110">Attributes and Elements</span></span>  
 <span data-ttu-id="98c95-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="98c95-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98c95-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="98c95-112">Attributes</span></span>  
  
|<span data-ttu-id="98c95-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="98c95-113">Attribute</span></span>|<span data-ttu-id="98c95-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98c95-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98c95-115">modalità</span><span class="sxs-lookup"><span data-stu-id="98c95-115">mode</span></span>|<span data-ttu-id="98c95-116">Specifica il tipo di sicurezza applicata a questa associazione.</span><span class="sxs-lookup"><span data-stu-id="98c95-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="98c95-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="98c95-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="98c95-118">Nessuno Questa operazione Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="98c95-118">-   None: This disables security.</span></span><br /><span data-ttu-id="98c95-119">Trasporto La sicurezza viene fornita utilizzando la sicurezza basata sul trasporto sottostante.</span><span class="sxs-lookup"><span data-stu-id="98c95-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="98c95-120">Con questa modalità è possibile controllare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="98c95-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="98c95-121">-Il valore predefinito è Transport.</span><span class="sxs-lookup"><span data-stu-id="98c95-121">-   The default value is Transport.</span></span> <span data-ttu-id="98c95-122">L'attributo è di tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="98c95-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98c95-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="98c95-123">Child Elements</span></span>  
  
|<span data-ttu-id="98c95-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="98c95-124">Element</span></span>|<span data-ttu-id="98c95-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98c95-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98c95-126">transport</span><span class="sxs-lookup"><span data-stu-id="98c95-126">transport</span></span>|<span data-ttu-id="98c95-127">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="98c95-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="98c95-128">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="98c95-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98c95-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="98c95-129">Parent Elements</span></span>  
  
|<span data-ttu-id="98c95-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="98c95-130">Element</span></span>|<span data-ttu-id="98c95-131">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="98c95-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98c95-132">binding</span><span class="sxs-lookup"><span data-stu-id="98c95-132">binding</span></span>|<span data-ttu-id="98c95-133">Elemento di associazione della [ \<> NetNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="98c95-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98c95-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c95-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="98c95-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="98c95-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="98c95-136">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="98c95-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="98c95-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="98c95-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98c95-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="98c95-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="98c95-139">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="98c95-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="98c95-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="98c95-140">\<binding></span></span>](../../../misc/binding.md)
