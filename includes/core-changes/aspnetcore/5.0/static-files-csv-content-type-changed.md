---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391182"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="5026e-101">File statici: il tipo di contenuto CSV modificato in standard-compliant</span><span class="sxs-lookup"><span data-stu-id="5026e-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="5026e-102">In ASP.NET Core 5.0, il valore dell'intestazione `Content-Type` di risposta predefinita utilizzato dal middleware dei file [statici](/aspnet/core/fundamentals/static-files) per i file *CSV* è stato modificato nel valore `text/csv`conforme agli standard.</span><span class="sxs-lookup"><span data-stu-id="5026e-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="5026e-103">Per una discussione su questo problema, vedere [dotnet/aspnetcore-17385](https://github.com/dotnet/AspNetCore/issues/17385).</span><span class="sxs-lookup"><span data-stu-id="5026e-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5026e-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5026e-104">Version introduced</span></span>

<span data-ttu-id="5026e-105">5.0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="5026e-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5026e-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="5026e-106">Old behavior</span></span>

<span data-ttu-id="5026e-107">È `Content-Type` stato `application/octet-stream` utilizzato il valore dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5026e-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5026e-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="5026e-108">New behavior</span></span>

<span data-ttu-id="5026e-109">Viene `Content-Type` utilizzato `text/csv` il valore dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5026e-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5026e-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="5026e-110">Reason for change</span></span>

<span data-ttu-id="5026e-111">Conformità con lo standard [RFC 7111.](https://tools.ietf.org/html/rfc7111#section-5.1)</span><span class="sxs-lookup"><span data-stu-id="5026e-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5026e-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5026e-112">Recommended action</span></span>

<span data-ttu-id="5026e-113">Se questa modifica influisce sull'app, puoi personalizzare il mapping tra estensione di file e tipo MIME.</span><span class="sxs-lookup"><span data-stu-id="5026e-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="5026e-114">Per ripristinare `application/octet-stream` il tipo MIME, modificare la chiamata al <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> metodo in `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="5026e-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="5026e-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5026e-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="5026e-116">Per ulteriori informazioni sulla personalizzazione del mapping, vedere [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="5026e-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="5026e-117">Category</span><span class="sxs-lookup"><span data-stu-id="5026e-117">Category</span></span>

<span data-ttu-id="5026e-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5026e-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5026e-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="5026e-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
