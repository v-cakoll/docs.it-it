---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394283"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>Autenticazione: OAuthHandler ExchangeCodeAsync firma modificata

Nella ASP.NET Core 3,0 la firma di `OAuthHandler.ExchangeCodeAsync` è stata modificata da:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

A:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le stringhe `code` e `redirectUri` sono state passate come argomenti distinti.

#### <a name="new-behavior"></a>Nuovo comportamento

`Code` e `RedirectUri` sono proprietà in `OAuthCodeExchangeContext` che possono essere impostate tramite il costruttore `OAuthCodeExchangeContext`. Il nuovo tipo `OAuthCodeExchangeContext` è l'unico argomento passato a `OAuthHandler.ExchangeCodeAsync`.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica consente di fornire parametri aggiuntivi in modo non sostanziale. Non è necessario creare nuovi overload `ExchangeCodeAsync`.

#### <a name="recommended-action"></a>Azione consigliata

Costruire un `OAuthCodeExchangeContext` con i valori `code` e `redirectUri` appropriati. È necessario fornire un'istanza <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>. Questa singola istanza `OAuthCodeExchangeContext` può essere passata al `OAuthHandler.ExchangeCodeAsync` anziché a più argomenti.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
