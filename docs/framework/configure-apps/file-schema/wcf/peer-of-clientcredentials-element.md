---
title: <peer> di <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107237"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="0c177-102">\<peer > di \<clientCredentials > elemento</span><span class="sxs-lookup"><span data-stu-id="0c177-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="0c177-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0c177-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="0c177-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c177-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c177-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0c177-105">\<behaviors></span></span>  
<span data-ttu-id="0c177-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c177-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0c177-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c177-107">\<behavior></span></span>  
<span data-ttu-id="0c177-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0c177-108">\<clientCredentials></span></span>  
<span data-ttu-id="0c177-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="0c177-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c177-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c177-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c177-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0c177-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0c177-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0c177-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c177-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0c177-113">Attributes</span></span>  
 <span data-ttu-id="0c177-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0c177-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c177-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0c177-115">Child Elements</span></span>  
  
|<span data-ttu-id="0c177-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c177-116">Element</span></span>|<span data-ttu-id="0c177-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c177-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c177-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="0c177-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="0c177-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0c177-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="0c177-120">.</span><span class="sxs-lookup"><span data-stu-id="0c177-120">.</span></span>|  
|[<span data-ttu-id="0c177-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="0c177-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="0c177-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="0c177-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="0c177-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="0c177-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="0c177-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="0c177-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c177-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0c177-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0c177-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c177-126">Element</span></span>|<span data-ttu-id="0c177-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c177-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c177-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0c177-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="0c177-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="0c177-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c177-130">Note</span><span class="sxs-lookup"><span data-stu-id="0c177-130">Remarks</span></span>  
 <span data-ttu-id="0c177-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="0c177-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="0c177-132">Per altre informazioni, vedere [l'autenticazione dei messaggi del canale Peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) e [protezione di applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0c177-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c177-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c177-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="0c177-134">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0c177-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="0c177-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="0c177-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- <span data-ttu-id="0c177-136">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0c177-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0c177-137">[Autenticazione personalizzata del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0c177-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0c177-138">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="0c177-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="0c177-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="0c177-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
