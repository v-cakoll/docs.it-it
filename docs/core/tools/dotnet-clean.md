---
title: Comando dotnet-clean - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-clean consente di pulire la directory corrente.
keywords: dotnet-clean, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10222781d5bff596d1b7883bc73097758e878235
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-clean"></a><span data-ttu-id="d07f0-104">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="d07f0-104">dotnet-clean</span></span>

## <a name="name"></a><span data-ttu-id="d07f0-105">Nome</span><span class="sxs-lookup"><span data-stu-id="d07f0-105">Name</span></span>

<span data-ttu-id="d07f0-106">`dotnet-clean`: pulisce l'output di un progetto.</span><span class="sxs-lookup"><span data-stu-id="d07f0-106">`dotnet-clean` - Cleans the output of a project.</span></span> 

## <a name="synopsis"></a><span data-ttu-id="d07f0-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d07f0-107">Synopsis</span></span>

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="d07f0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d07f0-108">Description</span></span>

<span data-ttu-id="d07f0-109">Il comando `dotnet clean` pulisce l'output della compilazione precedente.</span><span class="sxs-lookup"><span data-stu-id="d07f0-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="d07f0-110">Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d07f0-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="d07f0-111">Vengono puliti solo gli output creati durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="d07f0-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="d07f0-112">Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).</span><span class="sxs-lookup"><span data-stu-id="d07f0-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="d07f0-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d07f0-113">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d07f0-114">Progetto MSBuild da pulire.</span><span class="sxs-lookup"><span data-stu-id="d07f0-114">The MSBuild project to clean.</span></span> <span data-ttu-id="d07f0-115">Se non viene specificato un file di progetto, MSBuild cerca nella directory di lavoro corrente un file con estensione che termina con *proj* e usa tale file.</span><span class="sxs-lookup"><span data-stu-id="d07f0-115">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="d07f0-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d07f0-116">Options</span></span>

`-h|--help`

<span data-ttu-id="d07f0-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d07f0-117">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d07f0-118">Directory in cui vengono inseriti gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d07f0-118">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="d07f0-119">Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.</span><span class="sxs-lookup"><span data-stu-id="d07f0-119">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d07f0-120">[Framework](../../standard/frameworks.md) specificato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d07f0-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="d07f0-121">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="d07f0-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="d07f0-122">Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="d07f0-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="d07f0-123">Definisce la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d07f0-123">Defines the configuration.</span></span> <span data-ttu-id="d07f0-124">Se omessa, il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d07f0-124">If omitted, it defaults to `Debug`.</span></span> <span data-ttu-id="d07f0-125">Se è stata specificata durante la fase di compilazione, questa proprietà è necessaria soltanto al momento della pulizia.</span><span class="sxs-lookup"><span data-stu-id="d07f0-125">This property is only required when cleaning if you specified it during build time.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d07f0-126">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="d07f0-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d07f0-127">I livelli consentiti sono q[uiet], m[inimal], n[ormal], d[etailed] e diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="d07f0-127">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="d07f0-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="d07f0-128">Examples</span></span>

<span data-ttu-id="d07f0-129">Pulire una compilazione predefinita del progetto:</span><span class="sxs-lookup"><span data-stu-id="d07f0-129">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="d07f0-130">Pulire un progetto compilato con la configurazione di tipo Versione:</span><span class="sxs-lookup"><span data-stu-id="d07f0-130">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`

