---
title: Comando dotnet clean - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet clean consente di pulire la directory corrente.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144455"
---
# <a name="dotnet-clean"></a><span data-ttu-id="42c26-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="42c26-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="42c26-104">nome</span><span class="sxs-lookup"><span data-stu-id="42c26-104">Name</span></span>

<span data-ttu-id="42c26-105">`dotnet clean`: pulisce l'output di un progetto.</span><span class="sxs-lookup"><span data-stu-id="42c26-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="42c26-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="42c26-106">Synopsis</span></span>

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="42c26-107">Description</span><span class="sxs-lookup"><span data-stu-id="42c26-107">Description</span></span>

<span data-ttu-id="42c26-108">Il comando `dotnet clean` pulisce l'output della compilazione precedente.</span><span class="sxs-lookup"><span data-stu-id="42c26-108">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="42c26-109">Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="42c26-109">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="42c26-110">Vengono puliti solo gli output creati durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="42c26-110">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="42c26-111">Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).</span><span class="sxs-lookup"><span data-stu-id="42c26-111">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="42c26-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="42c26-112">Arguments</span></span>

`PROJECT`

<span data-ttu-id="42c26-113">Progetto MSBuild da pulire.</span><span class="sxs-lookup"><span data-stu-id="42c26-113">The MSBuild project to clean.</span></span> <span data-ttu-id="42c26-114">Se non viene specificato un file di progetto, MSBuild cerca nella directory di lavoro corrente un file con estensione che termina con *proj* e usa tale file.</span><span class="sxs-lookup"><span data-stu-id="42c26-114">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="42c26-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="42c26-115">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="42c26-116">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="42c26-116">Defines the build configuration.</span></span> <span data-ttu-id="42c26-117">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="42c26-117">The default value is `Debug`.</span></span> <span data-ttu-id="42c26-118">Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="42c26-118">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="42c26-119">[Framework](../../standard/frameworks.md) specificato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="42c26-119">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="42c26-120">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="42c26-120">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="42c26-121">Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="42c26-121">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="42c26-122">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="42c26-122">Prints out a short help for the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="42c26-123">Directory in cui vengono inseriti gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="42c26-123">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="42c26-124">Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.</span><span class="sxs-lookup"><span data-stu-id="42c26-124">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="42c26-125">Elimina la cartella di output del runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="42c26-125">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="42c26-126">Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="42c26-126">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="42c26-127">Opzione disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="42c26-127">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="42c26-128">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="42c26-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="42c26-129">I livelli consentiti sono q[uiet], m[inimal], n[ormal], d[etailed] e diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="42c26-129">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="42c26-130">Esempi</span><span class="sxs-lookup"><span data-stu-id="42c26-130">Examples</span></span>

* <span data-ttu-id="42c26-131">Pulire una compilazione predefinita del progetto:</span><span class="sxs-lookup"><span data-stu-id="42c26-131">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="42c26-132">Pulire un progetto compilato con la configurazione di tipo Versione:</span><span class="sxs-lookup"><span data-stu-id="42c26-132">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```