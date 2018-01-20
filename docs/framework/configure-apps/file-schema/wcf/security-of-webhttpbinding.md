---
title: '&lt;security&gt; di &lt;webHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: dc7edf528f509c725672036329989f9b7a9bfec2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="1a3c2-102">&lt;security&gt; di &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1a3c2-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="1a3c2-103">Specifica i requisiti di sicurezza per un endpoint configurato con un [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1a3c2-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="1a3c2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1a3c2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1a3c2-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1a3c2-105">\<bindings></span></span>  
<span data-ttu-id="1a3c2-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1a3c2-106">\<webHttpBinding></span></span>  
<span data-ttu-id="1a3c2-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1a3c2-107">\<binding></span></span>  
<span data-ttu-id="1a3c2-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1a3c2-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a3c2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a3c2-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a3c2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1a3c2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1a3c2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a3c2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1a3c2-112">Attributes</span></span>  
  
|<span data-ttu-id="1a3c2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1a3c2-113">Attribute</span></span>|<span data-ttu-id="1a3c2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a3c2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a3c2-115">modalità</span><span class="sxs-lookup"><span data-stu-id="1a3c2-115">mode</span></span>|<span data-ttu-id="1a3c2-116">Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="1a3c2-117">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-117">The default is `None`.</span></span> <span data-ttu-id="1a3c2-118">L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1a3c2-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="1a3c2-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="1a3c2-120">Valore</span><span class="sxs-lookup"><span data-stu-id="1a3c2-120">Value</span></span>|<span data-ttu-id="1a3c2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a3c2-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1a3c2-122">None</span><span class="sxs-lookup"><span data-stu-id="1a3c2-122">None</span></span>|<span data-ttu-id="1a3c2-123">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-123">Security is disabled.</span></span>|  
|<span data-ttu-id="1a3c2-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="1a3c2-124">Transport</span></span>|<span data-ttu-id="1a3c2-125">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="1a3c2-126">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="1a3c2-127">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="1a3c2-128">L'autenticazione client viene controllato tramite il `ClientCredentialType` attributo del [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1a3c2-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="1a3c2-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="1a3c2-129">TransportCredentialOnly</span></span>|<span data-ttu-id="1a3c2-130">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="1a3c2-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="1a3c2-131">ma fornisce l'autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="1a3c2-132">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-132">This mode should be used with caution.</span></span> <span data-ttu-id="1a3c2-133">In particolare, va usata in ambienti dove la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a3c2-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1a3c2-134">Child Elements</span></span>  
  
|<span data-ttu-id="1a3c2-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a3c2-135">Element</span></span>|<span data-ttu-id="1a3c2-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a3c2-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a3c2-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="1a3c2-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="1a3c2-138">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-138">Defines the transport security settings.</span></span> <span data-ttu-id="1a3c2-139">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a3c2-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1a3c2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="1a3c2-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a3c2-141">Element</span></span>|<span data-ttu-id="1a3c2-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a3c2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a3c2-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1a3c2-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="1a3c2-144">Elemento di associazione usato per configurare endpoint per servizi Web [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] che rispondono a richieste HTTP anziché a messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a3c2-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a3c2-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="1a3c2-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1a3c2-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1a3c2-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="1a3c2-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="1a3c2-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1a3c2-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1a3c2-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1a3c2-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1a3c2-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1a3c2-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1a3c2-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="1a3c2-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="1a3c2-152">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="1a3c2-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
