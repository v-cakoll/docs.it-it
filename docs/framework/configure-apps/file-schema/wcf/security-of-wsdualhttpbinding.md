---
title: '&lt;security&gt; di &lt;wsDualHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4b90bd304ef8d87593c5b78febc0182c8fa2f091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="4f05c-102">&lt;security&gt; di &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="4f05c-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="4f05c-103">Definisce le funzionalità di sicurezza di [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4f05c-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="4f05c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4f05c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f05c-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="4f05c-105">\<bindings></span></span>  
<span data-ttu-id="4f05c-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4f05c-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="4f05c-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="4f05c-107">\<binding></span></span>  
<span data-ttu-id="4f05c-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="4f05c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f05c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f05c-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f05c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f05c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f05c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f05c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f05c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f05c-112">Attributes</span></span>  
  
|<span data-ttu-id="4f05c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4f05c-113">Attribute</span></span>|<span data-ttu-id="4f05c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f05c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f05c-115">modalità</span><span class="sxs-lookup"><span data-stu-id="4f05c-115">mode</span></span>|<span data-ttu-id="4f05c-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4f05c-116">-   Optional.</span></span> <span data-ttu-id="4f05c-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="4f05c-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="4f05c-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="4f05c-118">The default value is `Message`.</span></span> <span data-ttu-id="4f05c-119">L'attributo è di tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4f05c-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4f05c-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="4f05c-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="4f05c-121">Valore</span><span class="sxs-lookup"><span data-stu-id="4f05c-121">Value</span></span>|<span data-ttu-id="4f05c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f05c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f05c-123">None</span><span class="sxs-lookup"><span data-stu-id="4f05c-123">None</span></span>|<span data-ttu-id="4f05c-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4f05c-124">Security is disabled.</span></span>|  
|<span data-ttu-id="4f05c-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="4f05c-125">Message</span></span>|<span data-ttu-id="4f05c-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="4f05c-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f05c-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f05c-127">Child Elements</span></span>  
  
|<span data-ttu-id="4f05c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f05c-128">Element</span></span>|<span data-ttu-id="4f05c-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f05c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f05c-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="4f05c-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="4f05c-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="4f05c-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="4f05c-132">L'elemento è di tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="4f05c-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f05c-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f05c-133">Parent Elements</span></span>  
  
|<span data-ttu-id="4f05c-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f05c-134">Element</span></span>|<span data-ttu-id="4f05c-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f05c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f05c-136">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="4f05c-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4f05c-137">Definisce tutte le funzionalità di associazione di [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4f05c-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f05c-138">Note</span><span class="sxs-lookup"><span data-stu-id="4f05c-138">Remarks</span></span>  
 <span data-ttu-id="4f05c-139">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="4f05c-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="4f05c-140">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="4f05c-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f05c-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f05c-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="4f05c-142">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="4f05c-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4f05c-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4f05c-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4f05c-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="4f05c-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4f05c-145">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4f05c-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4f05c-146">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="4f05c-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
