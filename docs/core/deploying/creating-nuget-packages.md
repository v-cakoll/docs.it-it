---
title: Creare un pacchetto NuGet con interfaccia della riga di comando di .NET Core
description: Informazioni su come creare un pacchetto NuGet con il comando 'dotnet pack'.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 4927e3796be42d70d25a1947d4519312aef7e289
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343609"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a><span data-ttu-id="a7cbd-103">Come creare un pacchetto NuGet con gli strumenti dell'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a7cbd-103">How to create a NuGet package with .NET Core command-line interface (CLI) tools</span></span>

> [!NOTE]
> <span data-ttu-id="a7cbd-104">Di seguito sono riportati esempi dalla riga di comando che usano Unix.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="a7cbd-105">Il comando `dotnet pack` funziona allo stesso modo in Windows, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="a7cbd-106">Le librerie .NET Standard e .NET Core devono essere distribuite come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="a7cbd-107">È infatti in questo modo che tutte le librerie .NET Standard vengono distribuite e utilizzate.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="a7cbd-108">La modalità più semplice per eseguire tale distribuzione è l'uso del comando `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="a7cbd-109">Si supponga di aver scritto una nuova libreria da distribuire tramite NuGet.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="a7cbd-110">A questo scopo, è possibile creare un pacchetto NuGet con strumenti multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span> <span data-ttu-id="a7cbd-111">L'esempio seguente presuppone l'esistenza di una libreria denominata **SuperAwesomeLibrary** che punta a `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="a7cbd-112">In caso di dipendenze transitive, ovvero un progetto che dipende da un altro pacchetto, è necessario assicurarsi di ripristinare i pacchetti per l'intera soluzione con il comando `dotnet restore` prima di creare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-112">If you have transitive dependencies; that is, a project which depends on another package, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span> <span data-ttu-id="a7cbd-113">In caso contrario, il comando `dotnet pack` non funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="a7cbd-114">Dopo aver verificato che i pacchetti siano stati ripristinati, è possibile passare alla directory in cui si trova una libreria:</span><span class="sxs-lookup"><span data-stu-id="a7cbd-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="a7cbd-115">Quindi è sufficiente eseguire un singolo comando dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="a7cbd-115">Then it's just a single command from the command line:</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="a7cbd-116">La cartella */bin/debug verranno incluse* sarà ora simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a7cbd-116">Your */bin/Debug* folder will now look like this:</span></span>

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a7cbd-117">Si noti che in questo modo verrà generato un pacchetto di cui può essere eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-117">Note that this will produce a package which is capable of being debugged.</span></span> <span data-ttu-id="a7cbd-118">Se si vuole creare un pacchetto NuGet con i file binari della versione, è sufficiente aggiungere l'opzione `--configuration` (o `-c`) e usare `release` come argomento.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```dotnetcli
dotnet pack --configuration release
```

<span data-ttu-id="a7cbd-119">La cartella */bin* includerà ora una cartella della *versione* contenente il pacchetto NuGet con i file binari della versione:</span><span class="sxs-lookup"><span data-stu-id="a7cbd-119">Your */bin* folder will now have a *release* folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a7cbd-120">Sono ora disponibili i file necessari per pubblicare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="a7cbd-121">Non confondere `dotnet pack` con `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="a7cbd-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="a7cbd-122">È importante notare che il comando `dotnet publish` non viene affatto coinvolto.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="a7cbd-123">Il comando `dotnet publish` viene usato per la distribuzione di applicazioni con tutte le relative dipendenze nello stesso bundle, non per la generazione di un pacchetto NuGet per la distribuzione e l'uso mediante NuGet.</span><span class="sxs-lookup"><span data-stu-id="a7cbd-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7cbd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7cbd-124">See also</span></span>

- [<span data-ttu-id="a7cbd-125">Avvio rapido: Creare e pubblicare un pacchetto</span><span class="sxs-lookup"><span data-stu-id="a7cbd-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
