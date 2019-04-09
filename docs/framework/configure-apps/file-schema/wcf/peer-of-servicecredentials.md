---
title: <peer> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: d726ab460141b1e373a1cabf770b8958f50319eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219148"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="da8ea-102">\<peer > di \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="da8ea-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="da8ea-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="da8ea-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="da8ea-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da8ea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da8ea-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="da8ea-105">\<behaviors></span></span>  
<span data-ttu-id="da8ea-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="da8ea-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="da8ea-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da8ea-107">\<behavior></span></span>  
<span data-ttu-id="da8ea-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="da8ea-108">\<serviceCredentials></span></span>  
<span data-ttu-id="da8ea-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="da8ea-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8ea-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da8ea-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da8ea-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="da8ea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="da8ea-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="da8ea-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da8ea-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="da8ea-113">Attributes</span></span>  
 <span data-ttu-id="da8ea-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="da8ea-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da8ea-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="da8ea-115">Child Elements</span></span>  
  
|<span data-ttu-id="da8ea-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="da8ea-116">Element</span></span>|<span data-ttu-id="da8ea-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da8ea-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da8ea-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="da8ea-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="da8ea-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="da8ea-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="da8ea-120">.</span><span class="sxs-lookup"><span data-stu-id="da8ea-120">.</span></span>|  
|[<span data-ttu-id="da8ea-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="da8ea-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="da8ea-122">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="da8ea-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="da8ea-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="da8ea-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="da8ea-124">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="da8ea-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da8ea-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="da8ea-125">Parent Elements</span></span>  
  
|<span data-ttu-id="da8ea-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="da8ea-126">Element</span></span>|<span data-ttu-id="da8ea-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da8ea-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da8ea-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="da8ea-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="da8ea-129">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="da8ea-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da8ea-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da8ea-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="da8ea-131">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="da8ea-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="da8ea-132">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="da8ea-132">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="da8ea-133">Autenticazione personalizzata dei messaggi del canale</span><span class="sxs-lookup"><span data-stu-id="da8ea-133">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="da8ea-134">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="da8ea-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="da8ea-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="da8ea-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
