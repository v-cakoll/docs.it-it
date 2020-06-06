---
title: <security> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736398"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="19bbd-102">\<security> di \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="19bbd-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="19bbd-103">Rappresenta le impostazioni di sicurezza utilizzate con l' [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="19bbd-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="19bbd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19bbd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19bbd-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="19bbd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="19bbd-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="19bbd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19bbd-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="19bbd-107">Attributes</span></span>  
  
|<span data-ttu-id="19bbd-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="19bbd-108">Attribute</span></span>|<span data-ttu-id="19bbd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19bbd-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="19bbd-110">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="19bbd-110">-   Optional.</span></span> <span data-ttu-id="19bbd-111">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="19bbd-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="19bbd-112">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="19bbd-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="19bbd-113">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="19bbd-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="19bbd-114">Attributo Mode</span><span class="sxs-lookup"><span data-stu-id="19bbd-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="19bbd-115">Valore</span><span class="sxs-lookup"><span data-stu-id="19bbd-115">Value</span></span>|<span data-ttu-id="19bbd-116">Description</span><span class="sxs-lookup"><span data-stu-id="19bbd-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="19bbd-117">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="19bbd-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="19bbd-118">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="19bbd-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="19bbd-119">Il servizio deve essere configurato con certificati Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="19bbd-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="19bbd-120">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="19bbd-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="19bbd-121">L'autenticazione client viene controllata tramite l' `ClientCredentials` attributo dell' [\<transport>](transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="19bbd-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="19bbd-122">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="19bbd-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="19bbd-123">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="19bbd-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="19bbd-124">Questa modalità offre varie funzionalità: è ad esempio possibile stabilire se le credenziali del servizio sono disponibili per i client fuori banda nonché specificare il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="19bbd-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="19bbd-125">L'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="19bbd-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="19bbd-126">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="19bbd-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="19bbd-127">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="19bbd-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19bbd-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="19bbd-128">Child Elements</span></span>  
  
|<span data-ttu-id="19bbd-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="19bbd-129">Element</span></span>|<span data-ttu-id="19bbd-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19bbd-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="19bbd-131">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="19bbd-131">Defines the transport security settings.</span></span> <span data-ttu-id="19bbd-132">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="19bbd-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="19bbd-133">Queste impostazioni vengono applicate solo quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="19bbd-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="19bbd-134">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="19bbd-134">Defines the security settings for the message.</span></span> <span data-ttu-id="19bbd-135">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="19bbd-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="19bbd-136">Queste impostazioni non vengono applicate quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="19bbd-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19bbd-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="19bbd-137">Parent Elements</span></span>  
  
|<span data-ttu-id="19bbd-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="19bbd-138">Element</span></span>|<span data-ttu-id="19bbd-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19bbd-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="19bbd-140">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="19bbd-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19bbd-141">Commenti</span><span class="sxs-lookup"><span data-stu-id="19bbd-141">Remarks</span></span>  
 <span data-ttu-id="19bbd-142">Questo elemento è progettato per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="19bbd-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="19bbd-143">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="19bbd-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19bbd-144">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="19bbd-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="19bbd-145">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="19bbd-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="19bbd-146">Binding</span><span class="sxs-lookup"><span data-stu-id="19bbd-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="19bbd-147">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="19bbd-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="19bbd-148">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="19bbd-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
