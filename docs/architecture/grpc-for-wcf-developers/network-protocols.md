---
title: Protocolli di rete-gRPC per sviluppatori WCF
description: Panoramica dei protocolli di rete gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cf99b2608d576765856c992679b93b6f21e796cf
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846392"
---
# <a name="network-protocols"></a><span data-ttu-id="08ff8-103">Protocolli di rete</span><span class="sxs-lookup"><span data-stu-id="08ff8-103">Network protocols</span></span>

<span data-ttu-id="08ff8-104">Diversamente da WCF, gRPC Usa HTTP/2 come base per la rete.</span><span class="sxs-lookup"><span data-stu-id="08ff8-104">Unlike WCF, gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="08ff8-105">Ciò offre vantaggi significativi rispetto a WCF e SOAP, che operano solo su HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="08ff8-105">This offers significant advantages over WCF and SOAP, which only operate on HTTP/1.1.</span></span> <span data-ttu-id="08ff8-106">Per gli sviluppatori che vogliono usare gRPC, dato che non esiste alcuna alternativa a HTTP/2, sembrerebbe il momento ideale per esplorare HTTP/2 in modo più dettagliato e identificare i vantaggi aggiuntivi per l'uso di gRPC.</span><span class="sxs-lookup"><span data-stu-id="08ff8-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits to using gRPC.</span></span>

<span data-ttu-id="08ff8-107">HTTP/2, rilasciato da Internet Engineering Task Force in 2015, è stato derivato dal protocollo sperimentale SPDY, che era già usato da Google.</span><span class="sxs-lookup"><span data-stu-id="08ff8-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="08ff8-108">È stato progettato appositamente per essere più efficiente, più veloce e più sicuro rispetto a HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="08ff8-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="08ff8-109">Funzionalità principali di HTTP/2</span><span class="sxs-lookup"><span data-stu-id="08ff8-109">Key features of HTTP/2</span></span>

<span data-ttu-id="08ff8-110">Nell'elenco seguente vengono illustrate alcune delle principali funzionalità e vantaggi di HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="08ff8-110">The following list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="08ff8-111">Protocollo binario</span><span class="sxs-lookup"><span data-stu-id="08ff8-111">Binary protocol</span></span>

<span data-ttu-id="08ff8-112">I cicli di richiesta/risposta non necessitano più di comandi di testo.</span><span class="sxs-lookup"><span data-stu-id="08ff8-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="08ff8-113">Questo semplifica e velocizza l'implementazione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="08ff8-113">This simplifies and speeds up implementation of commands.</span></span> <span data-ttu-id="08ff8-114">In particolare, l'analisi dei dati è più veloce e usa meno memoria, la latenza di rete è ridotta con evidenti miglioramenti correlati alla velocità e c'è un uso ottimale delle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="08ff8-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="08ff8-115">Flussi</span><span class="sxs-lookup"><span data-stu-id="08ff8-115">Streams</span></span>

<span data-ttu-id="08ff8-116">I flussi consentono la creazione di connessioni di lunga durata tra mittente e ricevitore, in cui è possibile inviare più messaggi o frame in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="08ff8-116">Streams allow for the creation of long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="08ff8-117">Più flussi possono funzionare in modo indipendente su una singola connessione HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="08ff8-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="08ff8-118">Richiedi multiplexing su una singola connessione TCP</span><span class="sxs-lookup"><span data-stu-id="08ff8-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="08ff8-119">Questa funzionalità è una delle innovazioni più importanti di HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="08ff8-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="08ff8-120">Consentendo più richieste parallele di dati, è ora possibile scaricare i file Web contemporaneamente da un singolo server.</span><span class="sxs-lookup"><span data-stu-id="08ff8-120">By allowing multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="08ff8-121">I siti Web vengono caricati più velocemente e la necessità di ottimizzazione è ridotta.</span><span class="sxs-lookup"><span data-stu-id="08ff8-121">Websites load faster and the need for optimization is reduced.</span></span> <span data-ttu-id="08ff8-122">Blocco Head-of-line (HOL), in cui le risposte pronte devono attendere l'invio finché non viene completata una richiesta precedente, viene anche attenuato (anche se il blocco di HOL può ancora verificarsi a livello di trasporto TCP).</span><span class="sxs-lookup"><span data-stu-id="08ff8-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="08ff8-123">Prestazioni simili a NetTCP, multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="08ff8-123">NetTCP-like performance, cross-platform</span></span>

<span data-ttu-id="08ff8-124">Fondamentalmente, la combinazione di gRPC e HTTP/2 offre agli sviluppatori almeno la velocità e l'efficienza equivalenti delle associazioni NetTCP per WCF e, in alcuni casi, una velocità ed efficienza ancora maggiore.</span><span class="sxs-lookup"><span data-stu-id="08ff8-124">Fundamentally, the combination of gRPC and HTTP/2 offer developers at least the equivalent speed and efficiency of NetTCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="08ff8-125">Tuttavia, a differenza di NetTCP, gRPC su HTTP/2 non è vincolato alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="08ff8-125">However, unlike NetTCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="08ff8-126">[Precedente](interface-definition-language.md)
>[Successivo](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="08ff8-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
