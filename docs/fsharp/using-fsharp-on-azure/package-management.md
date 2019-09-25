---
title: Uso di Gestione pacchetti F# con per Azure
description: Usare Paket o NuGet per gestire F# le dipendenze di Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 4aa32ace91f30d0e43b9c40067f5f0f456cc4069
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214221"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="96086-103">Gestione dei pacchetti per le dipendenze F# di Azure</span><span class="sxs-lookup"><span data-stu-id="96086-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="96086-104">Il recupero di pacchetti per lo sviluppo in Azure è semplice quando si usa una gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="96086-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="96086-105">Le due opzioni sono [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="96086-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="96086-106">Uso di Paket</span><span class="sxs-lookup"><span data-stu-id="96086-106">Using Paket</span></span>

<span data-ttu-id="96086-107">Se si usa il [pacchetto](https://fsprojects.github.io/Paket/) di gestione delle dipendenze, è possibile usare lo `paket.exe` strumento per aggiungere le dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="96086-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="96086-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96086-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="96086-109">In alternativa, se si usa [mono](https://www.mono-project.com/) per lo sviluppo .NET multipiattaforma:</span><span class="sxs-lookup"><span data-stu-id="96086-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="96086-110">Questa operazione verrà `WindowsAzure.Storage` aggiunta al set di dipendenze del pacchetto per il progetto nella directory corrente, modificare `paket.dependencies` il file e scaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="96086-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="96086-111">Se in precedenza sono state impostate dipendenze o si sta lavorando a un progetto in cui le dipendenze sono state configurate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:</span><span class="sxs-lookup"><span data-stu-id="96086-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="96086-112">Oppure, per lo sviluppo mono:</span><span class="sxs-lookup"><span data-stu-id="96086-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="96086-113">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente come la seguente:</span><span class="sxs-lookup"><span data-stu-id="96086-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="96086-114">Oppure, per lo sviluppo mono:</span><span class="sxs-lookup"><span data-stu-id="96086-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="96086-115">Uso di NuGet</span><span class="sxs-lookup"><span data-stu-id="96086-115">Using Nuget</span></span>

<span data-ttu-id="96086-116">Se si usa [NuGet](https://www.nuget.org/) come gestore delle dipendenze, è possibile usare lo `nuget.exe` strumento per aggiungere le dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="96086-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="96086-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96086-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="96086-118">Oppure, per lo sviluppo mono:</span><span class="sxs-lookup"><span data-stu-id="96086-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="96086-119">Questa operazione verrà `WindowsAzure.Storage` aggiunta al set di dipendenze del pacchetto per il progetto nella directory corrente e scaricherà il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="96086-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="96086-120">Se in precedenza sono state impostate dipendenze o si sta lavorando a un progetto in cui le dipendenze sono state configurate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:</span><span class="sxs-lookup"><span data-stu-id="96086-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="96086-121">Oppure, per lo sviluppo mono:</span><span class="sxs-lookup"><span data-stu-id="96086-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="96086-122">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente come la seguente:</span><span class="sxs-lookup"><span data-stu-id="96086-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="96086-123">Oppure, per lo sviluppo mono:</span><span class="sxs-lookup"><span data-stu-id="96086-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="96086-124">Assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="96086-124">Referencing Assemblies</span></span>

<span data-ttu-id="96086-125">Per utilizzare i pacchetti nello F# script, è necessario fare riferimento agli assembly inclusi nei pacchetti utilizzando una `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="96086-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="96086-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96086-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="96086-127">Come si può notare, è necessario specificare il percorso relativo della DLL e il nome completo della DLL, che potrebbe non corrispondere esattamente al nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="96086-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="96086-128">Il percorso includerà una versione del Framework ed eventualmente un numero di versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="96086-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="96086-129">Per trovare tutti gli assembly installati, è possibile usare un elemento simile al seguente in una riga di comando di Windows:</span><span class="sxs-lookup"><span data-stu-id="96086-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="96086-130">O in una shell UNIX, simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="96086-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="96086-131">In questo modo si otterranno i percorsi degli assembly installati.</span><span class="sxs-lookup"><span data-stu-id="96086-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="96086-132">Da qui è possibile selezionare il percorso corretto per la versione del Framework.</span><span class="sxs-lookup"><span data-stu-id="96086-132">From there, you can select the correct path for your framework version.</span></span>
