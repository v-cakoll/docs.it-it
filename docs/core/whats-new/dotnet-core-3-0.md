---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 09/05/2019
ms.openlocfilehash: 2d18e7750e0c2e2a44028d1e906a8536e47d979d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394290"
---
# <a name="whats-new-in-net-core-30-preview-9"></a><span data-ttu-id="36f76-103">Novità di .NET Core 3,0 (anteprima 9)</span><span class="sxs-lookup"><span data-stu-id="36f76-103">What's new in .NET Core 3.0 (Preview 9)</span></span>

<span data-ttu-id="36f76-104">Questo articolo descrive le novità di .NET Core 3,0 (tramite l'anteprima 9).</span><span class="sxs-lookup"><span data-stu-id="36f76-104">This article describes what is new in .NET Core 3.0 (through preview 9).</span></span> <span data-ttu-id="36f76-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="36f76-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="36f76-106">Con il componente Windows Desktop di .NET Core 3.0 SDK, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="36f76-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="36f76-107">Il componente Windows Desktop è dunque supportato e incluso solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="36f76-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="36f76-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="36f76-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="36f76-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="36f76-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="36f76-110">È consigliabile usare [Visual Studio 2019 16,3 Preview 3](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), [Visual Studio per Mac 8,3](https://docs.microsoft.com/visualstudio/mac/install-preview?view=vsmac-2019)o [Visual Studio Code](https://code.visualstudio.com/) con l'  **C# estensione**.</span><span class="sxs-lookup"><span data-stu-id="36f76-110">It's highly recommended that you use [Visual Studio 2019 16.3 Preview 3](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), [Visual Studio for Mac 8.3](https://docs.microsoft.com/visualstudio/mac/install-preview?view=vsmac-2019), or [Visual Studio Code](https://code.visualstudio.com/) with the **C# extension**.</span></span>

<span data-ttu-id="36f76-111">[Scarica e inizia subito a usare .NET Core 3,0 Preview 9](https://aka.ms/netcore3download) in Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="36f76-111">[Download and get started with .NET Core 3.0 preview 9](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="36f76-112">Per altre informazioni su ogni versione di anteprima, vedere gli annunci seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="36f76-113">Annuncio di .NET Core 3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="36f76-113">.NET Core 3.0 Preview 9 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-9/)
- [<span data-ttu-id="36f76-114">Annuncio di .NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="36f76-114">.NET Core 3.0 Preview 8 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)
- [<span data-ttu-id="36f76-115">Annuncio di .NET Core 3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="36f76-115">.NET Core 3.0 Preview 7 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)
- [<span data-ttu-id="36f76-116">Annuncio di .NET Core 3.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="36f76-116">.NET Core 3.0 Preview 6 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-6/)
- [<span data-ttu-id="36f76-117">Annuncio di .NET Core 3.0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="36f76-117">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="36f76-118">Annuncio di .NET Core 3.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="36f76-118">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="36f76-119">Annuncio di .NET Core 3.0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="36f76-119">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="36f76-120">Annuncio di .NET Core 3.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="36f76-120">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="36f76-121">Annuncio di .NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="36f76-121">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="production-supported-preview"></a><span data-ttu-id="36f76-122">Anteprima di produzione supportata</span><span class="sxs-lookup"><span data-stu-id="36f76-122">Production supported preview</span></span>

<span data-ttu-id="36f76-123">.NET Core Preview 9 è considerato pronto per la produzione da Microsoft ed è completamente supportato.</span><span class="sxs-lookup"><span data-stu-id="36f76-123">.NET Core Preview 9 is considered production ready by Microsoft and is fully supported.</span></span> <span data-ttu-id="36f76-124">A partire dalla versione Preview 7, le nuove versioni si incentreranno sul perfezionamento di .NET Core 3.0 invece di aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="36f76-124">Starting with preview 7, releases will focus on polishing .NET Core 3.0 instead of adding new features.</span></span> <span data-ttu-id="36f76-125">Per ulteriori informazioni sulle modifiche apportate nella versione Preview 9, vedere l' [annuncio dell'anteprima 9](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-9/).</span><span class="sxs-lookup"><span data-stu-id="36f76-125">For more information about what has changed in preview 9, see the [preview 9 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-9/).</span></span>

<span data-ttu-id="36f76-126">Se si usa una versione di anteprima precedente, è necessario passare all'anteprima 9 per il supporto continuo "Go Live".</span><span class="sxs-lookup"><span data-stu-id="36f76-126">If you're using a previous preview release, you must move to Preview 9 for continued "Go Live" support.</span></span>

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="36f76-127">Programma di installazione .NET Core SDK per Windows</span><span class="sxs-lookup"><span data-stu-id="36f76-127">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="36f76-128">Il programma di installazione di Windows Installer (MSI) per Windows è stato modificato a partire da .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="36f76-128">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="36f76-129">I programmi di installazione di SDK aggiorneranno ora le versioni della banda di funzionalità sul posto.</span><span class="sxs-lookup"><span data-stu-id="36f76-129">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="36f76-130">Le bande di funzionalità vengono definite nei gruppi *centinaia* nella sezione *patch* del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="36f76-130">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="36f76-131">Ad esempio, **3.0._101_** e **3.0._201_** sono versioni in due diverse bande di funzionalità, mentre **3.0._101_** e **3.0._199_** appartengono alla stessa banda.</span><span class="sxs-lookup"><span data-stu-id="36f76-131">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="36f76-132">Quindi, quando viene installato .NET Core SDK **3.0._101_** , .NET Core SDK **3.0._100_** verrà rimosso dal computer se è esistente.</span><span class="sxs-lookup"><span data-stu-id="36f76-132">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="36f76-133">Quando viene installato .NET Core SDK **3.0._200_** nello stesso computer, .NET Core SDK **3.0._101_** non verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="36f76-133">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="36f76-134">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-134">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="36f76-135">Anteprima di C# 8.0</span><span class="sxs-lookup"><span data-stu-id="36f76-135">C# 8.0 preview</span></span>

<span data-ttu-id="36f76-136">.NET core 3.0 supporta l'anteprima di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="36f76-136">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="36f76-137">Per altre informazioni sulle funzionalità di C# 8.0, vedere [Novità di C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-137">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="36f76-138">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="36f76-138">.NET Standard 2.1</span></span>

<span data-ttu-id="36f76-139">Anche se .NET Core 3.0 supporta **.NET Standard 2.1**, il modello `dotnet new classlib` predefinito genera un progetto per **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="36f76-139">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="36f76-140">Per destinarlo a **.NET Standard 2.1**, modificare il file di progetto e la proprietà `TargetFramework` in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="36f76-140">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="36f76-141">Se si usa Visual Studio, è necessario [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) perché Visual Studio 2017 non supporta **.NET Standard 2.1** o **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="36f76-141">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="36f76-142">Miglioramento delle API della versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="36f76-142">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="36f76-143">A partire da .NET Core 3.0, le API della versione di .NET Core restituiscono le informazioni previste.</span><span class="sxs-lookup"><span data-stu-id="36f76-143">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="36f76-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="36f76-144">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="36f76-145">Modifica importante:</span><span class="sxs-lookup"><span data-stu-id="36f76-145">Breaking change.</span></span> <span data-ttu-id="36f76-146">si tratta di una modifica tecnicamente importante perché è cambiato lo schema di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="36f76-146">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="36f76-147">Intrinseci dipendenti dalla piattaforma .NET</span><span class="sxs-lookup"><span data-stu-id="36f76-147">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="36f76-148">Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**.</span><span class="sxs-lookup"><span data-stu-id="36f76-148">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="36f76-149">Queste istruzioni consentono di ottenere miglioramenti delle prestazioni significativi in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36f76-149">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="36f76-150">Ove appropriato, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="36f76-150">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="36f76-151">Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET).</span><span class="sxs-lookup"><span data-stu-id="36f76-151">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="36f76-152">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="36f76-152">Default executables</span></span>

<span data-ttu-id="36f76-153">Per impostazione predefinita .NET Core ora compila [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="36f76-153">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="36f76-154">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="36f76-154">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="36f76-155">In precedenza solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) generavano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="36f76-155">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="36f76-156">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile che corrisponde all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="36f76-156">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="36f76-157">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="36f76-157">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="36f76-158">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="36f76-158">You can double-click on the executable.</span></span>
- <span data-ttu-id="36f76-159">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="36f76-159">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="36f76-160">File eseguibili singoli</span><span class="sxs-lookup"><span data-stu-id="36f76-160">Single-file executables</span></span>

<span data-ttu-id="36f76-161">Il comando `dotnet publish` supporta la creazione del pacchetto dell'app come file eseguibile singolo specifico per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="36f76-161">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="36f76-162">Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluse quelle native) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="36f76-162">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="36f76-163">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-163">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="36f76-164">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36f76-164">Startup is faster when the application is run again.</span></span> <span data-ttu-id="36f76-165">L'applicazione non dovrà ripetere l'estrazione una seconda volta, a meno che sia stata usata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="36f76-165">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="36f76-166">Per pubblicare un file eseguibile singolo, impostare `PublishSingleFile` nel progetto o nella riga di comando usando il comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="36f76-166">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="36f76-167">-oppure-</span><span class="sxs-lookup"><span data-stu-id="36f76-167">-or-</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="36f76-168">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-168">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="assembly-linking"></a><span data-ttu-id="36f76-169">Collegamento di assembly</span><span class="sxs-lookup"><span data-stu-id="36f76-169">Assembly linking</span></span>

<span data-ttu-id="36f76-170">.NET Core SDK 3.0 include uno strumento che consente di ridurre le dimensioni delle app analizzando il linguaggio intermedio (IL) e rimuovendo gli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="36f76-170">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="36f76-171">Le app autonome includono tutti gli elementi necessari per eseguire il codice, senza richiedere l'installazione di .NET nel computer host.</span><span class="sxs-lookup"><span data-stu-id="36f76-171">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="36f76-172">Tuttavia, per il funzionamento dell'app è spesso sufficiente un piccolo subset del framework, mentre altre librerie inutilizzate possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="36f76-172">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="36f76-173">.NET Core include ora un'impostazione che consente l'uso dello strumento [IL Linker](https://github.com/mono/linker) per analizzare il linguaggio intermedio dell'app.</span><span class="sxs-lookup"><span data-stu-id="36f76-173">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="36f76-174">Questo strumento rileva il codice necessario e rimuove le librerie inutilizzate.</span><span class="sxs-lookup"><span data-stu-id="36f76-174">this tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="36f76-175">Può quindi ridurre notevolmente le dimensioni di distribuzione di alcune app.</span><span class="sxs-lookup"><span data-stu-id="36f76-175">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="36f76-176">Per abilitare questo strumento, aggiungere l'impostazione `<PublishTrimmed>` nel progetto e pubblicare un'app autonoma:</span><span class="sxs-lookup"><span data-stu-id="36f76-176">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```console
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="36f76-177">Ad esempio, il nuovo modello predefinito per un progetto di console di base "hello world" ha una dimensione di circa 70 MB quando viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="36f76-177">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="36f76-178">Usando `<PublishTrimmed>` la dimensione viene ridotta fino a circa 30 MB.</span><span class="sxs-lookup"><span data-stu-id="36f76-178">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="36f76-179">È importante tenere presente che le applicazioni o i framework, inclusi ASP.NET Core e WPF, che usano la reflection o le funzionalità dinamiche correlate, sono spesso soggetti a interruzioni in caso di rimozione di assembly.</span><span class="sxs-lookup"><span data-stu-id="36f76-179">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="36f76-180">Le interruzioni si verificano perché il linker non riconosce questo comportamento dinamico e non è in grado di identificare i tipi di framework necessari per la reflection.</span><span class="sxs-lookup"><span data-stu-id="36f76-180">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="36f76-181">Lo strumento IL Linker può essere configurato in modo da riconoscere questo scenario.</span><span class="sxs-lookup"><span data-stu-id="36f76-181">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="36f76-182">È importante soprattutto accertarsi di testare l'app dopo la rimozione degli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="36f76-182">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="36f76-183">Per altre informazioni sullo strumento IL Linker, vedere la [documentazione](https://aka.ms/dotnet-illink) o visitare il repository [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="36f76-183">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="36f76-184">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="36f76-184">Tiered compilation</span></span>

<span data-ttu-id="36f76-185">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) è attiva.</span><span class="sxs-lookup"><span data-stu-id="36f76-185">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="36f76-186">Questa funzionalità consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="36f76-186">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="36f76-187">Il vantaggio principale della compilazione a livelli (TC) consiste nell'abilitazione di metodi di ricompilazione JIT con un livello lower-quality-but-faster (di minore qualità ma più veloce) o higher-quality-but-slower (di migliore qualità ma più lento).</span><span class="sxs-lookup"><span data-stu-id="36f76-187">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="36f76-188">In questo modo è possibile migliorare le prestazioni di un'applicazione nelle sue vari fasi di esecuzione, dall'avvio allo stato stabile.</span><span class="sxs-lookup"><span data-stu-id="36f76-188">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="36f76-189">Ciò si differenzia dall'approccio che non usa la compilazione a livelli. In questo caso ogni metodo viene compilato in un solo modo (come per il livello alta qualità), che dà priorità allo stato stabile piuttosto che alle prestazioni all'avvio.</span><span class="sxs-lookup"><span data-stu-id="36f76-189">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="36f76-190">Per abilitare la compilazione JIT rapida (codice JIT livello 0), usare questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="36f76-190">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="36f76-191">Per disabilitare completamente la compilazione a livelli, usare questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="36f76-191">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="readytorun-images"></a><span data-ttu-id="36f76-192">Immagini ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="36f76-192">ReadyToRun images</span></span>

<span data-ttu-id="36f76-193">È possibile migliorare il tempo di avvio delle applicazioni .NET Core compilando gli assembly nel formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="36f76-193">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="36f76-194">R2R è un formato di compilazione AOT (Ahead-of-time).</span><span class="sxs-lookup"><span data-stu-id="36f76-194">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="36f76-195">I file binari R2R migliorano le prestazioni di avvio riducendo la quantità di lavoro che deve eseguire il compilatore JIT (Just-in-time) durante il caricamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-195">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="36f76-196">I file binari contengono codice nativo simile a ciò che viene generato dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="36f76-196">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="36f76-197">I file binari R2R, tuttavia, sono più grandi poiché contengono sia il codice in linguaggio intermedio, che è comunque necessario per alcuni scenari, sia la versione nativa dello stesso codice.</span><span class="sxs-lookup"><span data-stu-id="36f76-197">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="36f76-198">R2R è disponibile solo quando si pubblica un'app autonoma che fa riferimento ad ambienti di runtime specifici (RID), ad esempio Linux x64 o Windows x64.</span><span class="sxs-lookup"><span data-stu-id="36f76-198">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="36f76-199">Per compilare il progetto come ReadyToRun, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="36f76-199">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="36f76-200">Aggiungere l'impostazione `<PublishReadyToRun>` al progetto.</span><span class="sxs-lookup"><span data-stu-id="36f76-200">Add the `<PublishReadyToRun>` setting to your project</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="36f76-201">Pubblicare un'app autonoma.</span><span class="sxs-lookup"><span data-stu-id="36f76-201">Publish a self-contained app.</span></span> <span data-ttu-id="36f76-202">Questo comando, ad esempio, crea un'app autonoma per la versione a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="36f76-202">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```console
    dotnet publish -c Release -r win-x64 --self-contained true
    ```

### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="36f76-203">Limitazioni per ambienti con più piattaforme o architetture</span><span class="sxs-lookup"><span data-stu-id="36f76-203">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="36f76-204">Il compilatore ReadyToRun attualmente non supporta la definizione di più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="36f76-204">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="36f76-205">La compilazione deve essere eseguita per una determinata destinazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-205">You must compile on a given target.</span></span> <span data-ttu-id="36f76-206">Se, ad esempio, si vogliono immagini R2R per Windows x64, è necessario eseguire il comando di pubblicazione in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="36f76-206">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="36f76-207">Eccezioni relative all'uso di più destinazioni:</span><span class="sxs-lookup"><span data-stu-id="36f76-207">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="36f76-208">Windows x64 può essere usato per compilare immagini Windows ARM32, ARM64 e x86.</span><span class="sxs-lookup"><span data-stu-id="36f76-208">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="36f76-209">Windows x86 può essere usato per compilare immagini Windows ARM32.</span><span class="sxs-lookup"><span data-stu-id="36f76-209">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="36f76-210">Linux x64 può essere usato per compilare immagini Linux ARM32 e ARM64.</span><span class="sxs-lookup"><span data-stu-id="36f76-210">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="36f76-211">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="36f76-211">Build copies dependencies</span></span>

<span data-ttu-id="36f76-212">Il comando `dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet nella cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-212">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="36f76-213">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="36f76-213">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="36f76-214">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-214">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="36f76-215">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="36f76-215">Local tools</span></span>

<span data-ttu-id="36f76-216">.NET core 3.0 introduce gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="36f76-216">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="36f76-217">Gli strumenti locali sono simili agli [strumenti globali](../tools/global-tools.md), ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="36f76-217">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="36f76-218">Gli strumenti locali non sono disponibili a livello globale e vengono distribuiti come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="36f76-218">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="36f76-219">Se è stata eseguita una prova degli strumenti locali in .NET Core 3.0 Preview 1, ad esempio eseguendo `dotnet tool restore` o `dotnet tool install`, eliminare la cartella della cache degli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="36f76-219">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="36f76-220">In caso contrario, gli strumenti locali non funzioneranno in una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="36f76-220">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="36f76-221">Questa cartella si trova in:</span><span class="sxs-lookup"><span data-stu-id="36f76-221">This folder is located at:</span></span>
>
> <span data-ttu-id="36f76-222">In macOS: Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="36f76-222">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="36f76-223">In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="36f76-223">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="36f76-224">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="36f76-224">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="36f76-225">Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="36f76-225">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="36f76-226">È possibile distribuire il file manifesto con il codice per assicurarsi che tutti gli utenti che usano il codice possano ripristinare e usare gli stessi strumenti.</span><span class="sxs-lookup"><span data-stu-id="36f76-226">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="36f76-227">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="36f76-227">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="36f76-228">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="36f76-228">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="36f76-229">Per installare questi strumenti a livello globale o locale, è comunque necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="36f76-229">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="36f76-230">Roll forward alla versione principale</span><span class="sxs-lookup"><span data-stu-id="36f76-230">Major-version Roll Forward</span></span>

<span data-ttu-id="36f76-231">.NET core 3.0 introduce una funzionalità con consenso esplicito che consente all'app di eseguire il roll forward alla versione principale più recente di NET Core.</span><span class="sxs-lookup"><span data-stu-id="36f76-231">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="36f76-232">È stata aggiunta anche una nuova impostazione per controllare come applicare il roll forward all'app.</span><span class="sxs-lookup"><span data-stu-id="36f76-232">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="36f76-233">Questa funzionalità può essere configurata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-233">This can be configured in the following ways:</span></span>

- <span data-ttu-id="36f76-234">Proprietà file di progetto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="36f76-234">Project file property: `RollForward`</span></span>
- <span data-ttu-id="36f76-235">Proprietà file di configurazione runtime: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="36f76-235">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="36f76-236">Variabile di ambiente: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="36f76-236">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="36f76-237">Argomento della riga di comando: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="36f76-237">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="36f76-238">È necessario specificare uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="36f76-238">One of the following values must be specified.</span></span> <span data-ttu-id="36f76-239">Se non viene impostato un valore, l'impostazione **Minor** sarà quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="36f76-239">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="36f76-240">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="36f76-240">**LatestPatch**</span></span>\
<span data-ttu-id="36f76-241">Esegue il roll forward alla versione di patch più recente.</span><span class="sxs-lookup"><span data-stu-id="36f76-241">Roll forward to the highest patch version.</span></span> <span data-ttu-id="36f76-242">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="36f76-242">This disables minor version roll forward.</span></span>
- <span data-ttu-id="36f76-243">**Minor**</span><span class="sxs-lookup"><span data-stu-id="36f76-243">**Minor**</span></span>\
<span data-ttu-id="36f76-244">Esegue il roll forward alla versione secondaria successiva minima, se la versione secondaria richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="36f76-244">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="36f76-245">Se la versione secondaria richiesta è presente, viene usato il criterio **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="36f76-245">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="36f76-246">**Major**</span><span class="sxs-lookup"><span data-stu-id="36f76-246">**Major**</span></span>\
<span data-ttu-id="36f76-247">Esegue il roll forward alla versione principale successiva minima e alla versione secondaria minima, se la versione principale richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="36f76-247">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="36f76-248">Se la versione principale richiesta è presente, viene usato il criterio **Minor**.</span><span class="sxs-lookup"><span data-stu-id="36f76-248">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="36f76-249">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="36f76-249">**LatestMinor**</span></span>\
<span data-ttu-id="36f76-250">Esegue il roll forward alla versione secondaria più recente, anche se la versione secondaria richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="36f76-250">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="36f76-251">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="36f76-251">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="36f76-252">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="36f76-252">**LatestMajor**</span></span>\
<span data-ttu-id="36f76-253">Esegue il roll forward alla versione principale e secondaria più recente, anche se la versione principale richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="36f76-253">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="36f76-254">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="36f76-254">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="36f76-255">**Disable**</span><span class="sxs-lookup"><span data-stu-id="36f76-255">**Disable**</span></span>\
<span data-ttu-id="36f76-256">Non esegue il roll forward.</span><span class="sxs-lookup"><span data-stu-id="36f76-256">Don't roll forward.</span></span> <span data-ttu-id="36f76-257">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="36f76-257">Only bind to specified version.</span></span> <span data-ttu-id="36f76-258">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="36f76-258">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="36f76-259">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="36f76-259">This value is only recommended for testing.</span></span>

<span data-ttu-id="36f76-260">Ad eccezione dell'impostazione **Disable**, tutte le impostazioni useranno la versione di patch disponibile più recente.</span><span class="sxs-lookup"><span data-stu-id="36f76-260">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="36f76-261">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="36f76-261">Windows desktop</span></span>

<span data-ttu-id="36f76-262">.NET Core 3.0 supporta applicazioni desktop di Windows che usano Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="36f76-262">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="36f76-263">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="36f76-263">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="36f76-264">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="36f76-264">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="36f76-265">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-265">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="36f76-266">Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="36f76-266">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="36f76-267">Per altre informazioni su come convertire un'applicazione .NET Framework esistente, vedere [Convertire progetti WPF](../porting/wpf.md) e [Convertire progetti Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-267">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="36f76-268">Componenti COM-Callable in Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="36f76-268">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="36f76-269">In Windows è ora possibile creare componenti gestiti COM-Callable.</span><span class="sxs-lookup"><span data-stu-id="36f76-269">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="36f76-270">Questa funzionalità è essenziale per usare .NET Core con modelli del componente aggiuntivo COM e anche per assicurare parità con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="36f76-270">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="36f76-271">A differenza di .NET Framework in cui *mscoree.dll* era usato come server COM, .NET Core aggiungerà un file dll di avvio nativo alla directory *bin* quando si compilerà il componente COM.</span><span class="sxs-lookup"><span data-stu-id="36f76-271">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="36f76-272">Per un esempio su come creare e usare un componente COM, vedere la [demo COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="36f76-272">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="36f76-273">Distribuzione MSIX in Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="36f76-273">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="36f76-274">[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="36f76-274">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="36f76-275">Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="36f76-275">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="36f76-276">Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="36f76-276">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="36f76-277">Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="36f76-277">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-high-dpi"></a><span data-ttu-id="36f76-278">Modalità con valori DPI alti per WinForms</span><span class="sxs-lookup"><span data-stu-id="36f76-278">WinForms high DPI</span></span>

<span data-ttu-id="36f76-279">Le applicazioni di Windows Forms in .NET Core possono impostare la modalità con valori DPI alti usando <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f76-279">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="36f76-280">Il metodo `SetHighDpiMode` imposta la modalità con valori DPI alti corrispondente a meno che l'impostazione sia stata configurata in altro modo, ad esempio con `App.Manifest` o P/Invoke prima di `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="36f76-280">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="36f76-281">I valori possibili per `highDpiMode`, espressi dall'enumerazione <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>, sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-281">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="36f76-282">Per altre informazioni sulle modalità con valori DPI alti, vedere [Sviluppo di applicazioni desktop con valori DPI alti in Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="36f76-282">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="36f76-283">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="36f76-283">Ranges and indices</span></span>

<span data-ttu-id="36f76-284">Il nuovo tipo <xref:System.Index?displayProperty=nameWithType> può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-284">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="36f76-285">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="36f76-285">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="36f76-286">Esiste anche il tipo <xref:System.Range?displayProperty=nameWithType>, costituito da due valori `Index`, uno per l'inizio e uno per la fine, e può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="36f76-286">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="36f76-287">È anche possibile poi indicizzare usano un oggetto `Range`, che genera una sezione:</span><span class="sxs-lookup"><span data-stu-id="36f76-287">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="36f76-288">Per altre informazioni, vedere l'[esercitazione su intervalli e indici](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-288">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

## <a name="async-streams"></a><span data-ttu-id="36f76-289">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="36f76-289">Async streams</span></span>

<span data-ttu-id="36f76-290">Il tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> è una nuova versione asincrona di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="36f76-290">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="36f76-291">Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="36f76-291">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="36f76-292">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="36f76-292">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="36f76-293">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="36f76-293">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="36f76-294">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="36f76-294">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="36f76-295">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="36f76-295">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="36f76-296">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="36f76-296">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="36f76-297">Per altre informazioni, vedere l'[esercitazione sui flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="36f76-297">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="36f76-298">Miglioramenti per le API a virgola mobile IEEE</span><span class="sxs-lookup"><span data-stu-id="36f76-298">IEEE Floating-point improvements</span></span>

<span data-ttu-id="36f76-299">È in corso l'aggiornamento di API virgola mobile per conformità alla [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="36f76-299">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="36f76-300">L'obiettivo di queste modifiche è esporre tutte le operazioni **obbligatorie** e assicurarsi che, a livello di comportamento, siano conformi alla specifica IEEE. Per altre informazioni sui miglioramenti di virgola mobile, vedere il post di blog [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) (Miglioramenti di analisi e formattazione di virgola mobile in .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="36f76-300">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="36f76-301">Di seguito sono riportate le correzioni per analisi e formattazione:</span><span class="sxs-lookup"><span data-stu-id="36f76-301">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="36f76-302">Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="36f76-302">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="36f76-303">Analisi corretta e formattazione dello zero negativo.</span><span class="sxs-lookup"><span data-stu-id="36f76-303">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="36f76-304">Analisi corretta di valori `Infinity` e `NaN` con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.</span><span class="sxs-lookup"><span data-stu-id="36f76-304">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="36f76-305">Le nuovi API <xref:System.Math?displayProperty=nameWithType> includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-305">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="36f76-306"><xref:System.Math.BitIncrement(System.Double)> e <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="36f76-306"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="36f76-307">Corrispondono alle operazioni IEEE `nextUp` e `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="36f76-307">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="36f76-308">Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="36f76-308">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="36f76-309">Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="36f76-309">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="36f76-310"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> e <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="36f76-310"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="36f76-311">Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="36f76-311">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="36f76-312">Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="36f76-312">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="36f76-313">Corrispondono all'operazione IEEE `logB` che restituisce un valore integrale, restituisce il logaritmo in base 2 integrale del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="36f76-313">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="36f76-314">Questo metodo equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="36f76-314">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="36f76-315">Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="36f76-315">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="36f76-316">Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2.</span><span class="sxs-lookup"><span data-stu-id="36f76-316">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="36f76-317">Gli errori di arrotondamento sono ridotti al minimo.</span><span class="sxs-lookup"><span data-stu-id="36f76-317">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="36f76-318">Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add).</span><span class="sxs-lookup"><span data-stu-id="36f76-318">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="36f76-319">Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="36f76-319">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="36f76-320">Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)` che restituisce `1e308`.</span><span class="sxs-lookup"><span data-stu-id="36f76-320">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="36f76-321">L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="36f76-321">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="36f76-322">Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.</span><span class="sxs-lookup"><span data-stu-id="36f76-322">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="36f76-323">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="36f76-323">Fast built-in JSON support</span></span>

<span data-ttu-id="36f76-324">Gli utenti .NET si sono ampiamente basati su [**Json.NET**](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide.</span><span class="sxs-lookup"><span data-stu-id="36f76-324">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="36f76-325">Come tipo di dati di base, **Json.NET** usa le stringhe .NET, che in realtà sono UTF-16.</span><span class="sxs-lookup"><span data-stu-id="36f76-325">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="36f76-326">Il nuovo supporto JSON predefinito offre prestazioni elevate, bassa allocazione ed è basato su `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="36f76-326">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="36f76-327">Sono stati aggiunti tre nuovi tipi correlati principali JSON a .NET Core 3.0 nello spazio dei nomi <xref:System.Text.Json?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f76-327">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="36f76-328">Questi tipi non supportano *ancora* la serializzazione e deserializzazione POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="36f76-328">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="36f76-329">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="36f76-329">Utf8JsonReader</span></span>

<span data-ttu-id="36f76-330"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="36f76-330"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="36f76-331">`Utf8JsonReader` è un tipo di base di basso livello, che può essere usato per creare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="36f76-331">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="36f76-332">La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="36f76-332">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="36f76-333">Non viene allocato fino a quando non è necessario realizzare token JSON come stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="36f76-333">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="36f76-334">Di seguito è riportato un esempio di lettura tramite il file [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creato da Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="36f76-334">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="36f76-335">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="36f76-335">Utf8JsonWriter</span></span>

<span data-ttu-id="36f76-336"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> rende disponibile un metodo ad alte prestazioni, senza memorizzazione nella cache e forward-only per la scrittura di test JSON con codifica UTF-8 da tipi .NET comuni, come `String`, `Int32` e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="36f76-336"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="36f76-337">Come il lettore, il writer è un tipo di base di basso livello, che può essere usato per creare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="36f76-337">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="36f76-338">La scrittura di un payload JSON con il nuovo `Utf8JsonWriter` offre velocità maggiori del 30-80% rispetto all'uso del writer di **Json.NET** e non prevede allocazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-338">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="36f76-339">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="36f76-339">JsonDocument</span></span>

<span data-ttu-id="36f76-340"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> è basato su `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="36f76-340"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="36f76-341">`JsonDocument` offre la possibilità di analizzare i dati JSON e compilare un modello DOM (Document Object Model) di sola lettura su cui è possibile eseguire query per supportare l'accesso casuale e l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-341">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="36f76-342">Gli elementi JSON che compongono i dati sono accessibili tramite il tipo <xref:System.Text.Json.JsonElement> che viene esposto da `JsonDocument` come una proprietà denominata `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="36f76-342">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="36f76-343">`JsonElement` contiene gli enumeratori di matrice e oggetto JSON insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="36f76-343">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="36f76-344">L'analisi di un payload JSON tipico e l'accesso a tutti i relativi membri tramite `JsonDocument` è 2/3 volte più veloce rispetto a **Json.NET** con allocazioni minime per dati di dimensioni ragionevoli, vale a dire inferiori a 1 MB.</span><span class="sxs-lookup"><span data-stu-id="36f76-344">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="36f76-345">Ecco un esempio di utilizzo di `JsonDocument` e `JsonElement` che può essere usato come punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="36f76-345">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

<span data-ttu-id="36f76-346">Di seguito è riportato un esempio di lettura di C# 8.0 tramite il file [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creato da Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="36f76-346">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="36f76-347">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="36f76-347">JsonSerializer</span></span>

<span data-ttu-id="36f76-348"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> si basa su <xref:System.Text.Json.Utf8JsonReader> e <xref:System.Text.Json.Utf8JsonWriter> per offrire un'opzione di serializzazione veloce della memoria insufficiente quando si usano documenti e frammenti JSON.</span><span class="sxs-lookup"><span data-stu-id="36f76-348"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast, low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="36f76-349">Di seguito è riportato un esempio di serializzazione di un oggetto in formato JSON:</span><span class="sxs-lookup"><span data-stu-id="36f76-349">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="36f76-350">Di seguito è riportato un esempio di deserializzazione di una stringa JSON in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="36f76-350">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="36f76-351">È possibile usare la stringa JSON generata nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="36f76-351">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="36f76-352">Miglioramenti di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="36f76-352">Interop improvements</span></span>

<span data-ttu-id="36f76-353">.NET core 3.0 migliora l'interoperabilità di API native.</span><span class="sxs-lookup"><span data-stu-id="36f76-353">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="36f76-354">Digitare:  NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="36f76-354">Type: NativeLibrary</span></span>

<span data-ttu-id="36f76-355"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> offre un incapsulamento per il caricamento di una libreria nativa (usando la stessa logica di caricamento di .NET Core P/Invoke) e offre le funzioni di supporto pertinenti, ad esempio `getSymbol`.</span><span class="sxs-lookup"><span data-stu-id="36f76-355"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="36f76-356">Per un esempio di codice, vedere la [demo DLLMap](https://github.com/dotnet/samples/tree/master/core/extensions/DllMapDemo).</span><span class="sxs-lookup"><span data-stu-id="36f76-356">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/DllMapDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="36f76-357">Interoperabilità nativa di Windows</span><span class="sxs-lookup"><span data-stu-id="36f76-357">Windows Native Interop</span></span>

<span data-ttu-id="36f76-358">Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT.</span><span class="sxs-lookup"><span data-stu-id="36f76-358">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="36f76-359">Mentre .NET Core supporta **P/Invoke**, .NET Core 3.0 aggiunge la possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="36f76-359">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="36f76-360">Per un esempio di codice, vedere la [demo Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="36f76-360">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="36f76-361">Supporto per HTTP/2</span><span class="sxs-lookup"><span data-stu-id="36f76-361">HTTP/2 support</span></span>

<span data-ttu-id="36f76-362">Il tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> supporta il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="36f76-362">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="36f76-363">Se HTTP/2 è abilitato, la versione del protocollo HTTP viene negoziata tramite TLS/ALPN e HTTP/2 viene usato solo in base alla decisione del server.</span><span class="sxs-lookup"><span data-stu-id="36f76-363">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="36f76-364">Il protocollo predefinito rimane HTTP/1.1, anche se HTTP/2 può essere abilitato in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="36f76-364">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="36f76-365">In primo luogo, è possibile impostare il messaggio di richiesta HTTP per usare HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="36f76-365">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!CODE-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="36f76-366">In secondo luogo, è possibile modificare <xref:System.Net.Http.HttpClient> in modo da usare HTTP/2 per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="36f76-366">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!CODE-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="36f76-367">Molto spesso, quando si sviluppa un'applicazione, si vuole usare una connessione non crittografata.</span><span class="sxs-lookup"><span data-stu-id="36f76-367">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="36f76-368">Se si è a conoscenza del fatto che l'endpoint di destinazione userà HTTP/2, è possibile attivare connessioni non crittografate per HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="36f76-368">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="36f76-369">Per attivare queste connessioni è possibile impostare la variabile di ambiente `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` su `1` o abilitarla nel contesto dell'app:</span><span class="sxs-lookup"><span data-stu-id="36f76-369">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!CODE-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="36f76-370">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="36f76-370">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="36f76-371">.NET Core sfrutta ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="36f76-371">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="36f76-372">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="36f76-372">With TLS 1.3:</span></span>

- <span data-ttu-id="36f76-373">La durata della connessione è migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="36f76-373">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="36f76-374">La sicurezza è migliorata grazie alla rimozione di vari algoritmi di crittografia obsoleti e non sicuri.</span><span class="sxs-lookup"><span data-stu-id="36f76-374">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="36f76-375">Quando è disponibile, .NET Core 3.0 usa **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** in un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="36f76-375">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="36f76-376">Quando **OpenSSL 1.1.1** è disponibile, entrambi i tipi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> useranno **TLS 1.3**, supponendo che sia il client sia il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="36f76-376">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="36f76-377">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="36f76-377">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="36f76-378">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="36f76-378">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="36f76-379">L'esempio seguente di C# 8.0 illustra .NET Core 3.0 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="36f76-379">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="36f76-380">Crittografia</span><span class="sxs-lookup"><span data-stu-id="36f76-380">Cryptography ciphers</span></span>

<span data-ttu-id="36f76-381">.NET 3.0 aggiunge supporto per le crittografie **AES-GCM** e **AES-CCM** implementate rispettivamente con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> e <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f76-381">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="36f76-382">Sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="36f76-382">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="36f76-383">Il codice seguente illustra l'uso della crittografia `AesGcm` per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="36f76-383">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="36f76-384">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="36f76-384">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="36f76-385">.NET core 3.0 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche da formati standard.</span><span class="sxs-lookup"><span data-stu-id="36f76-385">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="36f76-386">Non è necessario usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="36f76-386">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="36f76-387">Tutti i tipi di chiave, ad esempio *RSA*, *DSA*, *ECDsa* e *ECDiffieHellman*, supportano i formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-387">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="36f76-388">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="36f76-388">**Public Key**</span></span>
  - <span data-ttu-id="36f76-389">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="36f76-389">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="36f76-390">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="36f76-390">**Private key**</span></span>
  - <span data-ttu-id="36f76-391">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="36f76-391">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="36f76-392">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="36f76-392">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="36f76-393">Le chiavi RSA supportano anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f76-393">RSA keys also support:</span></span>

- <span data-ttu-id="36f76-394">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="36f76-394">**Public Key**</span></span>
  - <span data-ttu-id="36f76-395">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="36f76-395">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="36f76-396">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="36f76-396">**Private key**</span></span>
  - <span data-ttu-id="36f76-397">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="36f76-397">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="36f76-398">I metodi di esportazione generano dati binari con codifica DER e i metodi di importazione prevedono lo stesso tipo di comportamento.</span><span class="sxs-lookup"><span data-stu-id="36f76-398">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="36f76-399">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="36f76-399">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="36f76-400">I file **PKCS#8** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> e i file **PFX/PKCS#12** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f76-400">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="36f76-401">I file **PFX/PKCS#12** possono essere modificati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f76-401">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="36f76-402">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="36f76-402">SerialPort for Linux</span></span>

<span data-ttu-id="36f76-403">.NET Core 3.0 include il supporto di base per <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="36f76-403">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="36f76-404">In precedenza, .NET Core supportava solo l'uso di `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="36f76-404">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="36f76-405">Per altre informazioni sul supporto limitato per la porta seriale in Linux, vedere il [problema 33146 su GitHub](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="36f76-405">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="36f76-406">Docker e limiti di memoria cgroup</span><span class="sxs-lookup"><span data-stu-id="36f76-406">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="36f76-407">A partire da Preview 3, l'esecuzione di .NET Core 3.0 in Linux con Docker risulta migliorata usando limiti di memoria cgroup.</span><span class="sxs-lookup"><span data-stu-id="36f76-407">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="36f76-408">Eseguendo un contenitore Docker con limiti di memoria, ad esempio `docker run -m`, il comportamento di .NET Core cambia.</span><span class="sxs-lookup"><span data-stu-id="36f76-408">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="36f76-409">Dimensioni heap predefinite del Garbage Collector: massimo 20 MB o il 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="36f76-409">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="36f76-410">È possibile impostare dimensioni esplicite come numero assoluto o percentuale di un limite cgroup.</span><span class="sxs-lookup"><span data-stu-id="36f76-410">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="36f76-411">Le dimensioni minime del segmento riservato per ogni heap del Garbage Collection sono pari a 16 MB.</span><span class="sxs-lookup"><span data-stu-id="36f76-411">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="36f76-412">Le dimensioni riducono il numero di heap creati nei computer.</span><span class="sxs-lookup"><span data-stu-id="36f76-412">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="36f76-413">Riduzione delle dimensioni heap del Garbage Collector</span><span class="sxs-lookup"><span data-stu-id="36f76-413">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="36f76-414">Le dimensioni heap predefinite del Garbage Collector sono state ridotte tanto che .NET Core usa ora meno memoria.</span><span class="sxs-lookup"><span data-stu-id="36f76-414">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="36f76-415">Questa modifica consente un migliore allineamento del budget di allocazione di generazione 0 con le dimensioni della cache dei processori moderni.</span><span class="sxs-lookup"><span data-stu-id="36f76-415">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="36f76-416">Supporto per pagine grandi in Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="36f76-416">Garbage Collection Large Page support</span></span>

<span data-ttu-id="36f76-417">Le pagine di grandi dimensioni, dette anche huge page in Linux, consentono al sistema operativo di creare aree di memoria più grandi rispetto alle dimensioni di pagina native (spesso 4K). In questo modo si migliorano le prestazioni dell'applicazione che richiede pagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="36f76-417">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="36f76-418">Il Garbage Collector può ora essere configurato con l'impostazione **GCLargePages** come funzionalità con consenso esplicito per scegliere di allocare le pagine di grandi dimensioni in Windows.</span><span class="sxs-lookup"><span data-stu-id="36f76-418">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="36f76-419">Supporto di GPIO per Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="36f76-419">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="36f76-420">Sono stati rilasciati due pacchetti NuGet che è possibile usare per la programmazione GPIO:</span><span class="sxs-lookup"><span data-stu-id="36f76-420">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="36f76-421">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="36f76-421">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="36f76-422">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="36f76-422">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="36f76-423">I pacchetti GPIO includono le API per i dispositivi *GPIO*, *SPI*, *I2C* e *PWM*.</span><span class="sxs-lookup"><span data-stu-id="36f76-423">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="36f76-424">Il pacchetto di binding IoT include i binding di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="36f76-424">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="36f76-425">Per altre informazioni, vedere il [repository GitHub dei dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="36f76-425">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="36f76-426">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="36f76-426">ARM64 Linux support</span></span>

<span data-ttu-id="36f76-427">.NET Core 3.0 aggiunge il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="36f76-427">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="36f76-428">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="36f76-428">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="36f76-429">Per altre informazioni, vedere [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) (Stato di ARM64 per .NET Core).</span><span class="sxs-lookup"><span data-stu-id="36f76-429">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="36f76-430">Sono disponibili [immagini Docker per .NET Core in ARM64](https://hub.docker.com/r/microsoft/dotnet/) per Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="36f76-430">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="36f76-431">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="36f76-431">**ARM64** Windows support isn't yet available.</span></span>
