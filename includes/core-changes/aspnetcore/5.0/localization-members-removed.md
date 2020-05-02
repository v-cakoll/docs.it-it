---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728280"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="b3647-101">Localizzazione: classe ResourceManagerWithCultureStringLocalizer e membro dell'interfaccia WithCulture rimossi</span><span class="sxs-lookup"><span data-stu-id="b3647-101">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="b3647-102">La classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e il metodo [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) sono stati rimossi in .NET 5,0 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="b3647-102">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="b3647-103">Per il contesto, vedere [ASPNET/annunciations # 346](https://github.com/aspnet/Announcements/issues/346) e [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="b3647-103">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="b3647-104">Per informazioni su questa modifica, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="b3647-104">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3647-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b3647-105">Version introduced</span></span>

<span data-ttu-id="b3647-106">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="b3647-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b3647-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="b3647-107">Old behavior</span></span>

<span data-ttu-id="b3647-108">La `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo sono [obsoleti in .NET Core 3,0 Preview 3 e versioni successive](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="b3647-108">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b3647-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="b3647-109">New behavior</span></span>

<span data-ttu-id="b3647-110">La `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo sono stati rimossi in .NET 5,0 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="b3647-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="b3647-111">Per un inventario delle modifiche apportate, vedere la richiesta pull in [DotNet/Extensions # 2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="b3647-111">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b3647-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="b3647-112">Reason for change</span></span>

<span data-ttu-id="b3647-113">La classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e il metodo [ResourceManagerStringLocalizer. WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) spesso erano origini di confusione per gli utenti della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="b3647-113">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="b3647-114">La confusione era particolarmente elevata quando si crea un' <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b3647-114">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="b3647-115">Questa classe e metodo forniscono agli utenti l'impressione che `IStringLocalizer` un'istanza sia "per lingua, per risorsa".</span><span class="sxs-lookup"><span data-stu-id="b3647-115">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="b3647-116">In realtà, l'istanza deve essere solo "per risorsa".</span><span class="sxs-lookup"><span data-stu-id="b3647-116">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="b3647-117">In fase di esecuzione, <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> la proprietà determina il linguaggio da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b3647-117">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3647-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b3647-118">Recommended action</span></span>

<span data-ttu-id="b3647-119">Arrestare utilizzando la `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo.</span><span class="sxs-lookup"><span data-stu-id="b3647-119">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

#### <a name="category"></a><span data-ttu-id="b3647-120">Category</span><span class="sxs-lookup"><span data-stu-id="b3647-120">Category</span></span>

<span data-ttu-id="b3647-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3647-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3647-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="b3647-122">Affected APIs</span></span>

- [<span data-ttu-id="b3647-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="b3647-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="b3647-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="b3647-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
