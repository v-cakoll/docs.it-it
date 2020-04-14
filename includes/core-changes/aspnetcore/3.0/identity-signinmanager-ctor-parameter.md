---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275254"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="bd83b-101">Identità: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="bd83b-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="bd83b-102">A partire da ASP.NET Core `IUserConfirmation<TUser>` 3.0, `SignInManager` un nuovo parametro è stato aggiunto al costruttore.</span><span class="sxs-lookup"><span data-stu-id="bd83b-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="bd83b-103">Per ulteriori informazioni, vedere [dotnet/aspnetcore-8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="bd83b-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bd83b-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bd83b-104">Version introduced</span></span>

<span data-ttu-id="bd83b-105">3.0</span><span class="sxs-lookup"><span data-stu-id="bd83b-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bd83b-106">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="bd83b-106">Reason for change</span></span>

<span data-ttu-id="bd83b-107">La motivazione per il cambiamento è stata quella di aggiungere il supporto per nuovi flussi di email / conferma in Identity.</span><span class="sxs-lookup"><span data-stu-id="bd83b-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bd83b-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bd83b-108">Recommended action</span></span>

<span data-ttu-id="bd83b-109">Se si costruisce `SignInManager`manualmente un `IUserConfirmation` oggetto , fornire un'implementazione di o acquisirne una dall'inserimento delle dipendenze da fornire.</span><span class="sxs-lookup"><span data-stu-id="bd83b-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="bd83b-110">Category</span><span class="sxs-lookup"><span data-stu-id="bd83b-110">Category</span></span>

<span data-ttu-id="bd83b-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bd83b-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bd83b-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="bd83b-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
