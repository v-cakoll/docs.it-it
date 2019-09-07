---
title: <peer> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397635"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="9a6fb-102">\<peer > di \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9a6fb-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="9a6fb-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="9a6fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a6fb-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a6fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9a6fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9a6fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9a6fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="9a6fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> peer**</span><span class="sxs-lookup"><span data-stu-id="9a6fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6fb-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a6fb-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a6fb-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a6fb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9a6fb-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a6fb-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a6fb-114">Attributes</span></span>  
 <span data-ttu-id="9a6fb-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a6fb-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a6fb-116">Child Elements</span></span>  
  
|<span data-ttu-id="9a6fb-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a6fb-117">Element</span></span>|<span data-ttu-id="9a6fb-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9a6fb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a6fb-119">\<> certificato</span><span class="sxs-lookup"><span data-stu-id="9a6fb-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="9a6fb-120">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="9a6fb-121">.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-121">.</span></span>|  
|[<span data-ttu-id="9a6fb-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="9a6fb-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="9a6fb-123">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="9a6fb-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="9a6fb-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="9a6fb-125">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a6fb-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a6fb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9a6fb-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a6fb-127">Element</span></span>|<span data-ttu-id="9a6fb-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a6fb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a6fb-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9a6fb-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="9a6fb-130">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="9a6fb-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a6fb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a6fb-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="9a6fb-132">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="9a6fb-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="9a6fb-133">[Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9a6fb-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="9a6fb-134">[Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9a6fb-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="9a6fb-135">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="9a6fb-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="9a6fb-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9a6fb-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
