---
title: comando dotnet store
description: Il comando 'dotnet store' archivia gli assembly specificati nell'archivio pacchetti di runtime.
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: f819444c92afde0e1a5349a58918f993868a0143
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-store"></a><span data-ttu-id="a95a6-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="a95a6-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="a95a6-104">nome</span><span class="sxs-lookup"><span data-stu-id="a95a6-104">Name</span></span>

<span data-ttu-id="a95a6-105">`dotnet store`: archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="a95a6-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="a95a6-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a95a6-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="a95a6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a95a6-107">Description</span></span>

<span data-ttu-id="a95a6-108">`dotnet store` archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="a95a6-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="a95a6-109">Per impostazione predefinita, gli assembly sono ottimizzati per il framework e il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a95a6-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="a95a6-110">Per altre informazioni, vedere l'argomento [Archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="a95a6-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="a95a6-111">Opzioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="a95a6-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a95a6-112">Specifica il [framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a95a6-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="a95a6-113">Il *file manifesto dell'archivio pacchetti* è un file XML che contiene l'elenco di pacchetti da archiviare.</span><span class="sxs-lookup"><span data-stu-id="a95a6-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="a95a6-114">Il formato del file manifesto è compatibile con il formato *csproj*.</span><span class="sxs-lookup"><span data-stu-id="a95a6-114">The format of the manifest file is compatible with the *csproj* format.</span></span> <span data-ttu-id="a95a6-115">È quindi possibile usare un file di progetto *csproj* che fa riferimento ai pacchetti desiderati con l'opzione `-m|--manifest` per archiviare gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="a95a6-115">So, a *csproj* project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="a95a6-116">Per specificare più file manifesto, ripetere l'opzione e il percorso per ogni file: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="a95a6-116">To specify multiple manifest files, repeat the option and path for each file: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="a95a6-117">L'[identificatore di runtime](../rid-catalog.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a95a6-117">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="a95a6-118">Opzioni facoltative</span><span class="sxs-lookup"><span data-stu-id="a95a6-118">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="a95a6-119">Specifica la versione di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="a95a6-119">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="a95a6-120">Questa opzione consente di selezionare una versione di framework specifica, oltre al framework specificato dall'opzione `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="a95a6-120">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="a95a6-121">Visualizza le informazioni sulla guida.</span><span class="sxs-lookup"><span data-stu-id="a95a6-121">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a95a6-122">Specifica il percorso dell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="a95a6-122">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="a95a6-123">Se non viene specificato, per impostazione predefinita viene usata la sottodirectory *store* della directory di installazione di .NET Core del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="a95a6-123">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="a95a6-124">Ignora la fase di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="a95a6-124">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="a95a6-125">Ignora la generazione di simboli.</span><span class="sxs-lookup"><span data-stu-id="a95a6-125">Skips symbol generation.</span></span> <span data-ttu-id="a95a6-126">Attualmente è possibile generare simboli solo in Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="a95a6-126">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a95a6-127">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a95a6-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a95a6-128">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a95a6-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="a95a6-129">Directory di lavoro usata dal comando.</span><span class="sxs-lookup"><span data-stu-id="a95a6-129">The working directory used by the command.</span></span> <span data-ttu-id="a95a6-130">Se non viene specificata, viene usata la sottodirectory *obj* della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a95a6-130">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="a95a6-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="a95a6-131">Examples</span></span>

<span data-ttu-id="a95a6-132">Archiviare i pacchetti specificati nel file di progetto *packages.csproj* per .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="a95a6-132">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="a95a6-133">Archiviare i pacchetti specificati nel file di progetto *packages.csproj* senza ottimizzazione:</span><span class="sxs-lookup"><span data-stu-id="a95a6-133">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="a95a6-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a95a6-134">See also</span></span>

[<span data-ttu-id="a95a6-135">Archivio pacchetti di runtime</span><span class="sxs-lookup"><span data-stu-id="a95a6-135">Runtime package store</span></span>](../deploying/runtime-store.md)   
