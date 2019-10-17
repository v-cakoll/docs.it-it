---
ms.openlocfilehash: 1017801346e65940e4dc075ef72f7a00d7e6bcd9
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394190"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="2f040-101">Spa: SpaServices e NodeServices non eseguono più il fallback al logger della console</span><span class="sxs-lookup"><span data-stu-id="2f040-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="2f040-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> e <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> non visualizzeranno i log della console a meno che non sia stata configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2f040-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2f040-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2f040-103">Version introduced</span></span>

<span data-ttu-id="2f040-104">3.0</span><span class="sxs-lookup"><span data-stu-id="2f040-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2f040-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2f040-105">Old behavior</span></span>

<span data-ttu-id="2f040-106">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` usati per creare automaticamente un logger della console quando la registrazione non è configurata.</span><span class="sxs-lookup"><span data-stu-id="2f040-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span> 

#### <a name="new-behavior"></a><span data-ttu-id="2f040-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2f040-107">New behavior</span></span>

<span data-ttu-id="2f040-108">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` non visualizzeranno i log della console a meno che non sia stata configurata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2f040-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2f040-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2f040-109">Reason for change</span></span>

<span data-ttu-id="2f040-110">È necessario allineare al modo in cui gli altri pacchetti ASP.NET Core implementano la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2f040-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2f040-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2f040-111">Recommended action</span></span>

<span data-ttu-id="2f040-112">Se è necessario il comportamento precedente, per configurare la registrazione della console, aggiungere `services.AddLogging(builder => builder.AddConsole())` al metodo `Setup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="2f040-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="2f040-113">Category</span><span class="sxs-lookup"><span data-stu-id="2f040-113">Category</span></span>

<span data-ttu-id="2f040-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2f040-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2f040-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="2f040-115">Affected APIs</span></span>

<span data-ttu-id="2f040-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2f040-116">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
