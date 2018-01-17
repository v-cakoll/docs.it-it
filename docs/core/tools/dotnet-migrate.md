---
title: Comando dotnet migrate - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet migrate consente di eseguire la migrazione di un progetto e di tutte le relative dipendenze.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 7fad6bf67dfe7b0d6f70ce527a153080aa17d888
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-migrate"></a><span data-ttu-id="b9d84-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b9d84-103">dotnet migrate</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b9d84-104">nome</span><span class="sxs-lookup"><span data-stu-id="b9d84-104">Name</span></span>

<span data-ttu-id="b9d84-105">`dotnet migrate`: esegue la migrazione di un progetto .NET Core Preview 2 a un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="b9d84-105">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b9d84-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b9d84-106">Synopsis</span></span>

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a><span data-ttu-id="b9d84-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9d84-107">Description</span></span>

<span data-ttu-id="b9d84-108">Il comando `dotnet migrate` esegue la migrazione di un progetto basato su *project.json* Preview 2 valido a un progetto *csproj* .NET Core SDK 1.0 valido.</span><span class="sxs-lookup"><span data-stu-id="b9d84-108">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span> 

<span data-ttu-id="b9d84-109">Per impostazione predefinita, il comando esegue la migrazione del progetto radice e dei riferimenti del progetto presenti nel progetto radice.</span><span class="sxs-lookup"><span data-stu-id="b9d84-109">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="b9d84-110">Questo comportamento viene disabilitato usando l'opzione `--skip-project-references` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-110">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span> 

<span data-ttu-id="b9d84-111">È possibile eseguire la migrazione in uno degli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9d84-111">Migration is performed on the following:</span></span>

* <span data-ttu-id="b9d84-112">Un singolo progetto, specificando il file *project.json* di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-112">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="b9d84-113">Tutte le directory specificate nel file *global.json*, passando un percorso del file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b9d84-113">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="b9d84-114">Un file *solution.sln*, dove vengono migrati i progetti a cui viene fatto riferimento nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-114">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="b9d84-115">Tutte le sottodirectory della directory specificata, in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="b9d84-115">On all sub-directories of the given directory recursively.</span></span>

<span data-ttu-id="b9d84-116">Il comando `dotnet migrate` mantiene il file *project.json* di cui è stata eseguita la migrazione all'interno di una directory `backup`, che verrà creata se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="b9d84-116">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="b9d84-117">Questo comportamento viene sottoposto a override tramite l'opzione `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="b9d84-117">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="b9d84-118">Per impostazione predefinita, l'operazione di migrazione restituisce lo stato del processo di migrazione all'output standard (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="b9d84-118">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="b9d84-119">Se si usa l'opzione `--report-file <REPORT_FILE>`, l'output viene salvato nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="b9d84-119">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span> 

<span data-ttu-id="b9d84-120">Il comando `dotnet migrate` supporta solo progetti basati su *project.json* Preview 2 validi.</span><span class="sxs-lookup"><span data-stu-id="b9d84-120">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="b9d84-121">Questo significa che non è possibile usare questo comando per eseguire la migrazione di progetti basati su DNX o *project.json* Preview 1 direttamente a progetti MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="b9d84-121">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="b9d84-122">È prima necessario eseguire manualmente la migrazione del progetto a un progetto basato su *project.json* Preview 2 e quindi usare il comando `dotnet migrate` per eseguire la migrazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="b9d84-122">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="b9d84-123">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b9d84-123">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="b9d84-124">Percorso a uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9d84-124">The path to one of the following:</span></span>

* <span data-ttu-id="b9d84-125">File *project.json* di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-125">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="b9d84-126">File *global.json*. Verrà eseguita la migrazione delle cartelle specificate in *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b9d84-126">a *global.json* file, it will migrate the folders specified in *global.json*.</span></span>
* <span data-ttu-id="b9d84-127">File *solution.sln*. Verrà eseguita la migrazione dei progetti a cui viene fatto riferimento nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-127">a *solution.sln* file, it will migrate the projects referenced in the solution.</span></span>
* <span data-ttu-id="b9d84-128">Directory di cui eseguire la migrazione. Verranno cercati in modo ricorsivo i file *project.json* di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-128">a directory to migrate, it will recursively search for *project.json* files to migrate.</span></span>

<span data-ttu-id="b9d84-129">Se non è specificata alcuna opzione, verrà impostata automaticamente la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b9d84-129">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="b9d84-130">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b9d84-130">Options</span></span>

`-h|--help`

<span data-ttu-id="b9d84-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b9d84-131">Prints out a short help for the command.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="b9d84-132">File csproj modello da usare per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-132">Template csproj file to use for migration.</span></span> <span data-ttu-id="b9d84-133">Per impostazione predefinita, viene usato lo stesso modello di quello eliminato da `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="b9d84-133">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="b9d84-134">Versione del pacchetto SDK a cui viene fatto riferimento nell'app di cui è stata eseguita la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9d84-134">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="b9d84-135">Il valore predefinito è la versione dell'SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="b9d84-135">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="b9d84-136">Percorso del file xproj da usare.</span><span class="sxs-lookup"><span data-stu-id="b9d84-136">The path to the xproj file to use.</span></span> <span data-ttu-id="b9d84-137">Obbligatorio quando è presente più di un progetto xproj nella directory di un progetto.</span><span class="sxs-lookup"><span data-stu-id="b9d84-137">Required when there is more than one xproj in a project directory.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="b9d84-138">Ignora la migrazione dei riferimenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="b9d84-138">Skip migrating project references.</span></span> <span data-ttu-id="b9d84-139">Per impostazione predefinita, i riferimenti al progetto vengono migrati in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="b9d84-139">By default, project references are migrated recursively.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="b9d84-140">Report di migrazione dell'output a un file oltre che alla console.</span><span class="sxs-lookup"><span data-stu-id="b9d84-140">Output migration report to a file in addition to the console.</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="b9d84-141">File di report di migrazione dell'output come JSON anziché messaggi utente.</span><span class="sxs-lookup"><span data-stu-id="b9d84-141">Output migration report file as JSON rather than user messages.</span></span>

`--skip-backup`

<span data-ttu-id="b9d84-142">Dopo l'esito positivo della migrazione, ignorare lo spostamento di *project.json*, *global.json* e *\\*.xproj* in una directory `backup`.</span><span class="sxs-lookup"><span data-stu-id="b9d84-142">Skip moving *project.json*, *global.json*, and *\\*.xproj* to a `backup` directory after successful migration.</span></span>

## <a name="examples"></a><span data-ttu-id="b9d84-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="b9d84-143">Examples</span></span>

<span data-ttu-id="b9d84-144">Eseguire la migrazione di un progetto nella directory corrente e in tutte le relative dipendenze da progetto a progetto:</span><span class="sxs-lookup"><span data-stu-id="b9d84-144">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="b9d84-145">Eseguire la migrazione di tutti i progetti inclusi nel file *global.json*:</span><span class="sxs-lookup"><span data-stu-id="b9d84-145">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="b9d84-146">Eseguire solo la migrazione del progetto corrente e non delle dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="b9d84-146">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="b9d84-147">Usare una versione specifica dell'SDK:</span><span class="sxs-lookup"><span data-stu-id="b9d84-147">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
