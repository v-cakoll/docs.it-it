---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901936"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo

In ASP.NET Core 3,0 è stato aggiunto un nuovo metodo di `GetFallbackPolicyAsync` al `IAuthorizationPolicyProvider`. Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.

Per ulteriori informazioni, vedere [DotNet/aspnetcore # 9759](https://github.com/dotnet/aspnetcore/pull/9759).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le implementazioni di `IAuthorizationPolicyProvider` non richiedono un metodo di `GetFallbackPolicyAsync`.

#### <a name="new-behavior"></a>Nuovo comportamento

Le implementazioni di `IAuthorizationPolicyProvider` richiedono un metodo di `GetFallbackPolicyAsync`.

#### <a name="reason-for-change"></a>Motivo della modifica

Un nuovo metodo era necessario per il nuovo `AuthorizationMiddleware` da utilizzare quando non viene specificato alcun criterio.

#### <a name="recommended-action"></a>Azione consigliata

Aggiungere il metodo `GetFallbackPolicyAsync` alle implementazioni di `IAuthorizationPolicyProvider`.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
