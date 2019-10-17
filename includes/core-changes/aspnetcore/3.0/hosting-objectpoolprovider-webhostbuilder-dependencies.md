---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394314"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="e0411-101">Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="e0411-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="e0411-102">Come parte del processo di ASP.NET Core, il `ObjectPoolProvider` è stato rimosso dal set principale di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="e0411-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="e0411-103">I componenti specifici che si basano su `ObjectPoolProvider` ora aggiungono se stessi.</span><span class="sxs-lookup"><span data-stu-id="e0411-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="e0411-104">Per informazioni, vedere [ASPNET/AspNetCore # 5944](https://github.com/aspnet/AspNetCore/issues/5944).</span><span class="sxs-lookup"><span data-stu-id="e0411-104">For discussion, see [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0411-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e0411-105">Version introduced</span></span>

<span data-ttu-id="e0411-106">3.0</span><span class="sxs-lookup"><span data-stu-id="e0411-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e0411-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e0411-107">Old behavior</span></span>

<span data-ttu-id="e0411-108">`WebHostBuilder` fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="e0411-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e0411-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e0411-109">New behavior</span></span>

<span data-ttu-id="e0411-110">`WebHostBuilder` non fornisce più `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="e0411-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e0411-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e0411-111">Reason for change</span></span>

<span data-ttu-id="e0411-112">Questa modifica è stata apportata per rendere ASP.NET Core più pagamento per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="e0411-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0411-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e0411-113">Recommended action</span></span>

<span data-ttu-id="e0411-114">Se il componente richiede `ObjectPoolProvider`, è necessario aggiungerlo alle dipendenze tramite il `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="e0411-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="e0411-115">Category</span><span class="sxs-lookup"><span data-stu-id="e0411-115">Category</span></span>

<span data-ttu-id="e0411-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0411-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0411-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="e0411-117">Affected APIs</span></span>

<span data-ttu-id="e0411-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="e0411-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
