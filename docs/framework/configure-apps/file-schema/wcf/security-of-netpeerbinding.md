---
title: <security> di <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738654"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="d125a-102">\<security> di \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="d125a-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="d125a-103">Definisce le impostazioni di sicurezza dell'oggetto [\<netPeerTcpBinding>](netpeertcpbinding.md) , incluso il tipo di autenticazione utilizzato e la sicurezza utilizzata per il trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d125a-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="d125a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d125a-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d125a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d125a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d125a-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d125a-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d125a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="d125a-107">Attributes</span></span>  
  
|<span data-ttu-id="d125a-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d125a-108">Attribute</span></span>|<span data-ttu-id="d125a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d125a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d125a-110">mode</span><span class="sxs-lookup"><span data-stu-id="d125a-110">mode</span></span>|<span data-ttu-id="d125a-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d125a-111">Optional.</span></span> <span data-ttu-id="d125a-112">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d125a-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="d125a-113">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="d125a-113">The default value is `Message`.</span></span> <span data-ttu-id="d125a-114">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="d125a-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="d125a-115">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="d125a-115">mode Attribute</span></span>  
  
|<span data-ttu-id="d125a-116">Valore</span><span class="sxs-lookup"><span data-stu-id="d125a-116">Value</span></span>|<span data-ttu-id="d125a-117">Description</span><span class="sxs-lookup"><span data-stu-id="d125a-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d125a-118">Message</span><span class="sxs-lookup"><span data-stu-id="d125a-118">Message</span></span>|<span data-ttu-id="d125a-119">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="d125a-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="d125a-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="d125a-120">None</span></span>|<span data-ttu-id="d125a-121">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d125a-121">Security is disabled.</span></span>|  
|<span data-ttu-id="d125a-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d125a-122">Transport</span></span>|<span data-ttu-id="d125a-123">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d125a-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="d125a-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="d125a-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="d125a-125">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="d125a-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="d125a-126">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="d125a-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d125a-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d125a-127">Child Elements</span></span>  
  
|<span data-ttu-id="d125a-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d125a-128">Element</span></span>|<span data-ttu-id="d125a-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d125a-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="d125a-130">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d125a-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="d125a-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d125a-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d125a-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d125a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d125a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d125a-133">Element</span></span>|<span data-ttu-id="d125a-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d125a-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d125a-135">Definisce tutte le funzionalità di associazione di [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d125a-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d125a-136">Commenti</span><span class="sxs-lookup"><span data-stu-id="d125a-136">Remarks</span></span>  
 <span data-ttu-id="d125a-137">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="d125a-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d125a-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d125a-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="d125a-139">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="d125a-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d125a-140">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="d125a-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="d125a-141">Binding</span><span class="sxs-lookup"><span data-stu-id="d125a-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d125a-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d125a-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d125a-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d125a-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
