---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74101115"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="6cdd9-101">Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso</span><span class="sxs-lookup"><span data-stu-id="6cdd9-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="6cdd9-102">I metodi `AddAuthorization` principali utilizzati per risiedere in `Microsoft.AspNetCore.Authorization` sono stati rinominati `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="6cdd9-103">I vecchi metodi di `AddAuthorization` esistono ancora, ma si trovano invece nell'assembly `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="6cdd9-104">Le app che usano entrambi i metodi non dovrebbero avere alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="6cdd9-105">Si noti che `Microsoft.AspNetCore.Authorization.Policy` ora viene fornito nel Framework condiviso anziché in un pacchetto autonomo, come illustrato in [Framework condiviso: assembly rimossi da Microsoft. AspNetCore. app](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="6cdd9-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6cdd9-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6cdd9-106">Version introduced</span></span>

<span data-ttu-id="6cdd9-107">3.0</span><span class="sxs-lookup"><span data-stu-id="6cdd9-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6cdd9-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="6cdd9-108">Old behavior</span></span>
<span data-ttu-id="6cdd9-109">i metodi `AddAuthorization` erano presenti in `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6cdd9-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="6cdd9-110">New behavior</span></span>

<span data-ttu-id="6cdd9-111">nel `Microsoft.AspNetCore.Authorization.Policy` sono presenti metodi `AddAuthorization`.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="6cdd9-112">`AddAuthorizationCore` è il nuovo nome per i metodi obsoleti.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6cdd9-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6cdd9-113">Reason for change</span></span>

<span data-ttu-id="6cdd9-114">`AddAuthorization` è un nome di metodo migliore per aggiungere tutti i servizi comuni necessari per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6cdd9-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6cdd9-115">Recommended action</span></span>

<span data-ttu-id="6cdd9-116">Aggiungere un riferimento a `Microsoft.AspNetCore.Authorization.Policy` o usare invece `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="6cdd9-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="6cdd9-117">Category</span><span class="sxs-lookup"><span data-stu-id="6cdd9-117">Category</span></span>

<span data-ttu-id="6cdd9-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6cdd9-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6cdd9-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="6cdd9-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
