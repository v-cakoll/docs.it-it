---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901967"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="baae2-101">Autenticazione: Proprietà HttpContext. Authentication rimossa</span><span class="sxs-lookup"><span data-stu-id="baae2-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="baae2-102">La proprietà `Authentication` deprecata `HttpContext` è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="baae2-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="baae2-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="baae2-103">Change description</span></span>

<span data-ttu-id="baae2-104">Come parte di [DotNet/aspnetcore # 6504](https://github.com/dotnet/aspnetcore/pull/6504), la proprietà `Authentication` deprecata `HttpContext` è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="baae2-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="baae2-105">La proprietà `Authentication` è stata deprecata a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="baae2-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="baae2-106">È stata pubblicata una [Guida alla migrazione](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) per eseguire la migrazione del codice utilizzando questa proprietà deprecata per le nuove API sostitutive.</span><span class="sxs-lookup"><span data-stu-id="baae2-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="baae2-107">Le altre classi/API inutilizzate correlate allo stack di autenticazione precedente ASP.NET Core 1. x sono state rimosse in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="baae2-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="baae2-108">Per informazioni, vedere [DotNet/aspnetcore # 6533](https://github.com/dotnet/aspnetcore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="baae2-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="baae2-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="baae2-109">Version introduced</span></span>

<span data-ttu-id="baae2-110">3.0</span><span class="sxs-lookup"><span data-stu-id="baae2-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="baae2-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="baae2-111">Reason for change</span></span>

<span data-ttu-id="baae2-112">ASP.NET Core 1,0 API sono state sostituite dai metodi di estensione in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="baae2-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="baae2-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="baae2-113">Recommended action</span></span>

<span data-ttu-id="baae2-114">Vedere la [Guida alla migrazione](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="baae2-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="baae2-115">Categoria</span><span class="sxs-lookup"><span data-stu-id="baae2-115">Category</span></span>

<span data-ttu-id="baae2-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="baae2-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="baae2-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="baae2-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
