---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901895"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="cc547-101">Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilderHosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span><span class="sxs-lookup"><span data-stu-id="cc547-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="cc547-102">Come parte di rendere ASP.NET Core `ObjectPoolProvider` più pagare per il gioco, il è stato rimosso dal set principale di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="cc547-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="cc547-103">Componenti specifici che `ObjectPoolProvider` si basano su ora aggiungerlo da soli.</span><span class="sxs-lookup"><span data-stu-id="cc547-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="cc547-104">Per una discussione, vedere [dotnet/aspnetcore-5944](https://github.com/dotnet/aspnetcore/issues/5944).</span><span class="sxs-lookup"><span data-stu-id="cc547-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc547-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="cc547-105">Version introduced</span></span>

<span data-ttu-id="cc547-106">3.0</span><span class="sxs-lookup"><span data-stu-id="cc547-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cc547-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="cc547-107">Old behavior</span></span>

<span data-ttu-id="cc547-108">`WebHostBuilder`fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI.</span><span class="sxs-lookup"><span data-stu-id="cc547-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cc547-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="cc547-109">New behavior</span></span>

<span data-ttu-id="cc547-110">`WebHostBuilder`non fornisce `ObjectPoolProvider` più per impostazione predefinita nel contenitore DI.</span><span class="sxs-lookup"><span data-stu-id="cc547-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cc547-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="cc547-111">Reason for change</span></span>

<span data-ttu-id="cc547-112">Questa modifica è stata fatta per rendere ASP.NET Core più pagare per il gioco.</span><span class="sxs-lookup"><span data-stu-id="cc547-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc547-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="cc547-113">Recommended action</span></span>

<span data-ttu-id="cc547-114">Se il `ObjectPoolProvider`componente richiede , è necessario aggiungerlo `IServiceCollection`alle dipendenze tramite il file .</span><span class="sxs-lookup"><span data-stu-id="cc547-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="cc547-115">Category</span><span class="sxs-lookup"><span data-stu-id="cc547-115">Category</span></span>

<span data-ttu-id="cc547-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc547-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc547-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="cc547-117">Affected APIs</span></span>

<span data-ttu-id="cc547-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="cc547-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
