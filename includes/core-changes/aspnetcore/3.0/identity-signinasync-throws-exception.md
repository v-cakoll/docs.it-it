---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393952"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="ae2ce-101">Identity: SignInAsync genera un'eccezione per l'identità non autenticata</span><span class="sxs-lookup"><span data-stu-id="ae2ce-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="ae2ce-102">Per impostazione predefinita, `SignInAsync` genera un'eccezione per entità/identità in cui `IsAuthenticated` è `false`.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ae2ce-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ae2ce-103">Version introduced</span></span>

<span data-ttu-id="ae2ce-104">3.0</span><span class="sxs-lookup"><span data-stu-id="ae2ce-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ae2ce-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ae2ce-105">Old behavior</span></span>

<span data-ttu-id="ae2ce-106">`SignInAsync` accetta qualsiasi entità/identità, incluse le identità in cui viene `false``IsAuthenticated`.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ae2ce-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ae2ce-107">New behavior</span></span>

<span data-ttu-id="ae2ce-108">Per impostazione predefinita, `SignInAsync` genera un'eccezione per entità/identità in cui `IsAuthenticated` è `false`.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="ae2ce-109">È disponibile un nuovo flag per l'eliminazione di questo comportamento, ma il comportamento predefinito è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ae2ce-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ae2ce-110">Reason for change</span></span>

<span data-ttu-id="ae2ce-111">Il comportamento precedente è problematico perché, per impostazione predefinita, queste entità sono state rifiutate da `[Authorize]` / `RequireAuthenticatedUser()`.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ae2ce-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ae2ce-112">Recommended action</span></span>

<span data-ttu-id="ae2ce-113">In ASP.NET Core 3,0 Preview 6 è disponibile un flag `RequireAuthenticatedSignIn` per `AuthenticationOptions` `true` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="ae2ce-114">Impostare questo flag su `false` per ripristinare il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="ae2ce-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="ae2ce-115">Category</span><span class="sxs-lookup"><span data-stu-id="ae2ce-115">Category</span></span>

<span data-ttu-id="ae2ce-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ae2ce-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae2ce-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="ae2ce-117">Affected APIs</span></span>

<span data-ttu-id="ae2ce-118">None</span><span class="sxs-lookup"><span data-stu-id="ae2ce-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
