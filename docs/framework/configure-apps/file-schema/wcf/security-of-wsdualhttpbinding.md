---
title: <security> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: c6f9e34724ccc3a0d05da3e1886b4f0bcbaae064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670443"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="1fe39-102">\<security> of \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1fe39-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="1fe39-103">Definisce le funzionalità di sicurezza del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1fe39-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="1fe39-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1fe39-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1fe39-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1fe39-105">\<bindings></span></span>  
<span data-ttu-id="1fe39-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1fe39-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="1fe39-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1fe39-107">\<binding></span></span>  
<span data-ttu-id="1fe39-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1fe39-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe39-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fe39-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fe39-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1fe39-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1fe39-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1fe39-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fe39-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1fe39-112">Attributes</span></span>  
  
|<span data-ttu-id="1fe39-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1fe39-113">Attribute</span></span>|<span data-ttu-id="1fe39-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe39-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fe39-115">modalità</span><span class="sxs-lookup"><span data-stu-id="1fe39-115">mode</span></span>|<span data-ttu-id="1fe39-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1fe39-116">-   Optional.</span></span> <span data-ttu-id="1fe39-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="1fe39-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1fe39-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="1fe39-118">The default value is `Message`.</span></span> <span data-ttu-id="1fe39-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1fe39-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1fe39-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="1fe39-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="1fe39-121">Value</span><span class="sxs-lookup"><span data-stu-id="1fe39-121">Value</span></span>|<span data-ttu-id="1fe39-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe39-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1fe39-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="1fe39-123">None</span></span>|<span data-ttu-id="1fe39-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1fe39-124">Security is disabled.</span></span>|  
|<span data-ttu-id="1fe39-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1fe39-125">Message</span></span>|<span data-ttu-id="1fe39-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="1fe39-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fe39-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1fe39-127">Child Elements</span></span>  
  
|<span data-ttu-id="1fe39-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fe39-128">Element</span></span>|<span data-ttu-id="1fe39-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe39-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe39-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="1fe39-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="1fe39-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1fe39-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="1fe39-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="1fe39-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fe39-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1fe39-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1fe39-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fe39-134">Element</span></span>|<span data-ttu-id="1fe39-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe39-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe39-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="1fe39-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1fe39-137">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1fe39-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fe39-138">Note</span><span class="sxs-lookup"><span data-stu-id="1fe39-138">Remarks</span></span>  
 <span data-ttu-id="1fe39-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="1fe39-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="1fe39-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="1fe39-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe39-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fe39-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="1fe39-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1fe39-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1fe39-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1fe39-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1fe39-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1fe39-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1fe39-145">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1fe39-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1fe39-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="1fe39-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
