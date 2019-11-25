---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282512"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="8ab46-101">HTTP: alcuni cookie navigava sullostesso sito predefiniti sono stati modificati in None</span><span class="sxs-lookup"><span data-stu-id="8ab46-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="8ab46-102">`SameSite` è un'opzione per i cookie che consentono di attenuare alcuni attacchi di richiesta intersito falsa (CSRF).</span><span class="sxs-lookup"><span data-stu-id="8ab46-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="8ab46-103">Quando questa opzione è stata introdotta inizialmente, sono state usate impostazioni predefinite incoerenti tra varie API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8ab46-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="8ab46-104">L'incoerenza ha determinato risultati confusi.</span><span class="sxs-lookup"><span data-stu-id="8ab46-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="8ab46-105">A partire da ASP.NET Core 3,0, queste impostazioni predefinite sono allineate meglio.</span><span class="sxs-lookup"><span data-stu-id="8ab46-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="8ab46-106">È necessario acconsentire esplicitamente a questa funzionalità in base ai singoli componenti.</span><span class="sxs-lookup"><span data-stu-id="8ab46-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8ab46-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8ab46-107">Version introduced</span></span>

<span data-ttu-id="8ab46-108">3.0</span><span class="sxs-lookup"><span data-stu-id="8ab46-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8ab46-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="8ab46-109">Old behavior</span></span>

<span data-ttu-id="8ab46-110">API ASP.NET Core simili utilizzano valori <xref:Microsoft.AspNetCore.Http.SameSiteMode> predefiniti diversi.</span><span class="sxs-lookup"><span data-stu-id="8ab46-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="8ab46-111">Un esempio di incoerenza è indicato in `HttpResponse.Cookies.Append(String, String)` e `HttpResponse.Cookies.Append(String, String, CookieOptions)`, che per impostazione predefinita sono rispettivamente `SameSiteMode.None` e `SameSiteMode.Lax`.</span><span class="sxs-lookup"><span data-stu-id="8ab46-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8ab46-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="8ab46-112">New behavior</span></span>

<span data-ttu-id="8ab46-113">Per impostazione predefinita, tutte le API interessate `SameSiteMode.None`.</span><span class="sxs-lookup"><span data-stu-id="8ab46-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8ab46-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="8ab46-114">Reason for change</span></span>

<span data-ttu-id="8ab46-115">Il valore predefinito è stato modificato in modo da rendere `SameSite` una funzionalità di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="8ab46-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8ab46-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8ab46-116">Recommended action</span></span>

<span data-ttu-id="8ab46-117">Ogni componente che emette cookie deve decidere se `SameSite` è appropriato per gli scenari.</span><span class="sxs-lookup"><span data-stu-id="8ab46-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="8ab46-118">Esaminare l'utilizzo delle API interessate e riconfigurare `SameSite` in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8ab46-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="8ab46-119">Category</span><span class="sxs-lookup"><span data-stu-id="8ab46-119">Category</span></span>

<span data-ttu-id="8ab46-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8ab46-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8ab46-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="8ab46-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
