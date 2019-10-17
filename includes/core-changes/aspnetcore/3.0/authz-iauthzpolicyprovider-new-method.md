---
ms.openlocfilehash: a16d443a37fb0bb5f6bdc4a39e7dcb4f91c54ead
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394099"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="bb707-101">Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo</span><span class="sxs-lookup"><span data-stu-id="bb707-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="bb707-102">In ASP.NET Core 3,0 è stato aggiunto un nuovo metodo `GetFallbackPolicyAsync` a `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="bb707-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="bb707-103">Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="bb707-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="bb707-104">Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 9759](https://github.com/aspnet/AspNetCore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="bb707-104">For more information, see [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="bb707-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bb707-105">Version introduced</span></span>

<span data-ttu-id="bb707-106">3.0</span><span class="sxs-lookup"><span data-stu-id="bb707-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bb707-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="bb707-107">Old behavior</span></span>

<span data-ttu-id="bb707-108">Le implementazioni di `IAuthorizationPolicyProvider` non hanno richiesto un metodo `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="bb707-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bb707-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="bb707-109">New behavior</span></span>

<span data-ttu-id="bb707-110">Per le implementazioni di `IAuthorizationPolicyProvider` è necessario un metodo `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="bb707-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bb707-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="bb707-111">Reason for change</span></span>

<span data-ttu-id="bb707-112">È necessario un nuovo metodo per la nuova `AuthorizationMiddleware` da usare quando non è specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="bb707-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bb707-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bb707-113">Recommended action</span></span>

<span data-ttu-id="bb707-114">Aggiungere il metodo `GetFallbackPolicyAsync` alle implementazioni di `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="bb707-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="bb707-115">Category</span><span class="sxs-lookup"><span data-stu-id="bb707-115">Category</span></span>

<span data-ttu-id="bb707-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bb707-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bb707-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="bb707-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
