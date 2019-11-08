---
title: <security> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736398"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="ee2df-102">\<> di sicurezza di \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ee2df-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="ee2df-103">Rappresenta le impostazioni di sicurezza utilizzate con l'elemento [\<> WS2007HttpBinding](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ee2df-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="ee2df-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee2df-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ee2df-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ee2df-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ee2df-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="ee2df-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="ee2df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**WS2007HttpBinding**](ws2007httpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="ee2df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="ee2df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="ee2df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ee2df-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="ee2df-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee2df-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee2df-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee2df-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee2df-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ee2df-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee2df-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee2df-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee2df-113">Attributes</span></span>  
  
|<span data-ttu-id="ee2df-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee2df-114">Attribute</span></span>|<span data-ttu-id="ee2df-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2df-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="ee2df-116">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="ee2df-116">-   Optional.</span></span> <span data-ttu-id="ee2df-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="ee2df-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ee2df-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="ee2df-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="ee2df-119">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ee2df-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ee2df-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="ee2df-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="ee2df-121">Value</span><span class="sxs-lookup"><span data-stu-id="ee2df-121">Value</span></span>|<span data-ttu-id="ee2df-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2df-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="ee2df-123">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="ee2df-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="ee2df-124">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ee2df-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="ee2df-125">Il servizio deve essere configurato con certificati Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="ee2df-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="ee2df-126">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee2df-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="ee2df-127">L'autenticazione client viene controllata tramite l'attributo `ClientCredentials` dell'elemento [\<transport >](transport-of-ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ee2df-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="ee2df-128">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="ee2df-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="ee2df-129">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="ee2df-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="ee2df-130">Questa modalità offre varie funzionalità: è ad esempio possibile stabilire se le credenziali del servizio sono disponibili per i client fuori banda nonché specificare il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="ee2df-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="ee2df-131">L'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="ee2df-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="ee2df-132">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="ee2df-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="ee2df-133">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="ee2df-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee2df-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee2df-134">Child Elements</span></span>  
  
|<span data-ttu-id="ee2df-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee2df-135">Element</span></span>|<span data-ttu-id="ee2df-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2df-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee2df-137">> trasporto \<</span><span class="sxs-lookup"><span data-stu-id="ee2df-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="ee2df-138">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee2df-138">Defines the transport security settings.</span></span> <span data-ttu-id="ee2df-139">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ee2df-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="ee2df-140">Queste impostazioni vengono applicate solo quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="ee2df-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="ee2df-141">\<message ></span><span class="sxs-lookup"><span data-stu-id="ee2df-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="ee2df-142">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ee2df-142">Defines the security settings for the message.</span></span> <span data-ttu-id="ee2df-143">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="ee2df-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="ee2df-144">Queste impostazioni non vengono applicate quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="ee2df-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee2df-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee2df-145">Parent Elements</span></span>  
  
|<span data-ttu-id="ee2df-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee2df-146">Element</span></span>|<span data-ttu-id="ee2df-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2df-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee2df-148">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ee2df-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="ee2df-149">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="ee2df-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee2df-150">Note</span><span class="sxs-lookup"><span data-stu-id="ee2df-150">Remarks</span></span>  
 <span data-ttu-id="ee2df-151">Questo elemento è progettato per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="ee2df-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="ee2df-152">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ee2df-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2df-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee2df-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="ee2df-154">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="ee2df-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ee2df-155">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ee2df-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ee2df-156">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="ee2df-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ee2df-157">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="ee2df-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ee2df-158">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ee2df-158">\<binding></span></span>](bindings.md)
