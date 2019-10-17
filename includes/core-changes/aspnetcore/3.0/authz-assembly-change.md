---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394268"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso

I metodi `AddAuthorization` principali utilizzati per risiedere in `Microsoft.AspNetCore.Authorization` sono stati rinominati `AddAuthorizationCore`. I metodi `AddAuthorization` precedenti esistono ancora, ma sono invece nel pacchetto `Microsoft.AspNetCore.Authorization.Policy`. Le app che usano entrambi i metodi non dovrebbero avere alcun effetto. Le app che non usano il pacchetto di criteri devono passare a con `AddAuthorizationCore`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

i metodi `AddAuthorization` erano presenti in `Microsoft.AspNetCore.Authorization`.

#### <a name="new-behavior"></a>Nuovo comportamento

nel `Microsoft.AspNetCore.Authorization.Policy` sono presenti metodi `AddAuthorization`. `AddAuthorizationCore` è il nuovo nome per i metodi obsoleti.

#### <a name="reason-for-change"></a>Motivo della modifica

`AddAuthorization` è un nome di metodo migliore per aggiungere tutti i servizi comuni necessari per l'autorizzazione.

#### <a name="recommended-action"></a>Azione consigliata

Aggiungere un riferimento a `Microsoft.AspNetCore.Authorization.Policy` o usare invece `AddAuthorizationCore`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
