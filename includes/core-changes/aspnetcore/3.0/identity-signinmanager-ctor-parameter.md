---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394366"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identity: il costruttore SignInManager accetta il nuovo parametro

A partire da ASP.NET Core 3,0, al costruttore `SignInManager` è stato aggiunto un nuovo parametro `IUserConfirmation<TUser>`. Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 8356](https://github.com/aspnet/AspNetCore/issues/8356).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

La motivazione della modifica consisteva nell'aggiungere il supporto per nuovi flussi di messaggi di posta elettronica/conferma in identità.

#### <a name="recommended-action"></a>Azione consigliata

Se si costruisce manualmente un `SignInManager`, fornire un'implementazione di `IUserConfirmation` o estrarne una dall'inserimento delle dipendenze da fornire.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
