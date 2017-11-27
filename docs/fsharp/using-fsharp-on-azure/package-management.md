---
title: 'Utilizzo di gestione dei pacchetti con F # per Azure'
description: 'Utilizzare Paket o Nuget per gestire le dipendenze di Azure di F #'
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="04684-104">Gestione dei pacchetti per le dipendenze F# di Azure</span><span class="sxs-lookup"><span data-stu-id="04684-104">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="04684-105">Acquisizione di pacchetti per lo sviluppo di Azure è semplice quando si utilizza una gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="04684-105">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="04684-106">Esistono due opzioni [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="04684-106">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="04684-107">Utilizzando Paket</span><span class="sxs-lookup"><span data-stu-id="04684-107">Using Paket</span></span>

<span data-ttu-id="04684-108">Se si utilizza [Paket](https://fsprojects.github.io/Paket/) come la gestione delle dipendenze, è possibile utilizzare il `paket.exe` strumento per aggiungere dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="04684-108">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="04684-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="04684-109">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="04684-110">Oppure, se si utilizza [Mono](http://www.mono-project.com/) per lo sviluppo multipiattaforma con .NET:</span><span class="sxs-lookup"><span data-stu-id="04684-110">Or, if you're using [Mono](http://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="04684-111">Verrà aggiunta `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente, modificare il `paket.dependencies` file e scaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04684-111">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="04684-112">Se si hanno impostato le dipendenze in precedenza o si lavora con un progetto in cui sono state impostate dipendenze da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="04684-112">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="04684-113">Oppure, per lo sviluppo Mono:</span><span class="sxs-lookup"><span data-stu-id="04684-113">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="04684-114">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="04684-114">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="04684-115">Oppure, per lo sviluppo Mono:</span><span class="sxs-lookup"><span data-stu-id="04684-115">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="04684-116">Uso di Nuget</span><span class="sxs-lookup"><span data-stu-id="04684-116">Using Nuget</span></span>

<span data-ttu-id="04684-117">Se si utilizza [NuGet](https://www.nuget.org/) come la gestione delle dipendenze, è possibile utilizzare il `nuget.exe` strumento per aggiungere dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="04684-117">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="04684-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="04684-118">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="04684-119">Oppure, per lo sviluppo Mono:</span><span class="sxs-lookup"><span data-stu-id="04684-119">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="04684-120">Verrà aggiunta `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente e il download del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04684-120">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="04684-121">Se si hanno impostato le dipendenze in precedenza o si lavora con un progetto in cui sono state impostate dipendenze da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="04684-121">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="04684-122">Oppure, per lo sviluppo Mono:</span><span class="sxs-lookup"><span data-stu-id="04684-122">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="04684-123">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="04684-123">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="04684-124">Oppure, per lo sviluppo Mono:</span><span class="sxs-lookup"><span data-stu-id="04684-124">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="04684-125">Assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="04684-125">Referencing Assemblies</span></span>

<span data-ttu-id="04684-126">Per utilizzare i pacchetti nello script F #, è necessario fare riferimento gli assembly inclusi nei pacchetti utilizzando un `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="04684-126">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="04684-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="04684-127">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="04684-128">Come si può notare, è necessario specificare il percorso relativo per la DLL e il nome completo della DLL, che potrebbe non essere esattamente lo stesso come il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04684-128">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="04684-129">Il percorso include una versione di framework ed eventualmente un numero di versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04684-129">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="04684-130">Per trovare tutti gli assembly installati, è possibile utilizzare codice simile al seguente su una riga di comando di Windows:</span><span class="sxs-lookup"><span data-stu-id="04684-130">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="04684-131">O in una shell Unix, simile a questo:</span><span class="sxs-lookup"><span data-stu-id="04684-131">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="04684-132">Questa query fornirà i percorsi per gli assembly installati.</span><span class="sxs-lookup"><span data-stu-id="04684-132">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="04684-133">Da qui, è possibile selezionare il percorso corretto per la versione di framework.</span><span class="sxs-lookup"><span data-stu-id="04684-133">From there, you can select the correct path for your framework version.</span></span>
