---
title: Sessioni affidabili
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735425"
---
# <a name="reliable-sessions"></a><span data-ttu-id="ff6b7-102">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="ff6b7-102">Reliable Sessions</span></span>

<span data-ttu-id="ff6b7-103">In questa sezione vengono descritte quali un Windows Communication Foundation (WCF) è una sessione affidabile, ciò che viene utilizzata, come e quando utilizzarla, quali configurazioni di binding supportano. vengono inoltre definite le procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="ff6b7-104">Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="ff6b7-105">La sessione affidabile WCF fornisce funzionalità garantendo che i messaggi inviati tra gli endpoint vengono trasferiti su intermediari SOAP o di trasporto e recapitati solo una volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="ff6b7-106">Per usare una sessione affidabile con un'applicazione WCF, utilizzare una delle associazioni fornite dal sistema in WCF che supportano una sessione affidabile per impostazione predefinita o come opzione o creare un'associazione personalizzata che supporti la sessione.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff6b7-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ff6b7-107">In This Section</span></span>

<span data-ttu-id="ff6b7-108">[Panoramica delle sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ff6b7-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="ff6b7-109">Descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili e come funzionano.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="ff6b7-110">[Procedura: Scambiare messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="ff6b7-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="ff6b7-111">Descrive come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="ff6b7-112">[Procedura: Proteggere i messaggi in sessioni affidabili](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="ff6b7-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="ff6b7-113">Descrive come proteggere una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="ff6b7-114">[Procedura: Creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="ff6b7-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="ff6b7-115">Descrive come creare una sessione affidabile su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="ff6b7-116">[Le procedure consigliate per le sessioni affidabili](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="ff6b7-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="ff6b7-117">Descrive alcune delle procedure consigliate associate all'utilizzo di una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="ff6b7-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="ff6b7-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ff6b7-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="ff6b7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff6b7-119">See also</span></span>

- [<span data-ttu-id="ff6b7-120">Code e sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="ff6b7-120">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="ff6b7-121">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="ff6b7-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
