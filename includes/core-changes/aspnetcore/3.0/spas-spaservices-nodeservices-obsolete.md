---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394032"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="c2ed1-101">Spa: SpaServices e NodeServices contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="c2ed1-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="c2ed1-102">I contenuti dei pacchetti NuGet seguenti non sono stati tutti necessari a partire da ASP.NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="c2ed1-103">Di conseguenza, i pacchetti seguenti vengono contrassegnati come obsoleti:</span><span class="sxs-lookup"><span data-stu-id="c2ed1-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="c2ed1-104">Microsoft. AspNetCore. SpaServices</span><span class="sxs-lookup"><span data-stu-id="c2ed1-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="c2ed1-105">Microsoft. AspNetCore. NodeServices</span><span class="sxs-lookup"><span data-stu-id="c2ed1-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="c2ed1-106">Per lo stesso motivo, i moduli NPM seguenti sono contrassegnati come deprecati:</span><span class="sxs-lookup"><span data-stu-id="c2ed1-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="c2ed1-107">ASPNET-angolare</span><span class="sxs-lookup"><span data-stu-id="c2ed1-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="c2ed1-108">ASPNET-prerendering</span><span class="sxs-lookup"><span data-stu-id="c2ed1-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="c2ed1-109">ASPNET-Webpack</span><span class="sxs-lookup"><span data-stu-id="c2ed1-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="c2ed1-110">ASPNET-Webpack-React</span><span class="sxs-lookup"><span data-stu-id="c2ed1-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="c2ed1-111">dominio-attività</span><span class="sxs-lookup"><span data-stu-id="c2ed1-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="c2ed1-112">I pacchetti e i moduli NPM precedenti verranno rimossi in un secondo momento in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c2ed1-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c2ed1-113">Version introduced</span></span>

<span data-ttu-id="c2ed1-114">3.0</span><span class="sxs-lookup"><span data-stu-id="c2ed1-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c2ed1-115">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="c2ed1-115">Old behavior</span></span>

<span data-ttu-id="c2ed1-116">I pacchetti e i moduli NPM deprecati hanno lo scopo di integrare ASP.NET Core con diversi framework di app a singola pagina (SPA).</span><span class="sxs-lookup"><span data-stu-id="c2ed1-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="c2ed1-117">Tali Framework includono angolari, React e React con Redux.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c2ed1-118">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="c2ed1-118">New behavior</span></span>

<span data-ttu-id="c2ed1-119">Un nuovo meccanismo di integrazione è presente nel pacchetto NuGet [Microsoft. AspNetCore. SpaServices. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) .</span><span class="sxs-lookup"><span data-stu-id="c2ed1-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="c2ed1-120">Il pacchetto rimane la base dei modelli di progetto angolari e React a partire da ASP.NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c2ed1-121">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="c2ed1-121">Reason for change</span></span>

<span data-ttu-id="c2ed1-122">ASP.NET Core supporta l'integrazione con vari Framework di app a singola pagina (SPA), tra cui angolare, React e React con Redux.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="c2ed1-123">Inizialmente, l'integrazione con questi Framework è stata realizzata con componenti specifici di ASP.NET Core che gestivano scenari come il prerendering lato server e l'integrazione con Webpack.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="c2ed1-124">Con il passare del tempo, gli standard di settore sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="c2ed1-125">Ogni Framework di SPA rilascia le interfacce della riga di comando standard.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="c2ed1-126">Ad esempio, l'interfaccia della riga di comando angolare e crea-React-app.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="c2ed1-127">Quando ASP.NET Core 2,1 è stato rilasciato nel maggio 2018, il team ha risposto alla modifica degli standard.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="c2ed1-128">È stato fornito un metodo più recente e più semplice per l'integrazione con il toolchain dei framework di SPA.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="c2ed1-129">Il nuovo meccanismo di integrazione è presente nel pacchetto `Microsoft.AspNetCore.SpaServices.Extensions` e rimane la base dei modelli di progetto angolari e React a partire da ASP.NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="c2ed1-130">Per chiarire che i componenti meno recenti ASP.NET Core specifici sono irrilevanti e non sono consigliati:</span><span class="sxs-lookup"><span data-stu-id="c2ed1-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="c2ed1-131">Il meccanismo di integrazione precedente a 2,1 è contrassegnato come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="c2ed1-132">I pacchetti NPM di supporto sono contrassegnati come deprecati.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c2ed1-133">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c2ed1-133">Recommended action</span></span>

<span data-ttu-id="c2ed1-134">Se si usano questi pacchetti, aggiornare le app per usare la funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c2ed1-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="c2ed1-135">Nel pacchetto `Microsoft.AspNetCore.SpaServices.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="c2ed1-136">Fornito dai Framework SPA in uso</span><span class="sxs-lookup"><span data-stu-id="c2ed1-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="c2ed1-137">Per abilitare funzionalità come il prerendering lato server e il ricaricamento del modulo attivo, vedere la documentazione relativa al Framework SPA corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="c2ed1-138">La funzionalità in `Microsoft.AspNetCore.SpaServices.Extensions` *non* è obsoleta e continuerà a essere supportata.</span><span class="sxs-lookup"><span data-stu-id="c2ed1-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="c2ed1-139">Category</span><span class="sxs-lookup"><span data-stu-id="c2ed1-139">Category</span></span>

<span data-ttu-id="c2ed1-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c2ed1-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c2ed1-141">API interessate</span><span class="sxs-lookup"><span data-stu-id="c2ed1-141">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
