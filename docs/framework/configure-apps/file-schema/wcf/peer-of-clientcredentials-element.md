---
title: Elemento &lt;peer&gt; di &lt;clientCredentials&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: accd6c261a393da3ffcffd261d6603d20b8fcb3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="cb429-102">Elemento &lt;peer&gt; di &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="cb429-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="cb429-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="cb429-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="cb429-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cb429-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb429-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="cb429-105">\<behaviors></span></span>  
<span data-ttu-id="cb429-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cb429-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cb429-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="cb429-107">\<behavior></span></span>  
<span data-ttu-id="cb429-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="cb429-108">\<clientCredentials></span></span>  
<span data-ttu-id="cb429-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="cb429-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb429-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb429-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb429-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cb429-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cb429-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cb429-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb429-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="cb429-113">Attributes</span></span>  
 <span data-ttu-id="cb429-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cb429-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb429-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cb429-115">Child Elements</span></span>  
  
|<span data-ttu-id="cb429-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb429-116">Element</span></span>|<span data-ttu-id="cb429-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb429-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb429-118">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="cb429-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="cb429-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="cb429-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="cb429-120">.</span><span class="sxs-lookup"><span data-stu-id="cb429-120">.</span></span>|  
|[<span data-ttu-id="cb429-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="cb429-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="cb429-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="cb429-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="cb429-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="cb429-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="cb429-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="cb429-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb429-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cb429-125">Parent Elements</span></span>  
  
|<span data-ttu-id="cb429-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb429-126">Element</span></span>|<span data-ttu-id="cb429-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb429-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb429-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="cb429-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="cb429-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="cb429-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb429-130">Note</span><span class="sxs-lookup"><span data-stu-id="cb429-130">Remarks</span></span>  
 <span data-ttu-id="cb429-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="cb429-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="cb429-132">Per ulteriori informazioni, vedere [l'autenticazione dei messaggi del canale Peer](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) e [protezione delle applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cb429-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb429-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb429-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="cb429-134">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="cb429-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="cb429-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="cb429-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="cb429-136">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="cb429-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="cb429-137">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="cb429-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="cb429-138">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="cb429-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="cb429-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="cb429-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
