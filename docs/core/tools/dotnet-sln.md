---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: 615e25e30a63b6ca36d9898cfcde565053830572
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389645"
---
# <a name="dotnet-sln"></a><span data-ttu-id="b6146-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b6146-103">dotnet sln</span></span>

<span data-ttu-id="b6146-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="b6146-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b6146-105">Nome</span><span class="sxs-lookup"><span data-stu-id="b6146-105">Name</span></span>

<span data-ttu-id="b6146-106">`dotnet sln`- Elenca o modifica i progetti in un file di soluzione .NET Core.- Lists or modifies the projects in a .NET Core solution file.</span><span class="sxs-lookup"><span data-stu-id="b6146-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b6146-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6146-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="b6146-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6146-108">Description</span></span>

<span data-ttu-id="b6146-109">Il `dotnet sln` comando fornisce un modo pratico per elencare e modificare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="b6146-110">Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente.</span><span class="sxs-lookup"><span data-stu-id="b6146-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="b6146-111">Se è necessario crearne uno, utilizzare il comando [dotnet new,](dotnet-new.md) come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b6146-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="b6146-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b6146-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b6146-113">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b6146-113">The solution file to use.</span></span> <span data-ttu-id="b6146-114">Se questo argomento viene omesso, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b6146-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="b6146-115">Se non trova alcun file di soluzione o più file di soluzione, il comando ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b6146-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="b6146-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b6146-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b6146-117">Stampa una descrizione dell'utilizzo del comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="b6146-118">Comandi:</span><span class="sxs-lookup"><span data-stu-id="b6146-118">Commands</span></span>

### `list`

<span data-ttu-id="b6146-119">Elenca tutti i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b6146-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6146-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b6146-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b6146-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b6146-122">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b6146-122">The solution file to use.</span></span> <span data-ttu-id="b6146-123">Se questo argomento viene omesso, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b6146-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="b6146-124">Se non trova alcun file di soluzione o più file di soluzione, il comando ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b6146-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="b6146-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b6146-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b6146-126">Stampa una descrizione dell'utilizzo del comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="b6146-127">Aggiunge uno o più progetti al file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b6146-128">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6146-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b6146-129">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b6146-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b6146-130">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b6146-130">The solution file to use.</span></span> <span data-ttu-id="b6146-131">Se non è specificato, il comando cerca nella directory corrente uno e ha esito negativo se sono presenti più file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="b6146-132">Percorso del progetto o dei progetti da aggiungere alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="b6146-133">Le espansioni del [modello di globbing](https://en.wikipedia.org/wiki/Glob_(programming)) `dotnet sln` della shell Unix/Linux vengono elaborate correttamente dal comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="b6146-134">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b6146-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b6146-135">Stampa una descrizione dell'utilizzo del comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="b6146-136">Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="b6146-137">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b6146-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="b6146-138">Percorso della cartella della soluzione di destinazione a cui aggiungere i progetti.</span><span class="sxs-lookup"><span data-stu-id="b6146-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="b6146-139">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b6146-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="b6146-140">Rimuove uno o più progetti dal file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b6146-141">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6146-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b6146-142">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b6146-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b6146-143">File di soluzione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b6146-143">The solution file to use.</span></span> <span data-ttu-id="b6146-144">Se non viene specificato, il comando cerca nella directory corrente uno e ha esito negativo se sono presenti più file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="b6146-145">Percorso del progetto o dei progetti da aggiungere alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b6146-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="b6146-146">Le espansioni del [modello di globbing](https://en.wikipedia.org/wiki/Glob_(programming)) `dotnet sln` della shell Unix/Linux vengono elaborate correttamente dal comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="b6146-147">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b6146-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b6146-148">Stampa una descrizione dell'utilizzo del comando.</span><span class="sxs-lookup"><span data-stu-id="b6146-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b6146-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="b6146-149">Examples</span></span>

- <span data-ttu-id="b6146-150">Elencare i progetti in una soluzione:List the projects in a solution:</span><span class="sxs-lookup"><span data-stu-id="b6146-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="b6146-151">Aggiungere un progetto C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="b6146-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="b6146-152">Rimuovere un progetto C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="b6146-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="b6146-153">Aggiungere più progetti in linguaggio C, alla radice di una soluzione:Add multiple C ' c' to the root of a solution:</span><span class="sxs-lookup"><span data-stu-id="b6146-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="b6146-154">Aggiungere più progetti C# a una soluzione:</span><span class="sxs-lookup"><span data-stu-id="b6146-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="b6146-155">Rimuovere più progetti C# da una soluzione:</span><span class="sxs-lookup"><span data-stu-id="b6146-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="b6146-156">Aggiungere più progetti in linguaggio C, usando un modello di globbing (solo Unix/Linux):Add multiple C' projects to a solution using a globbing pattern (Unix/Linux only):</span><span class="sxs-lookup"><span data-stu-id="b6146-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="b6146-157">Aggiungere più progetti in linguaggio C, usando un modello di globbing (solo Windows PowerShell):Add multiple C' projects to a solution using a globbing pattern (Windows PowerShell only):</span><span class="sxs-lookup"><span data-stu-id="b6146-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls **/*.csproj)
  ```

- <span data-ttu-id="b6146-158">Rimuovere più progetti in c'è da una soluzione utilizzando un modello di globbing (solo Unix/Linux):Remove multiple C' projects from a solution using a globbing pattern (Unix/Linux only):</span><span class="sxs-lookup"><span data-stu-id="b6146-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="b6146-159">Rimuovere più progetti in c'è da una soluzione utilizzando un modello globbing (solo Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="b6146-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls **/*.csproj)
  ```
