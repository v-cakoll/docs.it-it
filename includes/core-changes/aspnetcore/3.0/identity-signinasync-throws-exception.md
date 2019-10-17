---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393952"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>Identity: SignInAsync genera un'eccezione per l'identità non autenticata

Per impostazione predefinita, `SignInAsync` genera un'eccezione per entità/identità in cui `IsAuthenticated` è `false`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`SignInAsync` accetta qualsiasi entità/identità, incluse le identità in cui `IsAuthenticated` è `false`.

#### <a name="new-behavior"></a>Nuovo comportamento

Per impostazione predefinita, `SignInAsync` genera un'eccezione per entità/identità in cui `IsAuthenticated` è `false`. È disponibile un nuovo flag per l'eliminazione di questo comportamento, ma il comportamento predefinito è stato modificato.

#### <a name="reason-for-change"></a>Motivo della modifica

Il comportamento precedente è problematico perché, per impostazione predefinita, queste entità sono state rifiutate da `[Authorize]` @ no__t-1 @ no__t-2.

#### <a name="recommended-action"></a>Azione consigliata

In ASP.NET Core 3,0 Preview 6 è disponibile un flag `RequireAuthenticatedSignIn` in `AuthenticationOptions`, che è `true` per impostazione predefinita. Impostare questo flag su `false` per ripristinare il comportamento precedente.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
