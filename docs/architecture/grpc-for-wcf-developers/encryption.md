---
title: Crittografia e sicurezza di rete-gRPC per sviluppatori WCF
description: Alcune note sulla crittografia e la sicurezza di rete in gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846670"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="191cd-103">Crittografia e sicurezza di rete</span><span class="sxs-lookup"><span data-stu-id="191cd-103">Encryption and network security</span></span>

<span data-ttu-id="191cd-104">Il modello di sicurezza di rete di WCF è vasto e complesso, inclusa la sicurezza a livello di trasporto tramite HTTPS o TLS-over-TCP e la sicurezza a livello di messaggio utilizzando la specifica WS-Security per crittografare i singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="191cd-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="191cd-105">gRPC lascia la rete sicura al protocollo HTTP/2 sottostante, che può essere protetto usando i normali certificati TLS.</span><span class="sxs-lookup"><span data-stu-id="191cd-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="191cd-106">I Web browser si ostinano a usare le connessioni TLS per HTTP/2, ma la maggior parte dei client programmatici, incluso. `HttpClient`NET, può usare HTTP/2 su connessioni non crittografate.</span><span class="sxs-lookup"><span data-stu-id="191cd-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="191cd-107">`HttpClient` *richiede la crittografia* per impostazione predefinita, ma è possibile eseguirne l'override usando un'opzione di <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="191cd-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="191cd-108">Per le API pubbliche, è consigliabile usare sempre le connessioni TLS e fornire certificati validi per i servizi da un'autorità SSL corretta.</span><span class="sxs-lookup"><span data-stu-id="191cd-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="191cd-109">[LetsEncrypt](https://letsencrypt.org) offre certificati SSL gratuiti e automatizzati e la maggior parte dell'infrastruttura di hosting attualmente supporta lo standard LetsEncrypt con i plug-in comuni o le estensioni.</span><span class="sxs-lookup"><span data-stu-id="191cd-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="191cd-110">Per i servizi interni in una rete aziendale, è comunque consigliabile usare TLS per proteggere il traffico di rete da e verso i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="191cd-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="191cd-111">La comunicazione tra microservizi in un cluster, ad esempio Kubernetes o Docker Swarm, è in genere crittografata automaticamente dal livello di rete del contenitore. Pertanto, l'implementazione di TLS nei servizi in esecuzione esclusivamente in tale cluster non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="191cd-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="191cd-112">Nella sezione "mesh dei servizi" del capitolo successivo saranno disponibili ulteriori informazioni su questo argomento.</span><span class="sxs-lookup"><span data-stu-id="191cd-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="191cd-113">Se è necessario usare TLS esplicito tra i servizi in esecuzione in Kubernetes, è consigliabile usare un'autorità di certificazione nel cluster e un controller di gestione certificati, ad esempio [Cert-Manager](https://docs.cert-manager.io/en/latest/) , per assegnare certificati automatici ai servizi in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="191cd-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="191cd-114">[Precedente](channel-credentials.md)
>[Successivo](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="191cd-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
