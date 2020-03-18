---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902054"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="bbff8-101">HTTP: le costanti HeaderNames modificate in static readonly</span><span class="sxs-lookup"><span data-stu-id="bbff8-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="bbff8-102">A partire da ASP.NET Core 3.0 <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> Preview `const` `static readonly`5, i campi in sono stati modificati da a .</span><span class="sxs-lookup"><span data-stu-id="bbff8-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="bbff8-103">Per una discussione, vedere [dotnet/aspnetcore-9514](https://github.com/dotnet/aspnetcore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="bbff8-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bbff8-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bbff8-104">Version introduced</span></span>

<span data-ttu-id="bbff8-105">3.0</span><span class="sxs-lookup"><span data-stu-id="bbff8-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bbff8-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="bbff8-106">Old behavior</span></span>

<span data-ttu-id="bbff8-107">Questi campi erano `const`.</span><span class="sxs-lookup"><span data-stu-id="bbff8-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bbff8-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="bbff8-108">New behavior</span></span>

<span data-ttu-id="bbff8-109">Questi campi `static readonly`sono ora .</span><span class="sxs-lookup"><span data-stu-id="bbff8-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bbff8-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="bbff8-110">Reason for change</span></span>

<span data-ttu-id="bbff8-111">La modifica:</span><span class="sxs-lookup"><span data-stu-id="bbff8-111">The change:</span></span>

* <span data-ttu-id="bbff8-112">Impedisce che i valori vengano incorporati attraverso i limiti dell'assieme, consentendo correzioni di valori in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bbff8-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="bbff8-113">Consente controlli più rapidi di uguaglianza dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="bbff8-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bbff8-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bbff8-114">Recommended action</span></span>

<span data-ttu-id="bbff8-115">Ricompilare la versione 3.0.</span><span class="sxs-lookup"><span data-stu-id="bbff8-115">Recompile against 3.0.</span></span> <span data-ttu-id="bbff8-116">Il codice sorgente che usa questi campi nei seguenti modi non può più farlo:</span><span class="sxs-lookup"><span data-stu-id="bbff8-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="bbff8-117">Come argomento di attributo</span><span class="sxs-lookup"><span data-stu-id="bbff8-117">As an attribute argument</span></span>
* <span data-ttu-id="bbff8-118">Come `case` un `switch` in una dichiarazione</span><span class="sxs-lookup"><span data-stu-id="bbff8-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="bbff8-119">Quando si definiscono un altro`const`</span><span class="sxs-lookup"><span data-stu-id="bbff8-119">When defining another `const`</span></span>

<span data-ttu-id="bbff8-120">Per aggirare la modifica di rilievo, passare all'utilizzo di costanti del nome di intestazione autodefinite o valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="bbff8-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="bbff8-121">Category</span><span class="sxs-lookup"><span data-stu-id="bbff8-121">Category</span></span>

<span data-ttu-id="bbff8-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bbff8-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bbff8-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="bbff8-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
