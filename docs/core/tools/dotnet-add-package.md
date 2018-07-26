---
title: Comando dotnet add package - Interfaccia della riga di comando di .NET Core
description: Il comando 'dotnet add package' offre un'opzione utile per aggiungere un riferimento al pacchetto NuGet in un progetto.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 31dda9dbb101238b3a33d8b0d9a17765744480e0
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244393"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="4d614-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4d614-103">dotnet add package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4d614-104">nome</span><span class="sxs-lookup"><span data-stu-id="4d614-104">Name</span></span>

<span data-ttu-id="4d614-105">`dotnet add package`: aggiunge il riferimento al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d614-105">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4d614-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4d614-106">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="4d614-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d614-107">Description</span></span>

<span data-ttu-id="4d614-108">Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d614-108">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="4d614-109">Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto.</span><span class="sxs-lookup"><span data-stu-id="4d614-109">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="4d614-110">Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="4d614-110">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="4d614-111">Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4d614-111">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="4d614-112">Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4d614-112">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="4d614-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4d614-113">Arguments</span></span>

`PROJECT`

<span data-ttu-id="4d614-114">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d614-114">Specifies the project file.</span></span> <span data-ttu-id="4d614-115">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4d614-115">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="4d614-116">Riferimento al pacchetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="4d614-116">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="4d614-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4d614-117">Options</span></span>

`-h|--help`

<span data-ttu-id="4d614-118">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4d614-118">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4d614-119">Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="4d614-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

`-n|--no-restore`

<span data-ttu-id="4d614-120">Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="4d614-120">Adds a package reference without performing a restore preview and compatibility check.</span></span>

`--package-directory <PACKAGE_DIRECTORY>`

<span data-ttu-id="4d614-121">Ripristina il pacchetto nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="4d614-121">Restores the package to the specified directory.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="4d614-122">Usa un'origine di pacchetto NuGet specifica durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="4d614-122">Uses a specific NuGet package source during the restore operation.</span></span>

`-v|--version <VERSION>`

<span data-ttu-id="4d614-123">Versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4d614-123">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="4d614-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="4d614-124">Examples</span></span>

<span data-ttu-id="4d614-125">Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:</span><span class="sxs-lookup"><span data-stu-id="4d614-125">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

`dotnet add package Newtonsoft.Json`

<span data-ttu-id="4d614-126">Aggiungere una versione specifica di un pacchetto in un progetto:</span><span class="sxs-lookup"><span data-stu-id="4d614-126">Add a specific version of a package to a project:</span></span>

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

<span data-ttu-id="4d614-127">Aggiungere un pacchetto usando un'origine NuGet specifica:</span><span class="sxs-lookup"><span data-stu-id="4d614-127">Add a package using a specific NuGet source:</span></span>

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
