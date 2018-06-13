---
title: Elemento &lt;peer&gt; di &lt;clientCredentials&gt;
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d64f682f67dcc7c4f0c0f1600938f8ff9ac0dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746475"
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="f1bee-102">Elemento &lt;peer&gt; di &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="f1bee-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="f1bee-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f1bee-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="f1bee-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f1bee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f1bee-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f1bee-105">\<behaviors></span></span>  
<span data-ttu-id="f1bee-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f1bee-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f1bee-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f1bee-107">\<behavior></span></span>  
<span data-ttu-id="f1bee-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f1bee-108">\<clientCredentials></span></span>  
<span data-ttu-id="f1bee-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="f1bee-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1bee-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1bee-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1bee-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1bee-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f1bee-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1bee-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1bee-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1bee-113">Attributes</span></span>  
 <span data-ttu-id="f1bee-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f1bee-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1bee-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1bee-115">Child Elements</span></span>  
  
|<span data-ttu-id="f1bee-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1bee-116">Element</span></span>|<span data-ttu-id="f1bee-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1bee-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1bee-118">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="f1bee-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="f1bee-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f1bee-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="f1bee-120">.</span><span class="sxs-lookup"><span data-stu-id="f1bee-120">.</span></span>|  
|[<span data-ttu-id="f1bee-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1bee-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="f1bee-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="f1bee-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="f1bee-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1bee-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="f1bee-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="f1bee-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1bee-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1bee-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f1bee-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1bee-126">Element</span></span>|<span data-ttu-id="f1bee-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1bee-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1bee-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f1bee-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="f1bee-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="f1bee-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1bee-130">Note</span><span class="sxs-lookup"><span data-stu-id="f1bee-130">Remarks</span></span>  
 <span data-ttu-id="f1bee-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="f1bee-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="f1bee-132">Per ulteriori informazioni, vedere [l'autenticazione dei messaggi del canale Peer](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) e [protezione delle applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f1bee-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bee-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1bee-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="f1bee-134">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="f1bee-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="f1bee-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="f1bee-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="f1bee-136">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="f1bee-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="f1bee-137">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="f1bee-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="f1bee-138">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="f1bee-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="f1bee-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f1bee-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
