---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74101115"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorizzazione: sovraccarico AddAuthorization spostato in un assembly diversoAuthorization: AddAuthorization overload moved to different assembly

I `AddAuthorization` metodi principali utilizzati `Microsoft.AspNetCore.Authorization` per risiedere in sono stati rinominati in `AddAuthorizationCore`. I `AddAuthorization` metodi precedenti esistono ancora, `Microsoft.AspNetCore.Authorization.Policy` ma si trovano invece nell'assembly. Le app che usano entrambi i metodi non dovrebbero avere alcun impatto. Si `Microsoft.AspNetCore.Authorization.Policy` noti che ora viene fornito nel framework condiviso anziché in un pacchetto autonomo come descritto in [Framework condiviso: assembly rimossi da Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente
`AddAuthorization`metodi esistenti `Microsoft.AspNetCore.Authorization`in .

#### <a name="new-behavior"></a>Nuovo comportamento

`AddAuthorization`metodi esistenti `Microsoft.AspNetCore.Authorization.Policy`in . `AddAuthorizationCore`è il nuovo nome per i metodi precedenti.

#### <a name="reason-for-change"></a>Motivo della modifica

`AddAuthorization`è un nome di metodo migliore per l'aggiunta di tutti i servizi comuni necessari per l'autorizzazione.

#### <a name="recommended-action"></a>Azione consigliata

Aggiungere un riferimento `Microsoft.AspNetCore.Authorization.Policy` o `AddAuthorizationCore` utilizzarlo.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
