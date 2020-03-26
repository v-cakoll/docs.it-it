---
ms.openlocfilehash: 4340ed7444681b4601dea50c93926b0ee0c07eec
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134128"
---

<span data-ttu-id="047bd-101">I pacchetti aggiunti ai feed del gestore di `{product}-{type}-{version}`pacchetti sono denominati in un formato comcatenabile: .</span><span class="sxs-lookup"><span data-stu-id="047bd-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="047bd-102">**Prodotto**</span><span class="sxs-lookup"><span data-stu-id="047bd-102">**product**</span></span>\
<span data-ttu-id="047bd-103">Tipo di prodotto .NET da installare.</span><span class="sxs-lookup"><span data-stu-id="047bd-103">The type of .NET product to install.</span></span> <span data-ttu-id="047bd-104">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="047bd-104">Valid options are:</span></span>

  - <span data-ttu-id="047bd-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="047bd-105">dotnet</span></span>
  - <span data-ttu-id="047bd-106">aspnetcore (aspnetcore)</span><span class="sxs-lookup"><span data-stu-id="047bd-106">aspnetcore</span></span>

- <span data-ttu-id="047bd-107">**digitare**</span><span class="sxs-lookup"><span data-stu-id="047bd-107">**type**</span></span>\
<span data-ttu-id="047bd-108">Sceglie l'SDK o il runtime.</span><span class="sxs-lookup"><span data-stu-id="047bd-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="047bd-109">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="047bd-109">Valid options are:</span></span>

  - <span data-ttu-id="047bd-110">SDK</span><span class="sxs-lookup"><span data-stu-id="047bd-110">sdk</span></span>
  - <span data-ttu-id="047bd-111">runtime</span><span class="sxs-lookup"><span data-stu-id="047bd-111">runtime</span></span>

- <span data-ttu-id="047bd-112">**Versione**</span><span class="sxs-lookup"><span data-stu-id="047bd-112">**version**</span></span>\
<span data-ttu-id="047bd-113">Versione dell'SDK o del runtime da installare.</span><span class="sxs-lookup"><span data-stu-id="047bd-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="047bd-114">Questo articolo fornirà sempre le istruzioni per l'ultima versione supportata.</span><span class="sxs-lookup"><span data-stu-id="047bd-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="047bd-115">Le opzioni valide sono qualsiasi versione rilasciata, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="047bd-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="047bd-116">3.1</span><span class="sxs-lookup"><span data-stu-id="047bd-116">3.1</span></span>
  - <span data-ttu-id="047bd-117">3.0</span><span class="sxs-lookup"><span data-stu-id="047bd-117">3.0</span></span>
  - <span data-ttu-id="047bd-118">2.1</span><span class="sxs-lookup"><span data-stu-id="047bd-118">2.1</span></span>

  <span data-ttu-id="047bd-119">È possibile che l'SDK/runtime che si sta tentando di scaricare non sia disponibile per la distribuzione Linux.</span><span class="sxs-lookup"><span data-stu-id="047bd-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="047bd-120">Per un elenco delle distribuzioni supportate, vedere [Dipendenze e requisiti](../dependencies.md?pivots=os-linux)di .NET Core .</span><span class="sxs-lookup"><span data-stu-id="047bd-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="047bd-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="047bd-121">Examples</span></span>

- <span data-ttu-id="047bd-122">Installare il runtime di ASP.NET Core 3.1:Install the ASP.NET Core 3.1 runtime:`aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="047bd-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="047bd-123">Installare il runtime di .NET Core 2.1:`dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="047bd-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="047bd-124">Installare .NET Core 3.1 SDK:`dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="047bd-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="047bd-125">Pacchetto mancante</span><span class="sxs-lookup"><span data-stu-id="047bd-125">Package missing</span></span>

<span data-ttu-id="047bd-126">Se la combinazione pacchetto-versione non funziona, non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="047bd-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="047bd-127">Ad esempio, non esiste un ASP.NET Core SDK, i componenti SDK sono inclusi in .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="047bd-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="047bd-128">Il `aspnetcore-sdk-2.2` valore non è `dotnet-sdk-2.2`corretto e deve essere .</span><span class="sxs-lookup"><span data-stu-id="047bd-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="047bd-129">Per un elenco delle distribuzioni Linux supportate da .NET Core, vedere Dipendenze e requisiti di [.NET Core.](../dependencies.md?pivots=os-linux)</span><span class="sxs-lookup"><span data-stu-id="047bd-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
