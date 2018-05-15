---
title: '&lt;peer&gt; di &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: f50c192639df7b7ed35e863821d5b7a8d62f29bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="460ab-102">&lt;peer&gt; di &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="460ab-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="460ab-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="460ab-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="460ab-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="460ab-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="460ab-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="460ab-105">\<behaviors></span></span>  
<span data-ttu-id="460ab-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="460ab-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="460ab-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="460ab-107">\<behavior></span></span>  
<span data-ttu-id="460ab-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="460ab-108">\<serviceCredentials></span></span>  
<span data-ttu-id="460ab-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="460ab-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460ab-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="460ab-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="460ab-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="460ab-111">Attributes and Elements</span></span>  
 <span data-ttu-id="460ab-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="460ab-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="460ab-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="460ab-113">Attributes</span></span>  
 <span data-ttu-id="460ab-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="460ab-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="460ab-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="460ab-115">Child Elements</span></span>  
  
|<span data-ttu-id="460ab-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="460ab-116">Element</span></span>|<span data-ttu-id="460ab-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="460ab-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460ab-118">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="460ab-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="460ab-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="460ab-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="460ab-120">.</span><span class="sxs-lookup"><span data-stu-id="460ab-120">.</span></span>|  
|[<span data-ttu-id="460ab-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="460ab-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="460ab-122">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="460ab-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="460ab-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="460ab-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="460ab-124">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="460ab-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="460ab-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="460ab-125">Parent Elements</span></span>  
  
|<span data-ttu-id="460ab-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="460ab-126">Element</span></span>|<span data-ttu-id="460ab-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="460ab-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460ab-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="460ab-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="460ab-129">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="460ab-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="460ab-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460ab-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="460ab-131">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="460ab-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="460ab-132">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="460ab-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="460ab-133">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="460ab-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="460ab-134">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="460ab-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="460ab-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="460ab-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
