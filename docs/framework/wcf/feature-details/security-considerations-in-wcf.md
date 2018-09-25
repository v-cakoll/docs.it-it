---
title: Considerazioni sulla sicurezza in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
author: BrucePerlerMS
ms.openlocfilehash: f26369a567e89fc502f777383c22e74b96fe503c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47109511"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="59587-102">Considerazioni sulla sicurezza in WCF</span><span class="sxs-lookup"><span data-stu-id="59587-102">Security Considerations in WCF</span></span>
<span data-ttu-id="59587-103">Negli argomenti di questa sezione elenca i vari elementi correlati alla sicurezza da considerare quando si progetta un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="59587-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59587-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="59587-104">In This Section</span></span>  
 [<span data-ttu-id="59587-105">Divulgazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="59587-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="59587-106">Illustra le varie modalità in cui è possibile diffondere o lanciare attacchi alle informazioni e come limitare il problema</span><span class="sxs-lookup"><span data-stu-id="59587-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="59587-107">Elevazione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="59587-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="59587-108">Descrive gli effetti causati quando all'autore di un attacco vengono assegnate autorizzazioni che vanno oltre quelle concesse inizialmente e come circoscrivere il problema.</span><span class="sxs-lookup"><span data-stu-id="59587-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="59587-109">Negazione del servizio</span><span class="sxs-lookup"><span data-stu-id="59587-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="59587-110">Descrive ciò che avviene quando un sistema non è in grado di elaborare messaggi in modo appropriato e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="59587-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="59587-111">Manomissioni</span><span class="sxs-lookup"><span data-stu-id="59587-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="59587-112">Descrive la modifica dei messaggi o del recapito dei messaggi e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="59587-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="59587-113">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="59587-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="59587-114">Descrive ciò che avviene quando l'autore dell'attacco copia un flusso di messaggi tra due parti e lo riproduce verso una o più delle parti e spiega come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="59587-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="59587-115">Considerazioni sulla sicurezza per le sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="59587-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="59587-116">Descrive gli elementi seguenti che influiscono sulla protezione durante l'implementazione di sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="59587-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="59587-117">Scenari non supportati</span><span class="sxs-lookup"><span data-stu-id="59587-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="59587-118">Elenca i diversi scenari che non supportano un particolare aspetto della protezione e che devono essere evitati o presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="59587-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="59587-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="59587-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="59587-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="59587-120">Related Sections</span></span>  
 [<span data-ttu-id="59587-121">Linee guida e procedure consigliate per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="59587-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="59587-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59587-122">See Also</span></span>  
 [<span data-ttu-id="59587-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="59587-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
