---
title: Creazione di un pacchetto NuGet con strumenti multipiattaforma
description: Informazioni su come creare un pacchetto NuGet con il comando 'dotnet pack'.
keywords: .NET, .NET Core, NuGet
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2f0415c1-110b-433d-87c1-ae3d543a8844
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e5c762de0a14407c92c9752edc9619caa07d500
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="0dc36-104">Come creare un pacchetto NuGet con strumenti multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="0dc36-104">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="0dc36-105">Di seguito sono riportati esempi dalla riga di comando che usano Unix.</span><span class="sxs-lookup"><span data-stu-id="0dc36-105">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="0dc36-106">Il comando `dotnet pack` funziona allo stesso modo in Windows, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0dc36-106">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="0dc36-107">Per .NET Core 1.0, le librerie devono essere distribuite come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="0dc36-107">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="0dc36-108">È infatti in questo modo che tutte le librerie .NET Standard vengono distribuite e utilizzate.</span><span class="sxs-lookup"><span data-stu-id="0dc36-108">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="0dc36-109">La modalità più semplice per eseguire tale distribuzione è l'uso del comando `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="0dc36-109">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="0dc36-110">Si supponga di aver scritto una nuova libreria da distribuire tramite NuGet.</span><span class="sxs-lookup"><span data-stu-id="0dc36-110">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="0dc36-111">A questo scopo, è possibile creare un pacchetto NuGet con strumenti multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="0dc36-111">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="0dc36-112">L'esempio seguente presuppone l'esistenza di una libreria denominata **SuperAwesomeLibrary** che punta a `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="0dc36-112">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="0dc36-113">Se si dispone di dipendenze transitive (ossia un progetto che dipende da un altro progetto), è necessario assicurarsi di ripristinare i pacchetti per l'intera soluzione con il comando `dotnet restore` prima di creare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="0dc36-113">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="0dc36-114">In caso contrario, il comando `dotnet pack` non funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="0dc36-114">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

<span data-ttu-id="0dc36-115">Dopo aver verificato che i pacchetti siano stati ripristinati, è possibile passare alla directory in cui si trova una libreria:</span><span class="sxs-lookup"><span data-stu-id="0dc36-115">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="0dc36-116">Quindi è sufficiente eseguire un singolo comando dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="0dc36-116">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="0dc36-117">La cartella `/bin/Debug` avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0dc36-117">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="0dc36-118">Si noti che in questo modo verrà generato un pacchetto di cui può essere eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="0dc36-118">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="0dc36-119">Se si vuole creare un pacchetto NuGet con i file binari della versione, è sufficiente aggiungere l'opzione `-c`/`--configuration` e usare `release` come argomento.</span><span class="sxs-lookup"><span data-stu-id="0dc36-119">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="0dc36-120">La cartella `/bin` avrà una cartella `release` contenente il pacchetto NuGet con i file binari della versione:</span><span class="sxs-lookup"><span data-stu-id="0dc36-120">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="0dc36-121">Sono ora disponibili i file necessari per pubblicare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="0dc36-121">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="0dc36-122">Non confondere `dotnet pack` con `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="0dc36-122">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="0dc36-123">È importante notare che il comando `dotnet publish` non viene affatto coinvolto.</span><span class="sxs-lookup"><span data-stu-id="0dc36-123">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="0dc36-124">Il comando `dotnet publish` viene usato per la distribuzione di applicazioni con tutte le relative dipendenze nello stesso bundle, non per la generazione di un pacchetto NuGet per la distribuzione e l'uso mediante NuGet.</span><span class="sxs-lookup"><span data-stu-id="0dc36-124">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

