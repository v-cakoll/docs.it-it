---
title: <security> di <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: c6f9e34724ccc3a0d05da3e1886b4f0bcbaae064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171509"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="96d95-102">\<security> of \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="96d95-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="96d95-103">Definisce le funzionalità di sicurezza del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="96d95-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="96d95-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="96d95-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="96d95-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="96d95-105">\<bindings></span></span>  
<span data-ttu-id="96d95-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="96d95-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="96d95-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="96d95-107">\<binding></span></span>  
<span data-ttu-id="96d95-108">\<security></span><span class="sxs-lookup"><span data-stu-id="96d95-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d95-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96d95-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96d95-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96d95-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96d95-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96d95-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96d95-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="96d95-112">Attributes</span></span>  
  
|<span data-ttu-id="96d95-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="96d95-113">Attribute</span></span>|<span data-ttu-id="96d95-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96d95-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96d95-115">modalità</span><span class="sxs-lookup"><span data-stu-id="96d95-115">mode</span></span>|<span data-ttu-id="96d95-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96d95-116">-   Optional.</span></span> <span data-ttu-id="96d95-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="96d95-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="96d95-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="96d95-118">The default value is `Message`.</span></span> <span data-ttu-id="96d95-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="96d95-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="96d95-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="96d95-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="96d95-121">Value</span><span class="sxs-lookup"><span data-stu-id="96d95-121">Value</span></span>|<span data-ttu-id="96d95-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96d95-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="96d95-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="96d95-123">None</span></span>|<span data-ttu-id="96d95-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="96d95-124">Security is disabled.</span></span>|  
|<span data-ttu-id="96d95-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="96d95-125">Message</span></span>|<span data-ttu-id="96d95-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="96d95-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96d95-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96d95-127">Child Elements</span></span>  
  
|<span data-ttu-id="96d95-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="96d95-128">Element</span></span>|<span data-ttu-id="96d95-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96d95-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96d95-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="96d95-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="96d95-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="96d95-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="96d95-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="96d95-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96d95-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96d95-133">Parent Elements</span></span>  
  
|<span data-ttu-id="96d95-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="96d95-134">Element</span></span>|<span data-ttu-id="96d95-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96d95-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96d95-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="96d95-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="96d95-137">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="96d95-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96d95-138">Note</span><span class="sxs-lookup"><span data-stu-id="96d95-138">Remarks</span></span>  
 <span data-ttu-id="96d95-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="96d95-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="96d95-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="96d95-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d95-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96d95-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="96d95-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="96d95-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="96d95-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="96d95-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="96d95-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="96d95-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="96d95-145">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="96d95-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="96d95-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="96d95-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
