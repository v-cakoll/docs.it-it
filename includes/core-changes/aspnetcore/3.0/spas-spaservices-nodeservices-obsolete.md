---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394032"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="98400-101">SPAA: SpaServices e NodeServices contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="98400-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="98400-102">Il contenuto dei pacchetti NuGet seguenti sono stati tutti non necessari a partire da ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="98400-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="98400-103">Di conseguenza, i seguenti pacchetti vengono contrassegnati come obsoleti:</span><span class="sxs-lookup"><span data-stu-id="98400-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="98400-104">Microsoft.AspNetCore.SpaServices</span><span class="sxs-lookup"><span data-stu-id="98400-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="98400-105">Microsoft.AspNetCore.NodeServices</span><span class="sxs-lookup"><span data-stu-id="98400-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="98400-106">Per lo stesso motivo, i seguenti moduli npm vengono contrassegnati come deprecati:</span><span class="sxs-lookup"><span data-stu-id="98400-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="98400-107">angolare aspnet</span><span class="sxs-lookup"><span data-stu-id="98400-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="98400-108">prerendering di aspnet</span><span class="sxs-lookup"><span data-stu-id="98400-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="98400-109">aspnet-webpack (informazioni in lingua inglese)</span><span class="sxs-lookup"><span data-stu-id="98400-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="98400-110">aspnet-webpack-react</span><span class="sxs-lookup"><span data-stu-id="98400-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="98400-111">dominio-attività</span><span class="sxs-lookup"><span data-stu-id="98400-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="98400-112">I pacchetti precedenti e i moduli npm verranno successivamente rimossi in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="98400-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="98400-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="98400-113">Version introduced</span></span>

<span data-ttu-id="98400-114">3.0</span><span class="sxs-lookup"><span data-stu-id="98400-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="98400-115">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="98400-115">Old behavior</span></span>

<span data-ttu-id="98400-116">I pacchetti deprecati e i moduli npm erano destinati a integrare ASP.NET Core con vari framework SPA (Single-Page App).</span><span class="sxs-lookup"><span data-stu-id="98400-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="98400-117">Tali framework includono Angular, React e React with Redux.</span><span class="sxs-lookup"><span data-stu-id="98400-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="98400-118">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="98400-118">New behavior</span></span>

<span data-ttu-id="98400-119">Nel pacchetto NuGet di [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) è presente un nuovo meccanismo di integrazione.</span><span class="sxs-lookup"><span data-stu-id="98400-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="98400-120">Il pacchetto rimane la base dei modelli di progetto Angular e React da quando ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="98400-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="98400-121">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="98400-121">Reason for change</span></span>

<span data-ttu-id="98400-122">ASP.NET Core supporta l'integrazione con vari framework SPA (Single-Page App), tra cui Angular, React e React with Redux.</span><span class="sxs-lookup"><span data-stu-id="98400-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="98400-123">Inizialmente, l'integrazione con questi framework è stata completata con ASP.NET componenti specifici di Core che gestivano scenari come il prerendering lato server e l'integrazione con Webpack.</span><span class="sxs-lookup"><span data-stu-id="98400-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="98400-124">Col passare del tempo, gli standard del settore cambiarono.</span><span class="sxs-lookup"><span data-stu-id="98400-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="98400-125">Ognuno dei framework SPA rilasciato le proprie interfacce della riga di comando standard.</span><span class="sxs-lookup"><span data-stu-id="98400-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="98400-126">Ad esempio, CLI angolare e create-react-app.</span><span class="sxs-lookup"><span data-stu-id="98400-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="98400-127">Quando ASP.NET Core 2.1 è stato rilasciato nel maggio 2018, il team ha risposto al cambiamento degli standard.</span><span class="sxs-lookup"><span data-stu-id="98400-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="98400-128">È stato fornito un modo più nuovo e semplice per integrarsi con le catene di strumenti dei framework SPA.</span><span class="sxs-lookup"><span data-stu-id="98400-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="98400-129">Il nuovo meccanismo di `Microsoft.AspNetCore.SpaServices.Extensions` integrazione esiste nel pacchetto e rimane la base dei modelli di progetto Angular e React da quando ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="98400-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="98400-130">Per chiarire che i componenti meno recenti ASP.NET Core sono irrilevanti e non consigliati:</span><span class="sxs-lookup"><span data-stu-id="98400-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="98400-131">Il meccanismo di integrazione pre-2.1 è contrassegnato come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="98400-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="98400-132">I pacchetti npm di supporto sono contrassegnati come deprecati.</span><span class="sxs-lookup"><span data-stu-id="98400-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="98400-133">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="98400-133">Recommended action</span></span>

<span data-ttu-id="98400-134">Se usi questi pacchetti, aggiorna le app per usare la funzionalità:</span><span class="sxs-lookup"><span data-stu-id="98400-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="98400-135">Nel `Microsoft.AspNetCore.SpaServices.Extensions` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="98400-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="98400-136">Fornito dai framework SPA in uso</span><span class="sxs-lookup"><span data-stu-id="98400-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="98400-137">Per abilitare funzionalità come il prerendering sul lato server e il ricaricamento dei moduli a caldo, vedere la documentazione relativa al framework SPA corrispondente.</span><span class="sxs-lookup"><span data-stu-id="98400-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="98400-138">La funzionalità `Microsoft.AspNetCore.SpaServices.Extensions` in *non* è obsoleta e continuerà a essere supportata.</span><span class="sxs-lookup"><span data-stu-id="98400-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="98400-139">Category</span><span class="sxs-lookup"><span data-stu-id="98400-139">Category</span></span>

<span data-ttu-id="98400-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="98400-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="98400-141">API interessate</span><span class="sxs-lookup"><span data-stu-id="98400-141">Affected APIs</span></span>

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
