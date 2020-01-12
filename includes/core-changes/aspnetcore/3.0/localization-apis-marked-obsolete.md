---
ms.openlocfilehash: 8cb0aca991f5adfe4561ef56090cb9f7b2e56283
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901852"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="d9fbd-101">Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="d9fbd-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="d9fbd-102">La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini di confusione per gli utenti della localizzazione, soprattutto quando si crea una propria implementazione di `IStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="d9fbd-103">Questi elementi danno all'utente l'impressione che un'istanza di `IStringLocalizer` sia "per lingua, per risorsa".</span><span class="sxs-lookup"><span data-stu-id="d9fbd-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="d9fbd-104">In realtà, le istanze devono essere solo "per risorsa".</span><span class="sxs-lookup"><span data-stu-id="d9fbd-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="d9fbd-105">La lingua cercata è determinata dalla `CultureInfo.CurrentUICulture` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="d9fbd-106">Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3,0 Preview 3.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="d9fbd-107">Le API verranno rimosse in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="d9fbd-108">Per il contesto, vedere [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="d9fbd-108">For context, see [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="d9fbd-109">Per informazioni, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="d9fbd-109">For discussion, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9fbd-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d9fbd-110">Version introduced</span></span>

<span data-ttu-id="d9fbd-111">3.0</span><span class="sxs-lookup"><span data-stu-id="d9fbd-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d9fbd-112">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d9fbd-112">Old behavior</span></span>

<span data-ttu-id="d9fbd-113">I metodi non sono stati contrassegnati come `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d9fbd-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d9fbd-114">New behavior</span></span>

<span data-ttu-id="d9fbd-115">I metodi sono contrassegnati come `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d9fbd-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d9fbd-116">Reason for change</span></span>

<span data-ttu-id="d9fbd-117">Le API rappresentano un caso d'uso non consigliato.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="d9fbd-118">Si è verificato un confuso sulla progettazione della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9fbd-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d9fbd-119">Recommended action</span></span>

<span data-ttu-id="d9fbd-120">Si consiglia di usare invece `ResourceManagerStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="d9fbd-121">Consente di impostare le impostazioni cultura dal `CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="d9fbd-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="d9fbd-122">Se questa opzione non è disponibile, creare e usare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span><span class="sxs-lookup"><span data-stu-id="d9fbd-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="d9fbd-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="d9fbd-123">Category</span></span>

<span data-ttu-id="d9fbd-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9fbd-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9fbd-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="d9fbd-125">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
