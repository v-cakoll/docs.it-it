---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522689"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="1de5b-101">Spa: SpaServices e NodeServices non eseguono più il fallback al logger della console</span><span class="sxs-lookup"><span data-stu-id="1de5b-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="1de5b-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> e <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> non visualizzeranno i log della console a meno che non sia stata configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1de5b-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1de5b-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="1de5b-103">Version introduced</span></span>

<span data-ttu-id="1de5b-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1de5b-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1de5b-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="1de5b-105">Old behavior</span></span>

<span data-ttu-id="1de5b-106">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` usati per creare automaticamente un logger della console quando la registrazione non è configurata.</span><span class="sxs-lookup"><span data-stu-id="1de5b-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1de5b-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="1de5b-107">New behavior</span></span>

<span data-ttu-id="1de5b-108">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` non visualizzeranno i log della console a meno che non sia stata configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1de5b-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1de5b-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="1de5b-109">Reason for change</span></span>

<span data-ttu-id="1de5b-110">È necessario allineare al modo in cui gli altri pacchetti ASP.NET Core implementano la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1de5b-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1de5b-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="1de5b-111">Recommended action</span></span>

<span data-ttu-id="1de5b-112">Se è necessario il comportamento precedente, per configurare la registrazione della console, aggiungere `services.AddLogging(builder => builder.AddConsole())` al metodo `Setup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="1de5b-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="1de5b-113">Category</span><span class="sxs-lookup"><span data-stu-id="1de5b-113">Category</span></span>

<span data-ttu-id="1de5b-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1de5b-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1de5b-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="1de5b-115">Affected APIs</span></span>

<span data-ttu-id="1de5b-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1de5b-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
