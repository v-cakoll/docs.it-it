---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394283"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>Autenticazione: firma OAuthHandler ExchangeCodeAsync modificata

In ASP.NET Core 3.0, `OAuthHandler.ExchangeCodeAsync` la firma di è stata modificata da:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

Con:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le `code` `redirectUri` stringhe e sono state passate come argomenti separati.

#### <a name="new-behavior"></a>Nuovo comportamento

`Code`e `RedirectUri` sono `OAuthCodeExchangeContext` proprietà su che `OAuthCodeExchangeContext` possono essere impostate tramite il costruttore. Il `OAuthCodeExchangeContext` nuovo tipo è l'unico argomento passato a `OAuthHandler.ExchangeCodeAsync`.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica consente di fornire parametri aggiuntivi in modo non uniforme. Non è necessario creare `ExchangeCodeAsync` nuovi overload.

#### <a name="recommended-action"></a>Azione consigliata

Costruire `OAuthCodeExchangeContext` un con `code` `redirectUri` i valori e e appropriati. È <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> necessario fornire un'istanza. Questa `OAuthCodeExchangeContext` singola istanza può `OAuthHandler.ExchangeCodeAsync` essere passata a invece di più argomenti.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
