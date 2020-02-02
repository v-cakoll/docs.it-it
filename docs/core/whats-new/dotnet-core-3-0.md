---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 92d97ca3efe761c879d0940a02342edb5a8180f0
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920373"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="d52c3-103">Novità di .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d52c3-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="d52c3-104">Questo articolo descrive le novità di .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d52c3-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="d52c3-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="d52c3-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="d52c3-106">Con il componente Windows Desktop di .NET Core 3.0 SDK, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="d52c3-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="d52c3-107">Il componente Windows Desktop è dunque supportato e incluso solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="d52c3-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="d52c3-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="d52c3-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="d52c3-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="d52c3-110">È consigliabile usare [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successive, [Visual Studio per Mac 8,3](/visualstudio/mac/install-preview) o versioni successive o [Visual Studio Code](https://code.visualstudio.com/) con l'  **C# estensione**più recente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="d52c3-111">[Scarica e inizia subito a usare .NET Core 3.0](https://aka.ms/netcore3download) in Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="d52c3-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="d52c3-112">Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="d52c3-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="d52c3-113">.NET Core RC1 è stato considerato pronto per la produzione da Microsoft ed è stato completamente supportato.</span><span class="sxs-lookup"><span data-stu-id="d52c3-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="d52c3-114">Se si usa una versione di anteprima, è necessario passare alla versione RTM per il supporto continuo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="d52c3-115">Miglioramenti C# della lingua 8,0</span><span class="sxs-lookup"><span data-stu-id="d52c3-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="d52c3-116">C#8,0 fa anche parte di questa versione, che include la funzionalità dei [tipi di riferimento Nullable](../../csharp/tutorials/nullable-reference-types.md) , i [flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md)e [altri modelli](../../csharp/tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="d52c3-117">Per altre informazioni sulle funzionalità di C# 8.0, vedere [Novità di C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="d52c3-118">Sono stati aggiunti miglioramenti alla lingua per supportare le seguenti funzionalità API descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="d52c3-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="d52c3-119">Intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="d52c3-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="d52c3-120">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="d52c3-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="d52c3-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="d52c3-121">.NET Standard 2.1</span></span>

<span data-ttu-id="d52c3-122">.NET Core 3,0 implementa **.NET Standard 2,1**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="d52c3-123">Tuttavia, il modello di `dotnet new classlib` predefinito genera un progetto che è ancora destinato **.NET Standard 2,0**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="d52c3-124">Per destinarlo a **.NET Standard 2.1**, modificare il file di progetto e la proprietà `TargetFramework` in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="d52c3-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d52c3-125">Se si usa Visual Studio, è necessario [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) perché Visual Studio 2017 non supporta **.NET Standard 2.1** o **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="d52c3-126">Compilazione/distribuzione</span><span class="sxs-lookup"><span data-stu-id="d52c3-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="d52c3-127">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="d52c3-127">Default executables</span></span>

<span data-ttu-id="d52c3-128">Per impostazione predefinita .NET Core ora compila [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="d52c3-128">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="d52c3-129">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="d52c3-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="d52c3-130">In precedenza solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) generavano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d52c3-130">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="d52c3-131">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile che corrisponde all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="d52c3-131">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="d52c3-132">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d52c3-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="d52c3-133">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d52c3-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="d52c3-134">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="d52c3-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="d52c3-135">File eseguibili singoli</span><span class="sxs-lookup"><span data-stu-id="d52c3-135">Single-file executables</span></span>

<span data-ttu-id="d52c3-136">Il comando `dotnet publish` supporta la creazione del pacchetto dell'app come file eseguibile singolo specifico per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d52c3-136">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="d52c3-137">Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluse quelle native) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="d52c3-137">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="d52c3-138">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-138">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="d52c3-139">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-139">Startup is faster when the application is run again.</span></span> <span data-ttu-id="d52c3-140">L'applicazione non dovrà ripetere l'estrazione una seconda volta, a meno che sia stata usata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-140">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="d52c3-141">Per pubblicare un file eseguibile singolo, impostare `PublishSingleFile` nel progetto o nella riga di comando usando il comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="d52c3-141">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="d52c3-142">oppure</span><span class="sxs-lookup"><span data-stu-id="d52c3-142">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="d52c3-143">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-143">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="d52c3-144">Collegamento di assembly</span><span class="sxs-lookup"><span data-stu-id="d52c3-144">Assembly linking</span></span>

<span data-ttu-id="d52c3-145">.NET Core SDK 3.0 include uno strumento che consente di ridurre le dimensioni delle app analizzando il linguaggio intermedio (IL) e rimuovendo gli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="d52c3-145">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="d52c3-146">Le app autonome includono tutti gli elementi necessari per eseguire il codice, senza richiedere l'installazione di .NET nel computer host.</span><span class="sxs-lookup"><span data-stu-id="d52c3-146">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="d52c3-147">Tuttavia, per il funzionamento dell'app è spesso sufficiente un piccolo subset del framework, mentre altre librerie inutilizzate possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="d52c3-147">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="d52c3-148">.NET Core include ora un'impostazione che consente l'uso dello strumento [IL Linker](https://github.com/mono/linker) per analizzare il linguaggio intermedio dell'app.</span><span class="sxs-lookup"><span data-stu-id="d52c3-148">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="d52c3-149">Questo strumento rileva il codice necessario e quindi Elimina le librerie inutilizzate.</span><span class="sxs-lookup"><span data-stu-id="d52c3-149">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="d52c3-150">Può quindi ridurre notevolmente le dimensioni di distribuzione di alcune app.</span><span class="sxs-lookup"><span data-stu-id="d52c3-150">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="d52c3-151">Per abilitare questo strumento, aggiungere l'impostazione `<PublishTrimmed>` nel progetto e pubblicare un'app autonoma:</span><span class="sxs-lookup"><span data-stu-id="d52c3-151">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="d52c3-152">Ad esempio, il nuovo modello predefinito per un progetto di console di base "hello world" ha una dimensione di circa 70 MB quando viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d52c3-152">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="d52c3-153">Usando `<PublishTrimmed>` la dimensione viene ridotta fino a circa 30 MB.</span><span class="sxs-lookup"><span data-stu-id="d52c3-153">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="d52c3-154">È importante tenere presente che le applicazioni o i framework, inclusi ASP.NET Core e WPF, che usano la reflection o le funzionalità dinamiche correlate, sono spesso soggetti a interruzioni in caso di rimozione di assembly.</span><span class="sxs-lookup"><span data-stu-id="d52c3-154">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="d52c3-155">Le interruzioni si verificano perché il linker non riconosce questo comportamento dinamico e non è in grado di identificare i tipi di framework necessari per la reflection.</span><span class="sxs-lookup"><span data-stu-id="d52c3-155">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="d52c3-156">Lo strumento IL Linker può essere configurato in modo da riconoscere questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d52c3-156">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="d52c3-157">È importante soprattutto accertarsi di testare l'app dopo la rimozione degli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="d52c3-157">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="d52c3-158">Per altre informazioni sullo strumento IL Linker, vedere la [documentazione](https://aka.ms/dotnet-illink) o visitare il repository [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="d52c3-158">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="d52c3-159">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="d52c3-159">Tiered compilation</span></span>

<span data-ttu-id="d52c3-160">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) è attiva.</span><span class="sxs-lookup"><span data-stu-id="d52c3-160">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="d52c3-161">Questa funzionalità consente al runtime di più in modo adattivo di usare il compilatore JIT (just-in-Time) per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="d52c3-161">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="d52c3-162">Il vantaggio principale della compilazione a più livelli consiste nel fornire due metodi di jitting: in un livello di qualità inferiore, ma più veloce, o in un livello di qualità superiore ma più lento.</span><span class="sxs-lookup"><span data-stu-id="d52c3-162">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="d52c3-163">La qualità si riferisce al modo in cui viene ottimizzato il metodo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-163">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="d52c3-164">TC consente di migliorare le prestazioni di un'applicazione durante le varie fasi di esecuzione, dall'avvio fino allo stato stazionario.</span><span class="sxs-lookup"><span data-stu-id="d52c3-164">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="d52c3-165">Quando la compilazione a più livelli è disabilitata, ogni metodo viene compilato in un unico modo, che è influenzato dalle prestazioni di stato costante rispetto alle prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="d52c3-165">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="d52c3-166">Quando TC è abilitato, si applica il comportamento seguente per la compilazione del metodo all'avvio di un'app:</span><span class="sxs-lookup"><span data-stu-id="d52c3-166">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="d52c3-167">Se il metodo ha codice precompilato in anticipo, o [ReadyToRun](#readytorun-images), viene usato il codice pregenerato.</span><span class="sxs-lookup"><span data-stu-id="d52c3-167">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="d52c3-168">In caso contrario, il metodo è compilato JIT.</span><span class="sxs-lookup"><span data-stu-id="d52c3-168">Otherwise, the method is jitted.</span></span> <span data-ttu-id="d52c3-169">In genere, questi metodi sono generici sui tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d52c3-169">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="d52c3-170">*JIT rapido* produce più rapidamente codice di qualità inferiore (o meno ottimizzato).</span><span class="sxs-lookup"><span data-stu-id="d52c3-170">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="d52c3-171">In .NET Core 3,0, JIT rapido è abilitato per impostazione predefinita per i metodi che non contengono cicli ed è preferibile durante l'avvio.</span><span class="sxs-lookup"><span data-stu-id="d52c3-171">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="d52c3-172">Il codice JIT per l'ottimizzazione completa produce più lentamente codice di qualità superiore (o più ottimizzata).</span><span class="sxs-lookup"><span data-stu-id="d52c3-172">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="d52c3-173">Per i metodi in cui non è possibile usare JIT rapido (ad esempio, se il metodo è attribuito a <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), viene usata la modalità JIT completamente ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="d52c3-173">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="d52c3-174">Per i metodi denominati di frequente, il compilatore just-in-Time crea il codice completamente ottimizzato in background.</span><span class="sxs-lookup"><span data-stu-id="d52c3-174">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="d52c3-175">Il codice ottimizzato sostituisce quindi il codice precompilato per il metodo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-175">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="d52c3-176">Il codice generato da Quick JIT può essere eseguito più lentamente, allocare più memoria o usare più spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="d52c3-176">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="d52c3-177">Se si verificano problemi, è possibile disabilitare Quick JIT usando questa proprietà MSBuild nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="d52c3-177">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="d52c3-178">Per disabilitare completamente TC, usare questa proprietà MSBuild nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="d52c3-178">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="d52c3-179">Se si modificano queste impostazioni nel file di progetto, potrebbe essere necessario eseguire una compilazione pulita affinché le nuove impostazioni vengano riflesse (eliminare le directory `obj` e `bin` e ricompilarle).</span><span class="sxs-lookup"><span data-stu-id="d52c3-179">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="d52c3-180">Per ulteriori informazioni sulla configurazione della compilazione in fase di esecuzione, vedere [Opzioni di configurazione in fase di esecuzione per la compilazione](../run-time-config/compilation.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-180">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="d52c3-181">Immagini ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="d52c3-181">ReadyToRun images</span></span>

<span data-ttu-id="d52c3-182">È possibile migliorare il tempo di avvio delle applicazioni .NET Core compilando gli assembly nel formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="d52c3-182">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="d52c3-183">R2R è un formato di compilazione AOT (Ahead-of-time).</span><span class="sxs-lookup"><span data-stu-id="d52c3-183">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="d52c3-184">I file binari R2R migliorano le prestazioni di avvio riducendo la quantità di lavoro che deve eseguire il compilatore JIT (Just-in-time) durante il caricamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-184">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="d52c3-185">I file binari contengono codice nativo simile a ciò che viene generato dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="d52c3-185">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="d52c3-186">I file binari R2R, tuttavia, sono più grandi poiché contengono sia il codice in linguaggio intermedio, che è comunque necessario per alcuni scenari, sia la versione nativa dello stesso codice.</span><span class="sxs-lookup"><span data-stu-id="d52c3-186">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="d52c3-187">R2R è disponibile solo quando si pubblica un'app autonoma che fa riferimento ad ambienti di runtime specifici (RID), ad esempio Linux x64 o Windows x64.</span><span class="sxs-lookup"><span data-stu-id="d52c3-187">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="d52c3-188">Per compilare il progetto come ReadyToRun, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d52c3-188">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="d52c3-189">Aggiungere l'impostazione `<PublishReadyToRun>` al progetto:</span><span class="sxs-lookup"><span data-stu-id="d52c3-189">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="d52c3-190">Pubblicare un'app autonoma.</span><span class="sxs-lookup"><span data-stu-id="d52c3-190">Publish a self-contained app.</span></span> <span data-ttu-id="d52c3-191">Questo comando, ad esempio, crea un'app autonoma per la versione a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="d52c3-191">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="d52c3-192">Limitazioni per ambienti con più piattaforme o architetture</span><span class="sxs-lookup"><span data-stu-id="d52c3-192">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="d52c3-193">Il compilatore ReadyToRun attualmente non supporta la definizione di più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-193">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="d52c3-194">La compilazione deve essere eseguita per una determinata destinazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-194">You must compile on a given target.</span></span> <span data-ttu-id="d52c3-195">Se, ad esempio, si vogliono immagini R2R per Windows x64, è necessario eseguire il comando di pubblicazione in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-195">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="d52c3-196">Eccezioni relative all'uso di più destinazioni:</span><span class="sxs-lookup"><span data-stu-id="d52c3-196">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="d52c3-197">Windows x64 può essere usato per compilare immagini Windows ARM32, ARM64 e x86.</span><span class="sxs-lookup"><span data-stu-id="d52c3-197">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="d52c3-198">Windows x86 può essere usato per compilare immagini Windows ARM32.</span><span class="sxs-lookup"><span data-stu-id="d52c3-198">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="d52c3-199">Linux x64 può essere usato per compilare immagini Linux ARM32 e ARM64.</span><span class="sxs-lookup"><span data-stu-id="d52c3-199">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="d52c3-200">Runtime/SDK</span><span class="sxs-lookup"><span data-stu-id="d52c3-200">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="d52c3-201">Rollforward del runtime della versione principale</span><span class="sxs-lookup"><span data-stu-id="d52c3-201">Major-version runtime roll forward</span></span>

<span data-ttu-id="d52c3-202">.NET core 3.0 introduce una funzionalità con consenso esplicito che consente all'app di eseguire il roll forward alla versione principale più recente di NET Core.</span><span class="sxs-lookup"><span data-stu-id="d52c3-202">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="d52c3-203">È stata aggiunta anche una nuova impostazione per controllare come applicare il roll forward all'app.</span><span class="sxs-lookup"><span data-stu-id="d52c3-203">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="d52c3-204">Questa funzionalità può essere configurata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-204">This can be configured in the following ways:</span></span>

- <span data-ttu-id="d52c3-205">Proprietà file di progetto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="d52c3-205">Project file property: `RollForward`</span></span>
- <span data-ttu-id="d52c3-206">Proprietà del file di configurazione in fase di esecuzione: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="d52c3-206">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="d52c3-207">Variabile di ambiente: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="d52c3-207">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="d52c3-208">Argomento della riga di comando: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="d52c3-208">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="d52c3-209">È necessario specificare uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-209">One of the following values must be specified.</span></span> <span data-ttu-id="d52c3-210">Se non viene impostato un valore, l'impostazione **Minor** sarà quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="d52c3-210">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="d52c3-211">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="d52c3-211">**LatestPatch**</span></span>\
<span data-ttu-id="d52c3-212">Esegue il roll forward alla versione di patch più recente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-212">Roll forward to the highest patch version.</span></span> <span data-ttu-id="d52c3-213">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="d52c3-213">This disables minor version roll forward.</span></span>
- <span data-ttu-id="d52c3-214">**Minor**</span><span class="sxs-lookup"><span data-stu-id="d52c3-214">**Minor**</span></span>\
<span data-ttu-id="d52c3-215">Esegue il roll forward alla versione secondaria successiva minima, se la versione secondaria richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="d52c3-215">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="d52c3-216">Se la versione secondaria richiesta è presente, viene usato il criterio **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-216">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="d52c3-217">**Major**</span><span class="sxs-lookup"><span data-stu-id="d52c3-217">**Major**</span></span>\
<span data-ttu-id="d52c3-218">Esegue il roll forward alla versione principale successiva minima e alla versione secondaria minima, se la versione principale richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="d52c3-218">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="d52c3-219">Se la versione principale richiesta è presente, viene usato il criterio **Minor**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-219">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="d52c3-220">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="d52c3-220">**LatestMinor**</span></span>\
<span data-ttu-id="d52c3-221">Esegue il roll forward alla versione secondaria più recente, anche se la versione secondaria richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-221">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="d52c3-222">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-222">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="d52c3-223">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="d52c3-223">**LatestMajor**</span></span>\
<span data-ttu-id="d52c3-224">Esegue il roll forward alla versione principale e secondaria più recente, anche se la versione principale richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-224">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="d52c3-225">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-225">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="d52c3-226">**Disable**</span><span class="sxs-lookup"><span data-stu-id="d52c3-226">**Disable**</span></span>\
<span data-ttu-id="d52c3-227">Non esegue il roll forward.</span><span class="sxs-lookup"><span data-stu-id="d52c3-227">Don't roll forward.</span></span> <span data-ttu-id="d52c3-228">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="d52c3-228">Only bind to specified version.</span></span> <span data-ttu-id="d52c3-229">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-229">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="d52c3-230">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="d52c3-230">This value is only recommended for testing.</span></span>

<span data-ttu-id="d52c3-231">Ad eccezione dell'impostazione **Disable**, tutte le impostazioni useranno la versione di patch disponibile più recente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-231">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="d52c3-232">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="d52c3-232">Build copies dependencies</span></span>

<span data-ttu-id="d52c3-233">Il comando `dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet nella cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-233">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="d52c3-234">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-234">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="d52c3-235">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-235">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="d52c3-236">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="d52c3-236">Local tools</span></span>

<span data-ttu-id="d52c3-237">.NET core 3.0 introduce gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="d52c3-237">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="d52c3-238">Gli strumenti locali sono simili agli [strumenti globali](../tools/global-tools.md), ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="d52c3-238">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="d52c3-239">Gli strumenti locali non sono disponibili a livello globale e vengono distribuiti come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="d52c3-239">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="d52c3-240">Se è stata eseguita una prova degli strumenti locali in .NET Core 3.0 Preview 1, ad esempio eseguendo `dotnet tool restore` o `dotnet tool install`, eliminare la cartella della cache degli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="d52c3-240">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="d52c3-241">In caso contrario, gli strumenti locali non funzioneranno in una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-241">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="d52c3-242">Questa cartella si trova in:</span><span class="sxs-lookup"><span data-stu-id="d52c3-242">This folder is located at:</span></span>
>
> <span data-ttu-id="d52c3-243">In macOS: Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="d52c3-243">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="d52c3-244">In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="d52c3-244">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="d52c3-245">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-245">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="d52c3-246">Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="d52c3-246">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="d52c3-247">È possibile distribuire il file manifesto con il codice per assicurarsi che tutti gli utenti che usano il codice possano ripristinare e usare gli stessi strumenti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-247">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="d52c3-248">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="d52c3-248">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="d52c3-249">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="d52c3-249">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="d52c3-250">Per installare questi strumenti a livello globale o locale, è comunque necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="d52c3-250">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="d52c3-251">Nuove opzioni di Global. JSON</span><span class="sxs-lookup"><span data-stu-id="d52c3-251">New global.json options</span></span>

<span data-ttu-id="d52c3-252">Il file *Global. JSON* include nuove opzioni che offrono maggiore flessibilità quando si tenta di definire quale versione del .NET Core SDK viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d52c3-252">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="d52c3-253">Le nuove opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="d52c3-253">The new options are:</span></span>

- <span data-ttu-id="d52c3-254">`allowPrerelease`: indica se il resolver SDK deve prendere in considerazione le versioni provvisorie quando si seleziona la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="d52c3-254">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="d52c3-255">`rollForward`: indica i criteri di rollforward da usare quando si seleziona una versione di SDK, come fallback quando manca una versione specifica dell'SDK o come direttiva per usare una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d52c3-255">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="d52c3-256">Per altre informazioni sulle modifiche, inclusi i valori predefiniti, i valori supportati e le nuove regole di corrispondenza, vedere [Panoramica di Global. JSON](../tools/global-json.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-256">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="d52c3-257">Riduzione delle dimensioni heap del Garbage Collector</span><span class="sxs-lookup"><span data-stu-id="d52c3-257">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="d52c3-258">Le dimensioni heap predefinite del Garbage Collector sono state ridotte tanto che .NET Core usa ora meno memoria.</span><span class="sxs-lookup"><span data-stu-id="d52c3-258">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="d52c3-259">Questa modifica consente un migliore allineamento del budget di allocazione di generazione 0 con le dimensioni della cache dei processori moderni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-259">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="d52c3-260">Supporto per pagine grandi in Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d52c3-260">Garbage Collection Large Page support</span></span>

<span data-ttu-id="d52c3-261">Le pagine di grandi dimensioni, dette anche huge page in Linux, consentono al sistema operativo di creare aree di memoria più grandi rispetto alle dimensioni di pagina native (spesso 4K). In questo modo si migliorano le prestazioni dell'applicazione che richiede pagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-261">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="d52c3-262">Il Garbage Collector può ora essere configurato con l'impostazione **GCLargePages** come funzionalità con consenso esplicito per scegliere di allocare le pagine di grandi dimensioni in Windows.</span><span class="sxs-lookup"><span data-stu-id="d52c3-262">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="d52c3-263">Windows Desktop & COM</span><span class="sxs-lookup"><span data-stu-id="d52c3-263">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="d52c3-264">Programma di installazione .NET Core SDK per Windows</span><span class="sxs-lookup"><span data-stu-id="d52c3-264">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="d52c3-265">Il programma di installazione di Windows Installer (MSI) per Windows è stato modificato a partire da .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d52c3-265">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="d52c3-266">I programmi di installazione di SDK aggiorneranno ora le versioni della banda di funzionalità sul posto.</span><span class="sxs-lookup"><span data-stu-id="d52c3-266">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="d52c3-267">Le bande di funzionalità vengono definite nei gruppi *centinaia* nella sezione *patch* del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-267">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="d52c3-268">Ad esempio, **3.0._101_** e **3.0._201_** sono versioni in due diverse bande di funzionalità, mentre **3.0._101_** e **3.0._199_** appartengono alla stessa banda.</span><span class="sxs-lookup"><span data-stu-id="d52c3-268">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="d52c3-269">Quindi, quando viene installato .NET Core SDK **3.0._101_** , .NET Core SDK **3.0._100_** verrà rimosso dal computer se è esistente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-269">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="d52c3-270">Quando viene installato .NET Core SDK **3.0._200_** nello stesso computer, .NET Core SDK **3.0._101_** non verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="d52c3-270">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="d52c3-271">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-271">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="d52c3-272">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="d52c3-272">Windows desktop</span></span>

<span data-ttu-id="d52c3-273">.NET Core 3.0 supporta applicazioni desktop di Windows che usano Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="d52c3-273">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="d52c3-274">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="d52c3-274">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="d52c3-275">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d52c3-275">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="d52c3-276">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-276">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="d52c3-277">Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="d52c3-277">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="d52c3-278">Per altre informazioni su come convertire un'applicazione .NET Framework esistente, vedere [Convertire progetti WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) e [Convertire progetti Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-278">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="d52c3-279">Modalità con valori DPI alti per WinForms</span><span class="sxs-lookup"><span data-stu-id="d52c3-279">WinForms high DPI</span></span>

<span data-ttu-id="d52c3-280">Le applicazioni di Windows Forms in .NET Core possono impostare la modalità con valori DPI alti usando <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d52c3-280">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d52c3-281">Il metodo `SetHighDpiMode` imposta la modalità con valori DPI alti corrispondente a meno che l'impostazione sia stata configurata in altro modo, ad esempio con `App.Manifest` o P/Invoke prima di `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-281">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="d52c3-282">I valori possibili per `highDpiMode`, espressi dall'enumerazione <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>, sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-282">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="d52c3-283">Per altre informazioni sulle modalità con valori DPI alti, vedere [Sviluppo di applicazioni desktop con valori DPI alti in Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="d52c3-283">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="d52c3-284">Creazione di componenti COM</span><span class="sxs-lookup"><span data-stu-id="d52c3-284">Create COM components</span></span>

<span data-ttu-id="d52c3-285">In Windows è ora possibile creare componenti gestiti COM-Callable.</span><span class="sxs-lookup"><span data-stu-id="d52c3-285">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="d52c3-286">Questa funzionalità è essenziale per usare .NET Core con modelli del componente aggiuntivo COM e anche per assicurare parità con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d52c3-286">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="d52c3-287">A differenza di .NET Framework in cui *mscoree.dll* era usato come server COM, .NET Core aggiungerà un file dll di avvio nativo alla directory *bin* quando si compilerà il componente COM.</span><span class="sxs-lookup"><span data-stu-id="d52c3-287">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="d52c3-288">Per un esempio su come creare e usare un componente COM, vedere la [demo COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="d52c3-288">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="d52c3-289">Interoperabilità nativa di Windows</span><span class="sxs-lookup"><span data-stu-id="d52c3-289">Windows Native Interop</span></span>

<span data-ttu-id="d52c3-290">Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT.</span><span class="sxs-lookup"><span data-stu-id="d52c3-290">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="d52c3-291">Mentre .NET Core supporta **P/Invoke**, .NET Core 3.0 aggiunge la possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-291">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="d52c3-292">Per un esempio di codice, vedere la [demo Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="d52c3-292">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="d52c3-293">Distribuzione di MSIX</span><span class="sxs-lookup"><span data-stu-id="d52c3-293">MSIX Deployment</span></span>

<span data-ttu-id="d52c3-294">[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="d52c3-294">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="d52c3-295">Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d52c3-295">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="d52c3-296">Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d52c3-296">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="d52c3-297">Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="d52c3-297">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="d52c3-298">Miglioramenti per Linux</span><span class="sxs-lookup"><span data-stu-id="d52c3-298">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="d52c3-299">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="d52c3-299">SerialPort for Linux</span></span>

<span data-ttu-id="d52c3-300">.NET Core 3.0 include il supporto di base per <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="d52c3-300">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="d52c3-301">In precedenza, .NET Core supportava solo l'uso di `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="d52c3-301">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="d52c3-302">Per altre informazioni sul supporto limitato per la porta seriale in Linux, vedere il [problema 33146 su GitHub](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="d52c3-302">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="d52c3-303">Docker e limiti di memoria cgroup</span><span class="sxs-lookup"><span data-stu-id="d52c3-303">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="d52c3-304">L'esecuzione di .NET Core 3.0 in Linux con Docker funziona meglio con i limiti di memoria cgroup.</span><span class="sxs-lookup"><span data-stu-id="d52c3-304">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="d52c3-305">Eseguendo un contenitore Docker con limiti di memoria, ad esempio `docker run -m`, il comportamento di .NET Core cambia.</span><span class="sxs-lookup"><span data-stu-id="d52c3-305">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="d52c3-306">Dimensioni heap predefinite del Garbage Collector: massimo 20 MB o il 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="d52c3-306">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="d52c3-307">È possibile impostare dimensioni esplicite come numero assoluto o percentuale di un limite cgroup.</span><span class="sxs-lookup"><span data-stu-id="d52c3-307">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="d52c3-308">Le dimensioni minime del segmento riservato per ogni heap del Garbage Collection sono pari a 16 MB.</span><span class="sxs-lookup"><span data-stu-id="d52c3-308">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="d52c3-309">Le dimensioni riducono il numero di heap creati nei computer.</span><span class="sxs-lookup"><span data-stu-id="d52c3-309">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="d52c3-310">Supporto di GPIO per Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="d52c3-310">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="d52c3-311">Sono stati rilasciati due pacchetti NuGet che è possibile usare per la programmazione GPIO:</span><span class="sxs-lookup"><span data-stu-id="d52c3-311">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="d52c3-312">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="d52c3-312">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="d52c3-313">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="d52c3-313">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="d52c3-314">I pacchetti GPIO includono le API per i dispositivi *GPIO*, *SPI*, *I2C* e *PWM*.</span><span class="sxs-lookup"><span data-stu-id="d52c3-314">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="d52c3-315">Il pacchetto di binding IoT include i binding di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d52c3-315">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="d52c3-316">Per altre informazioni, vedere il [repository GitHub dei dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="d52c3-316">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="d52c3-317">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="d52c3-317">ARM64 Linux support</span></span>

<span data-ttu-id="d52c3-318">.NET Core 3.0 aggiunge il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="d52c3-318">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="d52c3-319">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="d52c3-319">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="d52c3-320">Per altre informazioni, vedere [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) (Stato di ARM64 per .NET Core).</span><span class="sxs-lookup"><span data-stu-id="d52c3-320">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="d52c3-321">Sono disponibili [immagini Docker per .NET Core in ARM64](https://hub.docker.com/r/microsoft/dotnet/) per Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="d52c3-321">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="d52c3-322">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="d52c3-322">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="d52c3-323">Sicurezza -</span><span class="sxs-lookup"><span data-stu-id="d52c3-323">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="d52c3-324">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="d52c3-324">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="d52c3-325">.NET Core sfrutta ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="d52c3-325">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="d52c3-326">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="d52c3-326">With TLS 1.3:</span></span>

- <span data-ttu-id="d52c3-327">La durata della connessione è migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="d52c3-327">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="d52c3-328">La sicurezza è migliorata grazie alla rimozione di vari algoritmi di crittografia obsoleti e non sicuri.</span><span class="sxs-lookup"><span data-stu-id="d52c3-328">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="d52c3-329">Quando è disponibile, .NET Core 3.0 usa **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** in un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="d52c3-329">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="d52c3-330">Quando **OpenSSL 1.1.1** è disponibile, entrambi i tipi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> useranno **TLS 1.3**, supponendo che sia il client sia il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-330">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d52c3-331">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-331">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="d52c3-332">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="d52c3-332">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="d52c3-333">L'esempio seguente di C# 8.0 illustra .NET Core 3.0 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="d52c3-333">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="d52c3-334">Crittografia</span><span class="sxs-lookup"><span data-stu-id="d52c3-334">Cryptography ciphers</span></span>

<span data-ttu-id="d52c3-335">.NET 3.0 aggiunge supporto per le crittografie **AES-GCM** e **AES-CCM** implementate rispettivamente con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> e <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d52c3-335">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="d52c3-336">Sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="d52c3-336">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="d52c3-337">Il codice seguente illustra l'uso della crittografia `AesGcm` per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="d52c3-337">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="d52c3-338">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="d52c3-338">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="d52c3-339">.NET core 3.0 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche da formati standard.</span><span class="sxs-lookup"><span data-stu-id="d52c3-339">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="d52c3-340">Non è necessario usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d52c3-340">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="d52c3-341">Tutti i tipi di chiave, ad esempio *RSA*, *DSA*, *ECDsa* e *ECDiffieHellman*, supportano i formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-341">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="d52c3-342">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="d52c3-342">**Public Key**</span></span>
  - <span data-ttu-id="d52c3-343">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d52c3-343">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="d52c3-344">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="d52c3-344">**Private key**</span></span>
  - <span data-ttu-id="d52c3-345">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d52c3-345">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="d52c3-346">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d52c3-346">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="d52c3-347">Le chiavi RSA supportano anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-347">RSA keys also support:</span></span>

- <span data-ttu-id="d52c3-348">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="d52c3-348">**Public Key**</span></span>
  - <span data-ttu-id="d52c3-349">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="d52c3-349">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="d52c3-350">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="d52c3-350">**Private key**</span></span>
  - <span data-ttu-id="d52c3-351">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="d52c3-351">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="d52c3-352">I metodi di esportazione generano dati binari con codifica DER e i metodi di importazione prevedono lo stesso tipo di comportamento.</span><span class="sxs-lookup"><span data-stu-id="d52c3-352">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="d52c3-353">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-353">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="d52c3-354">I file **PKCS#8** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> e i file **PFX/PKCS#12** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d52c3-354">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d52c3-355">I file **PFX/PKCS#12** possono essere modificati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d52c3-355">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="d52c3-356">Modifiche all'API di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="d52c3-356">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="d52c3-357">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="d52c3-357">Ranges and indices</span></span>

<span data-ttu-id="d52c3-358">Il nuovo tipo <xref:System.Index?displayProperty=nameWithType> può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="d52c3-358">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="d52c3-359">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="d52c3-359">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="d52c3-360">Esiste anche il tipo <xref:System.Range?displayProperty=nameWithType>, costituito da due valori `Index`, uno per l'inizio e uno per la fine, e può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="d52c3-360">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="d52c3-361">È anche possibile poi indicizzare usano un oggetto `Range`, che genera una sezione:</span><span class="sxs-lookup"><span data-stu-id="d52c3-361">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="d52c3-362">Per altre informazioni, vedere l'[esercitazione su intervalli e indici](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-362">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="d52c3-363">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="d52c3-363">Async streams</span></span>

<span data-ttu-id="d52c3-364">Il tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> è una nuova versione asincrona di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d52c3-364">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d52c3-365">Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d52c3-365">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="d52c3-366">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-366">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="d52c3-367">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="d52c3-367">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="d52c3-368">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-368">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="d52c3-369">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-369">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="d52c3-370">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-370">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="d52c3-371">Per altre informazioni, vedere l'[esercitazione sui flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-371">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="d52c3-372">Virgola mobile IEEE</span><span class="sxs-lookup"><span data-stu-id="d52c3-372">IEEE Floating-point</span></span>

<span data-ttu-id="d52c3-373">È in corso l'aggiornamento di API virgola mobile per conformità alla [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="d52c3-373">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="d52c3-374">L'obiettivo di queste modifiche consiste nell'esporre tutte le operazioni **necessarie** e garantire che siano conformi alla specifica IEEE. Per altre informazioni sui miglioramenti a virgola mobile, vedere il post di Blog relativo all' [analisi a virgola mobile e alla formattazione in .NET Core 3,0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) .</span><span class="sxs-lookup"><span data-stu-id="d52c3-374">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="d52c3-375">Di seguito sono riportate le correzioni per analisi e formattazione:</span><span class="sxs-lookup"><span data-stu-id="d52c3-375">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="d52c3-376">Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d52c3-376">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="d52c3-377">Analisi corretta e formattazione dello zero negativo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-377">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="d52c3-378">Analisi corretta di valori `Infinity` e `NaN` con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.</span><span class="sxs-lookup"><span data-stu-id="d52c3-378">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="d52c3-379">Le nuovi API <xref:System.Math?displayProperty=nameWithType> includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-379">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="d52c3-380"><xref:System.Math.BitIncrement(System.Double)> e <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="d52c3-380"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="d52c3-381">Corrispondono alle operazioni IEEE `nextUp` e `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-381">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="d52c3-382">Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="d52c3-382">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="d52c3-383">Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-383">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="d52c3-384"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> e <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="d52c3-384"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="d52c3-385">Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="d52c3-385">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="d52c3-386">Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-386">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="d52c3-387">Corrispondono all'operazione IEEE `logB` che restituisce un valore integrale, restituisce il logaritmo in base 2 integrale del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="d52c3-387">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="d52c3-388">Questo metodo equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d52c3-388">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="d52c3-389">Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d52c3-389">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="d52c3-390">Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2.</span><span class="sxs-lookup"><span data-stu-id="d52c3-390">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="d52c3-391">Gli errori di arrotondamento sono ridotti al minimo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-391">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="d52c3-392">Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add).</span><span class="sxs-lookup"><span data-stu-id="d52c3-392">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="d52c3-393">Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d52c3-393">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="d52c3-394">Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)`, che restituisce `1e308`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-394">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="d52c3-395">L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-395">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="d52c3-396">Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.</span><span class="sxs-lookup"><span data-stu-id="d52c3-396">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="d52c3-397">Intrinseci dipendenti dalla piattaforma .NET</span><span class="sxs-lookup"><span data-stu-id="d52c3-397">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="d52c3-398">Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**.</span><span class="sxs-lookup"><span data-stu-id="d52c3-398">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="d52c3-399">Queste istruzioni consentono di ottenere miglioramenti delle prestazioni significativi in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.</span><span class="sxs-lookup"><span data-stu-id="d52c3-399">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="d52c3-400">Ove appropriato, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-400">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="d52c3-401">Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET).</span><span class="sxs-lookup"><span data-stu-id="d52c3-401">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="d52c3-402">Miglioramento delle API della versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="d52c3-402">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="d52c3-403">A partire da .NET Core 3.0, le API della versione di .NET Core restituiscono le informazioni previste.</span><span class="sxs-lookup"><span data-stu-id="d52c3-403">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="d52c3-404">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d52c3-404">For example:</span></span>

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
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="d52c3-405">Modifica importante:</span><span class="sxs-lookup"><span data-stu-id="d52c3-405">Breaking change.</span></span> <span data-ttu-id="d52c3-406">si tratta di una modifica tecnicamente importante perché è cambiato lo schema di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="d52c3-406">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="d52c3-407">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="d52c3-407">Fast built-in JSON support</span></span>

<span data-ttu-id="d52c3-408">Gli utenti .NET si sono affidati principalmente a [Newtonsoft. JSON](https://www.newtonsoft.com/json) e ad altre librerie JSON più diffuse, che continuano a essere scelte efficaci.</span><span class="sxs-lookup"><span data-stu-id="d52c3-408">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="d52c3-409">`Newtonsoft.Json` usa le stringhe .NET come tipo di dati di base, che è UTF-16 dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="d52c3-409">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="d52c3-410">Il nuovo supporto JSON incorporato è ad alte prestazioni e a bassa allocazione e funziona con testo JSON con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d52c3-410">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="d52c3-411">Per ulteriori informazioni sullo spazio dei nomi e sui tipi di <xref:System.Text.Json>, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52c3-411">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="d52c3-412">Serializzazione JSON in .NET-Panoramica</span><span class="sxs-lookup"><span data-stu-id="d52c3-412">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="d52c3-413">[Come serializzare e deserializzare JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="d52c3-413">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="d52c3-414">Come eseguire la migrazione da Newtonsoft. JSON a System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="d52c3-414">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="d52c3-415">Supporto per HTTP/2</span><span class="sxs-lookup"><span data-stu-id="d52c3-415">HTTP/2 support</span></span>

<span data-ttu-id="d52c3-416">Il tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> supporta il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d52c3-416">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="d52c3-417">Se HTTP/2 è abilitato, la versione del protocollo HTTP viene negoziata tramite TLS/ALPN e HTTP/2 viene usato solo in base alla decisione del server.</span><span class="sxs-lookup"><span data-stu-id="d52c3-417">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="d52c3-418">Il protocollo predefinito rimane HTTP/1.1, anche se HTTP/2 può essere abilitato in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="d52c3-418">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="d52c3-419">In primo luogo, è possibile impostare il messaggio di richiesta HTTP per usare HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="d52c3-419">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="d52c3-420">In secondo luogo, è possibile modificare <xref:System.Net.Http.HttpClient> in modo da usare HTTP/2 per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="d52c3-420">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="d52c3-421">Molto spesso, quando si sviluppa un'applicazione, si vuole usare una connessione non crittografata.</span><span class="sxs-lookup"><span data-stu-id="d52c3-421">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="d52c3-422">Se si è a conoscenza del fatto che l'endpoint di destinazione userà HTTP/2, è possibile attivare connessioni non crittografate per HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d52c3-422">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="d52c3-423">Per attivare queste connessioni è possibile impostare la variabile di ambiente `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` su `1` o abilitarla nel contesto dell'app:</span><span class="sxs-lookup"><span data-stu-id="d52c3-423">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="d52c3-424">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d52c3-424">Next steps</span></span>

- [<span data-ttu-id="d52c3-425">Esaminare le modifiche di rilievo tra .NET Core 2,2 e 3,0.</span><span class="sxs-lookup"><span data-stu-id="d52c3-425">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="d52c3-426">Esaminare le modifiche di rilievo apportate in .NET Core 3,0 per le app Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d52c3-426">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
