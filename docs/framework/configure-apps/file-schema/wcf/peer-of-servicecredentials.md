---
title: <peer> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397635"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="bdfd9-102">\<peer> di \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="bdfd9-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="bdfd9-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="bdfd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdfd9-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdfd9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bdfd9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bdfd9-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdfd9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="bdfd9-107">Attributes</span></span>  
 <span data-ttu-id="bdfd9-108">No.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bdfd9-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bdfd9-109">Child Elements</span></span>  
  
|<span data-ttu-id="bdfd9-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfd9-110">Element</span></span>|<span data-ttu-id="bdfd9-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdfd9-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="bdfd9-112">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="bdfd9-113">.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="bdfd9-114">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="bdfd9-115">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdfd9-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bdfd9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bdfd9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfd9-117">Element</span></span>|<span data-ttu-id="bdfd9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdfd9-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="bdfd9-119">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="bdfd9-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdfd9-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bdfd9-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="bdfd9-121">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="bdfd9-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="bdfd9-122">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bdfd9-122">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="bdfd9-123">[Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bdfd9-123">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="bdfd9-124">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="bdfd9-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="bdfd9-125">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="bdfd9-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
