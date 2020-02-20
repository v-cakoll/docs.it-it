---
title: Sicurezza nelle applicazioni gRPC-gRPC per sviluppatori WCF
description: Panoramica dell'autenticazione e dell'autorizzazione di chiamata e canale in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503414"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="8de6a-103">Sicurezza nelle applicazioni gRPC</span><span class="sxs-lookup"><span data-stu-id="8de6a-103">Security in gRPC applications</span></span>

<span data-ttu-id="8de6a-104">In qualsiasi scenario reale, è essenziale proteggere le applicazioni e i servizi.</span><span class="sxs-lookup"><span data-stu-id="8de6a-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="8de6a-105">La sicurezza copre tre aree principali:</span><span class="sxs-lookup"><span data-stu-id="8de6a-105">Security covers three key areas:</span></span> 

* <span data-ttu-id="8de6a-106">Crittografia del traffico di rete per impedire l'intercettazione da hacker malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="8de6a-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="8de6a-107">Autenticazione dei client e dei server per stabilire l'identità e l'attendibilità.</span><span class="sxs-lookup"><span data-stu-id="8de6a-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="8de6a-108">Autorizzazione dei client a controllare l'accesso ai sistemi e applicare le autorizzazioni in base all'identità.</span><span class="sxs-lookup"><span data-stu-id="8de6a-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="8de6a-109">L' *autenticazione* è responsabile della definizione dell'identità di un client o di un server.</span><span class="sxs-lookup"><span data-stu-id="8de6a-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="8de6a-110">L' *autorizzazione* è responsabile di determinare se un client è autorizzato ad accedere a una risorsa o a eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="8de6a-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="8de6a-111">In questo capitolo vengono trattate le funzionalità per l'autenticazione e l'autorizzazione in gRPC per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8de6a-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="8de6a-112">Verrà inoltre discussa la sicurezza di rete tramite connessioni crittografate TLS.</span><span class="sxs-lookup"><span data-stu-id="8de6a-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="8de6a-113">Autenticazione e autorizzazione WCF</span><span class="sxs-lookup"><span data-stu-id="8de6a-113">WCF authentication and authorization</span></span>

<span data-ttu-id="8de6a-114">In Windows Communication Foundation (WCF), l'autenticazione e l'autorizzazione venivano gestite in modi diversi, a seconda dei trasporti e delle associazioni utilizzate.</span><span class="sxs-lookup"><span data-stu-id="8de6a-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="8de6a-115">WCF supporta diversi standard di sicurezza WS-\*.</span><span class="sxs-lookup"><span data-stu-id="8de6a-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="8de6a-116">Supporta inoltre l'autenticazione di Windows per i servizi HTTP in esecuzione nei servizi IIS o NetTCP tra i sistemi Windows.</span><span class="sxs-lookup"><span data-stu-id="8de6a-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="8de6a-117">autenticazione e autorizzazione di gRPC</span><span class="sxs-lookup"><span data-stu-id="8de6a-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="8de6a-118">l'autenticazione e l'autorizzazione di gRPC funzionano su due livelli:</span><span class="sxs-lookup"><span data-stu-id="8de6a-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="8de6a-119">L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita tramite token che vengono applicati ai metadati quando viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8de6a-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span> 
* <span data-ttu-id="8de6a-120">L'autenticazione a livello di canale usa un certificato client applicato a livello di connessione.</span><span class="sxs-lookup"><span data-stu-id="8de6a-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="8de6a-121">Può inoltre includere le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8de6a-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> 

<span data-ttu-id="8de6a-122">È possibile utilizzare uno o entrambi i meccanismi per proteggere il servizio.</span><span class="sxs-lookup"><span data-stu-id="8de6a-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="8de6a-123">L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione attraverso la maggior parte dei meccanismi di ASP.NET Core standard:</span><span class="sxs-lookup"><span data-stu-id="8de6a-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="8de6a-124">Autenticazione chiamata</span><span class="sxs-lookup"><span data-stu-id="8de6a-124">Call authentication</span></span>
  - <span data-ttu-id="8de6a-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8de6a-125">Azure Active Directory</span></span>
  - <span data-ttu-id="8de6a-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="8de6a-126">IdentityServer</span></span>
  - <span data-ttu-id="8de6a-127">Token di porta JWT</span><span class="sxs-lookup"><span data-stu-id="8de6a-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="8de6a-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="8de6a-128">OAuth 2.0</span></span>
  - <span data-ttu-id="8de6a-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="8de6a-129">OpenID Connect</span></span>
  - <span data-ttu-id="8de6a-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="8de6a-130">WS-Federation</span></span>
- <span data-ttu-id="8de6a-131">Autenticazione del canale</span><span class="sxs-lookup"><span data-stu-id="8de6a-131">Channel authentication</span></span>
  - <span data-ttu-id="8de6a-132">Certificato client</span><span class="sxs-lookup"><span data-stu-id="8de6a-132">Client certificate</span></span>

<span data-ttu-id="8de6a-133">I metodi di autenticazione della chiamata sono tutti basati su *token*.</span><span class="sxs-lookup"><span data-stu-id="8de6a-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="8de6a-134">L'unica differenza reale riguarda il modo in cui vengono generati i token e le librerie usate per convalidare i token nel servizio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8de6a-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="8de6a-135">Per altre informazioni, vedere l'articolo [autenticazione e autorizzazione](/aspnet/core/grpc/authn-and-authz) .</span><span class="sxs-lookup"><span data-stu-id="8de6a-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="8de6a-136">Quando si usa gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si usa l'autenticazione a livello di canale.</span><span class="sxs-lookup"><span data-stu-id="8de6a-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="8de6a-137">In questo capitolo viene illustrato come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="8de6a-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="8de6a-138">Verrà inoltre illustrato come utilizzare le credenziali di un client gRPC .NET Core per l'autenticazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="8de6a-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8de6a-139">[Precedente](client-libraries.md)
>[Successivo](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="8de6a-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
