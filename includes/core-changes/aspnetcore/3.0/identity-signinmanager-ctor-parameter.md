---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901663"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="e3810-101">Identity: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="e3810-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="e3810-102">A partire da ASP.NET Core 3,0, al costruttore `SignInManager` è stato aggiunto un nuovo parametro di `IUserConfirmation<TUser>`.</span><span class="sxs-lookup"><span data-stu-id="e3810-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="e3810-103">Per ulteriori informazioni, vedere [DotNet/aspnetcore # 8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="e3810-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e3810-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e3810-104">Version introduced</span></span>

<span data-ttu-id="e3810-105">3.0</span><span class="sxs-lookup"><span data-stu-id="e3810-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e3810-106">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e3810-106">Reason for change</span></span>

<span data-ttu-id="e3810-107">La motivazione della modifica consisteva nell'aggiungere il supporto per nuovi flussi di messaggi di posta elettronica/conferma in identità.</span><span class="sxs-lookup"><span data-stu-id="e3810-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e3810-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e3810-108">Recommended action</span></span>

<span data-ttu-id="e3810-109">Se si costruisce manualmente un `SignInManager`, fornire un'implementazione di `IUserConfirmation` o estrarne una dall'inserimento delle dipendenze da fornire.</span><span class="sxs-lookup"><span data-stu-id="e3810-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="e3810-110">Categoria</span><span class="sxs-lookup"><span data-stu-id="e3810-110">Category</span></span>

<span data-ttu-id="e3810-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3810-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e3810-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="e3810-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
