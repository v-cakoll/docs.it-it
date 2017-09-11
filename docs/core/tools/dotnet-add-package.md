---
title: Comando dotnet-add package - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-add package offre un'opzione utile per aggiungere il riferimento al pacchetto NuGet in un progetto.
keywords: dotnet-add, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40ee7cac969d4752ede66ba8df6ff6cb3f439aec
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-package"></a><span data-ttu-id="b777b-104">dotnet-add package</span><span class="sxs-lookup"><span data-stu-id="b777b-104">dotnet-add package</span></span>

## <a name="name"></a><span data-ttu-id="b777b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="b777b-105">Name</span></span>

<span data-ttu-id="b777b-106">`dotnet-add package`: aggiunge il riferimento al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b777b-106">`dotnet-add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b777b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b777b-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a><span data-ttu-id="b777b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b777b-108">Description</span></span>

<span data-ttu-id="b777b-109">Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b777b-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="b777b-110">Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto.</span><span class="sxs-lookup"><span data-stu-id="b777b-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="b777b-111">Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="b777b-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="b777b-112">Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b777b-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following:</span></span>

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

<span data-ttu-id="b777b-113">Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="b777b-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="b777b-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b777b-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b777b-115">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b777b-115">Specifies the project file.</span></span> <span data-ttu-id="b777b-116">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b777b-116">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="b777b-117">Riferimento al pacchetto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b777b-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="b777b-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b777b-118">Options</span></span>

`-h|--help`

<span data-ttu-id="b777b-119">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b777b-119">Prints out a short help for the command.</span></span>

`-v|--version <VERSION>`

<span data-ttu-id="b777b-120">Versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b777b-120">Version of the package.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b777b-121">Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="b777b-121">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

`-n|--no-restore`

<span data-ttu-id="b777b-122">Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="b777b-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="b777b-123">Usa un'origine di pacchetto NuGet specifica durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="b777b-123">Uses a specific NuGet package source during the restore operation.</span></span>

`--package-directory <PACKAGE_DIRECTORY>`

<span data-ttu-id="b777b-124">Ripristina il pacchetto nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="b777b-124">Restores the package to the specified directory.</span></span>

## <a name="examples"></a><span data-ttu-id="b777b-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="b777b-125">Examples</span></span>

<span data-ttu-id="b777b-126">Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:</span><span class="sxs-lookup"><span data-stu-id="b777b-126">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

`dotnet add package Newtonsoft.Json`

<span data-ttu-id="b777b-127">Aggiungere una versione specifica di un pacchetto in un progetto:</span><span class="sxs-lookup"><span data-stu-id="b777b-127">Add a specific version of a package to a project:</span></span>

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

<span data-ttu-id="b777b-128">Aggiungere un pacchetto usando un'origine NuGet specifica:</span><span class="sxs-lookup"><span data-stu-id="b777b-128">Add a package using a specific NuGet source:</span></span>

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

