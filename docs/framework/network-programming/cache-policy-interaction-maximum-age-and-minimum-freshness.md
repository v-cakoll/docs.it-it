---
title: "Interazione tra criteri di cache: durata massima e validità minima"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 75729fc92c6a4bfa0f5ad73b8bbd4b28456f21e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="f0fbb-102">Interazione tra criteri di cache: durata massima e validità minima</span><span class="sxs-lookup"><span data-stu-id="f0fbb-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>
<span data-ttu-id="f0fbb-103">Per garantire che all'applicazione client venga restituito il contenuto più aggiornato, l'interazione tra criteri di cache del client e requisiti di riconvalida del server determina sempre la creazione dei criteri di cache più conservativi.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="f0fbb-104">In tutti gli esempi di questo argomento vengono illustrati i criteri di cache per una risorsa memorizzata nella cache il 1° gennaio con scadenza il 4 gennaio.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="f0fbb-105">Gli esempi seguenti illustrano i criteri di cache risultanti dall'interazione tra il valore di durata massima (`maxAge`) e il valore di validità minima (`minFresh`).</span><span class="sxs-lookup"><span data-stu-id="f0fbb-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
-   <span data-ttu-id="f0fbb-106">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e `minFresh` non viene specificato, il contenuto viene riconvalidato il 3 gennaio.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="f0fbb-107">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 1 giorno, in base sia al valore di `maxAge`</span><span class="sxs-lookup"><span data-stu-id="f0fbb-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="f0fbb-108">sia al valore di `minFresh`, il contenuto rimane valido fino al 3 gennaio,</span><span class="sxs-lookup"><span data-stu-id="f0fbb-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="f0fbb-109">data in cui deve essere riconvalidato.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="f0fbb-110">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 2 giorni, in base al valore di `maxAge` il contenuto rimane valido fino al 3 gennaio,</span><span class="sxs-lookup"><span data-stu-id="f0fbb-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="f0fbb-111">mentre in base al valore di `minFresh` è valido fino al 2 gennaio.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="f0fbb-112">Il contenuto deve essere quindi riconvalidato il 2 gennaio.</span><span class="sxs-lookup"><span data-stu-id="f0fbb-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fbb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0fbb-113">See Also</span></span>  
 [<span data-ttu-id="f0fbb-114">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f0fbb-114">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="f0fbb-115">Criteri di cache</span><span class="sxs-lookup"><span data-stu-id="f0fbb-115">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="f0fbb-116">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="f0fbb-116">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="f0fbb-117">Criteri di cache basati sull'ora</span><span class="sxs-lookup"><span data-stu-id="f0fbb-117">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="f0fbb-118">Configurazione della memorizzazione nella cache per applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f0fbb-118">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="f0fbb-119">Interazione tra criteri di cache: durata massima e obsolescenza massima</span><span class="sxs-lookup"><span data-stu-id="f0fbb-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
