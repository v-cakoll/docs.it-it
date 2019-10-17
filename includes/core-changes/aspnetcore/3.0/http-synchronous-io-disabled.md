---
ms.openlocfilehash: ab7c097f6b65d539117e5a6ef38eb67b24695a32
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394348"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="76e6b-101">HTTP: IO sincrono disabilitato in tutti i server</span><span class="sxs-lookup"><span data-stu-id="76e6b-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="76e6b-102">A partire da ASP.NET Core 3,0, le operazioni sincrone del server sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76e6b-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="76e6b-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="76e6b-103">Change description</span></span>

<span data-ttu-id="76e6b-104">`AllowSynchronousIO` è un'opzione in ogni server che Abilita o Disabilita le API di i/o sincrono come `HttpRequest.Body.Read`, `HttpResponse.Body.Write` e `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="76e6b-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="76e6b-105">Queste API sono state a lungo un'origine di inedia dei thread e l'app si blocca.</span><span class="sxs-lookup"><span data-stu-id="76e6b-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="76e6b-106">A partire da ASP.NET Core 3,0 Preview 3, queste operazioni sincrone sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76e6b-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="76e6b-107">Server interessati:</span><span class="sxs-lookup"><span data-stu-id="76e6b-107">Affected servers:</span></span>

- <span data-ttu-id="76e6b-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="76e6b-108">Kestrel</span></span>
- <span data-ttu-id="76e6b-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="76e6b-109">HttpSys</span></span>
- <span data-ttu-id="76e6b-110">IIS in-process</span><span class="sxs-lookup"><span data-stu-id="76e6b-110">IIS in-process</span></span>
- <span data-ttu-id="76e6b-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="76e6b-111">TestServer</span></span>

<span data-ttu-id="76e6b-112">Si verificano errori simili a:</span><span class="sxs-lookup"><span data-stu-id="76e6b-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="76e6b-113">Ogni server dispone di un'opzione `AllowSynchronousIO` che controlla questo comportamento e il valore predefinito per tutti i server è ora `false`.</span><span class="sxs-lookup"><span data-stu-id="76e6b-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="76e6b-114">È anche possibile eseguire l'override del comportamento in base alle singole richieste come mitigazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="76e6b-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="76e6b-115">Esempio:</span><span class="sxs-lookup"><span data-stu-id="76e6b-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="76e6b-116">Se si riscontrano problemi con un `TextWriter` o un altro flusso che chiama un'API sincrona in `Dispose`, chiamare invece la nuova API `DisposeAsync`.</span><span class="sxs-lookup"><span data-stu-id="76e6b-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="76e6b-117">Per informazioni, vedere [ASPNET/AspNetCore # 7644](https://github.com/aspnet/AspNetCore/issues/7644).</span><span class="sxs-lookup"><span data-stu-id="76e6b-117">For discussion, see [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76e6b-118">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="76e6b-118">Version introduced</span></span>

<span data-ttu-id="76e6b-119">3.0</span><span class="sxs-lookup"><span data-stu-id="76e6b-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="76e6b-120">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="76e6b-120">Old behavior</span></span>

<span data-ttu-id="76e6b-121">per impostazione predefinita sono consentiti `HttpRequest.Body.Read`, `HttpResponse.Body.Write` e `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="76e6b-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="76e6b-122">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="76e6b-122">New behavior</span></span>

<span data-ttu-id="76e6b-123">Queste API sincrone non sono consentite per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="76e6b-123">These synchronous APIs are disallowed by default:</span></span> 

<span data-ttu-id="76e6b-124">Si verificano errori simili a:</span><span class="sxs-lookup"><span data-stu-id="76e6b-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="76e6b-125">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="76e6b-125">Reason for change</span></span>

<span data-ttu-id="76e6b-126">Queste API sincrone sono state a lungo un'origine di inedia dei thread e l'app si blocca.</span><span class="sxs-lookup"><span data-stu-id="76e6b-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="76e6b-127">A partire da ASP.NET Core 3,0 Preview 3, le operazioni sincrone sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76e6b-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76e6b-128">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="76e6b-128">Recommended action</span></span>

<span data-ttu-id="76e6b-129">Usare le versioni asincrone dei metodi.</span><span class="sxs-lookup"><span data-stu-id="76e6b-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="76e6b-130">È anche possibile eseguire l'override del comportamento in base alle singole richieste come mitigazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="76e6b-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="76e6b-131">Category</span><span class="sxs-lookup"><span data-stu-id="76e6b-131">Category</span></span>

<span data-ttu-id="76e6b-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76e6b-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76e6b-133">API interessate</span><span class="sxs-lookup"><span data-stu-id="76e6b-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
