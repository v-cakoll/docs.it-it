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
ms.openlocfilehash: 4f2fa776711223ace6a4cebce7783b1fa0c148a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="dbd7e-102">Elemento &lt;peer&gt; di &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="dbd7e-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="dbd7e-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="dbd7e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dbd7e-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-105">\<behaviors></span></span>  
<span data-ttu-id="dbd7e-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="dbd7e-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-107">\<behavior></span></span>  
<span data-ttu-id="dbd7e-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-108">\<clientCredentials></span></span>  
<span data-ttu-id="dbd7e-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd7e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbd7e-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbd7e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbd7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dbd7e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbd7e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbd7e-113">Attributes</span></span>  
 <span data-ttu-id="dbd7e-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dbd7e-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbd7e-115">Child Elements</span></span>  
  
|<span data-ttu-id="dbd7e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbd7e-116">Element</span></span>|<span data-ttu-id="dbd7e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd7e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbd7e-118">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="dbd7e-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="dbd7e-120">.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-120">.</span></span>|  
|[<span data-ttu-id="dbd7e-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="dbd7e-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="dbd7e-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="dbd7e-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbd7e-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbd7e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dbd7e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbd7e-126">Element</span></span>|<span data-ttu-id="dbd7e-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd7e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbd7e-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="dbd7e-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="dbd7e-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd7e-130">Note</span><span class="sxs-lookup"><span data-stu-id="dbd7e-130">Remarks</span></span>  
 <span data-ttu-id="dbd7e-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="dbd7e-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="dbd7e-132">Per ulteriori informazioni, vedere [l'autenticazione dei messaggi del canale Peer](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) e [protezione delle applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="dbd7e-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd7e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbd7e-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="dbd7e-134">Rete peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="dbd7e-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="dbd7e-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="dbd7e-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="dbd7e-136">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="dbd7e-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="dbd7e-137">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="dbd7e-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="dbd7e-138">Protezione delle applicazioni del canale Peer</span><span class="sxs-lookup"><span data-stu-id="dbd7e-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="dbd7e-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="dbd7e-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
