---
title: <peer> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933779"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="f9dd2-102">\<peer > di \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="f9dd2-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="f9dd2-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="f9dd2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9dd2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9dd2-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f9dd2-105">\<behaviors></span></span>  
<span data-ttu-id="f9dd2-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f9dd2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f9dd2-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f9dd2-107">\<behavior></span></span>  
<span data-ttu-id="f9dd2-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f9dd2-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f9dd2-109">\<> peer</span><span class="sxs-lookup"><span data-stu-id="f9dd2-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9dd2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9dd2-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9dd2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9dd2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9dd2-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9dd2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9dd2-113">Attributes</span></span>  
 <span data-ttu-id="f9dd2-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9dd2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9dd2-115">Child Elements</span></span>  
  
|<span data-ttu-id="f9dd2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9dd2-116">Element</span></span>|<span data-ttu-id="f9dd2-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f9dd2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9dd2-118">\<> certificato</span><span class="sxs-lookup"><span data-stu-id="f9dd2-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="f9dd2-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="f9dd2-120">.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-120">.</span></span>|  
|[<span data-ttu-id="f9dd2-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f9dd2-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="f9dd2-122">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="f9dd2-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="f9dd2-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="f9dd2-124">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9dd2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9dd2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f9dd2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9dd2-126">Element</span></span>|<span data-ttu-id="f9dd2-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9dd2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9dd2-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f9dd2-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="f9dd2-129">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="f9dd2-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9dd2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9dd2-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="f9dd2-131">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="f9dd2-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f9dd2-132">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f9dd2-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f9dd2-133">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f9dd2-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f9dd2-134">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="f9dd2-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="f9dd2-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f9dd2-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
