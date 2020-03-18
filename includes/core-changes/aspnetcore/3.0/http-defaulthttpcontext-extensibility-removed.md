---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78290730"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="40911-101">HTTP: estensibilità DefaultHttpContext rimossa</span><span class="sxs-lookup"><span data-stu-id="40911-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="40911-102">Come parte dei miglioramenti delle prestazioni di ASP.NET Core `DefaultHttpContext` 3.0, l'estendibilità di è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="40911-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="40911-103">La classe `sealed`è ora .</span><span class="sxs-lookup"><span data-stu-id="40911-103">The class is now `sealed`.</span></span> <span data-ttu-id="40911-104">Per ulteriori informazioni, vedere [dotnet/aspnetcore-6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="40911-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="40911-105">Se gli unit `Mock<DefaultHttpContext>`test `Mock<HttpContext>` `new DefaultHttpContext()` utilizzano , utilizzare o invece.</span><span class="sxs-lookup"><span data-stu-id="40911-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` or `new DefaultHttpContext()` instead.</span></span>

<span data-ttu-id="40911-106">Per una discussione, vedere [dotnet/aspnetcore-6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="40911-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="40911-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="40911-107">Version introduced</span></span>

<span data-ttu-id="40911-108">3.0</span><span class="sxs-lookup"><span data-stu-id="40911-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="40911-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="40911-109">Old behavior</span></span>

<span data-ttu-id="40911-110">Le classi `DefaultHttpContext`possono derivare da .</span><span class="sxs-lookup"><span data-stu-id="40911-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="40911-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="40911-111">New behavior</span></span>

<span data-ttu-id="40911-112">Le classi non `DefaultHttpContext`possono derivare da .</span><span class="sxs-lookup"><span data-stu-id="40911-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="40911-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="40911-113">Reason for change</span></span>

<span data-ttu-id="40911-114">L'estendibilità è stata fornita inizialmente per consentire il `HttpContext`pooling di , ma ha introdotto una complessità non necessaria e ostacolato altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="40911-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="40911-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="40911-115">Recommended action</span></span>

<span data-ttu-id="40911-116">Se si utilizza `Mock<DefaultHttpContext>` negli unit test, `Mock<HttpContext>` iniziare a utilizzare.</span><span class="sxs-lookup"><span data-stu-id="40911-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="40911-117">Category</span><span class="sxs-lookup"><span data-stu-id="40911-117">Category</span></span>

<span data-ttu-id="40911-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="40911-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="40911-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="40911-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
