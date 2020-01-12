---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901870"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="f606c-101">HTTP: DefaultHttpContext estensibilità rimosso</span><span class="sxs-lookup"><span data-stu-id="f606c-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="f606c-102">Come parte del miglioramento delle prestazioni ASP.NET Core 3,0, l'estendibilità di `DefaultHttpContext` è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="f606c-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="f606c-103">La classe è ora `sealed`.</span><span class="sxs-lookup"><span data-stu-id="f606c-103">The class is now `sealed`.</span></span> <span data-ttu-id="f606c-104">Per ulteriori informazioni, vedere [DotNet/aspnetcore # 6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="f606c-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="f606c-105">Se gli unit test usano `Mock<DefaultHttpContext>`, usare invece `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="f606c-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span>

<span data-ttu-id="f606c-106">Per informazioni, vedere [DotNet/aspnetcore # 6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="f606c-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f606c-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f606c-107">Version introduced</span></span>

<span data-ttu-id="f606c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="f606c-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f606c-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="f606c-109">Old behavior</span></span>

<span data-ttu-id="f606c-110">Le classi possono derivare da `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="f606c-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f606c-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="f606c-111">New behavior</span></span>

<span data-ttu-id="f606c-112">Le classi non possono derivare da `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="f606c-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f606c-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="f606c-113">Reason for change</span></span>

<span data-ttu-id="f606c-114">Inizialmente è stata fornita l'estendibilità per consentire il pool di `HttpContext`, ma è stata introdotta una complessità superflua e sono state ostacolate altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f606c-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f606c-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f606c-115">Recommended action</span></span>

<span data-ttu-id="f606c-116">Se si usa `Mock<DefaultHttpContext>` negli unit test, iniziare a usare `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="f606c-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="f606c-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="f606c-117">Category</span></span>

<span data-ttu-id="f606c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f606c-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f606c-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="f606c-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
