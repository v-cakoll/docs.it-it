---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901936"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="575d0-101">Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodoAuthorization: IAuthorizationPolicyProvider implementations require new method</span><span class="sxs-lookup"><span data-stu-id="575d0-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="575d0-102">In ASP.NET Core 3.0 `GetFallbackPolicyAsync` è stato `IAuthorizationPolicyProvider`aggiunto un nuovo metodo a .</span><span class="sxs-lookup"><span data-stu-id="575d0-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="575d0-103">Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="575d0-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="575d0-104">Per ulteriori informazioni, vedere [dotnet/aspnetcore-9759](https://github.com/dotnet/aspnetcore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="575d0-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="575d0-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="575d0-105">Version introduced</span></span>

<span data-ttu-id="575d0-106">3.0</span><span class="sxs-lookup"><span data-stu-id="575d0-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="575d0-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="575d0-107">Old behavior</span></span>

<span data-ttu-id="575d0-108">Le implementazioni di `IAuthorizationPolicyProvider` non `GetFallbackPolicyAsync` richiedevano un metodo.</span><span class="sxs-lookup"><span data-stu-id="575d0-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="575d0-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="575d0-109">New behavior</span></span>

<span data-ttu-id="575d0-110">Le implementazioni `IAuthorizationPolicyProvider` `GetFallbackPolicyAsync` di richiedono un metodo.</span><span class="sxs-lookup"><span data-stu-id="575d0-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="575d0-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="575d0-111">Reason for change</span></span>

<span data-ttu-id="575d0-112">Era necessario un nuovo `AuthorizationMiddleware` metodo per il nuovo da utilizzare quando non viene specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="575d0-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="575d0-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="575d0-113">Recommended action</span></span>

<span data-ttu-id="575d0-114">Aggiungere `GetFallbackPolicyAsync` il metodo alle `IAuthorizationPolicyProvider`implementazioni di .</span><span class="sxs-lookup"><span data-stu-id="575d0-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="575d0-115">Category</span><span class="sxs-lookup"><span data-stu-id="575d0-115">Category</span></span>

<span data-ttu-id="575d0-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="575d0-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="575d0-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="575d0-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
