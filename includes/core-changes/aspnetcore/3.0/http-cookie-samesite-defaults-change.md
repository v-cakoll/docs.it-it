---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282512"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="ea0ad-101">HTTP: alcune impostazioni predefinite di SameSite dei cookie sono state modificate in Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea0ad-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="ea0ad-102">`SameSite`è un'opzione per i cookie che può aiutare a mitigare alcuni attacchi CSRF (Cross-Site Request Forgery).</span><span class="sxs-lookup"><span data-stu-id="ea0ad-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="ea0ad-103">Quando questa opzione è stata inizialmente introdotta, i valori predefiniti incoerenti sono stati usati in varie API di ASP.NET Core.When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="ea0ad-104">L'incoerenza ha portato a risultati confusi.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="ea0ad-105">A partire da ASP.NET Core 3.0, queste impostazioni predefinite sono meglio allineate.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="ea0ad-106">È necessario acconsentire esplicitamente a questa funzionalità in base al componente.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ea0ad-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ea0ad-107">Version introduced</span></span>

<span data-ttu-id="ea0ad-108">3.0</span><span class="sxs-lookup"><span data-stu-id="ea0ad-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ea0ad-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ea0ad-109">Old behavior</span></span>

<span data-ttu-id="ea0ad-110">Simile ASP.NET API core usavano valori predefiniti <xref:Microsoft.AspNetCore.Http.SameSiteMode> diversi.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="ea0ad-111">Un esempio di incoerenza `HttpResponse.Cookies.Append(String, String)` è `HttpResponse.Cookies.Append(String, String, CookieOptions)`visto in `SameSiteMode.None` e `SameSiteMode.Lax`, che per impostazione predefinita è e , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ea0ad-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ea0ad-112">New behavior</span></span>

<span data-ttu-id="ea0ad-113">Per impostazione predefinita, `SameSiteMode.None`tutte le API interessate vengono .</span><span class="sxs-lookup"><span data-stu-id="ea0ad-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ea0ad-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ea0ad-114">Reason for change</span></span>

<span data-ttu-id="ea0ad-115">Il valore predefinito è `SameSite` stato modificato per creare una funzionalità di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ea0ad-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ea0ad-116">Recommended action</span></span>

<span data-ttu-id="ea0ad-117">Ogni componente che emette cookie `SameSite` deve decidere se è appropriato per i propri scenari.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="ea0ad-118">Esaminare l'utilizzo delle API interessate e riconfigurare `SameSite` in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea0ad-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="ea0ad-119">Category</span><span class="sxs-lookup"><span data-stu-id="ea0ad-119">Category</span></span>

<span data-ttu-id="ea0ad-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ea0ad-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ea0ad-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="ea0ad-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
