---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393987"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="223af-101">Gheppio: adapter di connessione rimossi</span><span class="sxs-lookup"><span data-stu-id="223af-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="223af-102">Come parte del passaggio per spostare le API "pubternal" in `public`, il concetto di `IConnectionAdapter` è stato rimosso da gheppio.</span><span class="sxs-lookup"><span data-stu-id="223af-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="223af-103">Le schede di connessione vengono sostituite con il middleware di connessione (simile al middleware HTTP nella pipeline ASP.NET Core, ma per le connessioni di livello inferiore).</span><span class="sxs-lookup"><span data-stu-id="223af-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="223af-104">HTTPS e la registrazione della connessione sono stati spostati dagli adattatori di connessione al middleware di connessione.</span><span class="sxs-lookup"><span data-stu-id="223af-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="223af-105">Questi metodi di estensione devono continuare a funzionare senza interruzioni, ma i dettagli di implementazione sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="223af-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="223af-106">Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 11412](https://github.com/aspnet/AspNetCore/pull/11412).</span><span class="sxs-lookup"><span data-stu-id="223af-106">For more information, see [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412).</span></span> <span data-ttu-id="223af-107">Per informazioni, vedere [ASPNET/AspNetCore # 11475](https://github.com/aspnet/AspNetCore/issues/11475).</span><span class="sxs-lookup"><span data-stu-id="223af-107">For discussion, see [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="223af-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="223af-108">Version introduced</span></span>

<span data-ttu-id="223af-109">3.0</span><span class="sxs-lookup"><span data-stu-id="223af-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="223af-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="223af-110">Old behavior</span></span>

<span data-ttu-id="223af-111">I componenti di estendibilità del gheppio sono stati creati con `IConnectionAdapter`.</span><span class="sxs-lookup"><span data-stu-id="223af-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="223af-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="223af-112">New behavior</span></span>

<span data-ttu-id="223af-113">I componenti di estendibilità di Gheppio vengono creati come [middleware](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="223af-113">Kestrel extensibility components are created as [middleware](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="223af-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="223af-114">Reason for change</span></span>

<span data-ttu-id="223af-115">Questa modifica è concepita per offrire un'architettura di estendibilità più flessibile.</span><span class="sxs-lookup"><span data-stu-id="223af-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="223af-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="223af-116">Recommended action</span></span>

<span data-ttu-id="223af-117">Convertire tutte le implementazioni di `IConnectionAdapter` per usare il nuovo modello di middleware, come illustrato di [seguito](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="223af-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="223af-118">Category</span><span class="sxs-lookup"><span data-stu-id="223af-118">Category</span></span>

<span data-ttu-id="223af-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="223af-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="223af-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="223af-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
