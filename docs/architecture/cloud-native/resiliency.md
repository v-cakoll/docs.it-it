---
title: Resilienza cloud nativa
description: Architettura di app .NET cloud native per Azure | Resilienza nativa del cloud
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613772"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="8076a-103">Resilienza cloud nativa</span><span class="sxs-lookup"><span data-stu-id="8076a-103">Cloud-native resiliency</span></span>

<span data-ttu-id="8076a-104">La resilienza è la capacità del sistema di reagire agli errori e rimane comunque funzionante.</span><span class="sxs-lookup"><span data-stu-id="8076a-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="8076a-105">Non si tratta di evitare errori, ma di accettare un errore e costruire i servizi nativi del cloud per rispondervi.</span><span class="sxs-lookup"><span data-stu-id="8076a-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="8076a-106">Si vuole tornare a uno stato completamente funzionante più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="8076a-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="8076a-107">Diversamente dalle tradizionali applicazioni monolitiche, in cui tutto viene eseguito insieme in un unico processo, i sistemi nativi del cloud adottano un'architettura distribuita, come illustrato nella figura 6-1:</span><span class="sxs-lookup"><span data-stu-id="8076a-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![Ambiente nativo cloud distribuito](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="8076a-109">**Figura 6-1.**</span><span class="sxs-lookup"><span data-stu-id="8076a-109">**Figure 6-1.**</span></span> <span data-ttu-id="8076a-110">Ambiente nativo cloud distribuito</span><span class="sxs-lookup"><span data-stu-id="8076a-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="8076a-111">Nella figura precedente ogni microservizio e [servizio di backup](https://12factor.net/backing-services) basato sul cloud vengono eseguiti in un processo separato, attraverso l'infrastruttura server, comunicando tramite chiamate basate su rete.</span><span class="sxs-lookup"><span data-stu-id="8076a-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="8076a-112">Operando in questo ambiente, un servizio deve essere sensibile a molti problemi diversi:</span><span class="sxs-lookup"><span data-stu-id="8076a-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="8076a-113">Latenza di rete imprevista: tempo impiegato da una richiesta di servizio per il trasferimento al ricevitore e viceversa.</span><span class="sxs-lookup"><span data-stu-id="8076a-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="8076a-114">Errori [temporanei](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) : errori di connettività di rete di breve durata.</span><span class="sxs-lookup"><span data-stu-id="8076a-114">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="8076a-115">Blocco mediante un'operazione sincrona a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="8076a-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="8076a-116">Un processo host che si è arrestato in modo anomalo e verrà riavviato o spostato.</span><span class="sxs-lookup"><span data-stu-id="8076a-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="8076a-117">Un microservizio di overload che non può rispondere per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8076a-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="8076a-118">Operazione dell'agente di orchestrazione in corso, ad esempio un aggiornamento in sequenza o lo scorrimento di un servizio da un nodo a un altro.</span><span class="sxs-lookup"><span data-stu-id="8076a-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="8076a-119">Errori hardware.</span><span class="sxs-lookup"><span data-stu-id="8076a-119">Hardware failures.</span></span>

<span data-ttu-id="8076a-120">Le piattaforme cloud possono rilevare e mitigare molti di questi problemi di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="8076a-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="8076a-121">Il servizio può essere riavviato, ridimensionato e persino ridistribuito in un altro nodo.</span><span class="sxs-lookup"><span data-stu-id="8076a-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="8076a-122">Tuttavia, per sfruttare tutti i vantaggi di questa protezione incorporata, è necessario progettare i servizi in modo che reagisca e prosperino in questo ambiente dinamico.</span><span class="sxs-lookup"><span data-stu-id="8076a-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="8076a-123">Nelle sezioni seguenti verranno esaminate le tecniche difensive che il servizio e le risorse cloud gestite possono sfruttare per ridurre al minimo i tempi di inattività e le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="8076a-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8076a-124">[Precedente](elastic-search-in-azure.md) 
> [Avanti](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="8076a-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
