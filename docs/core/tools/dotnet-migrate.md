---
title: Comando dotnet migrate
description: Il comando dotnet migrate consente di eseguire la migrazione di un progetto e di tutte le relative dipendenze.
ms.date: 08/08/2019
ms.openlocfilehash: afc16161761d151e743e53a8572a6564add43517
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117691"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="12072-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="12072-103">dotnet migrate</span></span>

<span data-ttu-id="12072-104">**Questo articolo si applica a: ✓** .NET Core 1. x SDK **✓** .NET Core 2. x SDK</span><span class="sxs-lookup"><span data-stu-id="12072-104">**This article applies to: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="12072-105">nome</span><span class="sxs-lookup"><span data-stu-id="12072-105">Name</span></span>

<span data-ttu-id="12072-106">`dotnet migrate`: esegue la migrazione di un progetto .NET Core Preview 2 a un progetto di tipo .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="12072-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="12072-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="12072-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="12072-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12072-108">Description</span></span>

<span data-ttu-id="12072-109">Il comando `dotnet migrate` esegue la migrazione di un progetto basato su *project.json* Preview 2 valido a un progetto *csproj* di tipo .NET Core SDK valido.</span><span class="sxs-lookup"><span data-stu-id="12072-109">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="12072-110">Per impostazione predefinita, il comando esegue la migrazione del progetto radice e dei riferimenti del progetto presenti nel progetto radice.</span><span class="sxs-lookup"><span data-stu-id="12072-110">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="12072-111">Questo comportamento viene disabilitato usando l'opzione `--skip-project-references` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12072-111">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="12072-112">È possibile eseguire la migrazione in uno degli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="12072-112">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="12072-113">Un singolo progetto, specificando il file *project.json* di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="12072-113">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="12072-114">Tutte le directory specificate nel file *global.json*, passando un percorso del file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="12072-114">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="12072-115">Un file *solution.sln*, dove vengono migrati i progetti a cui viene fatto riferimento nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="12072-115">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="12072-116">Tutte le sottodirectory della directory specificata, in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="12072-116">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="12072-117">Il comando `dotnet migrate` mantiene il file *project.json* di cui è stata eseguita la migrazione all'interno di una directory `backup`, che verrà creata se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="12072-117">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="12072-118">Questo comportamento viene sottoposto a override tramite l'opzione `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="12072-118">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="12072-119">Per impostazione predefinita, l'operazione di migrazione restituisce lo stato del processo di migrazione all'output standard (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="12072-119">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="12072-120">Se si usa l'opzione `--report-file <REPORT_FILE>`, l'output viene salvato nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="12072-120">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="12072-121">Il comando `dotnet migrate` supporta solo progetti basati su *project.json* Preview 2 validi.</span><span class="sxs-lookup"><span data-stu-id="12072-121">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="12072-122">Questo significa che non è possibile usare questo comando per eseguire la migrazione di progetti basati su DNX o *project.json* Preview 1 direttamente a progetti MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="12072-122">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="12072-123">È prima necessario eseguire manualmente la migrazione del progetto a un progetto basato su *project.json* Preview 2 e quindi usare il comando `dotnet migrate` per eseguire la migrazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="12072-123">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

<span data-ttu-id="12072-124">Il `dotnet migrate` comando non è più disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="12072-124">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span>

## <a name="arguments"></a><span data-ttu-id="12072-125">Argomenti</span><span class="sxs-lookup"><span data-stu-id="12072-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="12072-126">Percorso a uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12072-126">The path to one of the following:</span></span>

* <span data-ttu-id="12072-127">File *project.json* di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="12072-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="12072-128">File *global.json*: viene eseguita la migrazione delle cartelle specificate in *global.json*.</span><span class="sxs-lookup"><span data-stu-id="12072-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="12072-129">File *solution.sln*: viene eseguita la migrazione dei progetti a cui viene fatto riferimento nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="12072-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="12072-130">Directory di cui eseguire la migrazione: vengono cercati in modo ricorsivo i file *project.json* di cui eseguire la migrazione all'interno della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="12072-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="12072-131">Se non è specificata alcuna opzione, verrà impostata automaticamente la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="12072-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="12072-132">Opzioni</span><span class="sxs-lookup"><span data-stu-id="12072-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="12072-133">File di report di migrazione dell'output come JSON anziché messaggi utente.</span><span class="sxs-lookup"><span data-stu-id="12072-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="12072-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="12072-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="12072-135">Report di migrazione dell'output a un file oltre che alla console.</span><span class="sxs-lookup"><span data-stu-id="12072-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="12072-136">Ignora la migrazione dei riferimenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="12072-136">Skip migrating project references.</span></span> <span data-ttu-id="12072-137">Per impostazione predefinita, i riferimenti al progetto vengono migrati in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="12072-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="12072-138">Dopo l'esito positivo della migrazione, ignorare lo spostamento di *project.json*, *global.json* e *\*.xproj* in una directory `backup`.</span><span class="sxs-lookup"><span data-stu-id="12072-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="12072-139">File csproj modello da usare per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="12072-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="12072-140">Per impostazione predefinita, viene usato lo stesso modello di quello eliminato da `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="12072-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="12072-141">Versione del pacchetto SDK a cui viene fatto riferimento nell'app di cui è stata eseguita la migrazione.</span><span class="sxs-lookup"><span data-stu-id="12072-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="12072-142">Il valore predefinito è la versione dell'SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="12072-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="12072-143">Percorso del file xproj da usare.</span><span class="sxs-lookup"><span data-stu-id="12072-143">The path to the xproj file to use.</span></span> <span data-ttu-id="12072-144">Obbligatorio quando è presente più di un progetto xproj nella directory di un progetto.</span><span class="sxs-lookup"><span data-stu-id="12072-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="12072-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="12072-145">Examples</span></span>

<span data-ttu-id="12072-146">Eseguire la migrazione di un progetto nella directory corrente e in tutte le relative dipendenze da progetto a progetto:</span><span class="sxs-lookup"><span data-stu-id="12072-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="12072-147">Eseguire la migrazione di tutti i progetti inclusi nel file *global.json*:</span><span class="sxs-lookup"><span data-stu-id="12072-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="12072-148">Eseguire solo la migrazione del progetto corrente e non delle dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="12072-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="12072-149">Usare una versione specifica dell'SDK:</span><span class="sxs-lookup"><span data-stu-id="12072-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
