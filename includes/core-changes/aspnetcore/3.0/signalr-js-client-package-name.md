---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394069"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="6412c-101">SignalR: nome del pacchetto client JavaScript modificato</span><span class="sxs-lookup"><span data-stu-id="6412c-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="6412c-102">In ASP.NET Core 3,0 Preview 7, il nome del pacchetto client JavaScript SignalR è cambiato da `@aspnet/signalr` a `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="6412c-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="6412c-103">La modifica del nome riflette il fatto che SignalR è utile in più di ASP.NET Core app, grazie al servizio Azure SignalR.</span><span class="sxs-lookup"><span data-stu-id="6412c-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="6412c-104">Per rispondere a questa modifica, modificare i riferimenti nei file *Package. JSON* , nelle istruzioni `require` e nelle istruzioni ECMAScript `import`.</span><span class="sxs-lookup"><span data-stu-id="6412c-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="6412c-105">Nessuna API verrà modificata come parte di questa ridenominazione.</span><span class="sxs-lookup"><span data-stu-id="6412c-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="6412c-106">Per informazioni, vedere [ASPNET/AspNetCore # 11637](https://github.com/aspnet/AspNetCore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="6412c-106">For discussion, see [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6412c-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6412c-107">Version introduced</span></span>

<span data-ttu-id="6412c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="6412c-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6412c-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="6412c-109">Old behavior</span></span>

<span data-ttu-id="6412c-110">Il pacchetto client è denominato `@aspnet/signalr`.</span><span class="sxs-lookup"><span data-stu-id="6412c-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6412c-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="6412c-111">New behavior</span></span>

<span data-ttu-id="6412c-112">Il pacchetto client è denominato `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="6412c-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6412c-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6412c-113">Reason for change</span></span>

<span data-ttu-id="6412c-114">La modifica del nome chiarisce che SignalR è utile oltre ASP.NET Core app, grazie al servizio Azure SignalR.</span><span class="sxs-lookup"><span data-stu-id="6412c-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6412c-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6412c-115">Recommended action</span></span>

<span data-ttu-id="6412c-116">Passare al nuovo pacchetto `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="6412c-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="6412c-117">Category</span><span class="sxs-lookup"><span data-stu-id="6412c-117">Category</span></span>

<span data-ttu-id="6412c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6412c-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6412c-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="6412c-119">Affected APIs</span></span>

<span data-ttu-id="6412c-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6412c-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
