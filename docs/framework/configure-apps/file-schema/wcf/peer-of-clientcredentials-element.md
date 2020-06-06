---
title: <peer>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400103"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="7a887-102">\<peer>dell' \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="7a887-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="7a887-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7a887-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="7a887-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a887-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a887-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7a887-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7a887-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7a887-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a887-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a887-107">Attributes</span></span>  
 <span data-ttu-id="7a887-108">No.</span><span class="sxs-lookup"><span data-stu-id="7a887-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a887-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a887-109">Child Elements</span></span>  
  
|<span data-ttu-id="7a887-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a887-110">Element</span></span>|<span data-ttu-id="7a887-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a887-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="7a887-112">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7a887-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="7a887-113">.</span><span class="sxs-lookup"><span data-stu-id="7a887-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="7a887-114">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="7a887-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="7a887-115">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="7a887-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a887-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7a887-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7a887-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a887-117">Element</span></span>|<span data-ttu-id="7a887-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a887-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="7a887-119">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7a887-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a887-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="7a887-120">Remarks</span></span>  
 <span data-ttu-id="7a887-121">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="7a887-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="7a887-122">Per ulteriori informazioni, vedere [Peer Channel autenticazione dei messaggi](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) e [protezione delle applicazioni peer Channel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="7a887-122">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a887-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7a887-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="7a887-124">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7a887-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="7a887-125">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7a887-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="7a887-126">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7a887-126">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="7a887-127">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7a887-127">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="7a887-128">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="7a887-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="7a887-129">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="7a887-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
