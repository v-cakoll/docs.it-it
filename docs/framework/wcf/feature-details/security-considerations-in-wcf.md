---
title: Considerazioni sulla sicurezza in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 9d26acf8443967bff36637c482dd3270ef034f40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497529"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="1d89f-102">Considerazioni sulla sicurezza in WCF</span><span class="sxs-lookup"><span data-stu-id="1d89f-102">Security Considerations in WCF</span></span>
<span data-ttu-id="1d89f-103">Negli argomenti di questa sezione elencano vari elementi correlati alla sicurezza da considerare quando si progetta un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1d89f-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d89f-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1d89f-104">In This Section</span></span>  
 [<span data-ttu-id="1d89f-105">Divulgazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="1d89f-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="1d89f-106">Illustra le varie modalità in cui è possibile diffondere o lanciare attacchi alle informazioni e come limitare il problema</span><span class="sxs-lookup"><span data-stu-id="1d89f-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="1d89f-107">Elevazione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="1d89f-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="1d89f-108">Descrive gli effetti causati quando all'autore di un attacco vengono assegnate autorizzazioni che vanno oltre quelle concesse inizialmente e come circoscrivere il problema.</span><span class="sxs-lookup"><span data-stu-id="1d89f-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="1d89f-109">Negazione del servizio</span><span class="sxs-lookup"><span data-stu-id="1d89f-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="1d89f-110">Descrive ciò che avviene quando un sistema non è in grado di elaborare messaggi in modo appropriato e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="1d89f-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="1d89f-111">Manomissioni</span><span class="sxs-lookup"><span data-stu-id="1d89f-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="1d89f-112">Descrive la modifica dei messaggi o del recapito dei messaggi e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="1d89f-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="1d89f-113">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="1d89f-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="1d89f-114">Descrive ciò che avviene quando l'autore dell'attacco copia un flusso di messaggi tra due parti e lo riproduce verso una o più delle parti e spiega come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="1d89f-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="1d89f-115">Considerazioni sulla sicurezza per le sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="1d89f-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="1d89f-116">Descrive gli elementi seguenti che influiscono sulla protezione durante l'implementazione di sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="1d89f-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="1d89f-117">Scenari non supportati</span><span class="sxs-lookup"><span data-stu-id="1d89f-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="1d89f-118">Elenca i diversi scenari che non supportano un particolare aspetto della protezione e che devono essere evitati o presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="1d89f-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1d89f-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1d89f-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="1d89f-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1d89f-120">Related Sections</span></span>  
 [<span data-ttu-id="1d89f-121">Linee guida e procedure consigliate per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d89f-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d89f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d89f-122">See Also</span></span>  
 [<span data-ttu-id="1d89f-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1d89f-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
