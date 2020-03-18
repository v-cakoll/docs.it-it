---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901936"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodoAuthorization: IAuthorizationPolicyProvider implementations require new method

In ASP.NET Core 3.0 `GetFallbackPolicyAsync` è stato `IAuthorizationPolicyProvider`aggiunto un nuovo metodo a . Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.

Per ulteriori informazioni, vedere [dotnet/aspnetcore-9759](https://github.com/dotnet/aspnetcore/pull/9759).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le implementazioni di `IAuthorizationPolicyProvider` non `GetFallbackPolicyAsync` richiedevano un metodo.

#### <a name="new-behavior"></a>Nuovo comportamento

Le implementazioni `IAuthorizationPolicyProvider` `GetFallbackPolicyAsync` di richiedono un metodo.

#### <a name="reason-for-change"></a>Motivo della modifica

Era necessario un nuovo `AuthorizationMiddleware` metodo per il nuovo da utilizzare quando non viene specificato alcun criterio.

#### <a name="recommended-action"></a>Azione consigliata

Aggiungere `GetFallbackPolicyAsync` il metodo alle `IAuthorizationPolicyProvider`implementazioni di .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
