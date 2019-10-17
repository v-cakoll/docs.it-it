---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394134"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a><span data-ttu-id="9f7ca-101">Framework condiviso: rimosso Microsoft. AspNetCore. All</span><span class="sxs-lookup"><span data-stu-id="9f7ca-101">Shared framework: Removed Microsoft.AspNetCore.All</span></span>

<span data-ttu-id="9f7ca-102">A partire da ASP.NET Core 3,0, il metapacchetto `Microsoft.AspNetCore.All` e il Framework condiviso `Microsoft.AspNetCore.All` corrispondente non vengono più prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-102">Starting in ASP.NET Core 3.0, the `Microsoft.AspNetCore.All` metapackage and the matching `Microsoft.AspNetCore.All` shared framework are no longer produced.</span></span> <span data-ttu-id="9f7ca-103">Questo pacchetto è disponibile nel ASP.NET Core 2,2 e continuerà a ricevere gli aggiornamenti del servizio in ASP.NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-103">This package is available in ASP.NET Core 2.2 and will continue to receive servicing updates in ASP.NET Core 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f7ca-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="9f7ca-104">Version introduced</span></span>

<span data-ttu-id="9f7ca-105">3.0</span><span class="sxs-lookup"><span data-stu-id="9f7ca-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9f7ca-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="9f7ca-106">Old behavior</span></span>

<span data-ttu-id="9f7ca-107">Le app possono usare il metapacchetto `Microsoft.AspNetCore.All` per definire come destinazione il Framework condiviso `Microsoft.AspNetCore.All` in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-107">Apps could use the `Microsoft.AspNetCore.All` metapackage to target the `Microsoft.AspNetCore.All` shared framework on .NET Core.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9f7ca-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="9f7ca-108">New behavior</span></span>

<span data-ttu-id="9f7ca-109">.NET Core 3,0 non include un Framework condiviso `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-109">.NET Core 3.0 doesn't include a `Microsoft.AspNetCore.All` shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9f7ca-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="9f7ca-110">Reason for change</span></span>

<span data-ttu-id="9f7ca-111">Il metapacchetto `Microsoft.AspNetCore.All` include un numero elevato di dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-111">The `Microsoft.AspNetCore.All` metapackage included a large number of external dependencies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f7ca-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="9f7ca-112">Recommended action</span></span>

<span data-ttu-id="9f7ca-113">Eseguire la migrazione del progetto per usare il Framework `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-113">Migrate your project to use the `Microsoft.AspNetCore.App` framework.</span></span> <span data-ttu-id="9f7ca-114">I componenti precedentemente disponibili in `Microsoft.AspNetCore.All` sono ancora disponibili in NuGet.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-114">Components that were previously available in `Microsoft.AspNetCore.All` are still available on NuGet.</span></span> <span data-ttu-id="9f7ca-115">Questi componenti vengono ora distribuiti con l'app anziché essere inclusi nel Framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="9f7ca-115">Those components are now deployed with your app instead of being included in the shared framework.</span></span>

#### <a name="category"></a><span data-ttu-id="9f7ca-116">Category</span><span class="sxs-lookup"><span data-stu-id="9f7ca-116">Category</span></span>

<span data-ttu-id="9f7ca-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9f7ca-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f7ca-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="9f7ca-118">Affected APIs</span></span>

<span data-ttu-id="9f7ca-119">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9f7ca-119">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
