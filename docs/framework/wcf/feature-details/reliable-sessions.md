---
title: Sessioni affidabili
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16480996b96145873b1d1f84d56af6d1aa863710
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-sessions"></a><span data-ttu-id="78405-102">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="78405-102">Reliable Sessions</span></span>

<span data-ttu-id="78405-103">In questa sezione descrive cosa un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è una sessione affidabile, cosa è utilizzata, come e quando utilizzarla, quali configurazioni di associazione supportano e indicatori di misura su procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="78405-103">This section describes what a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="78405-104">Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="78405-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="78405-105">La sessione affidabile [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce featrues assicurandosi che i messaggi inviati tra endpoint vengono trasferiti su intermediari SOAP o trasporto e recapitati una sola volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="78405-105">The reliable session [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="78405-106">Per utilizzare una sessione affidabile con un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilizzare una delle associazioni fornite dal sistema in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che supporta una sessione affidabile per impostazione predefinita o come opzione, oppure creare un'associazione personalizzata che supporti la sessione.</span><span class="sxs-lookup"><span data-stu-id="78405-106">To use a reliable session with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, either use one of the system-provided bindings in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="78405-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="78405-107">In This Section</span></span>

<span data-ttu-id="78405-108">[Panoramica delle sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="78405-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="78405-109">Descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili e come funzionano.</span><span class="sxs-lookup"><span data-stu-id="78405-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="78405-110">[Procedura: scambiare messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="78405-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="78405-111">Descrive come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="78405-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="78405-112">[Procedura: proteggere i messaggi in sessioni affidabili](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="78405-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="78405-113">Descrive come proteggere una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="78405-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="78405-114">[Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="78405-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="78405-115">Descrive come creare una sessione affidabile su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="78405-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="78405-116">[Procedure consigliate per le sessioni affidabili](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="78405-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="78405-117">Descrive alcune delle procedure consigliate associate all'utilizzo di una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="78405-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="78405-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="78405-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="78405-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78405-119">See Also</span></span>

<span data-ttu-id="78405-120">[Code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="78405-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="78405-121">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="78405-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
