---
title: comando dotnet store
description: Il comando 'dotnet store' archivia gli assembly specificati nell'archivio pacchetti di runtime.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503589"
---
# <a name="dotnet-store"></a><span data-ttu-id="9c69b-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="9c69b-103">dotnet store</span></span>

<span data-ttu-id="9c69b-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="9c69b-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9c69b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="9c69b-105">Name</span></span>

<span data-ttu-id="9c69b-106">`dotnet store`: archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="9c69b-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="9c69b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9c69b-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a><span data-ttu-id="9c69b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c69b-108">Description</span></span>

<span data-ttu-id="9c69b-109">`dotnet store` archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="9c69b-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="9c69b-110">Per impostazione predefinita, gli assembly sono ottimizzati per il framework e il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9c69b-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="9c69b-111">Per altre informazioni, vedere l'argomento [Archivio pacchetti di runtime](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="9c69b-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="9c69b-112">Opzioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="9c69b-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9c69b-113">Specifica il [framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9c69b-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="9c69b-114">Il framework di destinazione deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="9c69b-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="9c69b-115">Il *file manifesto dell'archivio pacchetti* è un file XML che contiene l'elenco di pacchetti da archiviare.</span><span class="sxs-lookup"><span data-stu-id="9c69b-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="9c69b-116">Il formato del file manifesto è compatibile con il formato di progetto SDK.</span><span class="sxs-lookup"><span data-stu-id="9c69b-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="9c69b-117">È quindi possibile usare un file di progetto che fa riferimento ai pacchetti desiderati con l'opzione `-m|--manifest` per archiviare gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="9c69b-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="9c69b-118">Per specificare più file manifesto, ripetere l'opzione e il percorso per ogni file.</span><span class="sxs-lookup"><span data-stu-id="9c69b-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="9c69b-119">Ad esempio `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="9c69b-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="9c69b-120">[Identificatore di runtime](../rid-catalog.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9c69b-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="9c69b-121">Opzioni facoltative</span><span class="sxs-lookup"><span data-stu-id="9c69b-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="9c69b-122">Specifica la versione di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="9c69b-122">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="9c69b-123">Questa opzione consente di selezionare una versione di framework specifica, oltre al framework specificato dall'opzione `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="9c69b-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9c69b-124">Visualizza le informazioni sulla guida.</span><span class="sxs-lookup"><span data-stu-id="9c69b-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="9c69b-125">Specifica il percorso dell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="9c69b-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="9c69b-126">Se non viene specificato, per impostazione predefinita viene usata la sottodirectory *store* della directory di installazione di .NET Core del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="9c69b-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="9c69b-127">Ignora la fase di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="9c69b-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="9c69b-128">Ignora la generazione di simboli.</span><span class="sxs-lookup"><span data-stu-id="9c69b-128">Skips symbol generation.</span></span> <span data-ttu-id="9c69b-129">Attualmente è possibile generare simboli solo in Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="9c69b-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="9c69b-130">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="9c69b-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9c69b-131">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9c69b-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="9c69b-132">Directory di lavoro usata dal comando.</span><span class="sxs-lookup"><span data-stu-id="9c69b-132">The working directory used by the command.</span></span> <span data-ttu-id="9c69b-133">Se non viene specificata, viene usata la sottodirectory *obj* della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9c69b-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="9c69b-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="9c69b-134">Examples</span></span>

- <span data-ttu-id="9c69b-135">Archiviare i pacchetti specificati nel file di progetto *packages.csproj* per .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="9c69b-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="9c69b-136">Archiviare i pacchetti specificati nel file di progetto *packages.csproj* senza ottimizzazione:</span><span class="sxs-lookup"><span data-stu-id="9c69b-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="9c69b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c69b-137">See also</span></span>

- [<span data-ttu-id="9c69b-138">Archivio pacchetti di runtime</span><span class="sxs-lookup"><span data-stu-id="9c69b-138">Runtime package store</span></span>](../deploying/runtime-store.md)
