---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394268"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="6d754-101">Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso</span><span class="sxs-lookup"><span data-stu-id="6d754-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="6d754-102">I metodi `AddAuthorization` principali utilizzati per risiedere in `Microsoft.AspNetCore.Authorization` sono stati rinominati `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="6d754-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="6d754-103">I metodi `AddAuthorization` precedenti esistono ancora, ma sono invece nel pacchetto `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="6d754-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` package instead.</span></span> <span data-ttu-id="6d754-104">Le app che usano entrambi i metodi non dovrebbero avere alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="6d754-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="6d754-105">Le app che non usano il pacchetto di criteri devono passare a con `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="6d754-105">Apps that weren't using the policy package must switch to using `AddAuthorizationCore`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6d754-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6d754-106">Version introduced</span></span>

<span data-ttu-id="6d754-107">3.0</span><span class="sxs-lookup"><span data-stu-id="6d754-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6d754-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="6d754-108">Old behavior</span></span>

<span data-ttu-id="6d754-109">i metodi `AddAuthorization` erano presenti in `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="6d754-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6d754-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="6d754-110">New behavior</span></span>

<span data-ttu-id="6d754-111">nel `Microsoft.AspNetCore.Authorization.Policy` sono presenti metodi `AddAuthorization`.</span><span class="sxs-lookup"><span data-stu-id="6d754-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="6d754-112">`AddAuthorizationCore` è il nuovo nome per i metodi obsoleti.</span><span class="sxs-lookup"><span data-stu-id="6d754-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6d754-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6d754-113">Reason for change</span></span>

<span data-ttu-id="6d754-114">`AddAuthorization` è un nome di metodo migliore per aggiungere tutti i servizi comuni necessari per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="6d754-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6d754-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6d754-115">Recommended action</span></span>

<span data-ttu-id="6d754-116">Aggiungere un riferimento a `Microsoft.AspNetCore.Authorization.Policy` o usare invece `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="6d754-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="6d754-117">Category</span><span class="sxs-lookup"><span data-stu-id="6d754-117">Category</span></span>

<span data-ttu-id="6d754-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6d754-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6d754-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="6d754-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
