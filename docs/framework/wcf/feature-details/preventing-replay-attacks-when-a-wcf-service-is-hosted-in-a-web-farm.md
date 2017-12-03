---
title: "Prevenzione degli attacchi di tipo \"replay\" quando un servizio WCF è ospitato in una Web farm"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 383a93bee7a63bef966f4252ace13105d96ae505
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a><span data-ttu-id="a324c-102">Prevenzione degli attacchi di tipo "replay" quando un servizio WCF è ospitato in una Web farm</span><span class="sxs-lookup"><span data-stu-id="a324c-102">Preventing Replay Attacks When a WCF Service is Hosted in a Web Farm</span></span>
<span data-ttu-id="a324c-103">Quando si utilizza la sicurezza dei messaggi. in WCF si impediscono attacchi di tipo replay creando un parametro NONCE in base al messaggio in arrivo e controllando l'oggetto `InMemoryNonceCache` interno per verificare se il parametro NONCE generato è presente.</span><span class="sxs-lookup"><span data-stu-id="a324c-103">When using message security WCF prevents replay attacks by creating a NONCE out of the incoming message and checking the internal `InMemoryNonceCache` to see if the generated NONCE is present.</span></span> <span data-ttu-id="a324c-104">In tal caso, il messaggio viene rimosso come di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="a324c-104">If it is, the message is discarded as a replay.</span></span> <span data-ttu-id="a324c-105">Quando un servizio WCF viene ospitato in una Web farm, poiché `InMemoryNonceCache` non viene condiviso tra i nodi della Web farm, il servizio è vulnerabile agli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="a324c-105">When a WCF service is hosted in a web farm, since the `InMemoryNonceCache` is not shared across the nodes in the web farm, the service is vulnerable to replay attacks.</span></span>  <span data-ttu-id="a324c-106">Per attenuare questo scenario, WCF 4.5 fornisce un punto di estendibilità che consente di implementare la propria cache NONCE condivisa derivando una classe dalla classe astratta <xref:System.ServiceModel.Security.NonceCache>.</span><span class="sxs-lookup"><span data-stu-id="a324c-106">To mitigate this scenario WCF 4.5 provides an extensibility point that allows you to implement your own shared NONCE cache by deriving a class from the abstract class <xref:System.ServiceModel.Security.NonceCache>.</span></span>  
  
## <a name="noncecache-implementation"></a><span data-ttu-id="a324c-107">Implementazione di NonceCache</span><span class="sxs-lookup"><span data-stu-id="a324c-107">NonceCache Implementation</span></span>  
 <span data-ttu-id="a324c-108">Per implementare la propria cache NONCE condivisa, derivare una classe da <xref:System.ServiceModel.Security.NonceCache> ed eseguire l'override dei metodi <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> e <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A>.</span><span class="sxs-lookup"><span data-stu-id="a324c-108">To implement your own shared NONCE cache, derive a class from <xref:System.ServiceModel.Security.NonceCache> and override the <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> and <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> methods.</span></span> <span data-ttu-id="a324c-109"><xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> controllerà se il parametro NONCE specificato esiste nella cache.</span><span class="sxs-lookup"><span data-stu-id="a324c-109"><xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> will check to see if the specified NONCE exists in the cache.</span></span> <span data-ttu-id="a324c-110"><xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> tenterà di aggiungere un parametro NONCE alla cache.</span><span class="sxs-lookup"><span data-stu-id="a324c-110"><xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> will attempt to add a NONCE to the cache.</span></span> <span data-ttu-id="a324c-111">Una volta implementata, la classe viene associata creando un'istanza e assegnandola a <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> per il rilevamento di attacchi di tipo replay lato client e a <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> per il rilevamento di attacchi di tipo replay lato server.</span><span class="sxs-lookup"><span data-stu-id="a324c-111">Once the class is implemented, you hook it up by instantiating an instance and assigning it to <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> for client-side replay detection and <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> for server-side replay detection.</span></span> <span data-ttu-id="a324c-112">Non esiste alcun supporto di configurazione predefinito per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a324c-112">There is no out of the box configuration support for this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a324c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a324c-113">See Also</span></span>  
 [<span data-ttu-id="a324c-114">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a324c-114">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="a324c-115">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a324c-115">SymmetricSecurityBindingElement</span></span>](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)
