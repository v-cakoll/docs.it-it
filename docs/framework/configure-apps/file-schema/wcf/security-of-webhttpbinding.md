---
title: <security> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 2f0bc97e10fcd72f2f33cc20730320cbbfc42dd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399756"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="9e038-102">\<> di sicurezza \<di WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9e038-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="9e038-103">Specifica i requisiti di sicurezza per un endpoint configurato con un [ \<> WebHttpBinding](webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9e038-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="9e038-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e038-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e038-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9e038-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9e038-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9e038-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9e038-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> WebHttpBinding**](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9e038-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="9e038-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="9e038-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9e038-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="9e038-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e038-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e038-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e038-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e038-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9e038-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e038-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e038-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e038-113">Attributes</span></span>  
  
|<span data-ttu-id="9e038-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="9e038-114">Attribute</span></span>|<span data-ttu-id="9e038-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9e038-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e038-116">modalità</span><span class="sxs-lookup"><span data-stu-id="9e038-116">mode</span></span>|<span data-ttu-id="9e038-117">Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9e038-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="9e038-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="9e038-118">The default is `None`.</span></span> <span data-ttu-id="9e038-119">L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9e038-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9e038-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="9e038-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="9e038-121">Valore</span><span class="sxs-lookup"><span data-stu-id="9e038-121">Value</span></span>|<span data-ttu-id="9e038-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e038-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e038-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="9e038-123">None</span></span>|<span data-ttu-id="9e038-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9e038-124">Security is disabled.</span></span>|  
|<span data-ttu-id="9e038-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="9e038-125">Transport</span></span>|<span data-ttu-id="9e038-126">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9e038-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="9e038-127">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="9e038-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="9e038-128">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="9e038-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="9e038-129">L'autenticazione client viene controllata tramite l' `ClientCredentialType` attributo [ \<del > di trasporto](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9e038-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="9e038-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9e038-130">TransportCredentialOnly</span></span>|<span data-ttu-id="9e038-131">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="9e038-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9e038-132">ma fornisce l'autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e038-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="9e038-133">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="9e038-133">This mode should be used with caution.</span></span> <span data-ttu-id="9e038-134">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="9e038-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e038-135">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e038-135">Child Elements</span></span>  
  
|<span data-ttu-id="9e038-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e038-136">Element</span></span>|<span data-ttu-id="9e038-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e038-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e038-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="9e038-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="9e038-139">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="9e038-139">Defines the transport security settings.</span></span> <span data-ttu-id="9e038-140">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9e038-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e038-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e038-141">Parent Elements</span></span>  
  
|<span data-ttu-id="9e038-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e038-142">Element</span></span>|<span data-ttu-id="9e038-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e038-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e038-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9e038-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="9e038-145">Elemento di associazione utilizzato per configurare endpoint per i servizi Web di Windows Communication Foundation (WCF) che rispondono a richieste HTTP anziché a messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="9e038-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e038-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e038-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="9e038-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9e038-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9e038-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="9e038-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9e038-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9e038-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9e038-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9e038-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9e038-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="9e038-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9e038-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="9e038-152">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="9e038-153">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="9e038-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
