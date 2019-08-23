---
title: <security> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936592"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="e8c3e-102">\<> di sicurezza \<di WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e8c3e-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="e8c3e-103">Specifica i requisiti di sicurezza per un endpoint configurato con un [ \<> WebHttpBinding](webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e8c3e-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="e8c3e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8c3e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8c3e-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="e8c3e-105">\<bindings></span></span>  
<span data-ttu-id="e8c3e-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e8c3e-106">\<webHttpBinding></span></span>  
<span data-ttu-id="e8c3e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e8c3e-107">\<binding></span></span>  
<span data-ttu-id="e8c3e-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e8c3e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c3e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8c3e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8c3e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8c3e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e8c3e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8c3e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8c3e-112">Attributes</span></span>  
  
|<span data-ttu-id="e8c3e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8c3e-113">Attribute</span></span>|<span data-ttu-id="e8c3e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8c3e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8c3e-115">modalità</span><span class="sxs-lookup"><span data-stu-id="e8c3e-115">mode</span></span>|<span data-ttu-id="e8c3e-116">Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="e8c3e-117">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-117">The default is `None`.</span></span> <span data-ttu-id="e8c3e-118">L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e8c3e-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="e8c3e-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="e8c3e-120">Value</span><span class="sxs-lookup"><span data-stu-id="e8c3e-120">Value</span></span>|<span data-ttu-id="e8c3e-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e8c3e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8c3e-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e8c3e-122">None</span></span>|<span data-ttu-id="e8c3e-123">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-123">Security is disabled.</span></span>|  
|<span data-ttu-id="e8c3e-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="e8c3e-124">Transport</span></span>|<span data-ttu-id="e8c3e-125">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="e8c3e-126">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="e8c3e-127">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e8c3e-128">L'autenticazione client viene controllata tramite l' `ClientCredentialType` attributo [ \<del > di trasporto](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e8c3e-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="e8c3e-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="e8c3e-129">TransportCredentialOnly</span></span>|<span data-ttu-id="e8c3e-130">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="e8c3e-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="e8c3e-131">ma fornisce l'autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="e8c3e-132">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-132">This mode should be used with caution.</span></span> <span data-ttu-id="e8c3e-133">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8c3e-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8c3e-134">Child Elements</span></span>  
  
|<span data-ttu-id="e8c3e-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8c3e-135">Element</span></span>|<span data-ttu-id="e8c3e-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8c3e-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8c3e-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="e8c3e-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="e8c3e-138">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-138">Defines the transport security settings.</span></span> <span data-ttu-id="e8c3e-139">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8c3e-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8c3e-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e8c3e-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8c3e-141">Element</span></span>|<span data-ttu-id="e8c3e-142">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e8c3e-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8c3e-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e8c3e-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="e8c3e-144">Elemento di associazione utilizzato per configurare endpoint per i servizi Web di Windows Communication Foundation (WCF) che rispondono a richieste HTTP anziché a messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="e8c3e-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8c3e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8c3e-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="e8c3e-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e8c3e-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e8c3e-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="e8c3e-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e8c3e-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e8c3e-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e8c3e-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e8c3e-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e8c3e-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e8c3e-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e8c3e-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="e8c3e-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="e8c3e-152">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="e8c3e-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
