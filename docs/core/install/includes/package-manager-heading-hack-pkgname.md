---
ms.openlocfilehash: 7723892a33bf7dd8e475b2f696db5d9ab287e182
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602992"
---

<span data-ttu-id="ff25e-101">I pacchetti aggiunti ai feed di gestione pacchetti vengono denominati in un formato informatico: `{product}-{type}-{version}` .</span><span class="sxs-lookup"><span data-stu-id="ff25e-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="ff25e-102">**prodotto**</span><span class="sxs-lookup"><span data-stu-id="ff25e-102">**product**</span></span>\
<span data-ttu-id="ff25e-103">Tipo di prodotto .NET da installare.</span><span class="sxs-lookup"><span data-stu-id="ff25e-103">The type of .NET product to install.</span></span> <span data-ttu-id="ff25e-104">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="ff25e-104">Valid options are:</span></span>

  - <span data-ttu-id="ff25e-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="ff25e-105">dotnet</span></span>
  - <span data-ttu-id="ff25e-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="ff25e-106">aspnetcore</span></span>

- <span data-ttu-id="ff25e-107">**tipo**</span><span class="sxs-lookup"><span data-stu-id="ff25e-107">**type**</span></span>\
<span data-ttu-id="ff25e-108">Sceglie l'SDK o il Runtime.</span><span class="sxs-lookup"><span data-stu-id="ff25e-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="ff25e-109">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="ff25e-109">Valid options are:</span></span>

  - <span data-ttu-id="ff25e-110">SDK</span><span class="sxs-lookup"><span data-stu-id="ff25e-110">sdk</span></span>
  - <span data-ttu-id="ff25e-111">runtime</span><span class="sxs-lookup"><span data-stu-id="ff25e-111">runtime</span></span>

- <span data-ttu-id="ff25e-112">**Versione**</span><span class="sxs-lookup"><span data-stu-id="ff25e-112">**version**</span></span>\
<span data-ttu-id="ff25e-113">Versione dell'SDK o del runtime da installare.</span><span class="sxs-lookup"><span data-stu-id="ff25e-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="ff25e-114">Questo articolo fornirà sempre le istruzioni per la versione supportata più recente.</span><span class="sxs-lookup"><span data-stu-id="ff25e-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="ff25e-115">Le opzioni valide sono le versioni rilasciate, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff25e-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="ff25e-116">3.1</span><span class="sxs-lookup"><span data-stu-id="ff25e-116">3.1</span></span>
  - <span data-ttu-id="ff25e-117">3.0</span><span class="sxs-lookup"><span data-stu-id="ff25e-117">3.0</span></span>
  - <span data-ttu-id="ff25e-118">2.1</span><span class="sxs-lookup"><span data-stu-id="ff25e-118">2.1</span></span>

  <span data-ttu-id="ff25e-119">È possibile che l'SDK/Runtime che si sta provando a scaricare non sia disponibile per la distribuzione Linux.</span><span class="sxs-lookup"><span data-stu-id="ff25e-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="ff25e-120">Per un elenco delle distribuzioni supportate, vedere [dipendenze e requisiti di .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="ff25e-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="ff25e-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="ff25e-121">Examples</span></span>

- <span data-ttu-id="ff25e-122">Installare il runtime di ASP.NET Core 3,1:`aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="ff25e-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="ff25e-123">Installare il runtime di .NET Core 2,1:`dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="ff25e-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="ff25e-124">Installare .NET Core 3,1 SDK:`dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="ff25e-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="ff25e-125">Pacchetto mancante</span><span class="sxs-lookup"><span data-stu-id="ff25e-125">Package missing</span></span>

<span data-ttu-id="ff25e-126">Se la combinazione di versione del pacchetto non funziona, non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ff25e-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="ff25e-127">Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ff25e-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="ff25e-128">Il valore non `aspnetcore-sdk-2.2` è corretto e deve essere `dotnet-sdk-2.2` .</span><span class="sxs-lookup"><span data-stu-id="ff25e-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="ff25e-129">Per un elenco delle distribuzioni Linux supportate da .NET Core, vedere [dipendenze e requisiti di .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="ff25e-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../linux.md).</span></span>
