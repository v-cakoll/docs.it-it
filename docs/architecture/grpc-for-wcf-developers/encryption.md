---
title: Crittografia e sicurezza di rete-gRPC per sviluppatori WCF
description: Alcune note sulla crittografia e la sicurezza di rete in gRPC
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542769"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="7f8b3-103">Crittografia e sicurezza di rete</span><span class="sxs-lookup"><span data-stu-id="7f8b3-103">Encryption and network security</span></span>

<span data-ttu-id="7f8b3-104">Il modello di sicurezza di rete per Windows Communication Foundation (WCF) è completo e complesso.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-104">The network security model for Windows Communication Foundation (WCF) is extensive and complex.</span></span> <span data-ttu-id="7f8b3-105">Include la sicurezza a livello di trasporto usando HTTPS o TLS-over-TCP e la sicurezza a livello di messaggio usando la specifica WS-Security per crittografare i singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-105">It includes transport-level security by using HTTPS or TLS-over-TCP, and message-level security by using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="7f8b3-106">gRPC lascia la rete sicura al protocollo HTTP/2 sottostante, che è possibile proteggere usando i certificati TLS.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-106">gRPC leaves secure networking to the underlying HTTP/2 protocol, which you can secure by using TLS certificates.</span></span>

<span data-ttu-id="7f8b3-107">I Web browser si ostinano a usare le connessioni TLS per HTTP/2, ma la maggior parte dei client programmatici, incluso. `HttpClient`NET, può usare HTTP/2 su connessioni non crittografate.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-107">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="7f8b3-108">`HttpClient` richiede la crittografia per impostazione predefinita, ma è possibile eseguirne l'override usando un'opzione di <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-108">`HttpClient` does require encryption by default, but you can override this by using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="7f8b3-109">Per le API pubbliche, è consigliabile usare sempre le connessioni TLS e fornire certificati validi per i servizi da un'autorità SSL corretta.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-109">For public APIs, you should always use TLS connections, and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="7f8b3-110">[LetsEncrypt](https://letsencrypt.org) offre certificati SSL gratuiti e automatizzati e la maggior parte dell'infrastruttura di hosting attualmente supporta lo standard LetsEncrypt con i plug-in comuni o le estensioni.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-110">[LetsEncrypt](https://letsencrypt.org) provides free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="7f8b3-111">Per i servizi interni in una rete aziendale, è comunque consigliabile usare TLS per proteggere il traffico di rete da e verso i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-111">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="7f8b3-112">Se è necessario usare TLS esplicito tra i servizi in esecuzione in Kubernetes, è consigliabile usare un'autorità di certificazione nel cluster e un controller di gestione certificati come [Cert-Manager](https://docs.cert-manager.io/en/latest/).</span><span class="sxs-lookup"><span data-stu-id="7f8b3-112">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster certificate authority and a certificate manager controller like [cert-manager](https://docs.cert-manager.io/en/latest/).</span></span> <span data-ttu-id="7f8b3-113">È quindi possibile assegnare automaticamente i certificati ai servizi in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f8b3-113">You can then automatically assign certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7f8b3-114">[Precedente](channel-credentials.md)
>[Successivo](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="7f8b3-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
