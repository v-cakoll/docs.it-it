---
title: Considerazioni sulla sicurezza in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601036"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="eaa58-102">Considerazioni sulla sicurezza in WCF</span><span class="sxs-lookup"><span data-stu-id="eaa58-102">Security Considerations in WCF</span></span>
<span data-ttu-id="eaa58-103">Negli argomenti di questa sezione sono elencati i vari elementi correlati alla sicurezza da considerare durante la progettazione di un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eaa58-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eaa58-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="eaa58-104">In This Section</span></span>  
 [<span data-ttu-id="eaa58-105">Divulgazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="eaa58-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="eaa58-106">Illustra le varie modalità in cui è possibile diffondere o lanciare attacchi alle informazioni e come limitare il problema</span><span class="sxs-lookup"><span data-stu-id="eaa58-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eaa58-107">Elevazione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="eaa58-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="eaa58-108">Descrive gli effetti causati quando all'autore di un attacco vengono assegnate autorizzazioni che vanno oltre quelle concesse inizialmente e come circoscrivere il problema.</span><span class="sxs-lookup"><span data-stu-id="eaa58-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eaa58-109">Attacco Denial of Service</span><span class="sxs-lookup"><span data-stu-id="eaa58-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="eaa58-110">Descrive ciò che avviene quando un sistema non è in grado di elaborare messaggi in modo appropriato e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="eaa58-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="eaa58-111">Manomissione</span><span class="sxs-lookup"><span data-stu-id="eaa58-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="eaa58-112">Descrive la modifica dei messaggi o del recapito dei messaggi e come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="eaa58-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="eaa58-113">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="eaa58-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="eaa58-114">Descrive ciò che avviene quando l'autore dell'attacco copia un flusso di messaggi tra due parti e lo riproduce verso una o più delle parti e spiega come limitare il problema.</span><span class="sxs-lookup"><span data-stu-id="eaa58-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eaa58-115">Considerazioni sulla protezione per le sessioni protette</span><span class="sxs-lookup"><span data-stu-id="eaa58-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="eaa58-116">Descrive gli elementi seguenti che influiscono sulla protezione durante l'implementazione di sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="eaa58-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="eaa58-117">Scenari non supportati</span><span class="sxs-lookup"><span data-stu-id="eaa58-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="eaa58-118">Elenca i diversi scenari che non supportano un particolare aspetto della protezione e che devono essere evitati o presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="eaa58-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eaa58-119">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="eaa58-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="eaa58-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="eaa58-120">Related Sections</span></span>  
 [<span data-ttu-id="eaa58-121">Indicazioni di sicurezza e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="eaa58-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="eaa58-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaa58-122">See also</span></span>

- [<span data-ttu-id="eaa58-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="eaa58-123">Security</span></span>](security.md)
