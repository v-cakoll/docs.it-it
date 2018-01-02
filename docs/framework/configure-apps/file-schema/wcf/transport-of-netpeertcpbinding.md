---
title: '&lt;transport&gt; di &lt;netPeerTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3e933e1c3468a09b1d6b089b4abf52dad85017
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="d0f33-102">&lt;transport&gt; di &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="d0f33-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="d0f33-103">Specifica le impostazioni di sicurezza a livello di trasporto quando si usa il [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d0f33-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="d0f33-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d0f33-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0f33-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="d0f33-105">\<bindings></span></span>  
<span data-ttu-id="d0f33-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="d0f33-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="d0f33-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d0f33-107">\<binding></span></span>  
<span data-ttu-id="d0f33-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="d0f33-108">\<security></span></span>  
<span data-ttu-id="d0f33-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="d0f33-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f33-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0f33-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0f33-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d0f33-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d0f33-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d0f33-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0f33-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d0f33-113">Attributes</span></span>  
  
|<span data-ttu-id="d0f33-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d0f33-114">Attribute</span></span>|<span data-ttu-id="d0f33-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0f33-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0f33-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="d0f33-116">credentialType</span></span>|<span data-ttu-id="d0f33-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d0f33-117">Optional.</span></span> <span data-ttu-id="d0f33-118">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="d0f33-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="d0f33-119">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d0f33-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="d0f33-120">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="d0f33-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="d0f33-121">Valore</span><span class="sxs-lookup"><span data-stu-id="d0f33-121">Value</span></span>|<span data-ttu-id="d0f33-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0f33-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0f33-123">Certificato</span><span class="sxs-lookup"><span data-stu-id="d0f33-123">Certificate</span></span>|<span data-ttu-id="d0f33-124">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="d0f33-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="d0f33-125">Password</span><span class="sxs-lookup"><span data-stu-id="d0f33-125">Password</span></span>|<span data-ttu-id="d0f33-126">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="d0f33-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0f33-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d0f33-127">Child Elements</span></span>  
 <span data-ttu-id="d0f33-128">None</span><span class="sxs-lookup"><span data-stu-id="d0f33-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0f33-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d0f33-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d0f33-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0f33-130">Element</span></span>|<span data-ttu-id="d0f33-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0f33-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0f33-132">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="d0f33-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="d0f33-133">Definisce le impostazioni di sicurezza per il [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d0f33-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0f33-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0f33-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="d0f33-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="d0f33-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d0f33-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d0f33-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d0f33-137">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d0f33-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d0f33-138">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d0f33-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d0f33-139">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d0f33-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
