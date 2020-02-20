---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: dc0e2f294076ea649f150b076ac279cdc5d224a0
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503595"
---
# <a name="dotnet-sln"></a><span data-ttu-id="4f155-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4f155-103">dotnet sln</span></span>

<span data-ttu-id="4f155-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4f155-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4f155-105">Nome</span><span class="sxs-lookup"><span data-stu-id="4f155-105">Name</span></span>

<span data-ttu-id="4f155-106">`dotnet sln`: consente di modificare un file di soluzione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f155-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4f155-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4f155-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4f155-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f155-108">Description</span></span>

<span data-ttu-id="4f155-109">Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="4f155-110">Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente.</span><span class="sxs-lookup"><span data-stu-id="4f155-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="4f155-111">Se è necessario crearne uno, usare il comando [dotnet new](dotnet-new.md), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4f155-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="4f155-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f155-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="4f155-113">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4f155-113">The solution file to use.</span></span> <span data-ttu-id="4f155-114">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4f155-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="4f155-115">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="4f155-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="4f155-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4f155-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4f155-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4f155-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="4f155-118">Comandi:</span><span class="sxs-lookup"><span data-stu-id="4f155-118">Commands</span></span>

### `add`

<span data-ttu-id="4f155-119">Aggiunge uno o più progetti più al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="4f155-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4f155-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="4f155-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f155-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="4f155-122">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4f155-122">The solution file to use.</span></span> <span data-ttu-id="4f155-123">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4f155-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="4f155-124">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="4f155-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="4f155-125">Percorso del progetto da aggiungere alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="4f155-126">Aggiungere più progetti aggiungendoli uno dopo l'altro separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="4f155-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="4f155-127">Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="4f155-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="4f155-128">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4f155-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4f155-129">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4f155-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="4f155-130">Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="4f155-131">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4f155-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="4f155-132">Percorso della cartella della soluzione di destinazione a cui aggiungere i progetti.</span><span class="sxs-lookup"><span data-stu-id="4f155-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="4f155-133">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4f155-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="4f155-134">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="4f155-135">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4f155-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="4f155-136">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f155-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="4f155-137">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4f155-137">The solution file to use.</span></span> <span data-ttu-id="4f155-138">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4f155-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="4f155-139">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="4f155-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="4f155-140">Percorso del progetto da rimuovere dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="4f155-141">Rimuovere più progetti aggiungendoli uno dopo l'altro separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="4f155-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="4f155-142">Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="4f155-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="4f155-143">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4f155-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4f155-144">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4f155-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="4f155-145">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4f155-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="4f155-146">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4f155-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="4f155-147">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f155-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="4f155-148">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4f155-148">The solution file to use.</span></span> <span data-ttu-id="4f155-149">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4f155-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="4f155-150">Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.</span><span class="sxs-lookup"><span data-stu-id="4f155-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="4f155-151">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4f155-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4f155-152">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4f155-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="4f155-153">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f155-153">Examples</span></span>

- <span data-ttu-id="4f155-154">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="4f155-154">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="4f155-155">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="4f155-155">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="4f155-156">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="4f155-156">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="4f155-157">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="4f155-157">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="4f155-158">Aggiungere più C# progetti a una soluzione usando un modello glob (solo UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="4f155-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="4f155-159">Rimuovere più C# progetti da una soluzione usando un modello glob (solo UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="4f155-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
