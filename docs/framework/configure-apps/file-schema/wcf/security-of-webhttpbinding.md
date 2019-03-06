---
title: <security> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 7f714ffb89d5ff990239bd1a02ffaeead4ad7d91
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360777"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="9d6a4-102">\<security> of \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9d6a4-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="9d6a4-103">Specifica i requisiti di sicurezza per un endpoint configurato con un [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9d6a4-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d6a4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9d6a4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d6a4-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="9d6a4-105">\<bindings></span></span>  
<span data-ttu-id="9d6a4-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9d6a4-106">\<webHttpBinding></span></span>  
<span data-ttu-id="9d6a4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d6a4-107">\<binding></span></span>  
<span data-ttu-id="9d6a4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9d6a4-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6a4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d6a4-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d6a4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9d6a4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9d6a4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d6a4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9d6a4-112">Attributes</span></span>  
  
|<span data-ttu-id="9d6a4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9d6a4-113">Attribute</span></span>|<span data-ttu-id="9d6a4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6a4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d6a4-115">modalità</span><span class="sxs-lookup"><span data-stu-id="9d6a4-115">mode</span></span>|<span data-ttu-id="9d6a4-116">Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="9d6a4-117">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-117">The default is `None`.</span></span> <span data-ttu-id="9d6a4-118">L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9d6a4-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="9d6a4-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="9d6a4-120">Valore</span><span class="sxs-lookup"><span data-stu-id="9d6a4-120">Value</span></span>|<span data-ttu-id="9d6a4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6a4-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d6a4-122">None</span><span class="sxs-lookup"><span data-stu-id="9d6a4-122">None</span></span>|<span data-ttu-id="9d6a4-123">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-123">Security is disabled.</span></span>|  
|<span data-ttu-id="9d6a4-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="9d6a4-124">Transport</span></span>|<span data-ttu-id="9d6a4-125">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="9d6a4-126">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="9d6a4-127">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="9d6a4-128">L'autenticazione client è controllata tramite il `ClientCredentialType` attributo del [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9d6a4-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="9d6a4-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9d6a4-129">TransportCredentialOnly</span></span>|<span data-ttu-id="9d6a4-130">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="9d6a4-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9d6a4-131">ma fornisce l'autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="9d6a4-132">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-132">This mode should be used with caution.</span></span> <span data-ttu-id="9d6a4-133">Deve essere utilizzata nei ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e solo l'autenticazione client viene fornito dall'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d6a4-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d6a4-134">Child Elements</span></span>  
  
|<span data-ttu-id="9d6a4-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d6a4-135">Element</span></span>|<span data-ttu-id="9d6a4-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6a4-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d6a4-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="9d6a4-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="9d6a4-138">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-138">Defines the transport security settings.</span></span> <span data-ttu-id="9d6a4-139">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d6a4-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9d6a4-140">Parent Elements</span></span>  
  
|<span data-ttu-id="9d6a4-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d6a4-141">Element</span></span>|<span data-ttu-id="9d6a4-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d6a4-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d6a4-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9d6a4-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="9d6a4-144">Un elemento di associazione usato per configurare gli endpoint per Windows Communication Foundation (WCF) Web dei servizi che rispondono alle richieste HTTP anziché a messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="9d6a4-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d6a4-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d6a4-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="9d6a4-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9d6a4-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9d6a4-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="9d6a4-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9d6a4-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9d6a4-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9d6a4-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9d6a4-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9d6a4-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="9d6a4-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9d6a4-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d6a4-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="9d6a4-152">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="9d6a4-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
