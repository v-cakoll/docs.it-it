---
ms.openlocfilehash: 2945465bb6a3a362dc640641056712dffd73d559
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393901"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a>Autenticazione: Proprietà HttpContext. Authentication rimossa

La proprietà deprecata `Authentication` su `HttpContext` è stata rimossa.

#### <a name="change-description"></a>Descrizione della modifica

Come parte di [ASPNET/AspNetCore # 6504](https://github.com/aspnet/AspNetCore/pull/6504), la proprietà deprecata `Authentication` in `HttpContext` è stata rimossa. La proprietà `Authentication` è stata deprecata a partire da 2,0. È stata pubblicata una [Guida alla migrazione](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) per eseguire la migrazione del codice utilizzando questa proprietà deprecata per le nuove API sostitutive. Le altre classi/API inutilizzate correlate allo stack di autenticazione precedente ASP.NET Core 1. x sono state rimosse nel commit [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65).

Per informazioni, vedere [ASPNET/AspNetCore # 6533](https://github.com/aspnet/AspNetCore/issues/6533).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core 1,0 API sono state sostituite dai metodi di estensione in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.

#### <a name="recommended-action"></a>Azione consigliata

Vedere la [Guida alla migrazione](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

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
