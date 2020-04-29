---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507086"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="19cdd-101">Tipi HTTP: gheppio e IIS BadHttpRequestException contrassegnati come obsoleti e sostituiti</span><span class="sxs-lookup"><span data-stu-id="19cdd-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="19cdd-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sono stati contrassegnati come obsoleti e modificati per la `Microsoft.AspNetCore.Http.BadHttpRequestException`derivazione da.</span><span class="sxs-lookup"><span data-stu-id="19cdd-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="19cdd-103">Il gheppio e i server IIS generano ancora i vecchi tipi di eccezioni per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="19cdd-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="19cdd-104">I tipi obsoleti verranno rimossi in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="19cdd-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="19cdd-105">Per informazioni, vedere [DotNet/aspnetcore # 20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="19cdd-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="19cdd-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="19cdd-106">Version introduced</span></span>

<span data-ttu-id="19cdd-107">5,0 Anteprima 4</span><span class="sxs-lookup"><span data-stu-id="19cdd-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="19cdd-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="19cdd-108">Old behavior</span></span>

<span data-ttu-id="19cdd-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivato da <xref:System.IO.IOException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19cdd-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="19cdd-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="19cdd-110">New behavior</span></span>

<span data-ttu-id="19cdd-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sono obsoleti.</span><span class="sxs-lookup"><span data-stu-id="19cdd-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="19cdd-112">Anche i tipi derivano `Microsoft.AspNetCore.Http.BadHttpRequestException`da, che deriva da `System.IO.IOException`.</span><span class="sxs-lookup"><span data-stu-id="19cdd-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="19cdd-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="19cdd-113">Reason for change</span></span>

<span data-ttu-id="19cdd-114">La modifica è stata apportata a:</span><span class="sxs-lookup"><span data-stu-id="19cdd-114">The change was made to:</span></span>

* <span data-ttu-id="19cdd-115">Consolidare i tipi duplicati.</span><span class="sxs-lookup"><span data-stu-id="19cdd-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="19cdd-116">Comportamento unificato tra implementazioni server.</span><span class="sxs-lookup"><span data-stu-id="19cdd-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="19cdd-117">Un'app può ora intercettare l'eccezione `Microsoft.AspNetCore.Http.BadHttpRequestException` di base quando si usa gheppio o IIS.</span><span class="sxs-lookup"><span data-stu-id="19cdd-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="19cdd-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="19cdd-118">Recommended action</span></span>

<span data-ttu-id="19cdd-119">Sostituire gli utilizzi di `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` con `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="19cdd-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="19cdd-120">Category</span><span class="sxs-lookup"><span data-stu-id="19cdd-120">Category</span></span>

<span data-ttu-id="19cdd-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19cdd-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19cdd-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="19cdd-122">Affected APIs</span></span>

- [<span data-ttu-id="19cdd-123">Microsoft. AspNetCore. Server. IIS. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="19cdd-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="19cdd-124">Microsoft. AspNetCore. Server. gheppio. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="19cdd-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
