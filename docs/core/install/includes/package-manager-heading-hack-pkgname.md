---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116169"
---

<span data-ttu-id="c3602-101">I pacchetti aggiunti ai feed di gestione pacchetti vengono denominati in un formato informatico: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="c3602-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="c3602-102">\ **prodotto**</span><span class="sxs-lookup"><span data-stu-id="c3602-102">**product**\</span></span>
<span data-ttu-id="c3602-103">Tipo di prodotto .NET da installare.</span><span class="sxs-lookup"><span data-stu-id="c3602-103">The type of .NET product to install.</span></span> <span data-ttu-id="c3602-104">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="c3602-104">Valid options are:</span></span>

  - <span data-ttu-id="c3602-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="c3602-105">dotnet</span></span>
  - <span data-ttu-id="c3602-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="c3602-106">aspnetcore</span></span>

- <span data-ttu-id="c3602-107">**type**</span><span class="sxs-lookup"><span data-stu-id="c3602-107">**type**</span></span>\
<span data-ttu-id="c3602-108">Sceglie l'SDK o il Runtime.</span><span class="sxs-lookup"><span data-stu-id="c3602-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="c3602-109">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="c3602-109">Valid options are:</span></span>

  - <span data-ttu-id="c3602-110">SDK</span><span class="sxs-lookup"><span data-stu-id="c3602-110">sdk</span></span>
  - <span data-ttu-id="c3602-111">runtime di</span><span class="sxs-lookup"><span data-stu-id="c3602-111">runtime</span></span>

- <span data-ttu-id="c3602-112">\ **versione**</span><span class="sxs-lookup"><span data-stu-id="c3602-112">**version**\</span></span>
<span data-ttu-id="c3602-113">Versione dell'SDK o del runtime da installare.</span><span class="sxs-lookup"><span data-stu-id="c3602-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="c3602-114">Questo articolo fornirà sempre le istruzioni per la versione supportata più recente.</span><span class="sxs-lookup"><span data-stu-id="c3602-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="c3602-115">Le opzioni valide sono le versioni rilasciate, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3602-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="c3602-116">3.0</span><span class="sxs-lookup"><span data-stu-id="c3602-116">3.0</span></span>
  - <span data-ttu-id="c3602-117">2.2</span><span class="sxs-lookup"><span data-stu-id="c3602-117">2.2</span></span>
  - <span data-ttu-id="c3602-118">2.1</span><span class="sxs-lookup"><span data-stu-id="c3602-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="c3602-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="c3602-119">Examples</span></span>

- <span data-ttu-id="c3602-120">Installare .NET Core 2,2 SDK: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="c3602-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="c3602-121">Installare il runtime di ASP.NET Core 3,1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="c3602-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="c3602-122">Installare il runtime di .NET Core 2,1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="c3602-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="c3602-123">Risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="c3602-123">Troubleshoot</span></span>

<span data-ttu-id="c3602-124">Se la combinazione di pacchetti non funziona, non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3602-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="c3602-125">Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c3602-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="c3602-126">Il valore `aspnetcore-sdk-2.2` non è corretto e deve essere `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="c3602-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
