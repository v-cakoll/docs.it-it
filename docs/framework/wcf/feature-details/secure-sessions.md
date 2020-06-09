---
title: Sessioni protette
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590085"
---
# <a name="secure-sessions"></a><span data-ttu-id="d1392-102">Sessioni protette</span><span class="sxs-lookup"><span data-stu-id="d1392-102">Secure Sessions</span></span>
<span data-ttu-id="d1392-103">Una funzionalità di Windows Communication Foundation (WCF) è costituita da sessioni affidabili che garantiscono la ricezione di messaggi nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="d1392-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="d1392-104">Negli argomenti di questa sezione vengono descritte le implicazioni di sicurezza da tenere presenti quando si crea una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="d1392-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="d1392-105">Per ulteriori informazioni sulle sessioni affidabili, vedere [Using Sessions](../using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d1392-105">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1392-106">Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token del contesto di sicurezza (SCT, Security Context Token) con stato.</span><span class="sxs-lookup"><span data-stu-id="d1392-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="d1392-107">Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="d1392-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="d1392-108">Per altre informazioni, vedere [scenari non supportati](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="d1392-108">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1392-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d1392-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="d1392-110">Conversazioni e sessioni protette</span><span class="sxs-lookup"><span data-stu-id="d1392-110">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="d1392-111">Il termine "conversazione protetta" è sinonimo di "sessione protetta".</span><span class="sxs-lookup"><span data-stu-id="d1392-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="d1392-112">In questo argomento viene illustrato il funzionamento di una conversazione protetta nonché i contesti in cui utilizzare tale modello.</span><span class="sxs-lookup"><span data-stu-id="d1392-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="d1392-113">Procedura: creare una sessione protetta</span><span class="sxs-lookup"><span data-stu-id="d1392-113">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="d1392-114">Questo argomento descrive i passaggi della procedura di base per creare una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="d1392-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="d1392-115">Procedura: creare un token di contesto di sicurezza per una sessione sicura</span><span class="sxs-lookup"><span data-stu-id="d1392-115">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="d1392-116">Questo argomento descrive i passaggi della procedura per creare una Web farm che interagisce con i client tramite una sessione protetta con stato.</span><span class="sxs-lookup"><span data-stu-id="d1392-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="d1392-117">Considerazioni sulla protezione per le sessioni protette</span><span class="sxs-lookup"><span data-stu-id="d1392-117">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="d1392-118">Questo argomento contiene considerazioni specifiche sulle sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="d1392-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="d1392-119">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="d1392-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="d1392-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d1392-120">Related Sections</span></span>  
 [<span data-ttu-id="d1392-121">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="d1392-121">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="d1392-122">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="d1392-122">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1392-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1392-123">See also</span></span>

- [<span data-ttu-id="d1392-124">Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d1392-124">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="d1392-125">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="d1392-125">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="d1392-126">Procedura: creare un servizio che richiede sessioni</span><span class="sxs-lookup"><span data-stu-id="d1392-126">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
