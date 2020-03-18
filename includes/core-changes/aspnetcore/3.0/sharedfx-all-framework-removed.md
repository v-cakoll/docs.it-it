---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394134"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a><span data-ttu-id="62695-101">Framework condiviso: rimosso Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="62695-101">Shared framework: Removed Microsoft.AspNetCore.All</span></span>

<span data-ttu-id="62695-102">A partire da ASP.NET Core `Microsoft.AspNetCore.All` 3.0, `Microsoft.AspNetCore.All` il metapacchetto e il framework condiviso corrispondente non vengono più prodotti.</span><span class="sxs-lookup"><span data-stu-id="62695-102">Starting in ASP.NET Core 3.0, the `Microsoft.AspNetCore.All` metapackage and the matching `Microsoft.AspNetCore.All` shared framework are no longer produced.</span></span> <span data-ttu-id="62695-103">Questo pacchetto è disponibile in ASP.NET Core 2.2 e continuerà a ricevere gli aggiornamenti di manutenzione in ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="62695-103">This package is available in ASP.NET Core 2.2 and will continue to receive servicing updates in ASP.NET Core 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="62695-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="62695-104">Version introduced</span></span>

<span data-ttu-id="62695-105">3.0</span><span class="sxs-lookup"><span data-stu-id="62695-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="62695-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="62695-106">Old behavior</span></span>

<span data-ttu-id="62695-107">Le app `Microsoft.AspNetCore.All` potrebbero usare il `Microsoft.AspNetCore.All` metapacchetto per il framework condiviso in .NET Core.Apps could use the metapackage to target the shared framework on .NET Core.</span><span class="sxs-lookup"><span data-stu-id="62695-107">Apps could use the `Microsoft.AspNetCore.All` metapackage to target the `Microsoft.AspNetCore.All` shared framework on .NET Core.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="62695-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="62695-108">New behavior</span></span>

<span data-ttu-id="62695-109">.NET Core 3.0 non `Microsoft.AspNetCore.All` include un framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="62695-109">.NET Core 3.0 doesn't include a `Microsoft.AspNetCore.All` shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="62695-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="62695-110">Reason for change</span></span>

<span data-ttu-id="62695-111">Il `Microsoft.AspNetCore.All` metapacchetto includeva un numero elevato di dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="62695-111">The `Microsoft.AspNetCore.All` metapackage included a large number of external dependencies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="62695-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="62695-112">Recommended action</span></span>

<span data-ttu-id="62695-113">Eseguire la migrazione `Microsoft.AspNetCore.App` del progetto per utilizzare il framework.</span><span class="sxs-lookup"><span data-stu-id="62695-113">Migrate your project to use the `Microsoft.AspNetCore.App` framework.</span></span> <span data-ttu-id="62695-114">I componenti precedentemente `Microsoft.AspNetCore.All` disponibili in sono ancora disponibili su NuGet.Components that were previously available in are still available on NuGet.</span><span class="sxs-lookup"><span data-stu-id="62695-114">Components that were previously available in `Microsoft.AspNetCore.All` are still available on NuGet.</span></span> <span data-ttu-id="62695-115">Questi componenti vengono ora distribuiti con l'app anziché essere inclusi nel framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="62695-115">Those components are now deployed with your app instead of being included in the shared framework.</span></span>

#### <a name="category"></a><span data-ttu-id="62695-116">Category</span><span class="sxs-lookup"><span data-stu-id="62695-116">Category</span></span>

<span data-ttu-id="62695-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="62695-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62695-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="62695-118">Affected APIs</span></span>

<span data-ttu-id="62695-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="62695-119">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
