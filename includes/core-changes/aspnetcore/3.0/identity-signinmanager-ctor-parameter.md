---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394366"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="e407a-101">Identity: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="e407a-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="e407a-102">A partire da ASP.NET Core 3,0, al costruttore `SignInManager` è stato aggiunto un nuovo parametro `IUserConfirmation<TUser>`.</span><span class="sxs-lookup"><span data-stu-id="e407a-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="e407a-103">Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 8356](https://github.com/aspnet/AspNetCore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="e407a-103">For more information, see [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e407a-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e407a-104">Version introduced</span></span>

<span data-ttu-id="e407a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="e407a-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e407a-106">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e407a-106">Reason for change</span></span>

<span data-ttu-id="e407a-107">La motivazione della modifica consisteva nell'aggiungere il supporto per nuovi flussi di messaggi di posta elettronica/conferma in identità.</span><span class="sxs-lookup"><span data-stu-id="e407a-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e407a-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e407a-108">Recommended action</span></span>

<span data-ttu-id="e407a-109">Se si costruisce manualmente un `SignInManager`, fornire un'implementazione di `IUserConfirmation` o estrarne una dall'inserimento delle dipendenze da fornire.</span><span class="sxs-lookup"><span data-stu-id="e407a-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="e407a-110">Category</span><span class="sxs-lookup"><span data-stu-id="e407a-110">Category</span></span>

<span data-ttu-id="e407a-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e407a-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e407a-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="e407a-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
