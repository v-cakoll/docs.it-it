---
title: '&lt;security&gt; di &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: c817ea6faf5229a8d372a06b866c75e0f40af3b3
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113056"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="044ee-102">&lt;security&gt; di &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="044ee-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="044ee-103">Definisce le funzionalità di sicurezza del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="044ee-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="044ee-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="044ee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="044ee-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="044ee-105">\<bindings></span></span>  
<span data-ttu-id="044ee-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="044ee-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="044ee-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="044ee-107">\<binding></span></span>  
<span data-ttu-id="044ee-108">\<security></span><span class="sxs-lookup"><span data-stu-id="044ee-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="044ee-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="044ee-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="044ee-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="044ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="044ee-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="044ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="044ee-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="044ee-112">Attributes</span></span>  
  
|<span data-ttu-id="044ee-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="044ee-113">Attribute</span></span>|<span data-ttu-id="044ee-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="044ee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="044ee-115">modalità</span><span class="sxs-lookup"><span data-stu-id="044ee-115">mode</span></span>|<span data-ttu-id="044ee-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="044ee-116">-   Optional.</span></span> <span data-ttu-id="044ee-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="044ee-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="044ee-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="044ee-118">The default value is `Message`.</span></span> <span data-ttu-id="044ee-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="044ee-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="044ee-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="044ee-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="044ee-121">Valore</span><span class="sxs-lookup"><span data-stu-id="044ee-121">Value</span></span>|<span data-ttu-id="044ee-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="044ee-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="044ee-123">None</span><span class="sxs-lookup"><span data-stu-id="044ee-123">None</span></span>|<span data-ttu-id="044ee-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="044ee-124">Security is disabled.</span></span>|  
|<span data-ttu-id="044ee-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="044ee-125">Message</span></span>|<span data-ttu-id="044ee-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="044ee-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="044ee-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="044ee-127">Child Elements</span></span>  
  
|<span data-ttu-id="044ee-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="044ee-128">Element</span></span>|<span data-ttu-id="044ee-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="044ee-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="044ee-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="044ee-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="044ee-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="044ee-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="044ee-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="044ee-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="044ee-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="044ee-133">Parent Elements</span></span>  
  
|<span data-ttu-id="044ee-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="044ee-134">Element</span></span>|<span data-ttu-id="044ee-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="044ee-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="044ee-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="044ee-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="044ee-137">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="044ee-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="044ee-138">Note</span><span class="sxs-lookup"><span data-stu-id="044ee-138">Remarks</span></span>  
 <span data-ttu-id="044ee-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="044ee-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="044ee-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="044ee-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044ee-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="044ee-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="044ee-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="044ee-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="044ee-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="044ee-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="044ee-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="044ee-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="044ee-145">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="044ee-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="044ee-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="044ee-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
