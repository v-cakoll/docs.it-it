---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522689"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="ea4f6-101">SPAA: SpaServices e NodeServices non eseguire più il rollback al logger della console</span><span class="sxs-lookup"><span data-stu-id="ea4f6-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="ea4f6-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType>e <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> non visualizzerà i registri della console a meno che non sia configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ea4f6-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ea4f6-103">Version introduced</span></span>

<span data-ttu-id="ea4f6-104">3.0</span><span class="sxs-lookup"><span data-stu-id="ea4f6-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ea4f6-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ea4f6-105">Old behavior</span></span>

<span data-ttu-id="ea4f6-106">`Microsoft.AspNetCore.SpaServices`e `Microsoft.AspNetCore.NodeServices` utilizzato per creare automaticamente un logger di console quando la registrazione non è configurata.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ea4f6-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ea4f6-107">New behavior</span></span>

<span data-ttu-id="ea4f6-108">`Microsoft.AspNetCore.SpaServices`e `Microsoft.AspNetCore.NodeServices` non visualizzerà i registri della console a meno che non sia configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ea4f6-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ea4f6-109">Reason for change</span></span>

<span data-ttu-id="ea4f6-110">È necessario allinearsi con il modo in cui altri pacchetti ASP.NET Core implementano la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ea4f6-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ea4f6-111">Recommended action</span></span>

<span data-ttu-id="ea4f6-112">Se il comportamento precedente è necessario, `services.AddLogging(builder => builder.AddConsole())` per `Setup.ConfigureServices` configurare la registrazione della console, aggiungere al metodo.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="ea4f6-113">Category</span><span class="sxs-lookup"><span data-stu-id="ea4f6-113">Category</span></span>

<span data-ttu-id="ea4f6-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ea4f6-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ea4f6-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="ea4f6-115">Affected APIs</span></span>

<span data-ttu-id="ea4f6-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="ea4f6-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
