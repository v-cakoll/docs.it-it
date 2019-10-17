---
ms.openlocfilehash: da1ec7908b3082fc61313cb805773aa600bc1b5d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394096"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="2cf41-101">Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="2cf41-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="2cf41-102">La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini di confusione per gli utenti della localizzazione, soprattutto quando si crea una propria implementazione `IStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="2cf41-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="2cf41-103">Questi elementi danno all'utente l'impressione che un'istanza `IStringLocalizer` sia "per lingua, per risorsa".</span><span class="sxs-lookup"><span data-stu-id="2cf41-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="2cf41-104">In realtà, le istanze devono essere solo "per risorsa".</span><span class="sxs-lookup"><span data-stu-id="2cf41-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="2cf41-105">La lingua cercata è determinata dalla `CultureInfo.CurrentUICulture` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2cf41-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="2cf41-106">Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3,0 Preview 3.</span><span class="sxs-lookup"><span data-stu-id="2cf41-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="2cf41-107">Le API verranno rimosse in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="2cf41-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="2cf41-108">Per il contesto, vedere [ASPNET/AspNetCore # 3324](https://github.com/aspnet/AspNetCore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="2cf41-108">For context, see [aspnet/AspNetCore#3324](https://github.com/aspnet/AspNetCore/issues/3324).</span></span> <span data-ttu-id="2cf41-109">Per informazioni, vedere [ASPNET/AspNetCore # 7756](https://github.com/aspnet/AspNetCore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="2cf41-109">For discussion, see [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2cf41-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2cf41-110">Version introduced</span></span>

<span data-ttu-id="2cf41-111">3.0</span><span class="sxs-lookup"><span data-stu-id="2cf41-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2cf41-112">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2cf41-112">Old behavior</span></span>

<span data-ttu-id="2cf41-113">I metodi non sono stati contrassegnati come `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="2cf41-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2cf41-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2cf41-114">New behavior</span></span>

<span data-ttu-id="2cf41-115">I metodi sono contrassegnati `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="2cf41-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2cf41-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2cf41-116">Reason for change</span></span>

<span data-ttu-id="2cf41-117">Le API rappresentano un caso d'uso non consigliato.</span><span class="sxs-lookup"><span data-stu-id="2cf41-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="2cf41-118">Si è verificato un confuso sulla progettazione della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cf41-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2cf41-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2cf41-119">Recommended action</span></span>

<span data-ttu-id="2cf41-120">Si consiglia di usare invece `ResourceManagerStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="2cf41-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="2cf41-121">Consente di impostare le impostazioni cultura tramite il `CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="2cf41-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="2cf41-122">Se questa opzione non è disponibile, creare e usare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span><span class="sxs-lookup"><span data-stu-id="2cf41-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="2cf41-123">Category</span><span class="sxs-lookup"><span data-stu-id="2cf41-123">Category</span></span>

<span data-ttu-id="2cf41-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2cf41-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2cf41-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="2cf41-125">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
