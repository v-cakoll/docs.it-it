---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394396"
---
### <a name="logging-debuglogger-class-made-internal"></a><span data-ttu-id="82ea2-101">Registrazione: classe DebugLogger creata internamente</span><span class="sxs-lookup"><span data-stu-id="82ea2-101">Logging: DebugLogger class made internal</span></span>

<span data-ttu-id="82ea2-102">Prima di ASP.NET Core 3,0, il modificatore di accesso `DebugLogger` era `public`.</span><span class="sxs-lookup"><span data-stu-id="82ea2-102">Prior to ASP.NET Core 3.0, `DebugLogger`'s access modifier was `public`.</span></span> <span data-ttu-id="82ea2-103">In ASP.NET Core 3,0, il modificatore di accesso è stato modificato in `internal`.</span><span class="sxs-lookup"><span data-stu-id="82ea2-103">In ASP.NET Core 3.0, the access modifier changed to `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="82ea2-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="82ea2-104">Version introduced</span></span>

<span data-ttu-id="82ea2-105">3.0</span><span class="sxs-lookup"><span data-stu-id="82ea2-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="82ea2-106">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="82ea2-106">Reason for change</span></span>

<span data-ttu-id="82ea2-107">La modifica viene apportata a:</span><span class="sxs-lookup"><span data-stu-id="82ea2-107">The change is being made to:</span></span>

* <span data-ttu-id="82ea2-108">Applicare la coerenza con altre implementazioni del logger, ad esempio `ConsoleLogger`.</span><span class="sxs-lookup"><span data-stu-id="82ea2-108">Enforce consistency with other logger implementations such as `ConsoleLogger`.</span></span>
* <span data-ttu-id="82ea2-109">Ridurre la superficie dell'API.</span><span class="sxs-lookup"><span data-stu-id="82ea2-109">Reduce the API surface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="82ea2-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="82ea2-110">Recommended action</span></span>

<span data-ttu-id="82ea2-111">Usare il metodo di estensione <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` per abilitare la registrazione del debug.</span><span class="sxs-lookup"><span data-stu-id="82ea2-111">Use the <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` extension method to enable debug logging.</span></span> <span data-ttu-id="82ea2-112">anche <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> è ancora `public` nel caso in cui il servizio debba essere registrato manualmente.</span><span class="sxs-lookup"><span data-stu-id="82ea2-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> is also still `public` in the event the service needs to be registered manually.</span></span>

#### <a name="category"></a><span data-ttu-id="82ea2-113">Category</span><span class="sxs-lookup"><span data-stu-id="82ea2-113">Category</span></span>

<span data-ttu-id="82ea2-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="82ea2-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="82ea2-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="82ea2-115">Affected APIs</span></span>

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
