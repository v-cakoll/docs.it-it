---
ms.openlocfilehash: b1d4b69b7a8ed68cd688dfd0249d5107b80e67c4
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281343"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a>Localizzazione: Costruttore obsoleto rimosso nel middleware di localizzazione della richiesta

Il <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> costruttore che non dispone di un <xref:Microsoft.Extensions.Logging.ILoggerFactory> parametro è stato contrassegnato come obsoleto [nel commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0). In ASP.NET Core 5,0, il costruttore obsoleto è stato rimosso. Per informazioni, vedere [DotNet/aspnetcore # 23785](https://github.com/dotnet/aspnetcore/issues/23785).

#### <a name="version-introduced"></a>Versione introdotta

5.0

#### <a name="old-behavior"></a>Comportamento precedente

Il costruttore obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` esiste.

#### <a name="new-behavior"></a>Nuovo comportamento

Il costruttore obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` non esiste.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica garantisce che il middleware di localizzazione delle richieste abbia sempre accesso a un logger.

#### <a name="recommended-action"></a>Azione consigliata

Quando si crea manualmente un'istanza di `RequestLocalizationMiddleware` , passare un' `ILoggerFactory` istanza del costruttore. Se un' `ILoggerFactory` istanza valida non è disponibile in tale contesto, provare a passare il costruttore del middleware a un' <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> istanza.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

[RequestLocalizationMiddleware. ctor (RequestDelegate, IOptions \<RequestLocalizationOptions> )](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
