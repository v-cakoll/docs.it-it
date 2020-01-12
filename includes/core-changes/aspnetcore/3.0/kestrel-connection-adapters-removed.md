---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902012"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="c54e4-101">Gheppio: adapter di connessione rimossi</span><span class="sxs-lookup"><span data-stu-id="c54e4-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="c54e4-102">Come parte del passaggio per spostare le API "pubternal" in `public`, il concetto di `IConnectionAdapter` è stato rimosso da gheppio.</span><span class="sxs-lookup"><span data-stu-id="c54e4-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="c54e4-103">Le schede di connessione vengono sostituite con il middleware di connessione (simile al middleware HTTP nella pipeline ASP.NET Core, ma per le connessioni di livello inferiore).</span><span class="sxs-lookup"><span data-stu-id="c54e4-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="c54e4-104">HTTPS e la registrazione della connessione sono stati spostati dagli adattatori di connessione al middleware di connessione.</span><span class="sxs-lookup"><span data-stu-id="c54e4-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="c54e4-105">Questi metodi di estensione devono continuare a funzionare senza interruzioni, ma i dettagli di implementazione sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="c54e4-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="c54e4-106">Per ulteriori informazioni, vedere [DotNet/aspnetcore # 11412](https://github.com/dotnet/aspnetcore/pull/11412).</span><span class="sxs-lookup"><span data-stu-id="c54e4-106">For more information, see [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412).</span></span> <span data-ttu-id="c54e4-107">Per informazioni, vedere [DotNet/aspnetcore # 11475](https://github.com/dotnet/aspnetcore/issues/11475).</span><span class="sxs-lookup"><span data-stu-id="c54e4-107">For discussion, see [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c54e4-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c54e4-108">Version introduced</span></span>

<span data-ttu-id="c54e4-109">3.0</span><span class="sxs-lookup"><span data-stu-id="c54e4-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c54e4-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="c54e4-110">Old behavior</span></span>

<span data-ttu-id="c54e4-111">I componenti di estendibilità di gheppio sono stati creati con `IConnectionAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c54e4-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c54e4-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="c54e4-112">New behavior</span></span>

<span data-ttu-id="c54e4-113">I componenti di estendibilità di Gheppio vengono creati come [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="c54e4-113">Kestrel extensibility components are created as [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c54e4-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="c54e4-114">Reason for change</span></span>

<span data-ttu-id="c54e4-115">Questa modifica è concepita per offrire un'architettura di estendibilità più flessibile.</span><span class="sxs-lookup"><span data-stu-id="c54e4-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c54e4-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c54e4-116">Recommended action</span></span>

<span data-ttu-id="c54e4-117">Convertire tutte le implementazioni di `IConnectionAdapter` per usare il nuovo modello di middleware, come illustrato di [seguito](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="c54e4-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="c54e4-118">Categoria</span><span class="sxs-lookup"><span data-stu-id="c54e4-118">Category</span></span>

<span data-ttu-id="c54e4-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c54e4-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c54e4-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="c54e4-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
