---
title: Comando dotnet clean
description: Il comando dotnet clean consente di pulire la directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503750"
---
# <a name="dotnet-clean"></a><span data-ttu-id="7ff7e-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="7ff7e-103">dotnet clean</span></span>

<span data-ttu-id="7ff7e-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="7ff7e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7ff7e-105">Nome</span><span class="sxs-lookup"><span data-stu-id="7ff7e-105">Name</span></span>

<span data-ttu-id="7ff7e-106">`dotnet clean`: pulisce l'output di un progetto.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7ff7e-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7ff7e-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7ff7e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ff7e-108">Description</span></span>

<span data-ttu-id="7ff7e-109">Il comando `dotnet clean` pulisce l'output della compilazione precedente.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="7ff7e-110">Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="7ff7e-111">Vengono puliti solo gli output creati durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="7ff7e-112">Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).</span><span class="sxs-lookup"><span data-stu-id="7ff7e-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="7ff7e-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7ff7e-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="7ff7e-114">Progetto o soluzione MSBuild da pulire.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="7ff7e-115">Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="7ff7e-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7ff7e-116">Options</span></span>

* **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="7ff7e-117">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-117">Defines the build configuration.</span></span> <span data-ttu-id="7ff7e-118">Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-118">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span> <span data-ttu-id="7ff7e-119">Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="7ff7e-120">[Framework](../../standard/frameworks.md) specificato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="7ff7e-121">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="7ff7e-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="7ff7e-122">Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="7ff7e-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="7ff7e-124">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="7ff7e-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="7ff7e-125">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-125">For example, to complete authentication.</span></span> <span data-ttu-id="7ff7e-126">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="7ff7e-127">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="7ff7e-128">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="7ff7e-129">Directory contenente gli artefatti di compilazione da pulire.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="7ff7e-130">Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="7ff7e-131">Elimina la cartella di output del runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="7ff7e-132">Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="7ff7e-132">This is used when a [self-contained deployment](../deploying/index.md#publish-self-contained) was created.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7ff7e-133">Imposta il livello di dettaglio di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-133">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="7ff7e-134">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-134">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7ff7e-135">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-135">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="7ff7e-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="7ff7e-136">Examples</span></span>

* <span data-ttu-id="7ff7e-137">Pulire una compilazione predefinita del progetto:</span><span class="sxs-lookup"><span data-stu-id="7ff7e-137">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="7ff7e-138">Pulire un progetto compilato con la configurazione di tipo Versione:</span><span class="sxs-lookup"><span data-stu-id="7ff7e-138">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
