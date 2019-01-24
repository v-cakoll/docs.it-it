---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 26fb7cb25b9bf7f00f87059fbe1848763f7f175d
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415546"
---
# <a name="whats-new-in-net-core-30-preview-1"></a><span data-ttu-id="c481a-103">Novità di .NET Core 3.0 (Preview 1)</span><span class="sxs-lookup"><span data-stu-id="c481a-103">What's new in .NET Core 3.0 (Preview 1)</span></span>

<span data-ttu-id="c481a-104">Questo articolo descrive le novità di .NET Core 3.0 (Preview 1).</span><span class="sxs-lookup"><span data-stu-id="c481a-104">This article describes what is new in .NET Core 3.0 (preview 1).</span></span> <span data-ttu-id="c481a-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="c481a-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="c481a-106">Utilizzando un componente di .NET Core 3.0 denominato Windows Desktop, è possibile convertire le applicazioni WPF (Windows Presentation Foundation) Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c481a-106">By utilizing a .NET Core 3.0 component called Windows Desktop, you can port your Windows Forms Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="c481a-107">Il componente Windows Desktop è dunque supportato solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="c481a-107">To be clear, the Windows Desktop component is only supported on Windows.</span></span> <span data-ttu-id="c481a-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="c481a-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="c481a-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="c481a-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="c481a-110">[Scaricare e iniziare subito a usare .NET Core 3 Preview 1](https://aka.ms/netcore3download) in Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="c481a-110">[Download and get started with .NET Core 3 Preview 1](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="c481a-111">È possibile visualizzare i dettagli completi della versione nelle [note sulla versione di .NET Core 3 Preview 1](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="c481a-111">You can see complete details of the release in the [.NET Core 3 Preview 1 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="c481a-112">Per altre informazioni, vedere l'[annuncio relativo a .NET Core 3.0 Preview 1](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span><span class="sxs-lookup"><span data-stu-id="c481a-112">For more information, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="c481a-113">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="c481a-113">.NET Standard 2.1</span></span>

<span data-ttu-id="c481a-114">.NET Core 3.0 implementa .NET Standard 2.1.</span><span class="sxs-lookup"><span data-stu-id="c481a-114">.NET Core 3.0 implements .NET Standard 2.1.</span></span>

## <a name="default-executables"></a><span data-ttu-id="c481a-115">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="c481a-115">Default executables</span></span>

<span data-ttu-id="c481a-116">Per impostazione predefinita .NET Core compilerà ora i [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="c481a-116">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="c481a-117">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="c481a-117">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="c481a-118">Finora solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) producevano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c481a-118">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="c481a-119">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile purché corrisponda all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="c481a-119">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="c481a-120">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c481a-120">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="c481a-121">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c481a-121">You can double-click on the executable.</span></span>
* <span data-ttu-id="c481a-122">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="c481a-122">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="c481a-123">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="c481a-123">Build copies dependencies</span></span>

<span data-ttu-id="c481a-124">`dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet alla cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="c481a-124">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="c481a-125">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="c481a-125">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="c481a-126">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c481a-126">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="c481a-127">Strumenti dotnet locali</span><span class="sxs-lookup"><span data-stu-id="c481a-127">Local dotnet tools</span></span>

<span data-ttu-id="c481a-128">Mentre .NET Core 2.1 supportava strumenti globali, .NET Core 3.0 ha ora strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="c481a-128">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="c481a-129">Gli strumenti locali sono simili agli strumenti globali, ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="c481a-129">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="c481a-130">Ciò consente di usare strumenti specifici per ogni progetto e ogni repository.</span><span class="sxs-lookup"><span data-stu-id="c481a-130">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="c481a-131">Gli strumenti installati in locale non sono disponibili a livello globale.</span><span class="sxs-lookup"><span data-stu-id="c481a-131">Any tool installed locally isn't available globally.</span></span>

<span data-ttu-id="c481a-132">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c481a-132">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="c481a-133">Questo file manifesto definisce gli strumenti che devono essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="c481a-133">This manifest file defines the tools to be available.</span></span> <span data-ttu-id="c481a-134">Creando questo file manifesto nella radice del repository, si ha la certezza che chiunque cloni il codice non possa ripristinare e usare gli strumenti necessari per lavorare in modo corretto con il codice.</span><span class="sxs-lookup"><span data-stu-id="c481a-134">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="c481a-135">Quando il file manifesto degli strumenti locali è disponibile, usare il comando seguente per scaricare e installare automaticamente tali strumenti in locale:</span><span class="sxs-lookup"><span data-stu-id="c481a-135">When the local tools manifest file is available, use the following command to automatically download and install those tools locally:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="c481a-136">Eseguire uno strumento locale con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c481a-136">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="c481a-137">Quando viene chiamato uno strumento locale, dotnet cerca un manifesto nella struttura di directory.</span><span class="sxs-lookup"><span data-stu-id="c481a-137">When a local tool is called, dotnet searches for a manifest up the directory structure.</span></span> <span data-ttu-id="c481a-138">Quando viene trovato un file manifesto degli strumenti, viene eseguita la ricerca dello strumento richiesto.</span><span class="sxs-lookup"><span data-stu-id="c481a-138">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="c481a-139">Lo strumento, se trovato, include le informazioni necessarie per trovare lo strumento nel percorso globale dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c481a-139">If the tool is found, it includes the information needed to find the tool in the NuGet global packages location.</span></span> 

<span data-ttu-id="c481a-140">Se lo strumento viene trovato nel manifesto, ma non la cache, l'utente visualizza un errore.</span><span class="sxs-lookup"><span data-stu-id="c481a-140">If the tool is found in the manifest, but not the cache, the user receives an error.</span></span> <span data-ttu-id="c481a-141">Il messaggio verrà migliorato dopo l'anteprima 1 per chiedere all'utente di eseguire `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="c481a-141">The message will be improved after Preview 1 to request the user run `dotnet tool restore`.</span></span>

<span data-ttu-id="c481a-142">Per aggiungere gli strumenti locali a una directory, è necessario creare prima il file manifesto degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="c481a-142">To add local tools to a directory, you need to first create the tool manifest file.</span></span> <span data-ttu-id="c481a-143">Dopo l'anteprima 1, sarà disponibile un meccanismo per la creazione di file manifesto degli strumenti, ad esempio un nuovo modello dotnet.</span><span class="sxs-lookup"><span data-stu-id="c481a-143">After Preview 1, we will offer a mechanism for creating tool manifest files, such as a dotnet new template.</span></span> <span data-ttu-id="c481a-144">Per l'anteprima 1 è necessario creare il file denominato `dotnet-tools.json` con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="c481a-144">For Preview 1 you must create the file named `dotnet-tools.json` with the following contents:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="c481a-145">Dopo aver creato il manifesto, è possibile aggiungere gli strumenti locali usando:</span><span class="sxs-lookup"><span data-stu-id="c481a-145">Once the manifest is created, you can add local tools to it using:</span></span>

```console
dotnet tool install <toolPackageId>
```

<span data-ttu-id="c481a-146">Questo comando installa la versione più recente dello strumento, a meno che non venga specificata un'altra versione.</span><span class="sxs-lookup"><span data-stu-id="c481a-146">This command installs the latest version of the tool, unless another version is specified.</span></span>  <span data-ttu-id="c481a-147">Anche se è stata scelta automaticamente la versione più recente, la versione dello strumento viene scritta nel file manifesto dello strumento per consentire il ripristino o l'esecuzione della versione corretta dello strumento.</span><span class="sxs-lookup"><span data-stu-id="c481a-147">Even if the latest version was automatically chosen, the version of the tool is written into the tool manifest file to allow the correct version of the tool to be restored or run.</span></span>

<span data-ttu-id="c481a-148">Il file manifesto dello strumento è progettato per consentire la modifica manuale, ad esempio per aggiornare la versione necessaria per usare il repository.</span><span class="sxs-lookup"><span data-stu-id="c481a-148">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span>

<span data-ttu-id="c481a-149">Ecco un file `dotnet-tools.json` di esempio:</span><span class="sxs-lookup"><span data-stu-id="c481a-149">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="c481a-150">Per rimuovere uno strumento dal file manifesto, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c481a-150">To remove a tool from the tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <toolPackageId>
```

<span data-ttu-id="c481a-151">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="c481a-151">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="c481a-152">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="c481a-152">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="c481a-153">Per installarli a livello globale o locale, è ancora necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="c481a-153">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="c481a-154">Per altre informazioni, vedere [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288) (Documentazione dell'anteprima preliminare degli strumenti locali).</span><span class="sxs-lookup"><span data-stu-id="c481a-154">For more information, see [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="c481a-155">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="c481a-155">Windows desktop</span></span>

<span data-ttu-id="c481a-156">A partire da .NET Core 3.0 Preview 1, è possibile compilare applicazioni desktop di Windows con WPF e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c481a-156">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="c481a-157">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="c481a-157">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="c481a-158">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c481a-158">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="c481a-159">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="c481a-159">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="c481a-160">È anche possibile aprire, avviare ed eseguire il debug di progetti .NET Core 3.0 WPF e Windows Form in Visual Studio 2019 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="c481a-160">You can also open, launch, and debug .NET Core 3.0 WPF and Windows Forms projects in Visual Studio 2019 Preview 1.</span></span> <span data-ttu-id="c481a-161">Anche se attualmente è possibile aprire questi progetti in Visual Studio 2017 15.9, questo non è uno scenario supportato (ed è necessario [abilitare le anteprime](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span><span class="sxs-lookup"><span data-stu-id="c481a-161">It's currently possible to open these projects in Visual Studio 2017 15.9, however, it isn't a supported scenario (and you need to [enable previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span></span>

<span data-ttu-id="c481a-162">I nuovi progetti sono uguali ai progetti .NET Core esistenti, con alcune aggiunte.</span><span class="sxs-lookup"><span data-stu-id="c481a-162">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="c481a-163">Di seguito è riportato il confronto tra il progetto console .NET Core di base e un progetto Windows Form e WPF di base.</span><span class="sxs-lookup"><span data-stu-id="c481a-163">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="c481a-164">In un progetto console .NET Core il progetto usa l'SDK `Microsoft.NET.Sdk` e dichiara una dipendenza da .NET Core 3.0 tramite il framework di destinazione `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="c481a-164">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="c481a-165">Per creare un'app desktop di Windows, usare l'SDK `Microsoft.NET.Sdk.WindowsDesktop` e scegliere quale framework interfaccia utente usare:</span><span class="sxs-lookup"><span data-stu-id="c481a-165">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c481a-166">Per scegliere Windows Form invece di WPF, impostare `UseWindowsForms` invece che `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="c481a-166">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c481a-167">Sia `UseWPF` che `UseWindowsForms` possono essere impostati su `true` se l'app usa entrambi i framework, ad esempio quando una finestra di dialogo di Windows Form ospita un controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="c481a-167">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="c481a-168">Condividere commenti e suggerimenti nei repository [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) e [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="c481a-168">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="c481a-169">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="c481a-169">Fast built-in JSON support</span></span>

<span data-ttu-id="c481a-170">`System.Text.Json.Utf8JsonReader` è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="c481a-170">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="c481a-171">`Utf8JsonReader` è un tipo di base di basso livello, che può essere sfruttato per compilare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c481a-171">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="c481a-172">La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di [Json.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="c481a-172">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from [Json.NET](https://www.newtonsoft.com/json).</span></span> <span data-ttu-id="c481a-173">Non viene allocato fino a quando non è necessario realizzare i token JSON come stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="c481a-173">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="c481a-174">Questa nuova API includerà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c481a-174">This new API will include the following components:</span></span>

* <span data-ttu-id="c481a-175">Nell'anteprima 1: lettore JSON (accesso sequenziale)</span><span class="sxs-lookup"><span data-stu-id="c481a-175">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="c481a-176">Presto disponibili: writer JSON, DOM (accesso casuale), serializzatore poco, deserializzatore poco</span><span class="sxs-lookup"><span data-stu-id="c481a-176">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="c481a-177">Ecco il ciclo del lettore di base per `Utf8JsonReader` che può essere usato come punto iniziale:</span><span class="sxs-lookup"><span data-stu-id="c481a-177">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

<span data-ttu-id="c481a-178">L'ecosistema .NET si è basato su [Json.NET](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide.</span><span class="sxs-lookup"><span data-stu-id="c481a-178">The .NET ecosystem has relied on [Json.NET](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="c481a-179">Come tipo di dati di base JSON.NET usa le stringhe .NET, che in realtà sono UTF-16.</span><span class="sxs-lookup"><span data-stu-id="c481a-179">JSON.NET uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span> 

<span data-ttu-id="c481a-180">In .NET Core 2.1 e 3.0 sono state aggiunte nuove API per poter scrivere API JSON (ad esempio, `Utf8JsonReader`) che richiedono molta meno memoria, in base sull'uso di stringhe UTF-8 e `Span<T>`, e soddisfano meglio le esigenze delle applicazioni a velocità effettiva elevata, come Kestrel, il server Web ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c481a-180">In .NET Core 2.1 and 3.0, we added new APIs that makes it possible to write JSON APIs (such as `Utf8JsonReader`) that require much less memory, based on using `Span<T>` and UTF-8 strings, and better serve the needs of high-throughput applications like Kestrel, ASP.NET Core web server.</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="c481a-181">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="c481a-181">Ranges and indices</span></span>

<span data-ttu-id="c481a-182">Il nuovo tipo `Index` può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="c481a-182">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="c481a-183">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="c481a-183">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="c481a-184">Esiste anche un tipo `Range`, costituito da due valori `Index`, uno per l'inizio e uno per la fine, che può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="c481a-184">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="c481a-185">È quindi possibile eseguire l'indicizzazione con `Range` per generare una sezione:</span><span class="sxs-lookup"><span data-stu-id="c481a-185">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> <span data-ttu-id="c481a-186">Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supporta la sintassi per `Range` e `Index`.</span><span class="sxs-lookup"><span data-stu-id="c481a-186">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports syntax for `Range` and `Index`.</span></span>

## <a name="async-streams"></a><span data-ttu-id="c481a-187">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="c481a-187">Async streams</span></span>

<span data-ttu-id="c481a-188">Il tipo `IAsyncEnumerable<T>` è una nuova versione asincrona di `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="c481a-188">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="c481a-189">Il linguaggio consente di usare `await foreach` su questi tipi per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="c481a-189">The language lets you `await foreach` over these to consume their elements, and `yield return` to them to produce elements.</span></span>

<span data-ttu-id="c481a-190">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="c481a-190">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="c481a-191">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="c481a-191">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="c481a-192">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="c481a-192">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> <span data-ttu-id="c481a-193">.NET Core 3.0 Preview 1 presenta attualmente un bug relativo a `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="c481a-193">.NET Core 3.0 Preview 1 currently has a bug with `await foreach`.</span></span> <span data-ttu-id="c481a-194">Usare invece `GetEnumerator` e `MoveNext` per elaborare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="c481a-194">Instead, use `GetEnumerator` and `MoveNext` to process elements.</span></span> <span data-ttu-id="c481a-195">Per altre informazioni, vedere [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span><span class="sxs-lookup"><span data-stu-id="c481a-195">For more information, see [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span></span>

<span data-ttu-id="c481a-196">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="c481a-196">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="c481a-197">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="c481a-197">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="c481a-198">Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supporta la sintassi `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="c481a-198">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports `await foreach` syntax.</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="c481a-199">Tipo: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="c481a-199">Type: SequenceReader</span></span>

<span data-ttu-id="c481a-200">In .NET Core 3.0 è stato aggiunto `System.Buffers.SequenceReader` che può essere usato come lettore per `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="c481a-200">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="c481a-201">Ciò consente un'analisi semplice, a prestazioni elevate e allocazione ridotta dei dati di `System.IO.Pipelines` che possono attraversare più buffer sottostanti.</span><span class="sxs-lookup"><span data-stu-id="c481a-201">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="c481a-202">L'esempio seguente suddivide un elemento `Sequence` di input in righe delimitate da `CR/LF` valide:</span><span class="sxs-lookup"><span data-stu-id="c481a-202">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="c481a-203">Tipo: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="c481a-203">Type: MetadataLoadContext</span></span>

<span data-ttu-id="c481a-204">È stato aggiunto il tipo `MetadataLoadContext` che consente la lettura dei metadati dell'assembly senza impatto sul dominio dell'applicazione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c481a-204">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="c481a-205">Gli assembly vengono letti come dati, inclusi gli assembly compilati per architetture e piattaforme diverse da quelle dell'ambiente di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="c481a-205">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="c481a-206">`MetadataLoadContext` si sovrappone a <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, che è disponibile solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c481a-206">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="c481a-207">`MetdataLoadContext` è disponibile nel pacchetto [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="c481a-207">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="c481a-208">Si tratta di un pacchetto .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c481a-208">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="c481a-209">`MetadataLoadContext` espone API simili al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, ma non si basa su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="c481a-209">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="c481a-210">In modo analogo a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` consente il caricamento degli assembly all'interno di un universo di caricamento di assembly isolato.</span><span class="sxs-lookup"><span data-stu-id="c481a-210">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="c481a-211">Le API `MetdataLoadContext` restituiscono oggetti <xref:System.Reflection.Assembly>, consentendo l'uso di API di reflection familiari.</span><span class="sxs-lookup"><span data-stu-id="c481a-211">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="c481a-212">Le API orientate all'esecuzione, ad esempio [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), non sono consentite e genereranno l'eccezione InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="c481a-212">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="c481a-213">L'esempio seguente illustra come trovare tipi concreti in un assembly che implementa una determinata interfaccia:</span><span class="sxs-lookup"><span data-stu-id="c481a-213">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="c481a-214">Gli scenari per `MetadataLoadContext` includono funzionalità della fase di progettazione, strumenti della fase di compilazione e funzionalità esclusive di runtime che devono esaminare un set di assembly come dati e i cui blocchi di file e la cui memoria vengono liberati dopo l'esecuzione dell'ispezione.</span><span class="sxs-lookup"><span data-stu-id="c481a-214">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="c481a-215">`MetadataLoadContext` ha una classe resolver passata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="c481a-215">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="c481a-216">Il processo del resolver consiste nel caricare un `Assembly`, dato il relativo `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c481a-216">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="c481a-217">La classe resolver deriva dalla classe astratta `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="c481a-217">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="c481a-218">Con `PathAssemblyResolver` viene fornita un'implementazione del resolver per gli scenari basati sul percorso.</span><span class="sxs-lookup"><span data-stu-id="c481a-218">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="c481a-219">I [test di MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) illustrano numerosi casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="c481a-219">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="c481a-220">I [test di Assembly](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sono un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="c481a-220">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="c481a-221">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="c481a-221">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="c481a-222">.NET Core sfrutterà ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="c481a-222">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="c481a-223">I vantaggi di TLS 1.3 sono diversi, secondo il [team di OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="c481a-223">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="c481a-224">Durata della connessione migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="c481a-224">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="c481a-225">Maggiore sicurezza grazie alla rimozione di algoritmi di crittografia obsoleti e non sicuri e alla crittografia di più elementi dell'handshake della connessione.</span><span class="sxs-lookup"><span data-stu-id="c481a-225">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="c481a-226">.NET Core 3.0 Preview 1 può utilizzare **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (a seconda della versione migliore trovata, in un sistema Linux).</span><span class="sxs-lookup"><span data-stu-id="c481a-226">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="c481a-227">Quando **OpenSSL 1.1.1** è disponibile, i tipi SslStream e HttpClient useranno **TLS 1.3** quando si usa `SslProtocols.None` (protocolli predefiniti di sistema), presupponendo che sia il client che il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="c481a-227">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="c481a-228">L'esempio seguente illustra .NET Core 3.0 Preview 1 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="c481a-228">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="c481a-229">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="c481a-229">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="c481a-230">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="c481a-230">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="c481a-231">Crittografia</span><span class="sxs-lookup"><span data-stu-id="c481a-231">Cryptography</span></span>

<span data-ttu-id="c481a-232">È stato aggiunto il supporto per le modalità di crittografia **AES-GCM** e **AES-CCM**, implementate tramite `System.Security.Cryptography.AesGcm` e `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="c481a-232">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="c481a-233">Questi algoritmi sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption) nonché i primi algoritmi di cifratura autenticata aggiunti a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c481a-233">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="c481a-234">Il codice seguente illustra l'uso della modalità di crittografia **AesGcm** per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="c481a-234">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="c481a-235">Il codice per **AesCcm** sarà pressoché identico, con la sola differenza dei nomi di variabile di classe.</span><span class="sxs-lookup"><span data-stu-id="c481a-235">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="c481a-236">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="c481a-236">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="c481a-237">.NET core 3.0 Preview 1 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche dai formati standard, senza bisogno usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="c481a-237">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="c481a-238">Tutti i tipi di chiavi (RSA, DSA, ECDsa, ECDiffieHellman) supportano il formato **X.509 SubjectPublicKeyInfo** per le chiavi pubbliche e i formati **PKCS#8 PrivateKeyInfo** e **PKCS#8 EncryptedPrivateKeyInfo** per le chiavi private.</span><span class="sxs-lookup"><span data-stu-id="c481a-238">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="c481a-239">RSA supporta anche **PKCS#1 RSAPublicKey** e **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="c481a-239">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="c481a-240">Tutti i metodi di esportazione producono dati binari con codifica DER e i metodi di importazione presentano lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="c481a-240">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="c481a-241">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="c481a-241">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="c481a-242">I file PKCS#8 possono essere esaminati con la classe `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="c481a-242">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="c481a-243">I file PFX/PKCS#12 possono essere esaminati e modificati rispettivamente con `System.Security.Cryptography.Pkcs.Pkcs12Info` e `System.Security.Cryptography.Pkcs.Pkcs12Builder`.</span><span class="sxs-lookup"><span data-stu-id="c481a-243">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="c481a-244">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="c481a-244">SerialPort for Linux</span></span>

<span data-ttu-id="c481a-245">.NET Core 3.0 supporta ora <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="c481a-245">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="c481a-246">In precedenza, .NET Core supportava solo l'uso del tipo `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="c481a-246">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="c481a-247">Altri miglioramenti BCL</span><span class="sxs-lookup"><span data-stu-id="c481a-247">More BCL Improvements</span></span>

<span data-ttu-id="c481a-248">`Span<T>`, `Memory<T>` e i tipi correlati introdotti in .NET Core 2.1 sono stati ottimizzati in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c481a-248">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="c481a-249">Le operazioni comuni, ad esempio la costruzione di intervalli, il sezionamento, l'analisi e la formattazione offrono ora prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="c481a-249">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="c481a-250">Inoltre, i tipi come `String` sono stati sottoposti a miglioramenti per aumentarne l'efficienza quando sono usati come chiavi con `Dictionary<TKey, TValue>` e altre raccolte.</span><span class="sxs-lookup"><span data-stu-id="c481a-250">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="c481a-251">Per trarre vantaggio da questi miglioramenti, non sono necessarie modifiche al codice.</span><span class="sxs-lookup"><span data-stu-id="c481a-251">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="c481a-252">.NET Core 3 Preview 1 presenta anche i nuovi miglioramenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c481a-252">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="c481a-253">Supporto di Brotli predefinito in HttpClient</span><span class="sxs-lookup"><span data-stu-id="c481a-253">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="c481a-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="c481a-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="c481a-255">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="c481a-255">Unsafe.Unbox</span></span>
* <span data-ttu-id="c481a-256">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="c481a-256">CancellationToken.Unregister</span></span>
* <span data-ttu-id="c481a-257">Operatori aritmetici complessi</span><span class="sxs-lookup"><span data-stu-id="c481a-257">Complex arithmetic operators</span></span>
* <span data-ttu-id="c481a-258">API socket per il keep-alive TCP</span><span class="sxs-lookup"><span data-stu-id="c481a-258">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="c481a-259">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="c481a-259">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="c481a-260">Analisi IPEndPoint</span><span class="sxs-lookup"><span data-stu-id="c481a-260">IPEndPoint parsing</span></span>
* <span data-ttu-id="c481a-261">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="c481a-261">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="c481a-262">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="c481a-262">Tiered compilation</span></span>

<span data-ttu-id="c481a-263">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) è attiva.</span><span class="sxs-lookup"><span data-stu-id="c481a-263">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="c481a-264">È una funzionalità che consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori, sia all'avvio che per ottimizzare la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="c481a-264">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="c481a-265">Questa funzionalità è stata aggiunta come funzionalità con consenso esplicito in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) ed è stata abilitata per impostazione predefinita in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="c481a-265">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="c481a-266">Successivamente, è stata ripristinata come funzionalità con consenso esplicito nella versione .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c481a-266">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="c481a-267">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="c481a-267">ARM64 Linux support</span></span>

<span data-ttu-id="c481a-268">In questa versione verrà aggiunto il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="c481a-268">We are adding support for ARM64 for Linux this release.</span></span> <span data-ttu-id="c481a-269">Per il contesto, è stato aggiunto il supporto per ARM32 per Linux con .NET Core 2.1 e per Windows con .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c481a-269">For context, we added support for ARM32 for Linux with .NET Core 2.1 and Windows with .NET Core 2.2.</span></span> <span data-ttu-id="c481a-270">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="c481a-270">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="c481a-271">[Sono disponibili immagini Docker per .NET Core per ARM64](https://hub.docker.com/r/microsoft/dotnet/) di Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="c481a-271">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="c481a-272">Per altre informazioni., vedere [Stato di ARM64 per .NET Core](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="c481a-272">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="c481a-273">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="c481a-273">**ARM64** Windows support isn't yet available.</span></span>
