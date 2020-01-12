---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901895"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="a0e17-101">Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="a0e17-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="a0e17-102">Come parte del processo di ASP.NET Core, il `ObjectPoolProvider` è stato rimosso dal set principale di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a0e17-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="a0e17-103">Componenti specifici che si basano su `ObjectPoolProvider` ora aggiungono se stessi.</span><span class="sxs-lookup"><span data-stu-id="a0e17-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="a0e17-104">Per informazioni, vedere [DotNet/aspnetcore # 5944](https://github.com/dotnet/aspnetcore/issues/5944).</span><span class="sxs-lookup"><span data-stu-id="a0e17-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a0e17-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a0e17-105">Version introduced</span></span>

<span data-ttu-id="a0e17-106">3.0</span><span class="sxs-lookup"><span data-stu-id="a0e17-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a0e17-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="a0e17-107">Old behavior</span></span>

<span data-ttu-id="a0e17-108">`WebHostBuilder` fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a0e17-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a0e17-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="a0e17-109">New behavior</span></span>

<span data-ttu-id="a0e17-110">`WebHostBuilder` non fornisce più `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a0e17-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a0e17-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="a0e17-111">Reason for change</span></span>

<span data-ttu-id="a0e17-112">Questa modifica è stata apportata per rendere ASP.NET Core più pagamento per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="a0e17-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a0e17-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a0e17-113">Recommended action</span></span>

<span data-ttu-id="a0e17-114">Se il componente richiede `ObjectPoolProvider`, è necessario aggiungerlo alle dipendenze tramite l'`IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="a0e17-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="a0e17-115">Categoria</span><span class="sxs-lookup"><span data-stu-id="a0e17-115">Category</span></span>

<span data-ttu-id="a0e17-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a0e17-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0e17-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="a0e17-117">Affected APIs</span></span>

<span data-ttu-id="a0e17-118">nessuna</span><span class="sxs-lookup"><span data-stu-id="a0e17-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
