---
title: <peer>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 2f1cb5689125e2483a74dcac515beb07abbb7c70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934044"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="b4fc1-102">\<> peer dell' \<elemento ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="b4fc1-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="b4fc1-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="b4fc1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b4fc1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b4fc1-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="b4fc1-105">\<behaviors></span></span>  
<span data-ttu-id="b4fc1-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b4fc1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="b4fc1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="b4fc1-107">\<behavior></span></span>  
<span data-ttu-id="b4fc1-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b4fc1-108">\<clientCredentials></span></span>  
<span data-ttu-id="b4fc1-109">\<> peer</span><span class="sxs-lookup"><span data-stu-id="b4fc1-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fc1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4fc1-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4fc1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4fc1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b4fc1-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4fc1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b4fc1-113">Attributes</span></span>  
 <span data-ttu-id="b4fc1-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4fc1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4fc1-115">Child Elements</span></span>  
  
|<span data-ttu-id="b4fc1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4fc1-116">Element</span></span>|<span data-ttu-id="b4fc1-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b4fc1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4fc1-118">\<> certificato</span><span class="sxs-lookup"><span data-stu-id="b4fc1-118">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="b4fc1-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="b4fc1-120">.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-120">.</span></span>|  
|[<span data-ttu-id="b4fc1-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="b4fc1-121">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="b4fc1-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="b4fc1-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="b4fc1-123">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="b4fc1-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4fc1-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4fc1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b4fc1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4fc1-126">Element</span></span>|<span data-ttu-id="b4fc1-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4fc1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4fc1-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b4fc1-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="b4fc1-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4fc1-130">Note</span><span class="sxs-lookup"><span data-stu-id="b4fc1-130">Remarks</span></span>  
 <span data-ttu-id="b4fc1-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="b4fc1-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="b4fc1-132">Per ulteriori informazioni, vedere [Peer Channel autenticazione dei messaggi](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) e [protezione delle applicazioni peer Channel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="b4fc1-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fc1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4fc1-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="b4fc1-134">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b4fc1-134">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="b4fc1-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="b4fc1-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="b4fc1-136">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b4fc1-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b4fc1-137">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b4fc1-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b4fc1-138">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="b4fc1-138">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="b4fc1-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="b4fc1-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
