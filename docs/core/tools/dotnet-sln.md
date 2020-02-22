---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543482"
---
# <a name="dotnet-sln"></a><span data-ttu-id="325e2-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="325e2-103">dotnet sln</span></span>

<span data-ttu-id="325e2-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="325e2-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="325e2-105">Nome</span><span class="sxs-lookup"><span data-stu-id="325e2-105">Name</span></span>

<span data-ttu-id="325e2-106">`dotnet sln`-elenca o modifica i progetti in un file di soluzione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="325e2-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="325e2-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="325e2-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="325e2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="325e2-108">Description</span></span>

<span data-ttu-id="325e2-109">Il `dotnet sln` comando rappresenta un modo pratico per elencare e modificare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="325e2-110">Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente.</span><span class="sxs-lookup"><span data-stu-id="325e2-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="325e2-111">Se è necessario crearne uno, usare il comando [DotNet New](dotnet-new.md) , come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="325e2-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="325e2-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="325e2-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="325e2-113">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="325e2-113">The solution file to use.</span></span> <span data-ttu-id="325e2-114">Se questo argomento viene omesso, il comando Cerca una directory corrente.</span><span class="sxs-lookup"><span data-stu-id="325e2-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="325e2-115">Se non viene trovato alcun file di soluzione o più file di soluzione, il comando ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="325e2-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="325e2-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="325e2-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="325e2-117">Stampa una descrizione dell'uso del comando.</span><span class="sxs-lookup"><span data-stu-id="325e2-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="325e2-118">Comandi:</span><span class="sxs-lookup"><span data-stu-id="325e2-118">Commands</span></span>

### `list`

<span data-ttu-id="325e2-119">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="325e2-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="325e2-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="325e2-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="325e2-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="325e2-122">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="325e2-122">The solution file to use.</span></span> <span data-ttu-id="325e2-123">Se questo argomento viene omesso, il comando Cerca una directory corrente.</span><span class="sxs-lookup"><span data-stu-id="325e2-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="325e2-124">Se non viene trovato alcun file di soluzione o più file di soluzione, il comando ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="325e2-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="325e2-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="325e2-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="325e2-126">Stampa una descrizione dell'uso del comando.</span><span class="sxs-lookup"><span data-stu-id="325e2-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="325e2-127">Aggiunge uno o più progetti al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="325e2-128">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="325e2-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="325e2-129">Argomenti</span><span class="sxs-lookup"><span data-stu-id="325e2-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="325e2-130">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="325e2-130">The solution file to use.</span></span> <span data-ttu-id="325e2-131">Se non è specificato, il comando Cerca una directory corrente e non riesce se sono presenti più file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="325e2-132">Percorso del progetto o dei progetti da aggiungere alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="325e2-133">Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="325e2-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="325e2-134">Opzioni</span><span class="sxs-lookup"><span data-stu-id="325e2-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="325e2-135">Stampa una descrizione dell'uso del comando.</span><span class="sxs-lookup"><span data-stu-id="325e2-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="325e2-136">Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="325e2-137">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="325e2-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="325e2-138">Percorso della cartella della soluzione di destinazione a cui aggiungere i progetti.</span><span class="sxs-lookup"><span data-stu-id="325e2-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="325e2-139">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="325e2-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="325e2-140">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="325e2-141">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="325e2-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="325e2-142">Argomenti</span><span class="sxs-lookup"><span data-stu-id="325e2-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="325e2-143">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="325e2-143">The solution file to use.</span></span> <span data-ttu-id="325e2-144">Se non viene specificato, il comando Cerca una directory corrente e non riesce se sono presenti più file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="325e2-145">Percorso del progetto o dei progetti da aggiungere alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="325e2-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="325e2-146">Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="325e2-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="325e2-147">Opzioni</span><span class="sxs-lookup"><span data-stu-id="325e2-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="325e2-148">Stampa una descrizione dell'uso del comando.</span><span class="sxs-lookup"><span data-stu-id="325e2-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="325e2-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="325e2-149">Examples</span></span>

- <span data-ttu-id="325e2-150">Elencare i progetti in una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="325e2-151">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="325e2-152">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="325e2-153">Aggiungere più C# progetti alla radice di una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="325e2-154">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="325e2-155">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="325e2-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="325e2-156">Aggiungere più C# progetti a una soluzione usando un modello glob (solo UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="325e2-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="325e2-157">Rimuovere più C# progetti da una soluzione usando un modello glob (solo UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="325e2-157">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
