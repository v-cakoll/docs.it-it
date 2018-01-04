---
title: Rete peer-to-peer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496c1191ebb55181ddb999a5a4327d5ff699828c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="d079f-102">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="d079f-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="d079f-103">Il canale peer è una tecnologia di comunicazione peer-to-peer (P2P) a più parti disponibile in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d079f-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="d079f-104">Fornisce un canale di comunicazione P2P basato su messaggi sicuro e scalabile per gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d079f-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="d079f-105">Un esempio comune di applicazione a più parti che può trarre vantaggio da un canale peer è rappresentato da un'applicazione collaborativa, ad esempio una chat, in cui un gruppo di persone comunica l'una con l'altra mediante un sistema peer-to-peer senza server.</span><span class="sxs-lookup"><span data-stu-id="d079f-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="d079f-106">Il canale peer consente la collaborazione P2P, la distribuzione di contenuti, il bilanciamento del carico e l'elaborazione distribuita per scenari aziendali e relativi a utenti.</span><span class="sxs-lookup"><span data-stu-id="d079f-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="d079f-107">Il canale peer è attivato per impostazione predefinita in [!INCLUDE[wv](../../../../includes/wv-md.md)], come lo è [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d079f-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d079f-108">Per accedere alle classi del canale peer, aggiungere riferimenti a System.ServiceModel.dll al progetto.</span><span class="sxs-lookup"><span data-stu-id="d079f-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="d079f-109">Nelle sezioni seguenti vengono fornite informazioni sulla rete peer-to-peer e sull'utilizzo delle classi del canale peer per creare applicazioni di rete abilitate al peer.</span><span class="sxs-lookup"><span data-stu-id="d079f-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d079f-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d079f-110">In This Section</span></span>  
 <span data-ttu-id="d079f-111">[Scenari relativi al canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): descrive gli scenari di sviluppo supportati dalle API del canale Peer, ad esempio la messaggistica, collaborazione, pubblicazione/sottoscrizione elaborazione distribuita e gioco.</span><span class="sxs-lookup"><span data-stu-id="d079f-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="d079f-112">[Concetti relativi al canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): descrive le reti Peer, i nodi Peer, sicurezza del canale Peer e i resolver del Peer.</span><span class="sxs-lookup"><span data-stu-id="d079f-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="d079f-113">[La creazione di un'applicazione del canale Peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): vengono fornite informazioni aggiuntive sullo sviluppo di applicazioni del canale Peer.</span><span class="sxs-lookup"><span data-stu-id="d079f-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="d079f-114">Esempi di codice del canale peer</span><span class="sxs-lookup"><span data-stu-id="d079f-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="d079f-115">Resolver Peer personalizzato del canale peer</span><span class="sxs-lookup"><span data-stu-id="d079f-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/en-us/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="d079f-116">Blog del team del canale peer</span><span class="sxs-lookup"><span data-stu-id="d079f-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="d079f-117">[Blog del Team del canale peer](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="d079f-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
