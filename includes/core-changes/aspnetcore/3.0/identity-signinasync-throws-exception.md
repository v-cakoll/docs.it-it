---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393952"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="67cae-101">Identità: SignInAsync genera un'eccezione per l'identità non autenticataIdentity: SignInAsync throws exception for unauthenticated identity</span><span class="sxs-lookup"><span data-stu-id="67cae-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="67cae-102">Per impostazione predefinita, `SignInAsync` genera un'eccezione per `IsAuthenticated` `false`le entità /identità in cui è .</span><span class="sxs-lookup"><span data-stu-id="67cae-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="67cae-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="67cae-103">Version introduced</span></span>

<span data-ttu-id="67cae-104">3.0</span><span class="sxs-lookup"><span data-stu-id="67cae-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="67cae-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="67cae-105">Old behavior</span></span>

<span data-ttu-id="67cae-106">`SignInAsync`accetta qualsiasi entità / identità, comprese le `IsAuthenticated` identità in cui è `false`.</span><span class="sxs-lookup"><span data-stu-id="67cae-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="67cae-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="67cae-107">New behavior</span></span>

<span data-ttu-id="67cae-108">Per impostazione predefinita, `SignInAsync` genera un'eccezione per `IsAuthenticated` `false`le entità /identità in cui è .</span><span class="sxs-lookup"><span data-stu-id="67cae-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="67cae-109">È disponibile un nuovo flag per eliminare questo comportamento, ma il comportamento predefinito è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="67cae-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="67cae-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="67cae-110">Reason for change</span></span>

<span data-ttu-id="67cae-111">Il comportamento precedente era problematico perché, per impostazione predefinita, queste entità sono state rifiutate da `[Authorize]`  /  `RequireAuthenticatedUser()`.</span><span class="sxs-lookup"><span data-stu-id="67cae-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="67cae-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="67cae-112">Recommended action</span></span>

<span data-ttu-id="67cae-113">In ASP.NET Core 3.0 Preview 6, c'è un `RequireAuthenticatedSignIn` flag su `AuthenticationOptions` che è `true` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="67cae-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="67cae-114">Impostare questo `false` flag su per ripristinare il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="67cae-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="67cae-115">Category</span><span class="sxs-lookup"><span data-stu-id="67cae-115">Category</span></span>

<span data-ttu-id="67cae-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="67cae-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67cae-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="67cae-117">Affected APIs</span></span>

<span data-ttu-id="67cae-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="67cae-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
