---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 10/22/2019
ms.openlocfilehash: 94284a196030d784909c41aae7fef9a5ad3cb52a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937242"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="d50fb-103">Novità di .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d50fb-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="d50fb-104">Questo articolo descrive le novità di .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d50fb-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="d50fb-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="d50fb-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="d50fb-106">Con il componente Windows Desktop di .NET Core 3.0 SDK, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="d50fb-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="d50fb-107">Il componente Windows Desktop è dunque supportato e incluso solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="d50fb-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="d50fb-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d50fb-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="d50fb-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="d50fb-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="d50fb-110">È consigliabile usare [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successive, [Visual Studio per Mac 8,3](/visualstudio/mac/install-preview) o versioni successive o [Visual Studio Code](https://code.visualstudio.com/) con l'  **C# estensione**più recente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="d50fb-111">[Scarica e inizia subito a usare .NET Core 3.0](https://aka.ms/netcore3download) in Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="d50fb-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="d50fb-112">Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="d50fb-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="d50fb-113">.NET Core RC1 è stato considerato pronto per la produzione da Microsoft ed è stato completamente supportato.</span><span class="sxs-lookup"><span data-stu-id="d50fb-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="d50fb-114">Se si usa una versione di anteprima, è necessario passare alla versione RTM per il supporto continuo.</span><span class="sxs-lookup"><span data-stu-id="d50fb-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="d50fb-115">Miglioramenti C# della lingua 8,0</span><span class="sxs-lookup"><span data-stu-id="d50fb-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="d50fb-116">C#8,0 fa anche parte di questa versione, che include la funzionalità dei [tipi di riferimento Nullable](../../csharp/tutorials/nullable-reference-types.md) , i [flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md)e [altri modelli](../../csharp/tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="d50fb-117">Per altre informazioni sulle funzionalità di C# 8.0, vedere [Novità di C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="d50fb-118">Sono stati aggiunti miglioramenti alla lingua per supportare le seguenti funzionalità API descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="d50fb-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="d50fb-119">Intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="d50fb-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="d50fb-120">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="d50fb-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="d50fb-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="d50fb-121">.NET Standard 2.1</span></span>

<span data-ttu-id="d50fb-122">.NET Core 3,0 implementa **.NET Standard 2,1**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="d50fb-123">Tuttavia, il modello di `dotnet new classlib` predefinito genera un progetto che è ancora destinato **.NET Standard 2,0**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="d50fb-124">Per destinarlo a **.NET Standard 2.1**, modificare il file di progetto e la proprietà `TargetFramework` in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="d50fb-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d50fb-125">Se si usa Visual Studio, è necessario [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) perché Visual Studio 2017 non supporta **.NET Standard 2.1** o **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="d50fb-126">Compilazione/distribuzione</span><span class="sxs-lookup"><span data-stu-id="d50fb-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="d50fb-127">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="d50fb-127">Default executables</span></span>

<span data-ttu-id="d50fb-128">Per impostazione predefinita .NET Core ora compila [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="d50fb-128">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="d50fb-129">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="d50fb-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="d50fb-130">In precedenza solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) generavano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-130">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="d50fb-131">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile che corrisponde all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="d50fb-131">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="d50fb-132">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d50fb-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="d50fb-133">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="d50fb-134">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="d50fb-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="d50fb-135">File eseguibili singoli</span><span class="sxs-lookup"><span data-stu-id="d50fb-135">Single-file executables</span></span>

<span data-ttu-id="d50fb-136">Il comando `dotnet publish` supporta la creazione del pacchetto dell'app come file eseguibile singolo specifico per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d50fb-136">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="d50fb-137">Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluse quelle native) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="d50fb-137">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="d50fb-138">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-138">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="d50fb-139">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-139">Startup is faster when the application is run again.</span></span> <span data-ttu-id="d50fb-140">L'applicazione non dovrà ripetere l'estrazione una seconda volta, a meno che sia stata usata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-140">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="d50fb-141">Per pubblicare un file eseguibile singolo, impostare `PublishSingleFile` nel progetto o nella riga di comando usando il comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="d50fb-141">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="d50fb-142">oppure</span><span class="sxs-lookup"><span data-stu-id="d50fb-142">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="d50fb-143">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-143">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="d50fb-144">Collegamento di assembly</span><span class="sxs-lookup"><span data-stu-id="d50fb-144">Assembly linking</span></span>

<span data-ttu-id="d50fb-145">.NET Core SDK 3.0 include uno strumento che consente di ridurre le dimensioni delle app analizzando il linguaggio intermedio (IL) e rimuovendo gli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="d50fb-145">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="d50fb-146">Le app autonome includono tutti gli elementi necessari per eseguire il codice, senza richiedere l'installazione di .NET nel computer host.</span><span class="sxs-lookup"><span data-stu-id="d50fb-146">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="d50fb-147">Tuttavia, per il funzionamento dell'app è spesso sufficiente un piccolo subset del framework, mentre altre librerie inutilizzate possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="d50fb-147">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="d50fb-148">.NET Core include ora un'impostazione che consente l'uso dello strumento [IL Linker](https://github.com/mono/linker) per analizzare il linguaggio intermedio dell'app.</span><span class="sxs-lookup"><span data-stu-id="d50fb-148">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="d50fb-149">Questo strumento rileva il codice necessario e quindi Elimina le librerie inutilizzate.</span><span class="sxs-lookup"><span data-stu-id="d50fb-149">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="d50fb-150">Può quindi ridurre notevolmente le dimensioni di distribuzione di alcune app.</span><span class="sxs-lookup"><span data-stu-id="d50fb-150">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="d50fb-151">Per abilitare questo strumento, aggiungere l'impostazione `<PublishTrimmed>` nel progetto e pubblicare un'app autonoma:</span><span class="sxs-lookup"><span data-stu-id="d50fb-151">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="d50fb-152">Ad esempio, il nuovo modello predefinito per un progetto di console di base "hello world" ha una dimensione di circa 70 MB quando viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d50fb-152">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="d50fb-153">Usando `<PublishTrimmed>` la dimensione viene ridotta fino a circa 30 MB.</span><span class="sxs-lookup"><span data-stu-id="d50fb-153">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="d50fb-154">È importante tenere presente che le applicazioni o i framework, inclusi ASP.NET Core e WPF, che usano la reflection o le funzionalità dinamiche correlate, sono spesso soggetti a interruzioni in caso di rimozione di assembly.</span><span class="sxs-lookup"><span data-stu-id="d50fb-154">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="d50fb-155">Le interruzioni si verificano perché il linker non riconosce questo comportamento dinamico e non è in grado di identificare i tipi di framework necessari per la reflection.</span><span class="sxs-lookup"><span data-stu-id="d50fb-155">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="d50fb-156">Lo strumento IL Linker può essere configurato in modo da riconoscere questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d50fb-156">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="d50fb-157">È importante soprattutto accertarsi di testare l'app dopo la rimozione degli assembly inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="d50fb-157">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="d50fb-158">Per altre informazioni sullo strumento IL Linker, vedere la [documentazione](https://aka.ms/dotnet-illink) o visitare il repository [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="d50fb-158">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="d50fb-159">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="d50fb-159">Tiered compilation</span></span>

<span data-ttu-id="d50fb-160">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) è attiva.</span><span class="sxs-lookup"><span data-stu-id="d50fb-160">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="d50fb-161">Questa funzionalità consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="d50fb-161">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="d50fb-162">Il vantaggio principale della compilazione a livelli (TC) consiste nell'abilitazione di metodi di ricompilazione JIT con un livello lower-quality-but-faster (di minore qualità ma più veloce) o higher-quality-but-slower (di migliore qualità ma più lento).</span><span class="sxs-lookup"><span data-stu-id="d50fb-162">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="d50fb-163">In questo modo è possibile migliorare le prestazioni di un'applicazione nelle sue vari fasi di esecuzione, dall'avvio allo stato stabile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-163">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="d50fb-164">Ciò si differenzia dall'approccio che non usa la compilazione a livelli. In questo caso ogni metodo viene compilato in un solo modo (come per il livello alta qualità), che dà priorità allo stato stabile piuttosto che alle prestazioni all'avvio.</span><span class="sxs-lookup"><span data-stu-id="d50fb-164">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="d50fb-165">Quando TC è abilitato, durante l'avvio di un metodo denominato:</span><span class="sxs-lookup"><span data-stu-id="d50fb-165">When TC is enabled, during startup for a method that is called:</span></span>

- <span data-ttu-id="d50fb-166">Se il metodo dispone di codice con compilazione AOT (ReadyToRun), verrà utilizzato il codice pregenerato.</span><span class="sxs-lookup"><span data-stu-id="d50fb-166">If the method has AOT-compiled code (ReadyToRun), the pregenerated code will be used.</span></span>
- <span data-ttu-id="d50fb-167">In caso contrario, il metodo sarà compilato JIT.</span><span class="sxs-lookup"><span data-stu-id="d50fb-167">Otherwise, the method will be jitted.</span></span> <span data-ttu-id="d50fb-168">In genere, questi metodi sono attualmente generici sui tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d50fb-168">Typically, these methods currently are generics over value types.</span></span>
  - <span data-ttu-id="d50fb-169">JIT rapido produce codice di qualità inferiore più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-169">Quick JIT produces lower-quality code more quickly.</span></span> <span data-ttu-id="d50fb-170">JIT rapido è abilitato per impostazione predefinita in .NET Core 3,0 per i metodi che non contengono cicli ed è preferibile durante l'avvio.</span><span class="sxs-lookup"><span data-stu-id="d50fb-170">Quick JIT is enabled by default in .NET Core 3.0 for methods that do not contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="d50fb-171">Il JIT con ottimizzazione completa produce un codice di qualità superiore più lentamente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-171">The fully-optimizing JIT produces higher-quality code more slowly.</span></span> <span data-ttu-id="d50fb-172">Per i metodi in cui non è possibile usare JIT rapido (ad esempio, se il metodo è attribuito a `[MethodImpl(MethodImplOptions.AggressiveOptimization)]`), viene usato l'ottimizzazione JIT completa.</span><span class="sxs-lookup"><span data-stu-id="d50fb-172">For methods where Quick JIT would not be used (for example, if the method is attributed with `[MethodImpl(MethodImplOptions.AggressiveOptimization)]`), the fully-optimizing JIT is used.</span></span>

<span data-ttu-id="d50fb-173">Infine, dopo che i metodi sono stati chiamati un numero di volte, vengono ricompilato JIT con la JIT completamente ottimizzata in background.</span><span class="sxs-lookup"><span data-stu-id="d50fb-173">Eventually, after methods are called a number of times, they are re-jitted with the fully-optimizing JIT in the background.</span></span>

<span data-ttu-id="d50fb-174">Il codice generato da Quick JIT può essere eseguito più lentamente, allocare più memoria o usare più spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="d50fb-174">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="d50fb-175">Se si verificano problemi, è possibile disabilitare Quick JIT usando questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="d50fb-175">If there are issues, Quick JIT may be disabled using this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="d50fb-176">Per disabilitare completamente la compilazione a livelli, usare questa impostazione nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="d50fb-176">To disable TC completely, use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

<span data-ttu-id="d50fb-177">Tutte le modifiche apportate alle impostazioni precedenti nel file di progetto possono richiedere la reflection di una compilazione pulita (eliminare le directory `obj` e `bin` e ricompilare).</span><span class="sxs-lookup"><span data-stu-id="d50fb-177">Any changes to the above settings in the project file may require a clean build to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="d50fb-178">Immagini ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="d50fb-178">ReadyToRun images</span></span>

<span data-ttu-id="d50fb-179">È possibile migliorare il tempo di avvio delle applicazioni .NET Core compilando gli assembly nel formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="d50fb-179">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="d50fb-180">R2R è un formato di compilazione AOT (Ahead-of-time).</span><span class="sxs-lookup"><span data-stu-id="d50fb-180">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="d50fb-181">I file binari R2R migliorano le prestazioni di avvio riducendo la quantità di lavoro che deve eseguire il compilatore JIT (Just-in-time) durante il caricamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-181">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="d50fb-182">I file binari contengono codice nativo simile a ciò che viene generato dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="d50fb-182">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="d50fb-183">I file binari R2R, tuttavia, sono più grandi poiché contengono sia il codice in linguaggio intermedio, che è comunque necessario per alcuni scenari, sia la versione nativa dello stesso codice.</span><span class="sxs-lookup"><span data-stu-id="d50fb-183">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="d50fb-184">R2R è disponibile solo quando si pubblica un'app autonoma che fa riferimento ad ambienti di runtime specifici (RID), ad esempio Linux x64 o Windows x64.</span><span class="sxs-lookup"><span data-stu-id="d50fb-184">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="d50fb-185">Per compilare il progetto come ReadyToRun, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d50fb-185">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="d50fb-186">Aggiungere l'impostazione `<PublishReadyToRun>` al progetto:</span><span class="sxs-lookup"><span data-stu-id="d50fb-186">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="d50fb-187">Pubblicare un'app autonoma.</span><span class="sxs-lookup"><span data-stu-id="d50fb-187">Publish a self-contained app.</span></span> <span data-ttu-id="d50fb-188">Questo comando, ad esempio, crea un'app autonoma per la versione a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="d50fb-188">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="d50fb-189">Limitazioni per ambienti con più piattaforme o architetture</span><span class="sxs-lookup"><span data-stu-id="d50fb-189">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="d50fb-190">Il compilatore ReadyToRun attualmente non supporta la definizione di più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-190">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="d50fb-191">La compilazione deve essere eseguita per una determinata destinazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-191">You must compile on a given target.</span></span> <span data-ttu-id="d50fb-192">Se, ad esempio, si vogliono immagini R2R per Windows x64, è necessario eseguire il comando di pubblicazione in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-192">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="d50fb-193">Eccezioni relative all'uso di più destinazioni:</span><span class="sxs-lookup"><span data-stu-id="d50fb-193">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="d50fb-194">Windows x64 può essere usato per compilare immagini Windows ARM32, ARM64 e x86.</span><span class="sxs-lookup"><span data-stu-id="d50fb-194">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="d50fb-195">Windows x86 può essere usato per compilare immagini Windows ARM32.</span><span class="sxs-lookup"><span data-stu-id="d50fb-195">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="d50fb-196">Linux x64 può essere usato per compilare immagini Linux ARM32 e ARM64.</span><span class="sxs-lookup"><span data-stu-id="d50fb-196">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="d50fb-197">Runtime/SDK</span><span class="sxs-lookup"><span data-stu-id="d50fb-197">Runtime/SDK</span></span>

### <a name="major-version-roll-forward"></a><span data-ttu-id="d50fb-198">Roll forward alla versione principale</span><span class="sxs-lookup"><span data-stu-id="d50fb-198">Major-version Roll Forward</span></span>

<span data-ttu-id="d50fb-199">.NET core 3.0 introduce una funzionalità con consenso esplicito che consente all'app di eseguire il roll forward alla versione principale più recente di NET Core.</span><span class="sxs-lookup"><span data-stu-id="d50fb-199">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="d50fb-200">È stata aggiunta anche una nuova impostazione per controllare come applicare il roll forward all'app.</span><span class="sxs-lookup"><span data-stu-id="d50fb-200">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="d50fb-201">Questa funzionalità può essere configurata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-201">This can be configured in the following ways:</span></span>

- <span data-ttu-id="d50fb-202">Proprietà file di progetto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="d50fb-202">Project file property: `RollForward`</span></span>
- <span data-ttu-id="d50fb-203">Proprietà file di configurazione runtime: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="d50fb-203">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="d50fb-204">Variabile di ambiente: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="d50fb-204">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="d50fb-205">Argomento della riga di comando: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="d50fb-205">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="d50fb-206">È necessario specificare uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-206">One of the following values must be specified.</span></span> <span data-ttu-id="d50fb-207">Se non viene impostato un valore, l'impostazione **Minor** sarà quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="d50fb-207">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="d50fb-208">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="d50fb-208">**LatestPatch**</span></span>\
<span data-ttu-id="d50fb-209">Esegue il roll forward alla versione di patch più recente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-209">Roll forward to the highest patch version.</span></span> <span data-ttu-id="d50fb-210">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="d50fb-210">This disables minor version roll forward.</span></span>
- <span data-ttu-id="d50fb-211">**Minor**</span><span class="sxs-lookup"><span data-stu-id="d50fb-211">**Minor**</span></span>\
<span data-ttu-id="d50fb-212">Esegue il roll forward alla versione secondaria successiva minima, se la versione secondaria richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="d50fb-212">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="d50fb-213">Se la versione secondaria richiesta è presente, viene usato il criterio **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-213">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="d50fb-214">**Major**</span><span class="sxs-lookup"><span data-stu-id="d50fb-214">**Major**</span></span>\
<span data-ttu-id="d50fb-215">Esegue il roll forward alla versione principale successiva minima e alla versione secondaria minima, se la versione principale richiesta non esiste.</span><span class="sxs-lookup"><span data-stu-id="d50fb-215">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="d50fb-216">Se la versione principale richiesta è presente, viene usato il criterio **Minor**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-216">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="d50fb-217">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="d50fb-217">**LatestMinor**</span></span>\
<span data-ttu-id="d50fb-218">Esegue il roll forward alla versione secondaria più recente, anche se la versione secondaria richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-218">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="d50fb-219">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-219">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="d50fb-220">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="d50fb-220">**LatestMajor**</span></span>\
<span data-ttu-id="d50fb-221">Esegue il roll forward alla versione principale e secondaria più recente, anche se la versione principale richiesta è presente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-221">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="d50fb-222">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-222">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="d50fb-223">**Disable**</span><span class="sxs-lookup"><span data-stu-id="d50fb-223">**Disable**</span></span>\
<span data-ttu-id="d50fb-224">Non esegue il roll forward.</span><span class="sxs-lookup"><span data-stu-id="d50fb-224">Don't roll forward.</span></span> <span data-ttu-id="d50fb-225">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="d50fb-225">Only bind to specified version.</span></span> <span data-ttu-id="d50fb-226">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-226">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="d50fb-227">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="d50fb-227">This value is only recommended for testing.</span></span>

<span data-ttu-id="d50fb-228">Ad eccezione dell'impostazione **Disable**, tutte le impostazioni useranno la versione di patch disponibile più recente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-228">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="d50fb-229">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="d50fb-229">Build copies dependencies</span></span>

<span data-ttu-id="d50fb-230">Il comando `dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet nella cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-230">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="d50fb-231">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-231">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="d50fb-232">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-232">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="d50fb-233">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="d50fb-233">Local tools</span></span>

<span data-ttu-id="d50fb-234">.NET core 3.0 introduce gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="d50fb-234">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="d50fb-235">Gli strumenti locali sono simili agli [strumenti globali](../tools/global-tools.md), ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="d50fb-235">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="d50fb-236">Gli strumenti locali non sono disponibili a livello globale e vengono distribuiti come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="d50fb-236">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="d50fb-237">Se è stata eseguita una prova degli strumenti locali in .NET Core 3.0 Preview 1, ad esempio eseguendo `dotnet tool restore` o `dotnet tool install`, eliminare la cartella della cache degli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="d50fb-237">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="d50fb-238">In caso contrario, gli strumenti locali non funzioneranno in una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-238">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="d50fb-239">Questa cartella si trova in:</span><span class="sxs-lookup"><span data-stu-id="d50fb-239">This folder is located at:</span></span>
>
> <span data-ttu-id="d50fb-240">In macOS: Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="d50fb-240">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="d50fb-241">In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="d50fb-241">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="d50fb-242">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-242">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="d50fb-243">Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="d50fb-243">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="d50fb-244">È possibile distribuire il file manifesto con il codice per assicurarsi che tutti gli utenti che usano il codice possano ripristinare e usare gli stessi strumenti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-244">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="d50fb-245">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="d50fb-245">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="d50fb-246">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="d50fb-246">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="d50fb-247">Per installare questi strumenti a livello globale o locale, è comunque necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="d50fb-247">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="d50fb-248">Riduzione delle dimensioni heap del Garbage Collector</span><span class="sxs-lookup"><span data-stu-id="d50fb-248">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="d50fb-249">Le dimensioni heap predefinite del Garbage Collector sono state ridotte tanto che .NET Core usa ora meno memoria.</span><span class="sxs-lookup"><span data-stu-id="d50fb-249">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="d50fb-250">Questa modifica consente un migliore allineamento del budget di allocazione di generazione 0 con le dimensioni della cache dei processori moderni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-250">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="d50fb-251">Supporto per pagine grandi in Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d50fb-251">Garbage Collection Large Page support</span></span>

<span data-ttu-id="d50fb-252">Le pagine di grandi dimensioni, dette anche huge page in Linux, consentono al sistema operativo di creare aree di memoria più grandi rispetto alle dimensioni di pagina native (spesso 4K). In questo modo si migliorano le prestazioni dell'applicazione che richiede pagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-252">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="d50fb-253">Il Garbage Collector può ora essere configurato con l'impostazione **GCLargePages** come funzionalità con consenso esplicito per scegliere di allocare le pagine di grandi dimensioni in Windows.</span><span class="sxs-lookup"><span data-stu-id="d50fb-253">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="d50fb-254">Windows Desktop & COM</span><span class="sxs-lookup"><span data-stu-id="d50fb-254">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="d50fb-255">Programma di installazione .NET Core SDK per Windows</span><span class="sxs-lookup"><span data-stu-id="d50fb-255">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="d50fb-256">Il programma di installazione di Windows Installer (MSI) per Windows è stato modificato a partire da .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d50fb-256">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="d50fb-257">I programmi di installazione di SDK aggiorneranno ora le versioni della banda di funzionalità sul posto.</span><span class="sxs-lookup"><span data-stu-id="d50fb-257">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="d50fb-258">Le bande di funzionalità vengono definite nei gruppi *centinaia* nella sezione *patch* del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-258">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="d50fb-259">Ad esempio, **3.0._101_** e **3.0._201_** sono versioni in due diverse bande di funzionalità, mentre **3.0._101_** e **3.0._199_** appartengono alla stessa banda.</span><span class="sxs-lookup"><span data-stu-id="d50fb-259">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="d50fb-260">Quindi, quando viene installato .NET Core SDK **3.0._101_** , .NET Core SDK **3.0._100_** verrà rimosso dal computer se è esistente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-260">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="d50fb-261">Quando viene installato .NET Core SDK **3.0._200_** nello stesso computer, .NET Core SDK **3.0._101_** non verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="d50fb-261">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="d50fb-262">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-262">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="d50fb-263">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="d50fb-263">Windows desktop</span></span>

<span data-ttu-id="d50fb-264">.NET Core 3.0 supporta applicazioni desktop di Windows che usano Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="d50fb-264">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="d50fb-265">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="d50fb-265">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="d50fb-266">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d50fb-266">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="d50fb-267">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-267">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="d50fb-268">Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="d50fb-268">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="d50fb-269">Per altre informazioni su come convertire un'applicazione .NET Framework esistente, vedere [Convertire progetti WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) e [Convertire progetti Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-269">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="d50fb-270">Modalità con valori DPI alti per WinForms</span><span class="sxs-lookup"><span data-stu-id="d50fb-270">WinForms high DPI</span></span>

<span data-ttu-id="d50fb-271">Le applicazioni di Windows Forms in .NET Core possono impostare la modalità con valori DPI alti usando <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d50fb-271">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d50fb-272">Il metodo `SetHighDpiMode` imposta la modalità con valori DPI alti corrispondente a meno che l'impostazione sia stata configurata in altro modo, ad esempio con `App.Manifest` o P/Invoke prima di `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-272">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="d50fb-273">I valori possibili per `highDpiMode`, espressi dall'enumerazione <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>, sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-273">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="d50fb-274">Per altre informazioni sulle modalità con valori DPI alti, vedere [Sviluppo di applicazioni desktop con valori DPI alti in Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="d50fb-274">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="d50fb-275">Creazione di componenti COM</span><span class="sxs-lookup"><span data-stu-id="d50fb-275">Create COM components</span></span>

<span data-ttu-id="d50fb-276">In Windows è ora possibile creare componenti gestiti COM-Callable.</span><span class="sxs-lookup"><span data-stu-id="d50fb-276">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="d50fb-277">Questa funzionalità è essenziale per usare .NET Core con modelli del componente aggiuntivo COM e anche per assicurare parità con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d50fb-277">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="d50fb-278">A differenza di .NET Framework in cui *mscoree.dll* era usato come server COM, .NET Core aggiungerà un file dll di avvio nativo alla directory *bin* quando si compilerà il componente COM.</span><span class="sxs-lookup"><span data-stu-id="d50fb-278">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="d50fb-279">Per un esempio su come creare e usare un componente COM, vedere la [demo COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="d50fb-279">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="d50fb-280">Interoperabilità nativa di Windows</span><span class="sxs-lookup"><span data-stu-id="d50fb-280">Windows Native Interop</span></span>

<span data-ttu-id="d50fb-281">Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT.</span><span class="sxs-lookup"><span data-stu-id="d50fb-281">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="d50fb-282">Mentre .NET Core supporta **P/Invoke**, .NET Core 3.0 aggiunge la possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-282">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="d50fb-283">Per un esempio di codice, vedere la [demo Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="d50fb-283">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="d50fb-284">Distribuzione di MSIX</span><span class="sxs-lookup"><span data-stu-id="d50fb-284">MSIX Deployment</span></span>

<span data-ttu-id="d50fb-285">[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="d50fb-285">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="d50fb-286">Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d50fb-286">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="d50fb-287">Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d50fb-287">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="d50fb-288">Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="d50fb-288">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="d50fb-289">Miglioramenti per Linux</span><span class="sxs-lookup"><span data-stu-id="d50fb-289">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="d50fb-290">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="d50fb-290">SerialPort for Linux</span></span>

<span data-ttu-id="d50fb-291">.NET Core 3.0 include il supporto di base per <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="d50fb-291">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="d50fb-292">In precedenza, .NET Core supportava solo l'uso di `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="d50fb-292">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="d50fb-293">Per altre informazioni sul supporto limitato per la porta seriale in Linux, vedere il [problema 33146 su GitHub](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="d50fb-293">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="d50fb-294">Docker e limiti di memoria cgroup</span><span class="sxs-lookup"><span data-stu-id="d50fb-294">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="d50fb-295">L'esecuzione di .NET Core 3.0 in Linux con Docker funziona meglio con i limiti di memoria cgroup.</span><span class="sxs-lookup"><span data-stu-id="d50fb-295">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="d50fb-296">Eseguendo un contenitore Docker con limiti di memoria, ad esempio `docker run -m`, il comportamento di .NET Core cambia.</span><span class="sxs-lookup"><span data-stu-id="d50fb-296">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="d50fb-297">Dimensioni heap predefinite del Garbage Collector: massimo 20 MB o il 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="d50fb-297">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="d50fb-298">È possibile impostare dimensioni esplicite come numero assoluto o percentuale di un limite cgroup.</span><span class="sxs-lookup"><span data-stu-id="d50fb-298">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="d50fb-299">Le dimensioni minime del segmento riservato per ogni heap del Garbage Collection sono pari a 16 MB.</span><span class="sxs-lookup"><span data-stu-id="d50fb-299">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="d50fb-300">Le dimensioni riducono il numero di heap creati nei computer.</span><span class="sxs-lookup"><span data-stu-id="d50fb-300">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="d50fb-301">Supporto di GPIO per Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="d50fb-301">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="d50fb-302">Sono stati rilasciati due pacchetti NuGet che è possibile usare per la programmazione GPIO:</span><span class="sxs-lookup"><span data-stu-id="d50fb-302">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="d50fb-303">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="d50fb-303">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="d50fb-304">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="d50fb-304">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="d50fb-305">I pacchetti GPIO includono le API per i dispositivi *GPIO*, *SPI*, *I2C* e *PWM*.</span><span class="sxs-lookup"><span data-stu-id="d50fb-305">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="d50fb-306">Il pacchetto di binding IoT include i binding di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d50fb-306">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="d50fb-307">Per altre informazioni, vedere il [repository GitHub dei dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="d50fb-307">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="d50fb-308">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="d50fb-308">ARM64 Linux support</span></span>

<span data-ttu-id="d50fb-309">.NET Core 3.0 aggiunge il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="d50fb-309">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="d50fb-310">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="d50fb-310">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="d50fb-311">Per altre informazioni, vedere [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) (Stato di ARM64 per .NET Core).</span><span class="sxs-lookup"><span data-stu-id="d50fb-311">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="d50fb-312">Sono disponibili [immagini Docker per .NET Core in ARM64](https://hub.docker.com/r/microsoft/dotnet/) per Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="d50fb-312">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="d50fb-313">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-313">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="d50fb-314">Sicurezza -</span><span class="sxs-lookup"><span data-stu-id="d50fb-314">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="d50fb-315">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="d50fb-315">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="d50fb-316">.NET Core sfrutta ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="d50fb-316">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="d50fb-317">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="d50fb-317">With TLS 1.3:</span></span>

- <span data-ttu-id="d50fb-318">La durata della connessione è migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="d50fb-318">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="d50fb-319">La sicurezza è migliorata grazie alla rimozione di vari algoritmi di crittografia obsoleti e non sicuri.</span><span class="sxs-lookup"><span data-stu-id="d50fb-319">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="d50fb-320">Quando è disponibile, .NET Core 3.0 usa **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** in un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="d50fb-320">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="d50fb-321">Quando **OpenSSL 1.1.1** è disponibile, entrambi i tipi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> useranno **TLS 1.3**, supponendo che sia il client sia il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-321">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d50fb-322">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-322">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="d50fb-323">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-323">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="d50fb-324">L'esempio seguente di C# 8.0 illustra .NET Core 3.0 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="d50fb-324">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="d50fb-325">Crittografia</span><span class="sxs-lookup"><span data-stu-id="d50fb-325">Cryptography ciphers</span></span>

<span data-ttu-id="d50fb-326">.NET 3.0 aggiunge supporto per le crittografie **AES-GCM** e **AES-CCM** implementate rispettivamente con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> e <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d50fb-326">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="d50fb-327">Sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="d50fb-327">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="d50fb-328">Il codice seguente illustra l'uso della crittografia `AesGcm` per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="d50fb-328">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="d50fb-329">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="d50fb-329">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="d50fb-330">.NET core 3.0 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche da formati standard.</span><span class="sxs-lookup"><span data-stu-id="d50fb-330">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="d50fb-331">Non è necessario usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d50fb-331">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="d50fb-332">Tutti i tipi di chiave, ad esempio *RSA*, *DSA*, *ECDsa* e *ECDiffieHellman*, supportano i formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-332">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="d50fb-333">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="d50fb-333">**Public Key**</span></span>
  - <span data-ttu-id="d50fb-334">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d50fb-334">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="d50fb-335">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="d50fb-335">**Private key**</span></span>
  - <span data-ttu-id="d50fb-336">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d50fb-336">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="d50fb-337">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="d50fb-337">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="d50fb-338">Le chiavi RSA supportano anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-338">RSA keys also support:</span></span>

- <span data-ttu-id="d50fb-339">**Chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="d50fb-339">**Public Key**</span></span>
  - <span data-ttu-id="d50fb-340">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="d50fb-340">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="d50fb-341">**Chiave privata**</span><span class="sxs-lookup"><span data-stu-id="d50fb-341">**Private key**</span></span>
  - <span data-ttu-id="d50fb-342">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="d50fb-342">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="d50fb-343">I metodi di esportazione generano dati binari con codifica DER e i metodi di importazione prevedono lo stesso tipo di comportamento.</span><span class="sxs-lookup"><span data-stu-id="d50fb-343">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="d50fb-344">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-344">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="d50fb-345">I file **PKCS#8** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> e i file **PFX/PKCS#12** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d50fb-345">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d50fb-346">I file **PFX/PKCS#12** possono essere modificati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d50fb-346">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="d50fb-347">Modifiche all'API di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="d50fb-347">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="d50fb-348">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="d50fb-348">Ranges and indices</span></span>

<span data-ttu-id="d50fb-349">Il nuovo tipo <xref:System.Index?displayProperty=nameWithType> può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="d50fb-349">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="d50fb-350">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="d50fb-350">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="d50fb-351">Esiste anche il tipo <xref:System.Range?displayProperty=nameWithType>, costituito da due valori `Index`, uno per l'inizio e uno per la fine, e può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="d50fb-351">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="d50fb-352">È anche possibile poi indicizzare usano un oggetto `Range`, che genera una sezione:</span><span class="sxs-lookup"><span data-stu-id="d50fb-352">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="d50fb-353">Per altre informazioni, vedere l'[esercitazione su intervalli e indici](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-353">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="d50fb-354">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="d50fb-354">Async streams</span></span>

<span data-ttu-id="d50fb-355">Il tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> è una nuova versione asincrona di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d50fb-355">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d50fb-356">Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d50fb-356">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="d50fb-357">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-357">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="d50fb-358">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="d50fb-358">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="d50fb-359">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-359">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="d50fb-360">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-360">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="d50fb-361">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-361">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="d50fb-362">Per altre informazioni, vedere l'[esercitazione sui flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-362">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="d50fb-363">Virgola mobile IEEE</span><span class="sxs-lookup"><span data-stu-id="d50fb-363">IEEE Floating-point</span></span>

<span data-ttu-id="d50fb-364">È in corso l'aggiornamento di API virgola mobile per conformità alla [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="d50fb-364">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="d50fb-365">L'obiettivo di queste modifiche consiste nell'esporre tutte le operazioni **necessarie** e garantire che siano conformi alla specifica IEEE. Per altre informazioni sui miglioramenti a virgola mobile, vedere il post di Blog relativo all' [analisi a virgola mobile e alla formattazione in .NET Core 3,0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) .</span><span class="sxs-lookup"><span data-stu-id="d50fb-365">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="d50fb-366">Di seguito sono riportate le correzioni per analisi e formattazione:</span><span class="sxs-lookup"><span data-stu-id="d50fb-366">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="d50fb-367">Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d50fb-367">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="d50fb-368">Analisi corretta e formattazione dello zero negativo.</span><span class="sxs-lookup"><span data-stu-id="d50fb-368">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="d50fb-369">Analisi corretta di valori `Infinity` e `NaN` con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.</span><span class="sxs-lookup"><span data-stu-id="d50fb-369">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="d50fb-370">Le nuovi API <xref:System.Math?displayProperty=nameWithType> includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d50fb-370">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="d50fb-371"><xref:System.Math.BitIncrement(System.Double)> e <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="d50fb-371"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="d50fb-372">Corrispondono alle operazioni IEEE `nextUp` e `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-372">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="d50fb-373">Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="d50fb-373">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="d50fb-374">Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-374">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="d50fb-375"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> e <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="d50fb-375"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="d50fb-376">Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="d50fb-376">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="d50fb-377">Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-377">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="d50fb-378">Corrispondono all'operazione IEEE `logB` che restituisce un valore integrale, restituisce il logaritmo in base 2 integrale del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="d50fb-378">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="d50fb-379">Questo metodo equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d50fb-379">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="d50fb-380">Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d50fb-380">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="d50fb-381">Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2.</span><span class="sxs-lookup"><span data-stu-id="d50fb-381">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="d50fb-382">Gli errori di arrotondamento sono ridotti al minimo.</span><span class="sxs-lookup"><span data-stu-id="d50fb-382">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="d50fb-383">Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add).</span><span class="sxs-lookup"><span data-stu-id="d50fb-383">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="d50fb-384">Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d50fb-384">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="d50fb-385">Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)` che restituisce `1e308`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-385">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="d50fb-386">L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-386">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="d50fb-387">Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-387">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="d50fb-388">Intrinseci dipendenti dalla piattaforma .NET</span><span class="sxs-lookup"><span data-stu-id="d50fb-388">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="d50fb-389">Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**.</span><span class="sxs-lookup"><span data-stu-id="d50fb-389">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="d50fb-390">Queste istruzioni consentono di ottenere miglioramenti delle prestazioni significativi in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.</span><span class="sxs-lookup"><span data-stu-id="d50fb-390">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="d50fb-391">Ove appropriato, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-391">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="d50fb-392">Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET).</span><span class="sxs-lookup"><span data-stu-id="d50fb-392">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="d50fb-393">Miglioramento delle API della versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="d50fb-393">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="d50fb-394">A partire da .NET Core 3.0, le API della versione di .NET Core restituiscono le informazioni previste.</span><span class="sxs-lookup"><span data-stu-id="d50fb-394">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="d50fb-395">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d50fb-395">For example:</span></span>

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
> <span data-ttu-id="d50fb-396">Modifica importante:</span><span class="sxs-lookup"><span data-stu-id="d50fb-396">Breaking change.</span></span> <span data-ttu-id="d50fb-397">si tratta di una modifica tecnicamente importante perché è cambiato lo schema di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="d50fb-397">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="d50fb-398">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="d50fb-398">Fast built-in JSON support</span></span>

<span data-ttu-id="d50fb-399">Gli utenti .NET si sono ampiamente basati su [**Json.NET**](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide.</span><span class="sxs-lookup"><span data-stu-id="d50fb-399">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="d50fb-400">Come tipo di dati di base, **Json.NET** usa le stringhe .NET, che in realtà sono UTF-16.</span><span class="sxs-lookup"><span data-stu-id="d50fb-400">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="d50fb-401">Il nuovo supporto JSON predefinito offre prestazioni elevate, bassa allocazione ed è basato su `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="d50fb-401">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="d50fb-402">Per altre informazioni sullo spazio dei nomi e sui tipi di <xref:System.Text.Json>, vedere [serializzazione JSON in .NET-Panoramica](../../standard/serialization/system-text-json-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-402">For more information about the <xref:System.Text.Json> namespace and types, see [JSON serialization in .NET - overview](../../standard/serialization/system-text-json-overview.md).</span></span> <span data-ttu-id="d50fb-403">Per esercitazioni sugli scenari comuni di serializzazione JSON, vedere [come serializzare e deserializzare JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="d50fb-403">For tutorials on common JSON serialization scenarios, see [How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>

### <a name="http2-support"></a><span data-ttu-id="d50fb-404">Supporto per HTTP/2</span><span class="sxs-lookup"><span data-stu-id="d50fb-404">HTTP/2 support</span></span>

<span data-ttu-id="d50fb-405">Il tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> supporta il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d50fb-405">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="d50fb-406">Se HTTP/2 è abilitato, la versione del protocollo HTTP viene negoziata tramite TLS/ALPN e HTTP/2 viene usato solo in base alla decisione del server.</span><span class="sxs-lookup"><span data-stu-id="d50fb-406">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="d50fb-407">Il protocollo predefinito rimane HTTP/1.1, anche se HTTP/2 può essere abilitato in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="d50fb-407">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="d50fb-408">In primo luogo, è possibile impostare il messaggio di richiesta HTTP per usare HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="d50fb-408">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="d50fb-409">In secondo luogo, è possibile modificare <xref:System.Net.Http.HttpClient> in modo da usare HTTP/2 per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="d50fb-409">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="d50fb-410">Molto spesso, quando si sviluppa un'applicazione, si vuole usare una connessione non crittografata.</span><span class="sxs-lookup"><span data-stu-id="d50fb-410">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="d50fb-411">Se si è a conoscenza del fatto che l'endpoint di destinazione userà HTTP/2, è possibile attivare connessioni non crittografate per HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d50fb-411">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="d50fb-412">Per attivare queste connessioni è possibile impostare la variabile di ambiente `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` su `1` o abilitarla nel contesto dell'app:</span><span class="sxs-lookup"><span data-stu-id="d50fb-412">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="d50fb-413">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d50fb-413">Next steps</span></span>

- [<span data-ttu-id="d50fb-414">Esaminare le modifiche di rilievo tra .NET Core 2,2 e 3,0.</span><span class="sxs-lookup"><span data-stu-id="d50fb-414">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="d50fb-415">Esaminare le modifiche di rilievo apportate in .NET Core 3,0 per le app Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d50fb-415">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
