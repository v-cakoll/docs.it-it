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
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590540"
---
# <a name="reliable-sessions"></a><span data-ttu-id="9d3f0-102">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="9d3f0-102">Reliable Sessions</span></span>

<span data-ttu-id="9d3f0-103">In questa sezione viene descritta la modalità di utilizzo di una sessione affidabile Windows Communication Foundation (WCF), come e quando utilizzarne una, le configurazioni di binding che la supportano e i puntatori alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="9d3f0-104">Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="9d3f0-105">La sessione affidabile WCF fornisce funzionalità che assicurano che i messaggi inviati tra gli endpoint vengano trasferiti tra gli intermediari SOAP o di trasporto e vengano recapitati solo una volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="9d3f0-106">Per utilizzare una sessione affidabile con un'applicazione WCF, utilizzare una delle associazioni fornite dal sistema in WCF che supportano una sessione affidabile per impostazione predefinita o come opzione oppure creare un'associazione personalizzata che supporti la sessione.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9d3f0-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9d3f0-107">In This Section</span></span>

<span data-ttu-id="9d3f0-108">[Panoramica delle sessioni affidabili](reliable-sessions-overview.md) Descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili e il loro funzionamento.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-108">[Reliable Sessions Overview](reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="9d3f0-109">[Procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md) Viene descritto come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-109">[How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="9d3f0-110">[Procedura: proteggere i messaggi all'interno di sessioni affidabili](how-to-secure-messages-within-reliable-sessions.md) Viene descritto come proteggere una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-110">[How to: Secure Messages within Reliable Sessions](how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="9d3f0-111">[Procedura: creare un'associazione di sessione affidabile personalizzata con https](how-to-create-a-custom-reliable-session-binding-with-https.md) Viene descritto come creare una sessione affidabile su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-111">[How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="9d3f0-112">[Procedure consigliate per le sessioni affidabili](best-practices-for-reliable-sessions.md) Vengono descritte alcune delle procedure consigliate associate all'utilizzo di una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="9d3f0-112">[Best Practices for Reliable Sessions](best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="9d3f0-113">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="9d3f0-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="9d3f0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d3f0-114">See also</span></span>

- [<span data-ttu-id="9d3f0-115">Code e sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="9d3f0-115">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
- [<span data-ttu-id="9d3f0-116">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="9d3f0-116">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
