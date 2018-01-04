---
title: Considerazioni sulla sicurezza in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f35bd56bdc69f8c57a7e46984778051b57b7a06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="58048-102">Considerazioni sulla sicurezza in WCF</span><span class="sxs-lookup"><span data-stu-id="58048-102">Security Considerations in WCF</span></span>
<span data-ttu-id="58048-103">Negli argomenti di questa sezione vengono elencati i vari elementi relativi alla protezione che è necessario considerare nella progettazione di un'applicazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58048-103">The topics in this section list various security-related items to consider when designing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58048-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="58048-104">In This Section</span></span>  
 [<span data-ttu-id="58048-105">Divulgazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="58048-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="58048-106">Illustra le varie modalità in cui è possibile diffondere o lanciare attacchi alle informazioni e come limitare il problema</span><span class="sxs-lookup"><span data-stu-id="58048-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="58048-107">Elevazione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="58048-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="58048-108">Descrive gli effetti causati quando all'autore di un attacco vengono assegnate autorizzazioni che vanno oltre quelle concesse inizialmente e come circoscrivere il problema.</span><span class="sxs-lookup"><span data-stu-id="58048-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="58048-109">Negazione del servizio</span><span class="sxs-lookup"><span data-stu-id="58048-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="58048-110">Descrive ciò che avviene quando un sistema non è in grado di elaborare messaggi in modo appropriato e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="58048-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="58048-111">Manomissioni</span><span class="sxs-lookup"><span data-stu-id="58048-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="58048-112">Descrive la modifica dei messaggi o del recapito dei messaggi e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="58048-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="58048-113">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="58048-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="58048-114">Descrive ciò che avviene quando l'autore dell'attacco copia un flusso di messaggi tra due parti e lo riproduce verso una o più delle parti e spiega come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="58048-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="58048-115">Considerazioni sulla sicurezza per le sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="58048-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="58048-116">Descrive gli elementi seguenti che influiscono sulla protezione durante l'implementazione di sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="58048-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="58048-117">Scenari non supportati</span><span class="sxs-lookup"><span data-stu-id="58048-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="58048-118">Elenca i diversi scenari che non supportano un particolare aspetto della protezione e che devono essere evitati o presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="58048-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="58048-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="58048-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="58048-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="58048-120">Related Sections</span></span>  
 [<span data-ttu-id="58048-121">Linee guida e procedure consigliate per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="58048-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="58048-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58048-122">See Also</span></span>  
 [<span data-ttu-id="58048-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="58048-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
