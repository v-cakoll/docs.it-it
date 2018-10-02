---
title: '&lt;security&gt; di &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: c817ea6faf5229a8d372a06b866c75e0f40af3b3
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863117"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="fa672-102">&lt;security&gt; di &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fa672-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="fa672-103">Definisce le funzionalità di sicurezza del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fa672-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="fa672-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa672-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa672-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="fa672-105">\<bindings></span></span>  
<span data-ttu-id="fa672-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fa672-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="fa672-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa672-107">\<binding></span></span>  
<span data-ttu-id="fa672-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fa672-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa672-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa672-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa672-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fa672-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa672-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fa672-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa672-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fa672-112">Attributes</span></span>  
  
|<span data-ttu-id="fa672-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fa672-113">Attribute</span></span>|<span data-ttu-id="fa672-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa672-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa672-115">modalità</span><span class="sxs-lookup"><span data-stu-id="fa672-115">mode</span></span>|<span data-ttu-id="fa672-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa672-116">-   Optional.</span></span> <span data-ttu-id="fa672-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="fa672-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="fa672-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="fa672-118">The default value is `Message`.</span></span> <span data-ttu-id="fa672-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fa672-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fa672-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="fa672-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="fa672-121">Valore</span><span class="sxs-lookup"><span data-stu-id="fa672-121">Value</span></span>|<span data-ttu-id="fa672-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa672-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa672-123">None</span><span class="sxs-lookup"><span data-stu-id="fa672-123">None</span></span>|<span data-ttu-id="fa672-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="fa672-124">Security is disabled.</span></span>|  
|<span data-ttu-id="fa672-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fa672-125">Message</span></span>|<span data-ttu-id="fa672-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="fa672-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa672-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fa672-127">Child Elements</span></span>  
  
|<span data-ttu-id="fa672-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa672-128">Element</span></span>|<span data-ttu-id="fa672-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa672-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa672-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="fa672-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="fa672-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="fa672-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="fa672-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="fa672-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa672-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fa672-133">Parent Elements</span></span>  
  
|<span data-ttu-id="fa672-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa672-134">Element</span></span>|<span data-ttu-id="fa672-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa672-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa672-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa672-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fa672-137">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fa672-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa672-138">Note</span><span class="sxs-lookup"><span data-stu-id="fa672-138">Remarks</span></span>  
 <span data-ttu-id="fa672-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="fa672-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="fa672-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="fa672-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa672-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa672-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="fa672-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="fa672-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fa672-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="fa672-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fa672-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="fa672-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fa672-145">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fa672-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fa672-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa672-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
