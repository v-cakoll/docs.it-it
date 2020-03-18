---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393952"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>Identità: SignInAsync genera un'eccezione per l'identità non autenticataIdentity: SignInAsync throws exception for unauthenticated identity

Per impostazione predefinita, `SignInAsync` genera un'eccezione per `IsAuthenticated` `false`le entità /identità in cui è .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`SignInAsync`accetta qualsiasi entità / identità, comprese le `IsAuthenticated` identità in cui è `false`.

#### <a name="new-behavior"></a>Nuovo comportamento

Per impostazione predefinita, `SignInAsync` genera un'eccezione per `IsAuthenticated` `false`le entità /identità in cui è . È disponibile un nuovo flag per eliminare questo comportamento, ma il comportamento predefinito è stato modificato.

#### <a name="reason-for-change"></a>Motivo della modifica

Il comportamento precedente era problematico perché, per impostazione predefinita, queste entità sono state rifiutate da `[Authorize]`  /  `RequireAuthenticatedUser()`.

#### <a name="recommended-action"></a>Azione consigliata

In ASP.NET Core 3.0 Preview 6, c'è un `RequireAuthenticatedSignIn` flag su `AuthenticationOptions` che è `true` per impostazione predefinita. Impostare questo `false` flag su per ripristinare il comportamento precedente.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
