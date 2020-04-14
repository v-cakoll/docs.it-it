---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275254"
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

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
