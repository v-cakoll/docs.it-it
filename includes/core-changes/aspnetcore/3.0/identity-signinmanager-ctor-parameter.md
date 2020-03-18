---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901663"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identità: il costruttore SignInManager accetta il nuovo parametro

A partire da ASP.NET Core `IUserConfirmation<TUser>` 3.0, `SignInManager` un nuovo parametro è stato aggiunto al costruttore. Per ulteriori informazioni, vedere [dotnet/aspnetcore-8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

La motivazione per il cambiamento è stata quella di aggiungere il supporto per nuovi flussi di email / conferma in Identity.

#### <a name="recommended-action"></a>Azione consigliata

Se si costruisce `SignInManager`manualmente un `IUserConfirmation` oggetto , fornire un'implementazione di o acquisirne una dall'inserimento delle dipendenze da fornire.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
