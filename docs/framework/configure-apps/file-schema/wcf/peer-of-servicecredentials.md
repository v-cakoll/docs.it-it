---
title: '&lt;peer&gt; di &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79af459aae2eef0544d713b86e8534635fcdd141
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="c64ed-102">&lt;peer&gt; di &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="c64ed-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="c64ed-103">Specifica le credenziali correnti per un nodo peer.</span><span class="sxs-lookup"><span data-stu-id="c64ed-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="c64ed-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c64ed-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c64ed-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="c64ed-105">\<behaviors></span></span>  
<span data-ttu-id="c64ed-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c64ed-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c64ed-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c64ed-107">\<behavior></span></span>  
<span data-ttu-id="c64ed-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c64ed-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c64ed-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="c64ed-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64ed-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c64ed-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c64ed-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c64ed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c64ed-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c64ed-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c64ed-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c64ed-113">Attributes</span></span>  
 <span data-ttu-id="c64ed-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c64ed-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c64ed-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c64ed-115">Child Elements</span></span>  
  
|<span data-ttu-id="c64ed-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c64ed-116">Element</span></span>|<span data-ttu-id="c64ed-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c64ed-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c64ed-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="c64ed-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="c64ed-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di servizi peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="c64ed-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="c64ed-120">.</span><span class="sxs-lookup"><span data-stu-id="c64ed-120">.</span></span>|  
|[<span data-ttu-id="c64ed-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="c64ed-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="c64ed-122">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c64ed-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="c64ed-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="c64ed-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="c64ed-124">Specifica le opzioni di autenticazione dei servizi peer.</span><span class="sxs-lookup"><span data-stu-id="c64ed-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c64ed-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c64ed-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c64ed-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c64ed-126">Element</span></span>|<span data-ttu-id="c64ed-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c64ed-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c64ed-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c64ed-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="c64ed-129">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="c64ed-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c64ed-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c64ed-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="c64ed-131">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c64ed-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="c64ed-132">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="c64ed-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="c64ed-133">Autenticazione personalizzata canale peer</span><span class="sxs-lookup"><span data-stu-id="c64ed-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="c64ed-134">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="c64ed-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="c64ed-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c64ed-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
