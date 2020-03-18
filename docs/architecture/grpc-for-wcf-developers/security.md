---
title: Sicurezza nelle applicazioni gRPC - gRPC per gli sviluppatori WCFSecurity in gRPC applications - gRPC for WCF developers
description: Panoramica dell'autenticazione e dell'autorizzazione delle chiamate e dei canali in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147815"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="a2b37-103">Sicurezza nelle applicazioni gRPC</span><span class="sxs-lookup"><span data-stu-id="a2b37-103">Security in gRPC applications</span></span>

<span data-ttu-id="a2b37-104">In qualsiasi scenario reale, la protezione di applicazioni e servizi è essenziale.</span><span class="sxs-lookup"><span data-stu-id="a2b37-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="a2b37-105">La sicurezza copre tre aree chiave:</span><span class="sxs-lookup"><span data-stu-id="a2b37-105">Security covers three key areas:</span></span>

* <span data-ttu-id="a2b37-106">Crittografia del traffico di rete per impedire a hacker malintenzionati di intercettarlo.</span><span class="sxs-lookup"><span data-stu-id="a2b37-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="a2b37-107">Autenticazione di client e server per stabilire identità e attendibilità.</span><span class="sxs-lookup"><span data-stu-id="a2b37-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="a2b37-108">Autorizzazione dei client a controllare l'accesso ai sistemi e applicare le autorizzazioni in base all'identità.</span><span class="sxs-lookup"><span data-stu-id="a2b37-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="a2b37-109">*L'autenticazione* riguarda la determinazione dell'identità di un client o di un server.</span><span class="sxs-lookup"><span data-stu-id="a2b37-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="a2b37-110">*L'autorizzazione* riguarda la determinazione se un client dispone dell'autorizzazione per accedere a una risorsa o eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="a2b37-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="a2b37-111">Questo capitolo tratterà le funzionalità per l'autenticazione e l'autorizzazione in gRPC per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b37-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="a2b37-112">Discuterà anche la sicurezza di rete attraverso le connessioni crittografate TLS.</span><span class="sxs-lookup"><span data-stu-id="a2b37-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="a2b37-113">Autenticazione e autorizzazione WCFWCF authentication and authorization</span><span class="sxs-lookup"><span data-stu-id="a2b37-113">WCF authentication and authorization</span></span>

<span data-ttu-id="a2b37-114">In Windows Communication Foundation (WCF), l'autenticazione e l'autorizzazione sono state gestite in modi diversi, a seconda dei trasporti e delle associazioni in uso.</span><span class="sxs-lookup"><span data-stu-id="a2b37-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="a2b37-115">WCF supportava\* vari standard di sicurezza WS.WCF supported various WS- security standards.</span><span class="sxs-lookup"><span data-stu-id="a2b37-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="a2b37-116">Supporta inoltre l'autenticazione di Windows per i servizi HTTP in esecuzione nei servizi IIS o NetTCP tra sistemi Windows.</span><span class="sxs-lookup"><span data-stu-id="a2b37-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="a2b37-117">Autenticazione e autorizzazione gRPC</span><span class="sxs-lookup"><span data-stu-id="a2b37-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="a2b37-118">L'autenticazione e l'autorizzazione gRPC funzionano su due livelli:</span><span class="sxs-lookup"><span data-stu-id="a2b37-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="a2b37-119">L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita tramite token applicati nei metadati quando viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a2b37-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="a2b37-120">L'autenticazione a livello di canale utilizza un certificato client applicato a livello di connessione.</span><span class="sxs-lookup"><span data-stu-id="a2b37-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="a2b37-121">Può anche includere automaticamente le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale.</span><span class="sxs-lookup"><span data-stu-id="a2b37-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="a2b37-122">È possibile utilizzare uno o entrambi questi meccanismi per proteggere il servizio.</span><span class="sxs-lookup"><span data-stu-id="a2b37-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="a2b37-123">L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione attraverso la maggior parte dei meccanismi standard ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="a2b37-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="a2b37-124">Autenticazione delle chiamate</span><span class="sxs-lookup"><span data-stu-id="a2b37-124">Call authentication</span></span>
  - <span data-ttu-id="a2b37-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a2b37-125">Azure Active Directory</span></span>
  - <span data-ttu-id="a2b37-126">Server identità</span><span class="sxs-lookup"><span data-stu-id="a2b37-126">IdentityServer</span></span>
  - <span data-ttu-id="a2b37-127">JWT Bearer Token</span><span class="sxs-lookup"><span data-stu-id="a2b37-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="a2b37-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="a2b37-128">OAuth 2.0</span></span>
  - <span data-ttu-id="a2b37-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="a2b37-129">OpenID Connect</span></span>
  - <span data-ttu-id="a2b37-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="a2b37-130">WS-Federation</span></span>
- <span data-ttu-id="a2b37-131">Autenticazione del canale</span><span class="sxs-lookup"><span data-stu-id="a2b37-131">Channel authentication</span></span>
  - <span data-ttu-id="a2b37-132">Certificato client</span><span class="sxs-lookup"><span data-stu-id="a2b37-132">Client certificate</span></span>

<span data-ttu-id="a2b37-133">I metodi di autenticazione delle chiamate sono tutti basati sui *token.*</span><span class="sxs-lookup"><span data-stu-id="a2b37-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="a2b37-134">L'unica vera differenza è il modo in cui vengono generati i token e le librerie utilizzate per convalidare i token nel servizio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b37-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="a2b37-135">Per altre informazioni, vedere l'articolo [Autenticazione e autorizzazione.](/aspnet/core/grpc/authn-and-authz)</span><span class="sxs-lookup"><span data-stu-id="a2b37-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="a2b37-136">Quando si utilizza gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si utilizza l'autenticazione a livello di canale.</span><span class="sxs-lookup"><span data-stu-id="a2b37-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="a2b37-137">In questo capitolo verrà illustrato come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="a2b37-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="a2b37-138">Verrà inoltre illustrato come utilizzare le credenziali da un client gRPC di .NET Core per l'autenticazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="a2b37-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a2b37-139">[Successivo](client-libraries.md)
>[precedente](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="a2b37-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
