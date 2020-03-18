---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74101115"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="2526c-101">Autorizzazione: sovraccarico AddAuthorization spostato in un assembly diversoAuthorization: AddAuthorization overload moved to different assembly</span><span class="sxs-lookup"><span data-stu-id="2526c-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="2526c-102">I `AddAuthorization` metodi principali utilizzati `Microsoft.AspNetCore.Authorization` per risiedere in sono stati rinominati in `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="2526c-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="2526c-103">I `AddAuthorization` metodi precedenti esistono ancora, `Microsoft.AspNetCore.Authorization.Policy` ma si trovano invece nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2526c-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="2526c-104">Le app che usano entrambi i metodi non dovrebbero avere alcun impatto.</span><span class="sxs-lookup"><span data-stu-id="2526c-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="2526c-105">Si `Microsoft.AspNetCore.Authorization.Policy` noti che ora viene fornito nel framework condiviso anziché in un pacchetto autonomo come descritto in [Framework condiviso: assembly rimossi da Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="2526c-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2526c-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2526c-106">Version introduced</span></span>

<span data-ttu-id="2526c-107">3.0</span><span class="sxs-lookup"><span data-stu-id="2526c-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2526c-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2526c-108">Old behavior</span></span>
<span data-ttu-id="2526c-109">`AddAuthorization`metodi esistenti `Microsoft.AspNetCore.Authorization`in .</span><span class="sxs-lookup"><span data-stu-id="2526c-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2526c-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2526c-110">New behavior</span></span>

<span data-ttu-id="2526c-111">`AddAuthorization`metodi esistenti `Microsoft.AspNetCore.Authorization.Policy`in .</span><span class="sxs-lookup"><span data-stu-id="2526c-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="2526c-112">`AddAuthorizationCore`è il nuovo nome per i metodi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2526c-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2526c-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2526c-113">Reason for change</span></span>

<span data-ttu-id="2526c-114">`AddAuthorization`è un nome di metodo migliore per l'aggiunta di tutti i servizi comuni necessari per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2526c-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2526c-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2526c-115">Recommended action</span></span>

<span data-ttu-id="2526c-116">Aggiungere un riferimento `Microsoft.AspNetCore.Authorization.Policy` o `AddAuthorizationCore` utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="2526c-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="2526c-117">Category</span><span class="sxs-lookup"><span data-stu-id="2526c-117">Category</span></span>

<span data-ttu-id="2526c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2526c-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2526c-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="2526c-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
