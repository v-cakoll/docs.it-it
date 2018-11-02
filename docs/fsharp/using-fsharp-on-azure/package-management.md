---
title: Usare Gestione pacchetti con F# per Azure
description: Usare Paket o Nuget per gestire F# dipendenze di Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566971"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="11aab-103">Gestione dei pacchetti per le dipendenze F# di Azure</span><span class="sxs-lookup"><span data-stu-id="11aab-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="11aab-104">Acquisizione di pacchetti per lo sviluppo di Azure è semplice quando si utilizza una gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="11aab-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="11aab-105">Esistono due opzioni [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="11aab-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="11aab-106">Usando Paket</span><span class="sxs-lookup"><span data-stu-id="11aab-106">Using Paket</span></span>

<span data-ttu-id="11aab-107">Se si usa [Paket](https://fsprojects.github.io/Paket/) il gestore delle dipendenze, è possibile usare il `paket.exe` dello strumento per aggiungere dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="11aab-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="11aab-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11aab-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="11aab-109">Oppure, se si usa [Mono](https://www.mono-project.com/) per sviluppo multipiattaforma con .NET:</span><span class="sxs-lookup"><span data-stu-id="11aab-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="11aab-110">Verrà aggiunto `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente, modificare il `paket.dependencies` file e scaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="11aab-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="11aab-111">Se si sono state impostate precedentemente le dipendenze, o si lavora con un progetto in cui le dipendenze sono state impostate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:</span><span class="sxs-lookup"><span data-stu-id="11aab-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="11aab-112">Oppure, per lo sviluppo di Mono:</span><span class="sxs-lookup"><span data-stu-id="11aab-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="11aab-113">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="11aab-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="11aab-114">Oppure, per lo sviluppo di Mono:</span><span class="sxs-lookup"><span data-stu-id="11aab-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="11aab-115">Uso di Nuget</span><span class="sxs-lookup"><span data-stu-id="11aab-115">Using Nuget</span></span>

<span data-ttu-id="11aab-116">Se si usa [NuGet](https://www.nuget.org/) il gestore delle dipendenze, è possibile usare il `nuget.exe` dello strumento per aggiungere dipendenze di Azure.</span><span class="sxs-lookup"><span data-stu-id="11aab-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="11aab-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11aab-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="11aab-118">Oppure, per lo sviluppo di Mono:</span><span class="sxs-lookup"><span data-stu-id="11aab-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="11aab-119">Consente di aggiungere `WindowsAzure.Storage` nel set di dipendenze di pacchetto per il progetto nella directory corrente e scaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="11aab-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="11aab-120">Se si sono state impostate precedentemente le dipendenze, o si lavora con un progetto in cui le dipendenze sono state impostate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:</span><span class="sxs-lookup"><span data-stu-id="11aab-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="11aab-121">Oppure, per lo sviluppo di Mono:</span><span class="sxs-lookup"><span data-stu-id="11aab-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="11aab-122">È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="11aab-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="11aab-123">Oppure, per lo sviluppo di Mono:</span><span class="sxs-lookup"><span data-stu-id="11aab-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="11aab-124">Assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="11aab-124">Referencing Assemblies</span></span>

<span data-ttu-id="11aab-125">Per usare i pacchetti in di F# script, è necessario fare riferimento l'assembly inclusi nei pacchetti usando una `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="11aab-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="11aab-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11aab-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="11aab-127">Come può notare, è necessario specificare il percorso relativo per la DLL e il nome completo della DLL, che potrebbe non essere esattamente lo stesso come il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="11aab-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="11aab-128">Il percorso include una versione di framework e possibilmente un numero di versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="11aab-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="11aab-129">Per trovare tutti gli assembly installati, è possibile usare codice simile al seguente in una riga di comando di Windows:</span><span class="sxs-lookup"><span data-stu-id="11aab-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="11aab-130">In alternativa, in una shell Unix, simile a questo:</span><span class="sxs-lookup"><span data-stu-id="11aab-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="11aab-131">Questo fornirà i percorsi agli assembly installato.</span><span class="sxs-lookup"><span data-stu-id="11aab-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="11aab-132">Da qui, è possibile selezionare il percorso corretto per la versione di framework.</span><span class="sxs-lookup"><span data-stu-id="11aab-132">From there, you can select the correct path for your framework version.</span></span>
