---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74101115"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso

I metodi `AddAuthorization` principali utilizzati per risiedere in `Microsoft.AspNetCore.Authorization` sono stati rinominati `AddAuthorizationCore`. I vecchi metodi di `AddAuthorization` esistono ancora, ma si trovano invece nell'assembly `Microsoft.AspNetCore.Authorization.Policy`. Le app che usano entrambi i metodi non dovrebbero avere alcun effetto. Si noti che `Microsoft.AspNetCore.Authorization.Policy` ora viene fornito nel Framework condiviso anziché in un pacchetto autonomo, come illustrato in [Framework condiviso: assembly rimossi da Microsoft. AspNetCore. app](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).

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
