---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325217"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="72fe5-101">IIS: vengono mantenute le stringhe di query del middleware UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="72fe5-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="72fe5-102">Un difetto del middleware UrlRewrite IIS ha impedito la conservazione della stringa di query nelle regole di riscrittura.</span><span class="sxs-lookup"><span data-stu-id="72fe5-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="72fe5-103">Questo difetto è stato corretto per garantire la coerenza con il comportamento del modulo UrlRewrite di IIS.</span><span class="sxs-lookup"><span data-stu-id="72fe5-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="72fe5-104">Per informazioni, vedere Issue [DotNet/aspnetcore # 22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="72fe5-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="72fe5-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="72fe5-105">Version introduced</span></span>

<span data-ttu-id="72fe5-106">ASP.NET Core 5,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="72fe5-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="72fe5-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="72fe5-107">Old behavior</span></span>

<span data-ttu-id="72fe5-108">Si consideri la regola di riscrittura seguente:</span><span class="sxs-lookup"><span data-stu-id="72fe5-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="72fe5-109">La regola precedente non aggiunge la stringa di query.</span><span class="sxs-lookup"><span data-stu-id="72fe5-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="72fe5-110">URI come `/about?id=1` reindirizza a `/contact` anziché `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="72fe5-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="72fe5-111">`appendQueryString`Per impostazione predefinita, viene impostato anche l'attributo `true` .</span><span class="sxs-lookup"><span data-stu-id="72fe5-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="72fe5-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="72fe5-112">New behavior</span></span>

<span data-ttu-id="72fe5-113">La stringa di query viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="72fe5-113">The query string is preserved.</span></span> <span data-ttu-id="72fe5-114">L'URI dell'esempio in un [comportamento precedente](#old-behavior) è `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="72fe5-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="72fe5-115">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="72fe5-115">Reason for change</span></span>

<span data-ttu-id="72fe5-116">Il comportamento precedente non corrisponde al comportamento del modulo UrlRewrite di IIS.</span><span class="sxs-lookup"><span data-stu-id="72fe5-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="72fe5-117">Per supportare il porting tra il middleware e il modulo, l'obiettivo è mantenere comportamenti coerenti.</span><span class="sxs-lookup"><span data-stu-id="72fe5-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="72fe5-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="72fe5-118">Recommended action</span></span>

<span data-ttu-id="72fe5-119">Se è preferibile il comportamento della rimozione della stringa di query, impostare l' `action` elemento su `appendQueryString="false"` .</span><span class="sxs-lookup"><span data-stu-id="72fe5-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="72fe5-120">Category</span><span class="sxs-lookup"><span data-stu-id="72fe5-120">Category</span></span>

<span data-ttu-id="72fe5-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72fe5-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="72fe5-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="72fe5-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
