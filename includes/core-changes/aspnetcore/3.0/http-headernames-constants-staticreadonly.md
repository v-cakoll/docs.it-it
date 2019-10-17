---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394325"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="ade03-101">Costanti HTTP: HeaderNames modificate in ReadOnly statico</span><span class="sxs-lookup"><span data-stu-id="ade03-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="ade03-102">A partire da ASP.NET Core 3,0 Preview 5, i campi in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> sono stati modificati da `const` a `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="ade03-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="ade03-103">Per informazioni, vedere [ASPNET/AspNetCore # 9514](https://github.com/aspnet/AspNetCore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="ade03-103">For discussion, see [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ade03-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ade03-104">Version introduced</span></span>

<span data-ttu-id="ade03-105">3.0</span><span class="sxs-lookup"><span data-stu-id="ade03-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ade03-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ade03-106">Old behavior</span></span>

<span data-ttu-id="ade03-107">Questi campi utilizzati per essere `const`.</span><span class="sxs-lookup"><span data-stu-id="ade03-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ade03-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ade03-108">New behavior</span></span>

<span data-ttu-id="ade03-109">Questi campi sono ora `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="ade03-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ade03-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ade03-110">Reason for change</span></span>

<span data-ttu-id="ade03-111">Modifica:</span><span class="sxs-lookup"><span data-stu-id="ade03-111">The change:</span></span>

* <span data-ttu-id="ade03-112">Impedisce che i valori vengano incorporati tra i limiti dell'assembly, consentendo le correzioni dei valori in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ade03-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="ade03-113">Abilita i controlli di uguaglianza di riferimento più veloci.</span><span class="sxs-lookup"><span data-stu-id="ade03-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ade03-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ade03-114">Recommended action</span></span>

<span data-ttu-id="ade03-115">Ricompilare con 3,0.</span><span class="sxs-lookup"><span data-stu-id="ade03-115">Recompile against 3.0.</span></span> <span data-ttu-id="ade03-116">Il codice sorgente che usa questi campi nei modi seguenti non può più eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="ade03-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="ade03-117">Come argomento dell'attributo</span><span class="sxs-lookup"><span data-stu-id="ade03-117">As an attribute argument</span></span>
* <span data-ttu-id="ade03-118">Come `case` in un'istruzione `switch`</span><span class="sxs-lookup"><span data-stu-id="ade03-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="ade03-119">Quando si definisce un altro `const`</span><span class="sxs-lookup"><span data-stu-id="ade03-119">When defining another `const`</span></span>

<span data-ttu-id="ade03-120">Per aggirare la modifica di rilievo, passare a utilizzando le costanti del nome di intestazione o i valori letterali stringa definiti autonomamente.</span><span class="sxs-lookup"><span data-stu-id="ade03-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="ade03-121">Category</span><span class="sxs-lookup"><span data-stu-id="ade03-121">Category</span></span>

<span data-ttu-id="ade03-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ade03-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ade03-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="ade03-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
