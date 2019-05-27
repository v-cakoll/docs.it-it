---
title: Comando dotnet add package
description: Il comando 'dotnet add package' offre un'opzione utile per aggiungere un riferimento al pacchetto NuGet in un progetto.
ms.date: 04/24/2019
ms.openlocfilehash: 07cb6cd8e7873def6f969a54c1f7b9a7325f9491
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632275"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="24865-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="24865-103">dotnet add package</span></span>

<span data-ttu-id="24865-104">**Questo articolo si applica a: ✓** .NET Core 1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="24865-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="24865-105">nome</span><span class="sxs-lookup"><span data-stu-id="24865-105">Name</span></span>

<span data-ttu-id="24865-106">`dotnet add package`: aggiunge il riferimento al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="24865-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="24865-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="24865-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="24865-108">Description</span><span class="sxs-lookup"><span data-stu-id="24865-108">Description</span></span>

<span data-ttu-id="24865-109">Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="24865-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="24865-110">Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto.</span><span class="sxs-lookup"><span data-stu-id="24865-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="24865-111">Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="24865-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="24865-112">Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="24865-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
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

<span data-ttu-id="24865-113">Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="24865-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="24865-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="24865-114">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="24865-115">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="24865-115">Specifies the project file.</span></span> <span data-ttu-id="24865-116">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24865-116">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="24865-117">Riferimento al pacchetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="24865-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="24865-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="24865-118">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="24865-119">Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="24865-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="24865-120">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="24865-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="24865-121">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="24865-121">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="24865-122">Disponibile a partire da .NET Core 2.1 SDK, versione 2.1.400 o successiva.</span><span class="sxs-lookup"><span data-stu-id="24865-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="24865-123">Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="24865-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="24865-124">La directory in cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="24865-124">The directory where to restore the packages.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="24865-125">L'origine del pacchetto NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="24865-125">The NuGet package source to use during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="24865-126">Versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="24865-126">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="24865-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="24865-127">Examples</span></span>

* <span data-ttu-id="24865-128">Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:</span><span class="sxs-lookup"><span data-stu-id="24865-128">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="24865-129">Aggiungere una versione specifica di un pacchetto in un progetto:</span><span class="sxs-lookup"><span data-stu-id="24865-129">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="24865-130">Aggiungere un pacchetto usando un'origine NuGet specifica:</span><span class="sxs-lookup"><span data-stu-id="24865-130">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```
