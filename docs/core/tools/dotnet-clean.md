---
title: Comando dotnet clean - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet clean consente di pulire la directory corrente.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 9e68781fe00590f3c8d429631a3f72d525d29fa9
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697031"
---
# <a name="dotnet-clean"></a><span data-ttu-id="db261-103">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="db261-103">dotnet-clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="db261-104">nome</span><span class="sxs-lookup"><span data-stu-id="db261-104">Name</span></span>

<span data-ttu-id="db261-105">`dotnet clean`: pulisce l'output di un progetto.</span><span class="sxs-lookup"><span data-stu-id="db261-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="db261-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="db261-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="db261-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="db261-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="db261-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="db261-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="db261-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db261-109">Description</span></span>

<span data-ttu-id="db261-110">Il comando `dotnet clean` pulisce l'output della compilazione precedente.</span><span class="sxs-lookup"><span data-stu-id="db261-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="db261-111">Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="db261-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="db261-112">Vengono puliti solo gli output creati durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="db261-113">Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).</span><span class="sxs-lookup"><span data-stu-id="db261-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="db261-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db261-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="db261-115">Progetto MSBuild da pulire.</span><span class="sxs-lookup"><span data-stu-id="db261-115">The MSBuild project to clean.</span></span> <span data-ttu-id="db261-116">Se non viene specificato un file di progetto, MSBuild cerca nella directory di lavoro corrente un file con estensione che termina con *proj* e usa tale file.</span><span class="sxs-lookup"><span data-stu-id="db261-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="db261-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="db261-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="db261-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="db261-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="db261-119">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-119">Defines the build configuration.</span></span> <span data-ttu-id="db261-120">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="db261-120">The default value is `Debug`.</span></span> <span data-ttu-id="db261-121">Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="db261-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="db261-122">[Framework](../../standard/frameworks.md) specificato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="db261-123">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="db261-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="db261-124">Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="db261-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="db261-125">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="db261-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="db261-126">Directory in cui vengono inseriti gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="db261-127">Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.</span><span class="sxs-lookup"><span data-stu-id="db261-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="db261-128">Elimina la cartella di output del runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="db261-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="db261-129">Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="db261-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="db261-130">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="db261-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="db261-131">I livelli consentiti sono q[uiet], m[inimal], n[ormal], d[etailed] e diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="db261-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="db261-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="db261-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="db261-133">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-133">Defines the build configuration.</span></span> <span data-ttu-id="db261-134">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="db261-134">The default value is `Debug`.</span></span> <span data-ttu-id="db261-135">Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="db261-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="db261-136">[Framework](../../standard/frameworks.md) specificato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="db261-137">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="db261-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="db261-138">Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="db261-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="db261-139">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="db261-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="db261-140">Directory in cui vengono inseriti gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db261-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="db261-141">Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.</span><span class="sxs-lookup"><span data-stu-id="db261-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="db261-142">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="db261-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="db261-143">I livelli consentiti sono q[uiet], m[inimal], n[ormal], d[etailed] e diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="db261-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="db261-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="db261-144">Examples</span></span>

<span data-ttu-id="db261-145">Pulire una compilazione predefinita del progetto:</span><span class="sxs-lookup"><span data-stu-id="db261-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="db261-146">Pulire un progetto compilato con la configurazione di tipo Versione:</span><span class="sxs-lookup"><span data-stu-id="db261-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
