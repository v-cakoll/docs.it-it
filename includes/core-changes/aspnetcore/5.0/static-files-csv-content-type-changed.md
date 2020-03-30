---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391182"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>File statici: il tipo di contenuto CSV modificato in standard-compliant

In ASP.NET Core 5.0, il valore dell'intestazione `Content-Type` di risposta predefinita utilizzato dal middleware dei file [statici](/aspnet/core/fundamentals/static-files) per i file *CSV* è stato modificato nel valore `text/csv`conforme agli standard.

Per una discussione su questo problema, vedere [dotnet/aspnetcore-17385](https://github.com/dotnet/AspNetCore/issues/17385).

#### <a name="version-introduced"></a>Versione introdotta

5.0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

È `Content-Type` stato `application/octet-stream` utilizzato il valore dell'intestazione.

#### <a name="new-behavior"></a>Nuovo comportamento

Viene `Content-Type` utilizzato `text/csv` il valore dell'intestazione.

#### <a name="reason-for-change"></a>Motivo della modifica

Conformità con lo standard [RFC 7111.](https://tools.ietf.org/html/rfc7111#section-5.1)

#### <a name="recommended-action"></a>Azione consigliata

Se questa modifica influisce sull'app, puoi personalizzare il mapping tra estensione di file e tipo MIME. Per ripristinare `application/octet-stream` il tipo MIME, modificare la chiamata al <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> metodo in `Startup.Configure`. Ad esempio:

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

Per ulteriori informazioni sulla personalizzazione del mapping, vedere [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
