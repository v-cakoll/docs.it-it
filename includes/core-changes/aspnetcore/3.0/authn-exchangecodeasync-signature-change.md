---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394283"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="75116-101">Autenticazione: firma OAuthHandler ExchangeCodeAsync modificata</span><span class="sxs-lookup"><span data-stu-id="75116-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="75116-102">In ASP.NET Core 3.0, `OAuthHandler.ExchangeCodeAsync` la firma di è stata modificata da:</span><span class="sxs-lookup"><span data-stu-id="75116-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="75116-103">Con:</span><span class="sxs-lookup"><span data-stu-id="75116-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="75116-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="75116-104">Version introduced</span></span>

<span data-ttu-id="75116-105">3.0</span><span class="sxs-lookup"><span data-stu-id="75116-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="75116-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="75116-106">Old behavior</span></span>

<span data-ttu-id="75116-107">Le `code` `redirectUri` stringhe e sono state passate come argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="75116-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="75116-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="75116-108">New behavior</span></span>

<span data-ttu-id="75116-109">`Code`e `RedirectUri` sono `OAuthCodeExchangeContext` proprietà su che `OAuthCodeExchangeContext` possono essere impostate tramite il costruttore.</span><span class="sxs-lookup"><span data-stu-id="75116-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="75116-110">Il `OAuthCodeExchangeContext` nuovo tipo è l'unico argomento passato a `OAuthHandler.ExchangeCodeAsync`.</span><span class="sxs-lookup"><span data-stu-id="75116-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="75116-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="75116-111">Reason for change</span></span>

<span data-ttu-id="75116-112">Questa modifica consente di fornire parametri aggiuntivi in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="75116-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="75116-113">Non è necessario creare `ExchangeCodeAsync` nuovi overload.</span><span class="sxs-lookup"><span data-stu-id="75116-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="75116-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="75116-114">Recommended action</span></span>

<span data-ttu-id="75116-115">Costruire `OAuthCodeExchangeContext` un con `code` `redirectUri` i valori e e appropriati.</span><span class="sxs-lookup"><span data-stu-id="75116-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="75116-116">È <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> necessario fornire un'istanza.</span><span class="sxs-lookup"><span data-stu-id="75116-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="75116-117">Questa `OAuthCodeExchangeContext` singola istanza può `OAuthHandler.ExchangeCodeAsync` essere passata a invece di più argomenti.</span><span class="sxs-lookup"><span data-stu-id="75116-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="75116-118">Category</span><span class="sxs-lookup"><span data-stu-id="75116-118">Category</span></span>

<span data-ttu-id="75116-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="75116-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="75116-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="75116-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
