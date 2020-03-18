---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902034"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="ddd77-101">HTTP: I/O sincrono disabilitato in tutti i server</span><span class="sxs-lookup"><span data-stu-id="ddd77-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="ddd77-102">A partire da ASP.NET Core 3.0, le operazioni sincrone del server sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd77-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ddd77-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="ddd77-103">Change description</span></span>

<span data-ttu-id="ddd77-104">`AllowSynchronousIO`è un'opzione in ogni server che abilita o `HttpRequest.Body.Read`disabilita `HttpResponse.Body.Write`le `Stream.Flush`API I/O sincrone come , , e .</span><span class="sxs-lookup"><span data-stu-id="ddd77-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="ddd77-105">Queste API sono state a lungo un'origine di fame di thread e app si blocca.</span><span class="sxs-lookup"><span data-stu-id="ddd77-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="ddd77-106">A partire da ASP.NET Core 3.0 Preview 3, queste operazioni sincrone sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd77-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="ddd77-107">Server interessati:</span><span class="sxs-lookup"><span data-stu-id="ddd77-107">Affected servers:</span></span>

- <span data-ttu-id="ddd77-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="ddd77-108">Kestrel</span></span>
- <span data-ttu-id="ddd77-109">HttpSys (informazioni in base al ruolo</span><span class="sxs-lookup"><span data-stu-id="ddd77-109">HttpSys</span></span>
- <span data-ttu-id="ddd77-110">IIS in-process</span><span class="sxs-lookup"><span data-stu-id="ddd77-110">IIS in-process</span></span>
- <span data-ttu-id="ddd77-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="ddd77-111">TestServer</span></span>

<span data-ttu-id="ddd77-112">Prevedere errori simili a:</span><span class="sxs-lookup"><span data-stu-id="ddd77-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="ddd77-113">Ogni server `AllowSynchronousIO` dispone di un'opzione che controlla questo `false`comportamento e l'impostazione predefinita per tutti è ora .</span><span class="sxs-lookup"><span data-stu-id="ddd77-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="ddd77-114">Il comportamento può anche essere sottoposto a override in base alle richieste come attenuazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="ddd77-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="ddd77-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ddd77-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="ddd77-116">Se si verificano `TextWriter` problemi con un o `Dispose`un altro `DisposeAsync` flusso che chiama un'API sincrona in , chiamare invece la nuova API.</span><span class="sxs-lookup"><span data-stu-id="ddd77-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="ddd77-117">Per una discussione, vedere [dotnet/aspnetcore-7644](https://github.com/dotnet/aspnetcore/issues/7644).</span><span class="sxs-lookup"><span data-stu-id="ddd77-117">For discussion, see [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ddd77-118">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ddd77-118">Version introduced</span></span>

<span data-ttu-id="ddd77-119">3.0</span><span class="sxs-lookup"><span data-stu-id="ddd77-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ddd77-120">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ddd77-120">Old behavior</span></span>

<span data-ttu-id="ddd77-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, `Stream.Flush` e sono stati consentiti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd77-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ddd77-122">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ddd77-122">New behavior</span></span>

<span data-ttu-id="ddd77-123">Queste API sincrone non sono consentite per impostazione predefinita:These synchronous APIs are disallowed by default:</span><span class="sxs-lookup"><span data-stu-id="ddd77-123">These synchronous APIs are disallowed by default:</span></span>

<span data-ttu-id="ddd77-124">Prevedere errori simili a:</span><span class="sxs-lookup"><span data-stu-id="ddd77-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="ddd77-125">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ddd77-125">Reason for change</span></span>

<span data-ttu-id="ddd77-126">Queste API sincrone sono state a lungo un'origine di fame di thread e si blocca l'app.</span><span class="sxs-lookup"><span data-stu-id="ddd77-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="ddd77-127">A partire da ASP.NET Core 3.0 Preview 3, le operazioni sincrone sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd77-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ddd77-128">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ddd77-128">Recommended action</span></span>

<span data-ttu-id="ddd77-129">Utilizzare le versioni asincrone dei metodi.</span><span class="sxs-lookup"><span data-stu-id="ddd77-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="ddd77-130">Il comportamento può anche essere sottoposto a override in base alle richieste come attenuazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="ddd77-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="ddd77-131">Category</span><span class="sxs-lookup"><span data-stu-id="ddd77-131">Category</span></span>

<span data-ttu-id="ddd77-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ddd77-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ddd77-133">API interessate</span><span class="sxs-lookup"><span data-stu-id="ddd77-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
