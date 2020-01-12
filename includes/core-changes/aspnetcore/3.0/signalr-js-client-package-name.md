---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902061"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="e1322-101">SignalR: nome del pacchetto client JavaScript modificato</span><span class="sxs-lookup"><span data-stu-id="e1322-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="e1322-102">In ASP.NET Core 3,0 Preview 7 il nome del pacchetto client JavaScript SignalR è cambiato da `@aspnet/signalr` a `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="e1322-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="e1322-103">La modifica del nome riflette il fatto che SignalR è utile in più di ASP.NET Core app, grazie al servizio Azure SignalR.</span><span class="sxs-lookup"><span data-stu-id="e1322-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="e1322-104">Per rispondere a questa modifica, modificare i riferimenti nei file *Package. JSON* , `require` istruzioni e le istruzioni `import` ECMAScript.</span><span class="sxs-lookup"><span data-stu-id="e1322-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="e1322-105">Nessuna API verrà modificata come parte di questa ridenominazione.</span><span class="sxs-lookup"><span data-stu-id="e1322-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="e1322-106">Per informazioni, vedere [DotNet/aspnetcore # 11637](https://github.com/dotnet/aspnetcore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="e1322-106">For discussion, see [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e1322-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e1322-107">Version introduced</span></span>

<span data-ttu-id="e1322-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e1322-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e1322-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e1322-109">Old behavior</span></span>

<span data-ttu-id="e1322-110">Il pacchetto client è denominato `@aspnet/signalr`.</span><span class="sxs-lookup"><span data-stu-id="e1322-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e1322-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e1322-111">New behavior</span></span>

<span data-ttu-id="e1322-112">Il pacchetto client è denominato `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="e1322-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e1322-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e1322-113">Reason for change</span></span>

<span data-ttu-id="e1322-114">La modifica del nome chiarisce che SignalR è utile oltre ASP.NET Core app, grazie al servizio Azure SignalR.</span><span class="sxs-lookup"><span data-stu-id="e1322-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e1322-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e1322-115">Recommended action</span></span>

<span data-ttu-id="e1322-116">Passare al nuovo pacchetto `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="e1322-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="e1322-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="e1322-117">Category</span></span>

<span data-ttu-id="e1322-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1322-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e1322-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="e1322-119">Affected APIs</span></span>

<span data-ttu-id="e1322-120">nessuna</span><span class="sxs-lookup"><span data-stu-id="e1322-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
