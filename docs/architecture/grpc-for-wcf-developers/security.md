---
title: Sicurezza nelle applicazioni gRPC-gRPC per sviluppatori WCF
description: Panoramica dell'autenticazione e dell'autorizzazione di chiamata e canale in gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f3d32817ccb5d9f278d256c0ee135f0e2a17cf2
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184141"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="7b842-103">Sicurezza nelle applicazioni gRPC</span><span class="sxs-lookup"><span data-stu-id="7b842-103">Security in gRPC applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7b842-104">In qualsiasi scenario reale, è essenziale proteggere le applicazioni e i servizi.</span><span class="sxs-lookup"><span data-stu-id="7b842-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="7b842-105">La sicurezza copre tre aree principali: la crittografia del traffico di rete per impedirne l'intercettazione da attori malintenzionati. autenticazione dei client e dei server per stabilire l'identità e l'attendibilità; e autorizzare i client a controllare l'accesso ai sistemi e a applicare le autorizzazioni in base all'identità.</span><span class="sxs-lookup"><span data-stu-id="7b842-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="7b842-106">L' **autenticazione** è responsabile della definizione dell'identità di un client o di un server.</span><span class="sxs-lookup"><span data-stu-id="7b842-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="7b842-107">L' **autorizzazione** è responsabile di determinare se un client è autorizzato ad accedere a una risorsa o a eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="7b842-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="7b842-108">In questo capitolo vengono illustrate le funzionalità di autenticazione e autorizzazione in gRPC per ASP.NET Core e viene illustrata la sicurezza di rete tramite connessioni crittografate TLS.</span><span class="sxs-lookup"><span data-stu-id="7b842-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="7b842-109">Autenticazione e autorizzazione WCF</span><span class="sxs-lookup"><span data-stu-id="7b842-109">WCF authentication and authorization</span></span>

<span data-ttu-id="7b842-110">In WCF, l'autenticazione e l'autorizzazione venivano gestite in modi diversi a seconda dei trasporti e delle associazioni utilizzati.</span><span class="sxs-lookup"><span data-stu-id="7b842-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="7b842-111">WCF supporta diversi standard WS\* -Security e l'autenticazione di Windows per i servizi HTTP in esecuzione nei servizi IIS o NetTcp tra i sistemi Windows.</span><span class="sxs-lookup"><span data-stu-id="7b842-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="7b842-112">autenticazione e autorizzazione di gRPC</span><span class="sxs-lookup"><span data-stu-id="7b842-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="7b842-113">l'autenticazione e l'autorizzazione di gRPC funzionano su due livelli.</span><span class="sxs-lookup"><span data-stu-id="7b842-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="7b842-114">L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita usando token che vengono applicati ai metadati quando viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7b842-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="7b842-115">L'autenticazione a livello di canale utilizza un certificato client applicato a livello di connessione e può includere anche le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7b842-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="7b842-116">È possibile utilizzare uno o entrambi i meccanismi per proteggere il servizio.</span><span class="sxs-lookup"><span data-stu-id="7b842-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="7b842-117">L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione utilizzando la maggior parte dei meccanismi di ASP.NET Core standard:</span><span class="sxs-lookup"><span data-stu-id="7b842-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="7b842-118">Autenticazione chiamata</span><span class="sxs-lookup"><span data-stu-id="7b842-118">Call authentication</span></span>
  - <span data-ttu-id="7b842-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b842-119">Azure Active Directory</span></span>
  - <span data-ttu-id="7b842-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="7b842-120">IdentityServer</span></span>
  - <span data-ttu-id="7b842-121">Token di porta JWT</span><span class="sxs-lookup"><span data-stu-id="7b842-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="7b842-122">OAuth 2,0</span><span class="sxs-lookup"><span data-stu-id="7b842-122">OAuth 2.0</span></span>
  - <span data-ttu-id="7b842-123">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="7b842-123">OpenID Connect</span></span>
  - <span data-ttu-id="7b842-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="7b842-124">WS-Federation</span></span>
- <span data-ttu-id="7b842-125">Autenticazione del canale</span><span class="sxs-lookup"><span data-stu-id="7b842-125">Channel authentication</span></span>
  - <span data-ttu-id="7b842-126">Certificato client</span><span class="sxs-lookup"><span data-stu-id="7b842-126">Client Certificate</span></span>

<span data-ttu-id="7b842-127">I metodi di autenticazione della chiamata sono tutti basati su *token*.</span><span class="sxs-lookup"><span data-stu-id="7b842-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="7b842-128">L'unica differenza reale è il modo in cui il token viene generato e le librerie usate per convalidare i token nel servizio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b842-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="7b842-129">Per ulteriori informazioni, vedere la [documentazione relativa all'autenticazione e all'autorizzazione su Microsoft docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="7b842-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="7b842-130">Quando si usa gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si usa l'autenticazione a livello di canale.</span><span class="sxs-lookup"><span data-stu-id="7b842-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="7b842-131">Questo capitolo illustra come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC e come usare le credenziali da un client gRPC di .NET Core per l'autenticazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="7b842-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7b842-132">[Precedente](client-libraries.md)
>[Successivo](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="7b842-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
