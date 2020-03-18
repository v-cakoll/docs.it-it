---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902034"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a>HTTP: I/O sincrono disabilitato in tutti i server

A partire da ASP.NET Core 3.0, le operazioni sincrone del server sono disabilitate per impostazione predefinita.

#### <a name="change-description"></a>Descrizione modifica:

`AllowSynchronousIO`è un'opzione in ogni server che abilita o `HttpRequest.Body.Read`disabilita `HttpResponse.Body.Write`le `Stream.Flush`API I/O sincrone come , , e . Queste API sono state a lungo un'origine di fame di thread e app si blocca. A partire da ASP.NET Core 3.0 Preview 3, queste operazioni sincrone sono disabilitate per impostazione predefinita.

Server interessati:

- Kestrel
- HttpSys (informazioni in base al ruolo
- IIS in-process
- TestServer

Prevedere errori simili a:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

Ogni server `AllowSynchronousIO` dispone di un'opzione che controlla questo `false`comportamento e l'impostazione predefinita per tutti è ora .

Il comportamento può anche essere sottoposto a override in base alle richieste come attenuazione temporanea. Ad esempio:

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

Se si verificano `TextWriter` problemi con un o `Dispose`un altro `DisposeAsync` flusso che chiama un'API sincrona in , chiamare invece la nuova API.

Per una discussione, vedere [dotnet/aspnetcore-7644](https://github.com/dotnet/aspnetcore/issues/7644).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, `Stream.Flush` e sono stati consentiti per impostazione predefinita.

#### <a name="new-behavior"></a>Nuovo comportamento

Queste API sincrone non sono consentite per impostazione predefinita:These synchronous APIs are disallowed by default:

Prevedere errori simili a:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a>Motivo della modifica

Queste API sincrone sono state a lungo un'origine di fame di thread e si blocca l'app. A partire da ASP.NET Core 3.0 Preview 3, le operazioni sincrone sono disabilitate per impostazione predefinita.

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare le versioni asincrone dei metodi. Il comportamento può anche essere sottoposto a override in base alle richieste come attenuazione temporanea.

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a>Category

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
