---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901663"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="82c67-101">Identità: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="82c67-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="82c67-102">A partire da ASP.NET Core `IUserConfirmation<TUser>` 3.0, `SignInManager` un nuovo parametro è stato aggiunto al costruttore.</span><span class="sxs-lookup"><span data-stu-id="82c67-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="82c67-103">Per ulteriori informazioni, vedere [dotnet/aspnetcore-8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="82c67-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="82c67-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="82c67-104">Version introduced</span></span>

<span data-ttu-id="82c67-105">3.0</span><span class="sxs-lookup"><span data-stu-id="82c67-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="82c67-106">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="82c67-106">Reason for change</span></span>

<span data-ttu-id="82c67-107">La motivazione per il cambiamento è stata quella di aggiungere il supporto per nuovi flussi di email / conferma in Identity.</span><span class="sxs-lookup"><span data-stu-id="82c67-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="82c67-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="82c67-108">Recommended action</span></span>

<span data-ttu-id="82c67-109">Se si costruisce `SignInManager`manualmente un `IUserConfirmation` oggetto , fornire un'implementazione di o acquisirne una dall'inserimento delle dipendenze da fornire.</span><span class="sxs-lookup"><span data-stu-id="82c67-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="82c67-110">Category</span><span class="sxs-lookup"><span data-stu-id="82c67-110">Category</span></span>

<span data-ttu-id="82c67-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="82c67-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="82c67-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="82c67-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
