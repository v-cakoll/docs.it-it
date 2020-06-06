---
title: <security> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738632"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="40dc5-102">\<security> di \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="40dc5-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="40dc5-103">Specifica i requisiti di sicurezza per un endpoint configurato con un [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="40dc5-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="40dc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40dc5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40dc5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="40dc5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="40dc5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="40dc5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40dc5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="40dc5-107">Attributes</span></span>  
  
|<span data-ttu-id="40dc5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="40dc5-108">Attribute</span></span>|<span data-ttu-id="40dc5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40dc5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40dc5-110">mode</span><span class="sxs-lookup"><span data-stu-id="40dc5-110">mode</span></span>|<span data-ttu-id="40dc5-111">Consente di specificare se un endpoint usa la sicurezza a livello di trasporto o se non usa alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="40dc5-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="40dc5-112">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="40dc5-112">The default is `None`.</span></span> <span data-ttu-id="40dc5-113">L'attributo è di tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="40dc5-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="40dc5-114">Attributo Mode</span><span class="sxs-lookup"><span data-stu-id="40dc5-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="40dc5-115">Valore</span><span class="sxs-lookup"><span data-stu-id="40dc5-115">Value</span></span>|<span data-ttu-id="40dc5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40dc5-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40dc5-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="40dc5-117">None</span></span>|<span data-ttu-id="40dc5-118">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="40dc5-118">Security is disabled.</span></span>|  
|<span data-ttu-id="40dc5-119">Trasporto</span><span class="sxs-lookup"><span data-stu-id="40dc5-119">Transport</span></span>|<span data-ttu-id="40dc5-120">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="40dc5-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="40dc5-121">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="40dc5-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="40dc5-122">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="40dc5-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="40dc5-123">L'autenticazione client viene controllata tramite l' `ClientCredentialType` attributo dell'oggetto [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="40dc5-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="40dc5-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="40dc5-124">TransportCredentialOnly</span></span>|<span data-ttu-id="40dc5-125">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="40dc5-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="40dc5-126">ma fornisce l'autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="40dc5-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="40dc5-127">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="40dc5-127">This mode should be used with caution.</span></span> <span data-ttu-id="40dc5-128">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="40dc5-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40dc5-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="40dc5-129">Child Elements</span></span>  
  
|<span data-ttu-id="40dc5-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="40dc5-130">Element</span></span>|<span data-ttu-id="40dc5-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40dc5-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="40dc5-132">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="40dc5-132">Defines the transport security settings.</span></span> <span data-ttu-id="40dc5-133">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="40dc5-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40dc5-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="40dc5-134">Parent Elements</span></span>  
  
|<span data-ttu-id="40dc5-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="40dc5-135">Element</span></span>|<span data-ttu-id="40dc5-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40dc5-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="40dc5-137">Elemento di associazione utilizzato per configurare endpoint per i servizi Web di Windows Communication Foundation (WCF) che rispondono a richieste HTTP anziché a messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="40dc5-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40dc5-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="40dc5-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="40dc5-139">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="40dc5-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="40dc5-140">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="40dc5-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="40dc5-141">Binding</span><span class="sxs-lookup"><span data-stu-id="40dc5-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="40dc5-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="40dc5-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="40dc5-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="40dc5-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="40dc5-144">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="40dc5-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
