---
ms.openlocfilehash: b1fb9647091cecb80b9c2f04ec9b6bb156eb39ba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84466817"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="0cd6b-101">API "Pubternal" rimosse</span><span class="sxs-lookup"><span data-stu-id="0cd6b-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="0cd6b-102">Per gestire meglio la superficie dell'API pubblica di ASP.NET Core, la maggior parte dei tipi negli `*.Internal` spazi dei nomi (detti :::no-loc text="\"pubternal\""::: API) è diventata effettivamente interna.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="0cd6b-103">I membri di questi spazi dei nomi non venivano mai progettati per essere supportati come API pubbliche.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="0cd6b-104">Le API possono interrompere le versioni secondarie e spesso.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="0cd6b-105">Il codice che dipende da queste API si interrompe quando si esegue l'aggiornamento a ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="0cd6b-106">Per altre informazioni, vedere [DotNet/aspnetcore # 4932](https://github.com/dotnet/aspnetcore/issues/4932) e [DotNet/aspnetcore # 11312](https://github.com/dotnet/aspnetcore/issues/11312).</span><span class="sxs-lookup"><span data-stu-id="0cd6b-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0cd6b-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0cd6b-107">Version introduced</span></span>

<span data-ttu-id="0cd6b-108">3.0</span><span class="sxs-lookup"><span data-stu-id="0cd6b-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0cd6b-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="0cd6b-109">Old behavior</span></span>

<span data-ttu-id="0cd6b-110">Le API interessate sono contrassegnate con il `public` modificatore di accesso e sono presenti negli `*.Internal` spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0cd6b-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="0cd6b-111">New behavior</span></span>

<span data-ttu-id="0cd6b-112">Le API interessate sono contrassegnate con il modificatore di accesso [interno](/dotnet/csharp/language-reference/keywords/internal) e non possono più essere utilizzate dal codice esterno a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-112">The affected APIs are marked with the [internal](/dotnet/csharp/language-reference/keywords/internal) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0cd6b-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="0cd6b-113">Reason for change</span></span>

<span data-ttu-id="0cd6b-114">Le linee guida per queste :::no-loc text="\"pubternal\""::: API sono:</span><span class="sxs-lookup"><span data-stu-id="0cd6b-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="0cd6b-115">Potrebbe cambiare senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-115">Could change without notice.</span></span>
* <span data-ttu-id="0cd6b-116">Non sono soggette ai criteri .NET per evitare modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="0cd6b-117">Lasciare le API `public` (anche negli `*.Internal` spazi dei nomi) è stato confuso per i clienti.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0cd6b-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0cd6b-118">Recommended action</span></span>

<span data-ttu-id="0cd6b-119">Interrompere l'uso di queste :::no-loc text="\"pubternal\""::: API.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="0cd6b-120">In caso di domande sulle API alternative, aprire un problema nel repository [DotNet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) .</span><span class="sxs-lookup"><span data-stu-id="0cd6b-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="0cd6b-121">Si consideri, ad esempio, il codice di buffer delle richieste HTTP seguente in un progetto ASP.NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="0cd6b-122">Il `EnableRewind` metodo di estensione esiste nello `Microsoft.AspNetCore.Http.Internal` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="0cd6b-123">In un progetto ASP.NET Core 3,0, sostituire la `EnableRewind` chiamata con una chiamata al `EnableBuffering` metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="0cd6b-124">La funzionalità di memorizzazione nel buffer delle richieste funziona come in passato.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="0cd6b-125">`EnableBuffering`chiama l' `internal` API Now.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="0cd6b-126">Categoria</span><span class="sxs-lookup"><span data-stu-id="0cd6b-126">Category</span></span>

<span data-ttu-id="0cd6b-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0cd6b-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0cd6b-128">API interessate</span><span class="sxs-lookup"><span data-stu-id="0cd6b-128">Affected APIs</span></span>

<span data-ttu-id="0cd6b-129">Tutte le API negli `Microsoft.AspNetCore.*` `Microsoft.Extensions.*` spazi dei nomi e che presentano un `Internal` segmento nel nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="0cd6b-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0cd6b-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
