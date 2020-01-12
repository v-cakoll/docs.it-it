---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901936"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="e9add-101">Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo</span><span class="sxs-lookup"><span data-stu-id="e9add-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="e9add-102">In ASP.NET Core 3,0 è stato aggiunto un nuovo metodo di `GetFallbackPolicyAsync` al `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="e9add-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="e9add-103">Questo criterio di fallback viene utilizzato dal middleware di autorizzazione quando non viene specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="e9add-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="e9add-104">Per ulteriori informazioni, vedere [DotNet/aspnetcore # 9759](https://github.com/dotnet/aspnetcore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="e9add-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e9add-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e9add-105">Version introduced</span></span>

<span data-ttu-id="e9add-106">3.0</span><span class="sxs-lookup"><span data-stu-id="e9add-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e9add-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e9add-107">Old behavior</span></span>

<span data-ttu-id="e9add-108">Le implementazioni di `IAuthorizationPolicyProvider` non richiedono un metodo di `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="e9add-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e9add-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e9add-109">New behavior</span></span>

<span data-ttu-id="e9add-110">Le implementazioni di `IAuthorizationPolicyProvider` richiedono un metodo di `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="e9add-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e9add-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e9add-111">Reason for change</span></span>

<span data-ttu-id="e9add-112">Un nuovo metodo era necessario per il nuovo `AuthorizationMiddleware` da utilizzare quando non viene specificato alcun criterio.</span><span class="sxs-lookup"><span data-stu-id="e9add-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e9add-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e9add-113">Recommended action</span></span>

<span data-ttu-id="e9add-114">Aggiungere il metodo `GetFallbackPolicyAsync` alle implementazioni di `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="e9add-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="e9add-115">Categoria</span><span class="sxs-lookup"><span data-stu-id="e9add-115">Category</span></span>

<span data-ttu-id="e9add-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e9add-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e9add-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="e9add-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
