---
title: Protocolli di rete-gRPC per sviluppatori WCF
description: Panoramica dei protocolli di rete gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 1ceb140f7b7ac7e796a87612ebb9d21e28d33968
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628488"
---
# <a name="network-protocols"></a><span data-ttu-id="6fef2-103">Protocolli di rete</span><span class="sxs-lookup"><span data-stu-id="6fef2-103">Network protocols</span></span>

<span data-ttu-id="6fef2-104">A differenza di Windows Communication Foundation (WCF), gRPC Usa HTTP/2 come base per la rete.</span><span class="sxs-lookup"><span data-stu-id="6fef2-104">Unlike Windows Communication Foundation (WCF), gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="6fef2-105">Ciò offre vantaggi significativi rispetto a WCF e SOAP, che operano solo su HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="6fef2-105">This offers significant advantages over WCF and SOAP, which operate only on HTTP/1.1.</span></span> <span data-ttu-id="6fef2-106">Per gli sviluppatori che vogliono usare gRPC, dato che non esiste alcuna alternativa a HTTP/2, sembrerebbe il momento ideale per esplorare HTTP/2 in modo più dettagliato e identificare i vantaggi aggiuntivi dell'uso di gRPC.</span><span class="sxs-lookup"><span data-stu-id="6fef2-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits of using gRPC.</span></span>

<span data-ttu-id="6fef2-107">HTTP/2, rilasciato da Internet Engineering Task Force in 2015, è stato derivato dal protocollo sperimentale SPDY, che era già usato da Google.</span><span class="sxs-lookup"><span data-stu-id="6fef2-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="6fef2-108">È stato progettato appositamente per essere più efficiente, più veloce e più sicuro rispetto a HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="6fef2-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="6fef2-109">Funzionalità principali di HTTP/2</span><span class="sxs-lookup"><span data-stu-id="6fef2-109">Key features of HTTP/2</span></span>

<span data-ttu-id="6fef2-110">In questo elenco vengono illustrate alcune delle principali funzionalità e vantaggi di HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="6fef2-110">This list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="6fef2-111">Protocollo binario</span><span class="sxs-lookup"><span data-stu-id="6fef2-111">Binary protocol</span></span>

<span data-ttu-id="6fef2-112">I cicli di richiesta/risposta non necessitano più di comandi di testo.</span><span class="sxs-lookup"><span data-stu-id="6fef2-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="6fef2-113">Questo semplifica e velocizza l'implementazione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6fef2-113">This simplifies and speeds up implementation of commands.</span></span> <span data-ttu-id="6fef2-114">In particolare, l'analisi dei dati è più veloce e usa meno memoria, la latenza di rete è ridotta con evidenti miglioramenti correlati alla velocità e c'è un uso ottimale delle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="6fef2-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="6fef2-115">Flussi</span><span class="sxs-lookup"><span data-stu-id="6fef2-115">Streams</span></span>

<span data-ttu-id="6fef2-116">I flussi consentono di creare connessioni di lunga durata tra mittente e ricevitore, in cui è possibile inviare più messaggi o frame in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="6fef2-116">Streams allow you to create long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="6fef2-117">Più flussi possono funzionare in modo indipendente su una singola connessione HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="6fef2-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="6fef2-118">Richiedi multiplexing su una singola connessione TCP</span><span class="sxs-lookup"><span data-stu-id="6fef2-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="6fef2-119">Questa funzionalità è una delle innovazioni più importanti di HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="6fef2-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="6fef2-120">Poiché consente più richieste parallele di dati, è ora possibile scaricare i file Web contemporaneamente da un singolo server.</span><span class="sxs-lookup"><span data-stu-id="6fef2-120">Because it allows multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="6fef2-121">I siti Web vengono caricati più velocemente e la necessità di ottimizzazione è ridotta.</span><span class="sxs-lookup"><span data-stu-id="6fef2-121">Websites load faster, and the need for optimization is reduced.</span></span> <span data-ttu-id="6fef2-122">Blocco Head-of-line (HOL), in cui le risposte pronte devono attendere l'invio finché non viene completata una richiesta precedente, viene anche attenuato (anche se il blocco di HOL può ancora verificarsi a livello di trasporto TCP).</span><span class="sxs-lookup"><span data-stu-id="6fef2-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP-transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="6fef2-123">Prestazioni di tipo NET. TCP, multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="6fef2-123">Net.TCP-like performance, cross-platform</span></span>

<span data-ttu-id="6fef2-124">Fondamentalmente, la combinazione di gRPC e HTTP/2 offre agli sviluppatori almeno la velocità e l'efficienza equivalenti dei binding net. TCP per WCF e, in alcuni casi, una velocità ed efficienza ancora maggiore.</span><span class="sxs-lookup"><span data-stu-id="6fef2-124">Fundamentally, the combination of gRPC and HTTP/2 offers developers at least the equivalent speed and efficiency of Net.TCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="6fef2-125">Tuttavia, a differenza di NET. TCP, gRPC su HTTP/2 non è vincolato alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="6fef2-125">But, unlike Net.TCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6fef2-126">[Precedente](interface-definition-language.md)
>[Successivo](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="6fef2-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
