---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198461"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo

In ASP.NET Core 3,0 è stato aggiunto un nuovo metodo `GetFallbackPolicyAsync` a `IAuthorizationPolicyProvider`. Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.

Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 9759](https://github.com/aspnet/AspNetCore/pull/9759).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le implementazioni di `IAuthorizationPolicyProvider` non hanno richiesto un metodo `GetFallbackPolicyAsync`.

#### <a name="new-behavior"></a>Nuovo comportamento

Per le implementazioni di `IAuthorizationPolicyProvider` è necessario un metodo `GetFallbackPolicyAsync`.

#### <a name="reason-for-change"></a>Motivo della modifica

È necessario un nuovo metodo per la nuova `AuthorizationMiddleware` da usare quando non è specificato alcun criterio.

#### <a name="recommended-action"></a>Azione consigliata

Aggiungere il metodo `GetFallbackPolicyAsync` alle implementazioni di `IAuthorizationPolicyProvider`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
