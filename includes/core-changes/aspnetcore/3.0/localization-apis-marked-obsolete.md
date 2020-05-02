---
ms.openlocfilehash: d70a8d2a3031a5b3d47ab3fb7f40193dce6e311e
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728345"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="38ed8-101">Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="38ed8-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="38ed8-102">La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini di confusione per gli utenti della localizzazione, soprattutto quando `IStringLocalizer` si crea una propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="38ed8-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="38ed8-103">Questi elementi danno all'utente l'impressione che un' `IStringLocalizer` istanza sia "per lingua, per risorsa".</span><span class="sxs-lookup"><span data-stu-id="38ed8-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="38ed8-104">In realtà, le istanze devono essere solo "per risorsa".</span><span class="sxs-lookup"><span data-stu-id="38ed8-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="38ed8-105">La lingua cercata è determinata da `CultureInfo.CurrentUICulture` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38ed8-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="38ed8-106">Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3,0 Preview 3.</span><span class="sxs-lookup"><span data-stu-id="38ed8-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="38ed8-107">Le API verranno rimosse in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="38ed8-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="38ed8-108">Per il contesto, vedere [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="38ed8-108">For context, see [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="38ed8-109">Per informazioni, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="38ed8-109">For discussion, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="38ed8-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="38ed8-110">Version introduced</span></span>

<span data-ttu-id="38ed8-111">3.0</span><span class="sxs-lookup"><span data-stu-id="38ed8-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="38ed8-112">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="38ed8-112">Old behavior</span></span>

<span data-ttu-id="38ed8-113">I metodi non sono `Obsolete`stati contrassegnati come.</span><span class="sxs-lookup"><span data-stu-id="38ed8-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="38ed8-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="38ed8-114">New behavior</span></span>

<span data-ttu-id="38ed8-115">I metodi sono `Obsolete`contrassegnati come.</span><span class="sxs-lookup"><span data-stu-id="38ed8-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="38ed8-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="38ed8-116">Reason for change</span></span>

<span data-ttu-id="38ed8-117">Le API rappresentano un caso d'uso non consigliato.</span><span class="sxs-lookup"><span data-stu-id="38ed8-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="38ed8-118">Si è verificato un confuso sulla progettazione della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="38ed8-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="38ed8-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="38ed8-119">Recommended action</span></span>

<span data-ttu-id="38ed8-120">Si consiglia di usare `ResourceManagerStringLocalizer` in alternativa.</span><span class="sxs-lookup"><span data-stu-id="38ed8-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="38ed8-121">Consentire alle impostazioni cultura di essere impostate `CurrentCulture`da.</span><span class="sxs-lookup"><span data-stu-id="38ed8-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="38ed8-122">Se questa opzione non è disponibile, creare e usare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span><span class="sxs-lookup"><span data-stu-id="38ed8-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="38ed8-123">Category</span><span class="sxs-lookup"><span data-stu-id="38ed8-123">Category</span></span>

<span data-ttu-id="38ed8-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="38ed8-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="38ed8-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="38ed8-125">Affected APIs</span></span>

- [<span data-ttu-id="38ed8-126">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="38ed8-126">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.0)
- [<span data-ttu-id="38ed8-127">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="38ed8-127">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.0)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
