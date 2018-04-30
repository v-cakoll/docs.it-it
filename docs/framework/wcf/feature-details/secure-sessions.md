---
title: Sessioni protette
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 068615510d7e1d73ae260441ccef6536ee6ff317
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="secure-sessions"></a><span data-ttu-id="5ffcf-102">Sessioni protette</span><span class="sxs-lookup"><span data-stu-id="5ffcf-102">Secure Sessions</span></span>
<span data-ttu-id="5ffcf-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] offre sessioni affidabili in grado di garantire che i messaggi vengano ricevuti nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="5ffcf-104">Negli argomenti di questa sezione vengono descritte le implicazioni di sicurezza da tenere presenti quando si crea una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="5ffcf-105">Per ulteriori informazioni sulle sessioni affidabili, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="5ffcf-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ffcf-106">Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token del contesto di sicurezza (SCT, Security Context Token) con stato.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="5ffcf-107">Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="5ffcf-108">Per altre informazioni, vedere [scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="5ffcf-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ffcf-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5ffcf-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="5ffcf-110">Conversazioni e sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="5ffcf-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="5ffcf-111">Il termine "conversazione protetta" è sinonimo di "sessione protetta".</span><span class="sxs-lookup"><span data-stu-id="5ffcf-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="5ffcf-112">In questo argomento viene illustrato il funzionamento di una conversazione protetta nonché i contesti in cui usare tale modello.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="5ffcf-113">Procedura: Creare una sessione sicura</span><span class="sxs-lookup"><span data-stu-id="5ffcf-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="5ffcf-114">Questo argomento descrive i passaggi della procedura di base per creare una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="5ffcf-115">Procedura: Creare un token del contesto di sicurezza per una sessione sicura</span><span class="sxs-lookup"><span data-stu-id="5ffcf-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="5ffcf-116">Questo argomento descrive i passaggi della procedura per creare una Web farm che interagisce con i client tramite una sessione protetta con stato.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="5ffcf-117">Considerazioni sulla sicurezza per le sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="5ffcf-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="5ffcf-118">Questo argomento contiene considerazioni specifiche sulle sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="5ffcf-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="5ffcf-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5ffcf-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="5ffcf-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5ffcf-120">Related Sections</span></span>  
 [<span data-ttu-id="5ffcf-121">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="5ffcf-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="5ffcf-122">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="5ffcf-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ffcf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ffcf-123">See Also</span></span>  
 [<span data-ttu-id="5ffcf-124">Procedura: Abilitare il rilevamento di attacchi di tipo replay dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5ffcf-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [<span data-ttu-id="5ffcf-125">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="5ffcf-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [<span data-ttu-id="5ffcf-126">Procedura: Creare un servizio che richiede sessioni</span><span class="sxs-lookup"><span data-stu-id="5ffcf-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
