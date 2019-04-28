---
title: <transport> di <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 157637615abafbd5913e4d90b702bb0224d5f121
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788323"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="93cf5-102">\<transport> of \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="93cf5-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="93cf5-103">Specifica le impostazioni per la sicurezza a livello di trasporto quando si usa la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="93cf5-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="93cf5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93cf5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93cf5-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="93cf5-105">\<bindings></span></span>  
<span data-ttu-id="93cf5-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="93cf5-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="93cf5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="93cf5-107">\<binding></span></span>  
<span data-ttu-id="93cf5-108">\<security></span><span class="sxs-lookup"><span data-stu-id="93cf5-108">\<security></span></span>  
<span data-ttu-id="93cf5-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="93cf5-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93cf5-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93cf5-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93cf5-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93cf5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="93cf5-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93cf5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93cf5-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="93cf5-113">Attributes</span></span>  
  
|<span data-ttu-id="93cf5-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="93cf5-114">Attribute</span></span>|<span data-ttu-id="93cf5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cf5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93cf5-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="93cf5-116">credentialType</span></span>|<span data-ttu-id="93cf5-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="93cf5-117">Optional.</span></span> <span data-ttu-id="93cf5-118">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="93cf5-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="93cf5-119">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="93cf5-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="93cf5-120">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="93cf5-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="93cf5-121">Value</span><span class="sxs-lookup"><span data-stu-id="93cf5-121">Value</span></span>|<span data-ttu-id="93cf5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cf5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93cf5-123">Certificato</span><span class="sxs-lookup"><span data-stu-id="93cf5-123">Certificate</span></span>|<span data-ttu-id="93cf5-124">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="93cf5-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="93cf5-125">Password</span><span class="sxs-lookup"><span data-stu-id="93cf5-125">Password</span></span>|<span data-ttu-id="93cf5-126">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="93cf5-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93cf5-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93cf5-127">Child Elements</span></span>  
 <span data-ttu-id="93cf5-128">nessuno</span><span class="sxs-lookup"><span data-stu-id="93cf5-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93cf5-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93cf5-129">Parent Elements</span></span>  
  
|<span data-ttu-id="93cf5-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="93cf5-130">Element</span></span>|<span data-ttu-id="93cf5-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cf5-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93cf5-132">\<security></span><span class="sxs-lookup"><span data-stu-id="93cf5-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="93cf5-133">Definisce le impostazioni di sicurezza per il [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="93cf5-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93cf5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93cf5-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="93cf5-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="93cf5-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="93cf5-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="93cf5-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="93cf5-137">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="93cf5-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="93cf5-138">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="93cf5-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="93cf5-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="93cf5-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
