---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902034"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a>HTTP: IO sincrono disabilitato in tutti i server

A partire da ASP.NET Core 3,0, le operazioni sincrone del server sono disabilitate per impostazione predefinita.

#### <a name="change-description"></a>Descrizione delle modifiche

`AllowSynchronousIO` è un'opzione in ogni server che Abilita o Disabilita le API di i/o sincrono come `HttpRequest.Body.Read`, `HttpResponse.Body.Write`e `Stream.Flush`. Queste API sono state a lungo un'origine di inedia dei thread e l'app si blocca. A partire da ASP.NET Core 3,0 Preview 3, queste operazioni sincrone sono disabilitate per impostazione predefinita.

Server interessati:

- Kestrel
- HttpSys
- IIS in-process
- TestServer

Si verificano errori simili a:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

Ogni server dispone di un'opzione di `AllowSynchronousIO` che controlla questo comportamento e il valore predefinito per tutti i server è ora `false`.

È anche possibile eseguire l'override del comportamento in base alle singole richieste come mitigazione temporanea. Ad esempio:

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

Se si riscontrano problemi con un `TextWriter` o un altro flusso che chiama un'API sincrona in `Dispose`, chiamare invece la nuova API `DisposeAsync`.

Per informazioni, vedere [DotNet/aspnetcore # 7644](https://github.com/dotnet/aspnetcore/issues/7644).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`HttpRequest.Body.Read`, `HttpResponse.Body.Write`e `Stream.Flush` sono consentiti per impostazione predefinita.

#### <a name="new-behavior"></a>Nuovo comportamento

Queste API sincrone non sono consentite per impostazione predefinita:

Si verificano errori simili a:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a>Motivo della modifica

Queste API sincrone sono state a lungo un'origine di inedia dei thread e l'app si blocca. A partire da ASP.NET Core 3,0 Preview 3, le operazioni sincrone sono disabilitate per impostazione predefinita.

#### <a name="recommended-action"></a>Azione consigliata

Usare le versioni asincrone dei metodi. È anche possibile eseguire l'override del comportamento in base alle singole richieste come mitigazione temporanea.

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
