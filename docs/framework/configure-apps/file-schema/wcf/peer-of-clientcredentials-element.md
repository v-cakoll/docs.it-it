---
title: <peer>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400103"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="ef57a-102">\<> peer dell' \<elemento ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="ef57a-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="ef57a-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ef57a-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="ef57a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef57a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ef57a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ef57a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ef57a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ef57a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="ef57a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="ef57a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> peer**</span><span class="sxs-lookup"><span data-stu-id="ef57a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef57a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef57a-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef57a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef57a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ef57a-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef57a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef57a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef57a-114">Attributes</span></span>  
 <span data-ttu-id="ef57a-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef57a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef57a-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef57a-116">Child Elements</span></span>  
  
|<span data-ttu-id="ef57a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef57a-117">Element</span></span>|<span data-ttu-id="ef57a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef57a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef57a-119">\<> certificato</span><span class="sxs-lookup"><span data-stu-id="ef57a-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="ef57a-120">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ef57a-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="ef57a-121">.</span><span class="sxs-lookup"><span data-stu-id="ef57a-121">.</span></span>|  
|[<span data-ttu-id="ef57a-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="ef57a-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="ef57a-123">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="ef57a-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="ef57a-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="ef57a-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="ef57a-125">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="ef57a-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef57a-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef57a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ef57a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef57a-127">Element</span></span>|<span data-ttu-id="ef57a-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef57a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef57a-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ef57a-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="ef57a-130">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="ef57a-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef57a-131">Note</span><span class="sxs-lookup"><span data-stu-id="ef57a-131">Remarks</span></span>  
 <span data-ttu-id="ef57a-132">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="ef57a-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="ef57a-133">Per ulteriori informazioni, vedere [Peer Channel autenticazione dei messaggi](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) e [protezione delle applicazioni peer Channel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ef57a-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef57a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef57a-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="ef57a-135">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ef57a-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="ef57a-136">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="ef57a-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="ef57a-137">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ef57a-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ef57a-138">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ef57a-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ef57a-139">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="ef57a-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="ef57a-140">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="ef57a-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
