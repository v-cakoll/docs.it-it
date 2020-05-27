---
title: Comando dotnet add package
description: Il comando 'dotnet add package' offre un'opzione utile per aggiungere un riferimento al pacchetto NuGet in un progetto.
ms.date: 02/14/2020
ms.openlocfilehash: bc79fe8adf5f775ddce62f3877a8de945c6a18ab
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840897"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="4bfa9-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4bfa9-103">dotnet add package</span></span>

<span data-ttu-id="4bfa9-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4bfa9-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4bfa9-105">Nome</span><span class="sxs-lookup"><span data-stu-id="4bfa9-105">Name</span></span>

<span data-ttu-id="4bfa9-106">`dotnet add package`: aggiunge il riferimento al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4bfa9-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4bfa9-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] package <PACKAGE_NAME>
    [-f|--framework <FRAMEWORK>] [--interactive]
    [-n|--no-restore] [--package-directory <PACKAGE_DIRECTORY>]
    [-s|--source <SOURCE>] [-v|--version <VERSION>]

dotnet add package -h|--help
```

## <a name="description"></a><span data-ttu-id="4bfa9-108">Description</span><span class="sxs-lookup"><span data-stu-id="4bfa9-108">Description</span></span>

<span data-ttu-id="4bfa9-109">Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="4bfa9-110">Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="4bfa9-111">Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="4bfa9-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="4bfa9-112">Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
Writing C:\Users\me\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="4bfa9-113">Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

### <a name="implicit-restore"></a><span data-ttu-id="4bfa9-114">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="4bfa9-114">Implicit restore</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="4bfa9-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4bfa9-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="4bfa9-116">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-116">Specifies the project file.</span></span> <span data-ttu-id="4bfa9-117">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-117">If not specified, the command searches the current directory for one.</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="4bfa9-118">Riferimento al pacchetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-118">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="4bfa9-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4bfa9-119">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="4bfa9-120">Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-120">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="4bfa9-121">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="4bfa9-122">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="4bfa9-122">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="4bfa9-123">Disponibile a partire da .NET Core 2.1 SDK, versione 2.1.400 o successiva.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-123">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

- **`-n|--no-restore`**

  <span data-ttu-id="4bfa9-124">Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-124">Adds a package reference without performing a restore preview and compatibility check.</span></span>

- **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="4bfa9-125">La directory in cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-125">The directory where to restore the packages.</span></span> <span data-ttu-id="4bfa9-126">Il percorso di ripristino del pacchetto predefinito è `%userprofile%\.nuget\packages` in Windows e `~/.nuget/packages` in macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-126">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="4bfa9-127">Per altre informazioni, vedere [Gestione delle cartelle dei pacchetti globale, della cache e temporanea in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span><span class="sxs-lookup"><span data-stu-id="4bfa9-127">For more information, see [Managing the global packages, cache, and temp folders in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="4bfa9-128">URI dell'origine del pacchetto NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-128">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--version <VERSION>`**

  <span data-ttu-id="4bfa9-129">Versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-129">Version of the package.</span></span> <span data-ttu-id="4bfa9-130">Vedere [Controllo delle versioni dei pacchetti NuGet](https://docs.microsoft.com/nuget/reference/package-versioning).</span><span class="sxs-lookup"><span data-stu-id="4bfa9-130">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="4bfa9-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="4bfa9-131">Examples</span></span>

- <span data-ttu-id="4bfa9-132">Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-132">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- <span data-ttu-id="4bfa9-133">Aggiungere una versione specifica di un pacchetto in un progetto:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-133">Add a specific version of a package to a project:</span></span>

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- <span data-ttu-id="4bfa9-134">Aggiungere un pacchetto usando un'origine NuGet specifica:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-134">Add a package using a specific NuGet source:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="4bfa9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bfa9-135">See also</span></span>

- [<span data-ttu-id="4bfa9-136">Gestione delle cartelle dei pacchetti globale, della cache e temporanea in NuGet</span><span class="sxs-lookup"><span data-stu-id="4bfa9-136">Managing the global packages, cache, and temp folders in NuGet</span></span>](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="4bfa9-137">Controllo delle versioni dei pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="4bfa9-137">NuGet package versioning</span></span>](https://docs.microsoft.com/nuget/reference/package-versioning)
