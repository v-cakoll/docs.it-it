---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901663"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identity: il costruttore SignInManager accetta il nuovo parametro

A partire da ASP.NET Core 3,0, al costruttore `SignInManager` è stato aggiunto un nuovo parametro di `IUserConfirmation<TUser>`. Per ulteriori informazioni, vedere [DotNet/aspnetcore # 8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

La motivazione della modifica consisteva nell'aggiungere il supporto per nuovi flussi di messaggi di posta elettronica/conferma in identità.

#### <a name="recommended-action"></a>Azione consigliata

Se si costruisce manualmente un `SignInManager`, fornire un'implementazione di `IUserConfirmation` o estrarne una dall'inserimento delle dipendenze da fornire.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
