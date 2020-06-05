---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446972"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="19006-101">Localizzazione: API "Pubternal" rimosse</span><span class="sxs-lookup"><span data-stu-id="19006-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="19006-102">Per gestire meglio la superficie dell'API pubblica di ASP.NET Core, alcune :::no-loc text="\"pubternal\""::: API di localizzazione sono state rimosse.</span><span class="sxs-lookup"><span data-stu-id="19006-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="19006-103">Un' :::no-loc text="\"pubternal\""::: API ha un `public` modificatore di accesso e viene definita in uno spazio dei nomi che implica una finalità [interna](/dotnet/csharp/language-reference/keywords/internal) .</span><span class="sxs-lookup"><span data-stu-id="19006-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](/dotnet/csharp/language-reference/keywords/internal) intent.</span></span>

<span data-ttu-id="19006-104">Per informazioni, vedere [DotNet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="19006-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="19006-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="19006-105">Version introduced</span></span>

<span data-ttu-id="19006-106">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="19006-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="19006-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="19006-107">Old behavior</span></span>

<span data-ttu-id="19006-108">Di seguito sono riportate le API `public` :</span><span class="sxs-lookup"><span data-stu-id="19006-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="19006-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`Overload del costruttore che accettano uno dei seguenti tipi di parametro:</span><span class="sxs-lookup"><span data-stu-id="19006-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="19006-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="19006-110">New behavior</span></span>

<span data-ttu-id="19006-111">Nell'elenco seguente vengono descritte le modifiche:</span><span class="sxs-lookup"><span data-stu-id="19006-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="19006-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper``Microsoft.Extensions.Localization.AssemblyWrapper`è diventato ed è ora `internal` .</span><span class="sxs-lookup"><span data-stu-id="19006-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="19006-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider``Microsoft.Extensions.Localization.Internal.IResourceStringProvider`è diventato ed è ora `internal` .</span><span class="sxs-lookup"><span data-stu-id="19006-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="19006-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`gli overload del costruttore che accettano uno dei seguenti tipi di parametro sono ora `internal` :</span><span class="sxs-lookup"><span data-stu-id="19006-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="19006-115">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="19006-115">Reason for change</span></span>

<span data-ttu-id="19006-116">Spiegazione più approfondita di [ASPNET/annunci n. 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: i tipi sono stati rimossi dalla `public` superficie dell'API.</span><span class="sxs-lookup"><span data-stu-id="19006-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="19006-117">Queste modifiche adattano più classi alla decisione di progettazione.</span><span class="sxs-lookup"><span data-stu-id="19006-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="19006-118">Le classi in questione sono state progettate come punti di estensione per i test interni del team.</span><span class="sxs-lookup"><span data-stu-id="19006-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="19006-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="19006-119">Recommended action</span></span>

<span data-ttu-id="19006-120">Sebbene sia improbabile, è possibile che alcune app dipendano intenzionalmente o accidentalmente dai :::no-loc text="\"pubternal\""::: tipi.</span><span class="sxs-lookup"><span data-stu-id="19006-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="19006-121">Vedere le sezioni relative al [nuovo comportamento](#new-behavior) per determinare la modalità di migrazione a partire dai tipi.</span><span class="sxs-lookup"><span data-stu-id="19006-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="19006-122">Se è stato identificato uno scenario che l'API pubblica consentiva prima di questa modifica, ma non ora, è necessario inviare un problema a [DotNet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="19006-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="19006-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="19006-123">Category</span></span>

<span data-ttu-id="19006-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19006-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19006-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="19006-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
