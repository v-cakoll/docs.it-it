---
ms.openlocfilehash: ae5a5fbf97ed4a03de7d35b9d5d5ca8de3aebc39
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394341"
---
### <a name="caching-responsecaching-pubternal-types-changed-to-internal"></a><span data-ttu-id="d967f-101">Caching: i tipi di "pubternal" di ResponseCaching sono stati modificati in Internal</span><span class="sxs-lookup"><span data-stu-id="d967f-101">Caching: ResponseCaching "pubternal" types changed to internal</span></span>

<span data-ttu-id="d967f-102">In ASP.NET Core 3,0 i tipi "pubternal" in `ResponseCaching` sono stati modificati in `internal`.</span><span class="sxs-lookup"><span data-stu-id="d967f-102">In ASP.NET Core 3.0, "pubternal" types in `ResponseCaching` have been changed to `internal`.</span></span>

<span data-ttu-id="d967f-103">Inoltre, le implementazioni predefinite di `IResponseCachingPolicyProvider` e `IResponseCachingKeyProvider` non sono più aggiunte ai servizi come parte del metodo `AddResponseCaching`.</span><span class="sxs-lookup"><span data-stu-id="d967f-103">In addition, default implementations of `IResponseCachingPolicyProvider` and `IResponseCachingKeyProvider` are no longer added to services as part of the `AddResponseCaching` method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d967f-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="d967f-104">Change description</span></span>

<span data-ttu-id="d967f-105">In ASP.NET Core i tipi "pubternal" sono dichiarati come `public`, ma risiedono in uno spazio dei nomi con suffisso `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="d967f-105">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a namespace suffixed with `.Internal`.</span></span> <span data-ttu-id="d967f-106">Sebbene questi tipi siano pubblici, non dispongono di criteri di supporto e sono soggetti a modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="d967f-106">While these types are public, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="d967f-107">Sfortunatamente, l'uso accidentale di questi tipi è stato comune, con conseguente riduzione delle modifiche apportate a questi progetti e della possibilità di mantenere il Framework.</span><span class="sxs-lookup"><span data-stu-id="d967f-107">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d967f-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d967f-108">Version introduced</span></span>

<span data-ttu-id="d967f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="d967f-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d967f-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d967f-110">Old behavior</span></span>

<span data-ttu-id="d967f-111">Questi tipi sono visibili pubblicamente, ma non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="d967f-111">These types were publicly visible, but unsupported.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d967f-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d967f-112">New behavior</span></span>

<span data-ttu-id="d967f-113">Questi tipi sono ora `internal`.</span><span class="sxs-lookup"><span data-stu-id="d967f-113">These types are now `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d967f-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d967f-114">Reason for change</span></span>

<span data-ttu-id="d967f-115">L'ambito `internal` riflette meglio i criteri non supportati.</span><span class="sxs-lookup"><span data-stu-id="d967f-115">The `internal` scope better reflects the unsupported policy.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d967f-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d967f-116">Recommended action</span></span>

<span data-ttu-id="d967f-117">Copiare i tipi usati dall'app o dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="d967f-117">Copy types that are used by your app or library.</span></span>

#### <a name="category"></a><span data-ttu-id="d967f-118">Category</span><span class="sxs-lookup"><span data-stu-id="d967f-118">Category</span></span>

<span data-ttu-id="d967f-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d967f-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d967f-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="d967f-120">Affected APIs</span></span>

- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- <xref:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.%23ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- `M:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)",
"nameWithType": "ResponseCachingMiddleware.ResponseCachingMiddleware(RequestDelegate, IOptions<ResponseCachingOptions>, ILoggerFactory, IResponseCachingPolicyProvider, IResponseCache, IResponseCachingKeyProvider)`

-->
