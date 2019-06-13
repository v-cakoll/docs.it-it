---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 05/06/2019
ms.openlocfilehash: f7dc95a9f0b652f1509720fb987cbdb88f64e78c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689261"
---
# <a name="whats-new-in-net-core-30-preview-5"></a><span data-ttu-id="5a1c9-103">Novità di .NET Core 3.0 (Preview 5)</span><span class="sxs-lookup"><span data-stu-id="5a1c9-103">What's new in .NET Core 3.0 (Preview 5)</span></span>

<span data-ttu-id="5a1c9-104">Questo articolo descrive le novità di .NET Core 3.0 (Preview 5).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-104">This article describes what is new in .NET Core 3.0 (through preview 5).</span></span> <span data-ttu-id="5a1c9-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="5a1c9-106">Con il componente Windows Desktop di .NET Core 3.0 SDK, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="5a1c9-107">Il componente Windows Desktop è dunque supportato e incluso solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="5a1c9-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="5a1c9-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="5a1c9-110">È consigliabile usare la versione più recente di Visual Studio 2019 Update 1 Preview o Visual Studio Code con l'estensione OmniSharp.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-110">It's highly recommended that you use the latest release of Visual Studio 2019 Update 1 Preview or VSCode with the OmniSharp extension.</span></span>

<span data-ttu-id="5a1c9-111">[Scaricare e iniziare subito a usare .NET Core 3.0 Preview 5](https://aka.ms/netcore3download) in Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-111">[Download and get started with .NET Core 3.0 Preview 5](https://aka.ms/netcore3download) right now on Windows, Mac, and Linux.</span></span>

<span data-ttu-id="5a1c9-112">Per altre informazioni su ogni versione di anteprima, vedere gli annunci seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="5a1c9-113">Annuncio di .NET Core 3.0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="5a1c9-113">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="5a1c9-114">Annuncio di .NET Core 3.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="5a1c9-114">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="5a1c9-115">Annuncio di .NET Core 3.0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="5a1c9-115">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="5a1c9-116">Annuncio di .NET Core 3.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="5a1c9-116">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="5a1c9-117">Annuncio di .NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="5a1c9-117">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="5a1c9-118">Programma di installazione .NET Core SDK per Windows</span><span class="sxs-lookup"><span data-stu-id="5a1c9-118">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="5a1c9-119">Il programma di installazione di Windows Installer (MSI) per Windows è stato modificato a partire da .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-119">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="5a1c9-120">I programmi di installazione di SDK aggiorneranno ora le versioni della banda di funzionalità sul posto.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-120">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="5a1c9-121">Le bande di funzionalità vengono definite nei gruppi *centinaia* nella sezione *patch* del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-121">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="5a1c9-122">Ad esempio, **3.0. \* 101**\* e **3.0. \* 201**\* sono versioni in due diverse bande di funzionalità, mentre **3.0. \* 101**\* e **3.0. \* 199**\* appartengono alla stessa banda.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-122">For example, **3.0.\*101**\* and **3.0.\*201**\* are versions in two different feature bands while **3.0.\*101**\* and **3.0.\*199**\* are in the same feature band.</span></span> <span data-ttu-id="5a1c9-123">Quindi, quando .NET Core SDK **3.0.\*101**\* viene installato, .NET Core SDK **3.0.\*100**\* sarà rimosso dal computer se è esistente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-123">And, when .NET Core SDK **3.0.\*101**\* is installed, .NET Core SDK **3.0.\*100**\* will be removed from the machine if it exists.</span></span> <span data-ttu-id="5a1c9-124">Quando .NET Core SDK **3.0. \* 200**\* viene installato nello stesso computer, .NET Core SDK **3.0. \* 101**\* non sarà rimosso.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-124">When .NET Core SDK **3.0.\*200**\* is installed on the same machine, .NET Core SDK **3.0.\*101**\* won't be removed.</span></span>

<span data-ttu-id="5a1c9-125">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-125">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="5a1c9-126">Anteprima di C# 8.0</span><span class="sxs-lookup"><span data-stu-id="5a1c9-126">C# 8.0 preview</span></span>

<span data-ttu-id="5a1c9-127">.NET core 3.0 supporta l'anteprima di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-127">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="5a1c9-128">Per altre informazioni sulle funzionalità di C# 8.0, vedere [Novità di C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-128">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="5a1c9-129">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="5a1c9-129">.NET Standard 2.1</span></span>

<span data-ttu-id="5a1c9-130">Anche se .NET Core 3.0 supporta **.NET Standard 2.1**, il modello `dotnet new classlib` predefinito genera un progetto per **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-130">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="5a1c9-131">Per destinarlo a **.NET Standard 2.1**, modificare il file di progetto e la proprietà `TargetFramework` in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-131">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
 
  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>
 
</Project>
```

<span data-ttu-id="5a1c9-132">Se si usa Visual Studio, è necessario Visual Studio 2019. Visual Studio 2017 non supporta **.NET Standard 2.1** o **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-132">If you're using Visual Studio, you need Visual Studio 2019, as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span> <span data-ttu-id="5a1c9-133">È consigliabile usare [Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-133">We highly recommend that you use [Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/).</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="5a1c9-134">Miglioramento delle API della versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="5a1c9-134">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="5a1c9-135">A partire da .NET Core 3.0, le API della versione di .NET Core restituiscono le informazioni previste.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-135">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="5a1c9-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-136">For example:</span></span>

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
> <span data-ttu-id="5a1c9-137">Modifica importante:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-137">Breaking change.</span></span> <span data-ttu-id="5a1c9-138">si tratta di una modifica tecnicamente importante perché è cambiato lo schema di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-138">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="5a1c9-139">Intrinseci dipendenti dalla piattaforma .NET</span><span class="sxs-lookup"><span data-stu-id="5a1c9-139">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="5a1c9-140">Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-140">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="5a1c9-141">Queste istruzioni consentono di ottenere miglioramenti delle prestazioni significativi in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-141">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> 

<span data-ttu-id="5a1c9-142">Ove appropriato, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-142">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="5a1c9-143">Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-143">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="5a1c9-144">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="5a1c9-144">Default executables</span></span>

<span data-ttu-id="5a1c9-145">Per impostazione predefinita .NET Core ora compila [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-145">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="5a1c9-146">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-146">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="5a1c9-147">In precedenza solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) generavano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-147">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="5a1c9-148">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile che corrisponde all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-148">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="5a1c9-149">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-149">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="5a1c9-150">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-150">You can double-click on the executable.</span></span>
* <span data-ttu-id="5a1c9-151">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-151">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="5a1c9-152">File eseguibili singoli</span><span class="sxs-lookup"><span data-stu-id="5a1c9-152">Single-file executables</span></span>

<span data-ttu-id="5a1c9-153">Il comando `dotnet publish` supporta la creazione del pacchetto dell'app come file eseguibile singolo specifico per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-153">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="5a1c9-154">Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluse quelle native) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-154">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="5a1c9-155">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-155">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="5a1c9-156">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-156">Startup is faster when the application is run again.</span></span> <span data-ttu-id="5a1c9-157">L'applicazione non dovrà ripetere l'estrazione una seconda volta, a meno che sia stata usata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-157">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="5a1c9-158">Per pubblicare un file eseguibile singolo, impostare `PublishSingleFile` nel progetto o nella riga di comando usando il comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-158">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="5a1c9-159">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-159">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="5a1c9-160">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="5a1c9-160">Tiered compilation</span></span>

<span data-ttu-id="5a1c9-161">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) è attiva.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-161">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="5a1c9-162">Questa funzionalità consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-162">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="5a1c9-163">Il vantaggio principale della compilazione a livelli (TC) consiste nell'abilitazione di metodi di ricompilazione JIT seguendo un approccio slower-but-faster (più lento ma più rapido) o higher-quality-but-slower (di migliore qualità ma più lento) per la produzione di codice.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-163">The main benefit of TC is to enable (re-)jitting methods with slower-but-faster to produce code or higher-quality-but-slower to produce code.</span></span> <span data-ttu-id="5a1c9-164">In questo modo è possibile migliorare le prestazioni di un'applicazione nelle sue vari fasi di esecuzione, dall'avvio allo stato stabile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-164">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="5a1c9-165">Ciò si differenzia dall'approccio che non usa la compilazione a livelli. In questo caso ogni metodo viene compilato in un solo modo (come per il livello alta qualità), che dà priorità allo stato stabile piuttosto che alle prestazioni all'avvio.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-165">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="5a1c9-166">Per abilitare la compilazione JIT rapida (codice JIT livello 0), usare questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-166">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="5a1c9-167">Per disabilitare completamente la compilazione a livelli, usare questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-167">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="build-copies-dependencies"></a><span data-ttu-id="5a1c9-168">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="5a1c9-168">Build copies dependencies</span></span>

<span data-ttu-id="5a1c9-169">Il comando `dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet nella cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-169">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="5a1c9-170">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-170">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="5a1c9-171">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-171">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="5a1c9-172">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="5a1c9-172">Local tools</span></span>

<span data-ttu-id="5a1c9-173">.NET core 3.0 introduce gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-173">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="5a1c9-174">Gli strumenti locali sono simili agli [strumenti globali](../tools/global-tools.md), ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-174">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="5a1c9-175">Gli strumenti locali non sono disponibili a livello globale e vengono distribuiti come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-175">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="5a1c9-176">Se è stata eseguita una prova degli strumenti locali in .NET Core 3.0 Preview 1, ad esempio eseguendo `dotnet tool restore` o `dotnet tool install`, eliminare la cartella della cache degli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-176">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="5a1c9-177">In caso contrario, gli strumenti locali non funzioneranno in una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-177">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="5a1c9-178">Questa cartella si trova in:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-178">This folder is located at:</span></span>
>
> <span data-ttu-id="5a1c9-179">In macOS: Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-179">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="5a1c9-180">In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-180">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="5a1c9-181">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-181">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="5a1c9-182">Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-182">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="5a1c9-183">È possibile distribuire il file manifesto con il codice per assicurarsi che tutti gli utenti che usano il codice possano ripristinare e usare gli stessi strumenti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-183">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="5a1c9-184">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-184">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="5a1c9-185">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-185">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="5a1c9-186">Per installare questi strumenti a livello globale o locale, è comunque necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-186">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="5a1c9-187">Roll forward alla versione principale</span><span class="sxs-lookup"><span data-stu-id="5a1c9-187">Major-version Roll Forward</span></span>

<span data-ttu-id="5a1c9-188">.NET core 3.0 introduce una funzionalità con consenso esplicito che consente all'app di eseguire il roll forward alla versione principale più recente di NET Core.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-188">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="5a1c9-189">È stata aggiunta anche una nuova impostazione per controllare come applicare il roll forward all'app.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-189">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="5a1c9-190">Questa funzionalità può essere configurata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-190">This can be configured in the following ways:</span></span>

- <span data-ttu-id="5a1c9-191">Proprietà file di progetto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-191">Project file property: `RollForward`</span></span>
- <span data-ttu-id="5a1c9-192">Proprietà file di configurazione runtime: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-192">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="5a1c9-193">Variabile di ambiente: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-193">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="5a1c9-194">Argomento della riga di comando: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="5a1c9-194">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="5a1c9-195">È necessario specificare uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-195">One of the following values must be specified.</span></span> <span data-ttu-id="5a1c9-196">Se non viene impostato un valore, l'impostazione **Minor** sarà quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-196">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="5a1c9-197">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-197">**LatestPatch**</span></span>\
<span data-ttu-id="5a1c9-198">Esegue il roll forward alla versione di patch più recente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-198">Roll forward to the highest patch version.</span></span> <span data-ttu-id="5a1c9-199">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-199">This disables minor version roll forward.</span></span>
- <span data-ttu-id="5a1c9-200">**Minor**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-200">**Minor**</span></span>\
<span data-ttu-id="5a1c9-201">Esegue il roll forward alla versione secondaria successiva minima, se la versione secondaria richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-201">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="5a1c9-202">Se la versione secondaria richiesta è presente, viene usato il criterio **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-202">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="5a1c9-203">**Major**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-203">**Major**</span></span>\
<span data-ttu-id="5a1c9-204">Esegue il roll forward alla versione principale successiva minima e alla versione secondaria minima, se la versione principale richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-204">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="5a1c9-205">Se la versione principale richiesta è presente, viene usato il criterio **Minor**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-205">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="5a1c9-206">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-206">**LatestMinor**</span></span>\
<span data-ttu-id="5a1c9-207">Esegue il roll forward alla versione secondaria più recente, anche se la versione secondaria richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-207">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="5a1c9-208">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-208">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="5a1c9-209">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-209">**LatestMajor**</span></span>\
<span data-ttu-id="5a1c9-210">Esegue il roll forward alla versione principale e secondaria più recente, anche se la versione principale richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-210">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="5a1c9-211">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-211">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="5a1c9-212">**Disable**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-212">**Disable**</span></span>\
<span data-ttu-id="5a1c9-213">Non esegue il roll forward.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-213">Don't roll forward.</span></span> <span data-ttu-id="5a1c9-214">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-214">Only bind to specified version.</span></span> <span data-ttu-id="5a1c9-215">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-215">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="5a1c9-216">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-216">This value is only recommended for testing.</span></span>

<span data-ttu-id="5a1c9-217">Ad eccezione dell'impostazione **Disable**, tutte le impostazioni useranno la versione di patch disponibile più recente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-217">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="5a1c9-218">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="5a1c9-218">Windows desktop</span></span>

<span data-ttu-id="5a1c9-219">.NET Core 3.0 supporta applicazioni desktop di Windows che usano Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-219">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="5a1c9-220">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-220">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="5a1c9-221">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-221">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="5a1c9-222">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-222">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="5a1c9-223">Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-223">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="5a1c9-224">Per altre informazioni su come convertire un'applicazione .NET Framework esistente, vedere [Convertire progetti WPF](../porting/wpf.md) e [Convertire progetti Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-224">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="5a1c9-225">Componenti COM-Callable in Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="5a1c9-225">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="5a1c9-226">In Windows è ora possibile creare componenti gestiti COM-Callable.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-226">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="5a1c9-227">Questa funzionalità è essenziale per usare .NET Core con modelli del componente aggiuntivo COM e anche per assicurare parità con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-227">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="5a1c9-228">A differenza di .NET Framework in cui *mscoree.dll* era usato come server COM, .NET Core aggiungerà un file dll di avvio nativo alla directory *bin* quando si compilerà il componente COM.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-228">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="5a1c9-229">Per un esempio su come creare e usare un componente COM, vedere la [demo COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-229">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="5a1c9-230">Distribuzione MSIX in Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="5a1c9-230">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="5a1c9-231">[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-231">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="5a1c9-232">Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-232">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="5a1c9-233">Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-233">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="5a1c9-234">Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-234">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-highdpi"></a><span data-ttu-id="5a1c9-235">HighDPI in WinForms</span><span class="sxs-lookup"><span data-stu-id="5a1c9-235">WinForms HighDPI</span></span>

<span data-ttu-id="5a1c9-236">Le applicazioni di Windows Forms in .NET Core possono impostare la modalità con valori DPI alti usando <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-236">.NET Core Windows Forms applications can set High DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a1c9-237">Il metodo `SetHighDpiMode` imposta la modalità con valori DPI alti corrispondente a meno che l'impostazione sia stata configurata in altro modo, ad esempio con `App.Manifest` o P/Invoke prima di `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-237">The `SetHighDpiMode` method sets the corresponding High DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="5a1c9-238">I valori possibili per `highDpiMode`, espressi dall'enumerazione <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>, sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-238">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

* `DpiUnaware`
* `SystemAware`
* `PerMonitor`
* `PerMonitorV2`
* `DpiUnawareGdiScaled`

<span data-ttu-id="5a1c9-239">Per altre informazioni sulle modalità con valori DPI alti vedere [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) (Sviluppo di applicazioni desktop con valori DPI alti in Windows).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-239">For more information about High DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="5a1c9-240">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="5a1c9-240">Ranges and indices</span></span>

<span data-ttu-id="5a1c9-241">Il nuovo tipo <xref:System.Index?displayProperty=nameWithType> può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-241">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="5a1c9-242">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-242">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="5a1c9-243">Esiste anche il tipo <xref:System.Range?displayProperty=nameWithType>, costituito da due valori `Index`, uno per l'inizio e uno per la fine, e può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-243">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="5a1c9-244">È anche possibile poi indicizzare usano un oggetto `Range`, che genera una sezione:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-244">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="5a1c9-245">Per altre informazioni, vedere l'[esercitazione su intervalli e indici](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-245">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="5a1c9-246">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="5a1c9-246">Async streams</span></span>

<span data-ttu-id="5a1c9-247">Il tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> è una nuova versione asincrona di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-247">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="5a1c9-248">Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-248">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="5a1c9-249">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-249">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="5a1c9-250">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-250">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="5a1c9-251">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-251">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="5a1c9-252">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-252">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="5a1c9-253">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-253">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="5a1c9-254">Per altre informazioni, vedere l'[esercitazione sui flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-254">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="5a1c9-255">Miglioramenti per le API a virgola mobile IEEE</span><span class="sxs-lookup"><span data-stu-id="5a1c9-255">IEEE Floating-point improvements</span></span>

<span data-ttu-id="5a1c9-256">È in corso l'aggiornamento di API virgola mobile per conformità alla [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-256">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="5a1c9-257">L'obiettivo di queste modifiche è esporre tutte le operazioni **obbligatorie** e assicurarsi che, a livello di comportamento, siano conformi alla specifica IEEE. Per altre informazioni sui miglioramenti di virgola mobile, vedere il post di blog [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) (Miglioramenti di analisi e formattazione di virgola mobile in .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-257">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="5a1c9-258">Di seguito sono riportate le correzioni per analisi e formattazione:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-258">Parsing and formatting fixes include:</span></span>

* <span data-ttu-id="5a1c9-259">Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-259">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="5a1c9-260">Analisi corretta e formattazione dello zero negativo.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-260">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="5a1c9-261">Analisi corretta di valori `Infinity` e `NaN` con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-261">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="5a1c9-262">Le nuovi API <xref:System.Math?displayProperty=nameWithType> includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-262">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

* <span data-ttu-id="5a1c9-263"><xref:System.Math.BitIncrement(System.Double)> e <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="5a1c9-263"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="5a1c9-264">Corrispondono alle operazioni IEEE `nextUp` e `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-264">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="5a1c9-265">Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-265">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="5a1c9-266">Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-266">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* <span data-ttu-id="5a1c9-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> e <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="5a1c9-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="5a1c9-268">Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-268">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="5a1c9-269">Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-269">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="5a1c9-270">Corrispondono all'operazione IEEE `logB` che restituisce un valore integrale, restituisce il logaritmo in base 2 integrale del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-270">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="5a1c9-271">Questo metodo equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-271">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="5a1c9-272">Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-272">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="5a1c9-273">Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-273">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="5a1c9-274">Gli errori di arrotondamento sono ridotti al minimo.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-274">It minimizes rounding error.</span></span>

* <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="5a1c9-275">Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-275">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="5a1c9-276">Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-276">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="5a1c9-277">Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)` che restituisce `1e308`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-277">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="5a1c9-278">L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-278">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="5a1c9-279">Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-279">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="5a1c9-280">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="5a1c9-280">Fast built-in JSON support</span></span>

<span data-ttu-id="5a1c9-281">Gli utenti .NET si sono ampiamente basati su [**Json.NET**](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-281">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="5a1c9-282">Come tipo di dati di base, **Json.NET** usa le stringhe .NET, che in realtà sono UTF-16.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-282">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="5a1c9-283">Il nuovo supporto JSON predefinito offre prestazioni elevate, bassa allocazione ed è basato su `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-283">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="5a1c9-284">Sono stati aggiunti tre nuovi tipi correlati principali JSON a .NET Core 3.0 nello spazio dei nomi <xref:System.Text.Json?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-284">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5a1c9-285">Questi tipi non supportano *ancora* la serializzazione e deserializzazione POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-285">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="5a1c9-286">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="5a1c9-286">Utf8JsonReader</span></span>

<span data-ttu-id="5a1c9-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="5a1c9-288">`Utf8JsonReader` è un tipo di base di basso livello, che può essere usato per creare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-288">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="5a1c9-289">La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-289">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="5a1c9-290">Non viene allocato fino a quando non è necessario realizzare token JSON come stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-290">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="5a1c9-291">Di seguito è riportato un esempio di lettura tramite il file [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creato da Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-291">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="5a1c9-292">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="5a1c9-292">Utf8JsonWriter</span></span>

<span data-ttu-id="5a1c9-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> rende disponibile un metodo ad alte prestazioni, senza memorizzazione nella cache e forward-only per la scrittura di test JSON con codifica UTF-8 da tipi .NET comuni, come `String`, `Int32` e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="5a1c9-294">Come il lettore, il writer è un tipo di base di basso livello, che può essere usato per creare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-294">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="5a1c9-295">La scrittura di un payload JSON con il nuovo `Utf8JsonWriter` offre velocità maggiori del 30-80% rispetto all'uso del writer di **Json.NET** e non prevede allocazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-295">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="5a1c9-296">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="5a1c9-296">JsonDocument</span></span>

<span data-ttu-id="5a1c9-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> è basato su `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="5a1c9-298">`JsonDocument` offre la possibilità di analizzare i dati JSON e compilare un modello DOM (Document Object Model) di sola lettura su cui è possibile eseguire query per supportare l'accesso casuale e l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-298">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="5a1c9-299">Gli elementi JSON che compongono i dati sono accessibili tramite il tipo <xref:System.Text.Json.JsonElement> che viene esposto da `JsonDocument` come una proprietà denominata `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-299">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="5a1c9-300">`JsonElement` contiene gli enumeratori di matrice e oggetto JSON insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-300">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="5a1c9-301">L'analisi di un payload JSON tipico e l'accesso a tutti i relativi membri tramite `JsonDocument` è 2/3 volte più veloce rispetto a **Json.NET** con allocazioni minime per dati di dimensioni ragionevoli, vale a dire inferiori a 1 MB.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-301">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="5a1c9-302">Ecco un esempio di utilizzo di `JsonDocument` e `JsonElement` che può essere usato come punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-302">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

<span data-ttu-id="5a1c9-303">Di seguito è riportato un esempio di lettura di C# 8.0 tramite il file [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creato da Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-303">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="5a1c9-304">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="5a1c9-304">JsonSerializer</span></span>

<span data-ttu-id="5a1c9-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> si basa su <xref:System.Text.Json.Utf8JsonReader> e <xref:System.Text.Json.Utf8JsonWriter> per offrire un'opzione di serializzazione veloce della memoria insufficiente quando si usano documenti e frammenti JSON.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="5a1c9-306">VEDERE: https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md per un esempio di conversione</span><span class="sxs-lookup"><span data-stu-id="5a1c9-306">EXAMINE: https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md for an example to port to this article</span></span>

<span data-ttu-id="5a1c9-307">Di seguito è riportato un esempio di serializzazione di un oggetto in formato JSON:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-307">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="5a1c9-308">Di seguito è riportato un esempio di deserializzazione di una stringa JSON in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-308">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="5a1c9-309">È possibile usare la stringa JSON generata nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-309">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="5a1c9-310">Miglioramenti di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="5a1c9-310">Interop improvements</span></span>

<span data-ttu-id="5a1c9-311">.NET core 3.0 migliora l'interoperabilità di API native.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-311">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="5a1c9-312">Tipo: NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="5a1c9-312">Type: NativeLibrary</span></span>

<span data-ttu-id="5a1c9-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> offre un incapsulamento per il caricamento di una libreria nativa (usando la stessa logica di caricamento di .NET Core P/Invoke) e offre le funzioni di supporto pertinenti, ad esempio `getSymbol`.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="5a1c9-314">Per un esempio di codice, vedere la [demo DLLMap](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-314">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="5a1c9-315">Interoperabilità nativa di Windows</span><span class="sxs-lookup"><span data-stu-id="5a1c9-315">Windows Native Interop</span></span>

<span data-ttu-id="5a1c9-316">Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-316">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="5a1c9-317">Mentre .NET Core supporta **P/Invoke**, .NET Core 3.0 aggiunge la possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-317">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="5a1c9-318">Per un esempio di codice, vedere la [demo Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-318">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="5a1c9-319">Supporto per HTTP/2</span><span class="sxs-lookup"><span data-stu-id="5a1c9-319">HTTP/2 support</span></span>

<span data-ttu-id="5a1c9-320">Il tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> supporta il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-320">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="5a1c9-321">Il supporto è attualmente disabilitato, ma può essere attivato chiamando `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` prima di usare <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-321">Support is currently disabled but can be turned on by calling `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` before you use <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="5a1c9-322">È anche possibile abilitare il supporto per HTTP/2 impostando la variabile di ambiente `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` su `true` prima di eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-322">You can also enable HTTP/2 support by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` environment variable to `true` before you run your app.</span></span>

<span data-ttu-id="5a1c9-323">Se HTTP/2 è abilitata, la versione del protocollo HTTP verrà negoziata tramite TLS/ALPN e HTTP/2 verrà usato solo se il server sceglie di usarlo.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-323">If HTTP/2 is enabled, the HTTP protocol version will be negotiated via TLS/ALPN, and HTTP/2 will only be used if the server elects to use it.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="5a1c9-324">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="5a1c9-324">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="5a1c9-325">.NET Core sfrutta ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-325">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="5a1c9-326">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-326">With TLS 1.3:</span></span>

* <span data-ttu-id="5a1c9-327">La durata della connessione è migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-327">Connection times are improved with reduced round trips required between the client and server.</span></span>
* <span data-ttu-id="5a1c9-328">La sicurezza è migliorata grazie alla rimozione di vari algoritmi di crittografia obsoleti e non sicuri.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-328">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="5a1c9-329">Quando è disponibile, .NET Core 3.0 usa **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** in un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-329">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="5a1c9-330">Quando **OpenSSL 1.1.1** è disponibile, entrambi i tipi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> useranno **TLS 1.3**, supponendo che sia il client sia il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-330">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="5a1c9-331">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-331">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="5a1c9-332">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-332">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="5a1c9-333">L'esempio seguente di C# 8.0 illustra .NET Core 3.0 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-333">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="5a1c9-334">Crittografia</span><span class="sxs-lookup"><span data-stu-id="5a1c9-334">Cryptography ciphers</span></span>

<span data-ttu-id="5a1c9-335">.NET 3.0 aggiunge supporto per le crittografie **AES-GCM** e **AES-CCM** implementate rispettivamente con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> e <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-335">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="5a1c9-336">Sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-336">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="5a1c9-337">Il codice seguente illustra l'uso della crittografia `AesGcm` per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-337">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="5a1c9-338">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="5a1c9-338">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="5a1c9-339">.NET core 3.0 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche da formati standard.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-339">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="5a1c9-340">Non è necessario usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-340">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="5a1c9-341">Tutti i tipi di chiave, ad esempio *RSA*, *DSA*, *ECDsa* e *ECDiffieHellman*, supportano i formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-341">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

* <span data-ttu-id="5a1c9-342">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-342">**Public Key**</span></span>
  * <span data-ttu-id="5a1c9-343">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="5a1c9-343">X.509 SubjectPublicKeyInfo</span></span>

* <span data-ttu-id="5a1c9-344">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-344">**Private key**</span></span>
  * <span data-ttu-id="5a1c9-345">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="5a1c9-345">PKCS#8 PrivateKeyInfo</span></span>
  * <span data-ttu-id="5a1c9-346">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="5a1c9-346">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="5a1c9-347">Le chiavi RSA supportano anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-347">RSA keys also support:</span></span>

* <span data-ttu-id="5a1c9-348">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-348">**Public Key**</span></span>
  * <span data-ttu-id="5a1c9-349">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="5a1c9-349">PKCS#1 RSAPublicKey</span></span>

* <span data-ttu-id="5a1c9-350">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="5a1c9-350">**Private key**</span></span>
  * <span data-ttu-id="5a1c9-351">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="5a1c9-351">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="5a1c9-352">I metodi di esportazione generano dati binari con codifica DER e i metodi di importazione prevedono lo stesso tipo di comportamento.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-352">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="5a1c9-353">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-353">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="5a1c9-354">I file **PKCS#8** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> e i file **PFX/PKCS#12** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-354">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a1c9-355">I file **PFX/PKCS#12** possono essere modificati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-355">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="5a1c9-356">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="5a1c9-356">SerialPort for Linux</span></span>

<span data-ttu-id="5a1c9-357">.NET Core 3.0 supporta <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-357">.NET Core 3.0 supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="5a1c9-358">In precedenza, .NET Core supportava solo l'uso di `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-358">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="5a1c9-359">Docker e limiti di memoria cgroup</span><span class="sxs-lookup"><span data-stu-id="5a1c9-359">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="5a1c9-360">A partire da Preview 3, l'esecuzione di .NET Core 3.0 in Linux con Docker risulta migliorata usando limiti di memoria cgroup.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-360">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="5a1c9-361">Eseguendo un contenitore Docker con limiti di memoria, ad esempio `docker run -m`, il comportamento di .NET Core cambia.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-361">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

* <span data-ttu-id="5a1c9-362">Dimensioni heap predefinite del Garbage Collector: massimo 20 MB o il 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-362">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
* <span data-ttu-id="5a1c9-363">È possibile impostare dimensioni esplicite come numero assoluto o percentuale di un limite cgroup.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-363">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
* <span data-ttu-id="5a1c9-364">Le dimensioni minime del segmento riservato per ogni heap del Garbage Collection sono pari a 16 MB.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-364">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="5a1c9-365">Le dimensioni riducono il numero di heap creati nei computer.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-365">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="5a1c9-366">Riduzione delle dimensioni heap del Garbage Collector</span><span class="sxs-lookup"><span data-stu-id="5a1c9-366">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="5a1c9-367">Le dimensioni heap predefinite del Garbage Collector sono state ridotte tanto che .NET Core usa ora meno memoria.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-367">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="5a1c9-368">Questa modifica consente un migliore allineamento del budget di allocazione di generazione 0 con le dimensioni della cache dei processori moderni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-368">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="5a1c9-369">Supporto per pagine grandi in Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5a1c9-369">Garbage Collection Large Page support</span></span>

<span data-ttu-id="5a1c9-370">Le pagine di grandi dimensioni, dette anche huge page in Linux, consentono al sistema operativo di creare aree di memoria più grandi rispetto alle dimensioni di pagina native (spesso 4K). In questo modo si migliorano le prestazioni dell'applicazione che richiede pagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-370">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="5a1c9-371">Il Garbage Collector può ora essere configurato con l'impostazione **GCLargePages** come funzionalità con consenso esplicito per scegliere di allocare le pagine di grandi dimensioni in Windows.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-371">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="5a1c9-372">Supporto di GPIO per Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="5a1c9-372">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="5a1c9-373">Sono stati rilasciati due pacchetti NuGet che è possibile usare per la programmazione GPIO:</span><span class="sxs-lookup"><span data-stu-id="5a1c9-373">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

* [<span data-ttu-id="5a1c9-374">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="5a1c9-374">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
* [<span data-ttu-id="5a1c9-375">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="5a1c9-375">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="5a1c9-376">I pacchetti GPIO includono le API per i dispositivi *GPIO*, *SPI*, *I2C* e *PWM*.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-376">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="5a1c9-377">Il pacchetto di binding IoT include i binding di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-377">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="5a1c9-378">Per altre informazioni, vedere il [repository GitHub dei dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-378">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="5a1c9-379">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="5a1c9-379">ARM64 Linux support</span></span>

<span data-ttu-id="5a1c9-380">.NET Core 3.0 aggiunge il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-380">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="5a1c9-381">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-381">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="5a1c9-382">Per altre informazioni, vedere [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) (Stato di ARM64 per .NET Core).</span><span class="sxs-lookup"><span data-stu-id="5a1c9-382">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="5a1c9-383">Sono disponibili [immagini Docker per .NET Core in ARM64](https://hub.docker.com/r/microsoft/dotnet/) per Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-383">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="5a1c9-384">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="5a1c9-384">**ARM64** Windows support isn't yet available.</span></span>
