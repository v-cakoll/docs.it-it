---
title: Novità di .NET Core 2.0
description: Informazioni sulle nuove funzionalità in .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: 115b3adc72b6798c6a7bac9cc18044a8822808a6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801888"
---
# <a name="whats-new-in-net-core-20"></a><span data-ttu-id="3d219-103">Novità di .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3d219-103">What's new in .NET Core 2.0</span></span>

<span data-ttu-id="3d219-104">.NET Core 2.0 include miglioramenti e nuove funzionalità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d219-104">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="3d219-105">Strumenti</span><span class="sxs-lookup"><span data-stu-id="3d219-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="3d219-106">Supporto dei linguaggi</span><span class="sxs-lookup"><span data-stu-id="3d219-106">Language support</span></span>](#language-support)
- [<span data-ttu-id="3d219-107">Miglioramenti della piattaforma</span><span class="sxs-lookup"><span data-stu-id="3d219-107">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="3d219-108">Modifiche dell'API</span><span class="sxs-lookup"><span data-stu-id="3d219-108">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="3d219-109">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d219-109">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="3d219-110">Miglioramenti della documentazione</span><span class="sxs-lookup"><span data-stu-id="3d219-110">Documentation improvements</span></span>](#documentation-improvements)

## <a name="tooling"></a><span data-ttu-id="3d219-111">Strumenti</span><span class="sxs-lookup"><span data-stu-id="3d219-111">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="3d219-112">Il comando dotnet restore viene eseguito in modo implicito</span><span class="sxs-lookup"><span data-stu-id="3d219-112">dotnet restore runs implicitly</span></span>

<span data-ttu-id="3d219-113">Nelle versioni precedenti di .NET Core, era necessario eseguire il comando [dotnet restore](../tools/dotnet-restore.md) per scaricare le dipendenze immediatamente dopo aver creato un nuovo progetto con il comando [dotnet new](../tools/dotnet-new.md), nonché in seguito all'aggiunta di una nuova dipendenza al progetto.</span><span class="sxs-lookup"><span data-stu-id="3d219-113">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="3d219-114">È anche possibile disabilitare la chiamata automatica di `dotnet restore` passando l'opzione `--no-restore` ai comandi `new`, `run`, `build`, `publish`, `pack` e `test`.</span><span class="sxs-lookup"><span data-stu-id="3d219-114">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span>

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="3d219-115">Ridestinazione a .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3d219-115">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="3d219-116">Se è installato .NET Core 2.0 SDK, i progetti destinati a .NET Core 1.x possono essere ridestinati a .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="3d219-116">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="3d219-117">Per ridestinare un progetto a .NET Core 2.0, modificare il file di progetto cambiando il valore dell'elemento `<TargetFramework>` (o l'elemento `<TargetFrameworks>` se il file di progetto include più destinazioni) da 1.x a 2.0:</span><span class="sxs-lookup"><span data-stu-id="3d219-117">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="3d219-118">È anche possibile ridestinare le librerie .NET Standard a .NET Standard 2.0 allo stesso modo:</span><span class="sxs-lookup"><span data-stu-id="3d219-118">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="3d219-119">Per altre informazioni sulla migrazione del progetto a .NET Core 2.0, vedere [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Migrazione da ASP.NET Core 1.x a ASP.NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="3d219-119">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="3d219-120">Supporto delle lingue</span><span class="sxs-lookup"><span data-stu-id="3d219-120">Language support</span></span>

<span data-ttu-id="3d219-121">Oltre a supportare C# e F#, .NET Core 2.0 supporta anche Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3d219-121">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="3d219-122">Visual Basic -</span><span class="sxs-lookup"><span data-stu-id="3d219-122">Visual Basic</span></span>

<span data-ttu-id="3d219-123">Con la versione 2.0, .NET Core supporta ora Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="3d219-123">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="3d219-124">È possibile usare Visual Basic per creare i tipi di progetto seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d219-124">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="3d219-125">App console .NET Core</span><span class="sxs-lookup"><span data-stu-id="3d219-125">.NET Core console apps</span></span>
- <span data-ttu-id="3d219-126">Librerie di classi .NET Core</span><span class="sxs-lookup"><span data-stu-id="3d219-126">.NET Core class libraries</span></span>
- <span data-ttu-id="3d219-127">Librerie di classi .NET Standard</span><span class="sxs-lookup"><span data-stu-id="3d219-127">.NET Standard class libraries</span></span>
- <span data-ttu-id="3d219-128">Progetti di unit test .NET Core</span><span class="sxs-lookup"><span data-stu-id="3d219-128">.NET Core unit test projects</span></span>
- <span data-ttu-id="3d219-129">Progetti di unit test xUnit .NET Core</span><span class="sxs-lookup"><span data-stu-id="3d219-129">.NET Core xUnit test projects</span></span>

<span data-ttu-id="3d219-130">Ad esempio, per creare un'applicazione Visual Basic "Hello World", eseguire i passaggi seguenti dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="3d219-130">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="3d219-131">Aprire una finestra della console, creare una directory per il progetto e impostarla come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="3d219-131">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="3d219-132">Immettere il comando `dotnet new console -lang vb`.</span><span class="sxs-lookup"><span data-stu-id="3d219-132">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="3d219-133">Il comando crea un file di progetto con estensione `.vbproj` oltre a un file di codice sorgente di Visual Basic denominato *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="3d219-133">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="3d219-134">Questo file contiene il codice sorgente per scrivere la stringa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="3d219-134">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="3d219-135">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="3d219-135">to the console window.</span></span>

1. <span data-ttu-id="3d219-136">Immettere il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="3d219-136">Enter the command `dotnet run`.</span></span> <span data-ttu-id="3d219-137">L'[interfaccia della riga di comando di .NET Core](../tools/index.md) compila ed esegue automaticamente l'applicazione, che visualizza il messaggio "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="3d219-137">The [.NET Core CLI](../tools/index.md) automatically compiles and executes the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="3d219-138">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="3d219-138">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="3d219-139">Supporto per C# 7.1</span><span class="sxs-lookup"><span data-stu-id="3d219-139">Support for C# 7.1</span></span>

<span data-ttu-id="3d219-140">.NET core 2.0 supporta C# 7.1, che aggiunge varie nuove funzionalità, tra cui:</span><span class="sxs-lookup"><span data-stu-id="3d219-140">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="3d219-141">Il metodo `Main`, ovvero il punto di ingresso dell'applicazione, può essere contrassegnato con la parola chiave [async](../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="3d219-141">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="3d219-142">Nomi di tupla dedotti.</span><span class="sxs-lookup"><span data-stu-id="3d219-142">Inferred tuple names.</span></span>
- <span data-ttu-id="3d219-143">Espressioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="3d219-143">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="3d219-144">Miglioramenti della piattaforma</span><span class="sxs-lookup"><span data-stu-id="3d219-144">Platform improvements</span></span>

<span data-ttu-id="3d219-145">.NET Core 2.0 include numerose funzionalità che semplificano l'installazione di .NET Core e il relativo uso nei sistemi operativi supportati.</span><span class="sxs-lookup"><span data-stu-id="3d219-145">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="3d219-146">.NET Core per Linux è un'implementazione singola</span><span class="sxs-lookup"><span data-stu-id="3d219-146">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="3d219-147">.NET Core 2.0 offre una singola implementazione di Linux che funziona su più distribuzioni di Linux.</span><span class="sxs-lookup"><span data-stu-id="3d219-147">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="3d219-148">In .NET Core 1.x era richiesto il download di un'implementazione di Linux specifica per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3d219-148">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="3d219-149">È anche possibile sviluppare app destinate a Linux come unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3d219-149">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="3d219-150">In .NET Core 1.x era necessario specificare separatamente ogni distribuzione di Linux come destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d219-150">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="3d219-151">Supporto per le librerie di crittografia Apple</span><span class="sxs-lookup"><span data-stu-id="3d219-151">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="3d219-152">Per .NET Core 1.x in macOS era richiesta la libreria di crittografia del toolkit OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="3d219-152">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="3d219-153">.NET Core 2.0 usa le librerie di crittografia Apple e non richiede OpenSSL, pertanto non è più necessario installarlo.</span><span class="sxs-lookup"><span data-stu-id="3d219-153">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="3d219-154">Modifiche delle API e supporto delle librerie</span><span class="sxs-lookup"><span data-stu-id="3d219-154">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="3d219-155">Supporto di .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="3d219-155">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="3d219-156">.NET Standard definisce un set di API con versioni specifiche che devono essere disponibili nelle implementazioni .NET conformi con tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="3d219-156">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="3d219-157">.NET Standard è destinato agli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="3d219-157">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="3d219-158">L'obiettivo è garantire le funzionalità disponibili in una libreria destinata a una versione di .NET Standard in ogni implementazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="3d219-158">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="3d219-159">.NET Core 1.x supporta .NET Standard versione 1.6; .NET Core 2.0 supporta l'ultima versione, ovvero .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="3d219-159">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="3d219-160">Per altre informazioni, vedere [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="3d219-160">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="3d219-161">.NET Standard 2.0 include più di 20.000 API aggiuntive rispetto a quelle disponibili in .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="3d219-161">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="3d219-162">Gran parte di questa superficie estesa deriva dall'incorporamento in .NET Standard delle API in comune per .NET Framework e Xamarin.</span><span class="sxs-lookup"><span data-stu-id="3d219-162">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="3d219-163">Anche le librerie di classi di .NET Standard 2.0 fanno riferimento alle librerie di classi di .NET Framework, a condizione che chiamino API presenti in .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="3d219-163">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="3d219-164">Non è richiesta alcuna ricompilazione delle librerie di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d219-164">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="3d219-165">Per un elenco delle API aggiunte alla .NET Standard dall'ultima versione, .NET Standard 1,6, vedere [.NET Standard 2,0 rispetto a 1,6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="3d219-165">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="3d219-166">Superficie estesa</span><span class="sxs-lookup"><span data-stu-id="3d219-166">Expanded surface area</span></span>

<span data-ttu-id="3d219-167">Il numero totale di API disponibili in .NET Core 2.0 è più che raddoppiato rispetto a .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="3d219-167">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="3d219-168">Con [Windows Compatibility Pack](../porting/windows-compat-pack.md) il trasferimento da .NET Framework è diventato anche molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="3d219-168">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="3d219-169">Supporto delle librerie di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3d219-169">Support for .NET Framework libraries</span></span>

<span data-ttu-id="3d219-170">Il codice .NET Core può fare riferimento a librerie esistenti di .NET Framework, inclusi pacchetti NuGet esistenti.</span><span class="sxs-lookup"><span data-stu-id="3d219-170">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="3d219-171">Si noti che le librerie devono usare le API disponibili in .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3d219-171">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="3d219-172">integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d219-172">Visual Studio integration</span></span>

<span data-ttu-id="3d219-173">Visual Studio 2017 versione 15.3 e in alcuni casi Visual Studio per Mac offrono numerosi miglioramenti significativi per gli sviluppatori che usano .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3d219-173">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="3d219-174">Ridestinazione delle app .NET Core e delle librerie .NET Standard</span><span class="sxs-lookup"><span data-stu-id="3d219-174">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="3d219-175">Se è installato .NET Core 2.0 SDK, è possibile ridestinare i progetti .NET Core 1.x a .NET Core 2.0 e le librerie .NET Standard 1.x a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="3d219-175">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="3d219-176">Per ridestinare il progetto in Visual Studio, aprire la scheda **Applicazione** della finestra di dialogo delle proprietà del progetto e cambiare il valore di **Framework di destinazione** in **.NET Core 2.0** o **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="3d219-176">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="3d219-177">Per cambiare questa impostazione, è anche possibile fare clic con il pulsante destro del mouse sul progetto e scegliere il comando **Modifica file \*.csproj**.</span><span class="sxs-lookup"><span data-stu-id="3d219-177">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="3d219-178">Per altre informazioni, vedere la sezione [Strumenti](#tooling) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3d219-178">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="3d219-179">Supporto per Live Unit Testing per .NET Core</span><span class="sxs-lookup"><span data-stu-id="3d219-179">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="3d219-180">Ogni volta che si modifica il codice, Live Unit Testing esegue automaticamente tutti gli unit test interessati in background, visualizzando in tempo reale i risultati e il code coverage nell'ambiente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d219-180">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="3d219-181">.NET Core 2.0 ora supporta Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="3d219-181">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="3d219-182">In precedenza, Live Unit Testing era disponibile solo per le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d219-182">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="3d219-183">Per altre informazioni, vedere [Live unit testing con Visual Studio](/visualstudio/test/live-unit-testing) e le [domande frequenti su Live unit testing](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="3d219-183">For more information, see [Live Unit Testing with Visual Studio](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="3d219-184">Supporto migliorato per più framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="3d219-184">Better support for multiple target frameworks</span></span>

<span data-ttu-id="3d219-185">Se è necessario ricompilare un progetto per più framework di destinazione, è ora possibile selezionare la piattaforma di destinazione dal menu di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3d219-185">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="3d219-186">Nella figura seguente un progetto denominato SCD1 è destinato a macOS X 10.11 a 64 bit (`osx.10.11-x64`) e a Windows 10/Windows Server 2016 a 64 bit (`win10-x64`).</span><span class="sxs-lookup"><span data-stu-id="3d219-186">In the following figure, a project named SCD1 targets 64-bit macOS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="3d219-187">È possibile selezionare il framework di destinazione prima di selezionare il pulsante per compilare il progetto, in questo caso per eseguire una build di debug.</span><span class="sxs-lookup"><span data-stu-id="3d219-187">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Screenshot che illustra la selezione del framework di destinazione al momento della compilazione di un progetto.](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="3d219-189">Supporto di .NET Core SDK affiancati</span><span class="sxs-lookup"><span data-stu-id="3d219-189">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="3d219-190">È ora possibile installare .NET Core SDK in modo indipendente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d219-190">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="3d219-191">In questo modo, una singola versione di Visual Studio consente di compilare progetti destinati a versioni diverse di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3d219-191">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="3d219-192">In precedenza, Visual Studio e .NET Core SDK erano strettamente collegati e associati in base a versioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="3d219-192">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="3d219-193">Miglioramenti della documentazione</span><span class="sxs-lookup"><span data-stu-id="3d219-193">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="3d219-194">.NET Application Architecture</span><span class="sxs-lookup"><span data-stu-id="3d219-194">.NET Application Architecture</span></span>

<span data-ttu-id="3d219-195">Dalla pagina [.NET Application Architecture](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) (Architettura delle applicazioni .NET) è possibile accedere a una serie di eBook che offrono linee guida, procedure consigliate e applicazioni di esempio per l'uso di .NET per creare:</span><span class="sxs-lookup"><span data-stu-id="3d219-195">[.NET Application Architecture](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- [<span data-ttu-id="3d219-196">Microservizi e contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="3d219-196">Microservices and Docker containers</span></span>](../../architecture/microservices/index.md)
- [<span data-ttu-id="3d219-197">Applicazioni Web con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3d219-197">Web applications with ASP.NET</span></span>](../../architecture/modern-web-apps-azure/index.md)
- [<span data-ttu-id="3d219-198">Applicazioni per dispositivi mobili con Xamarin</span><span class="sxs-lookup"><span data-stu-id="3d219-198">Mobile applications with Xamarin</span></span>](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [<span data-ttu-id="3d219-199">Applicazioni distribuite nel cloud con Azure</span><span class="sxs-lookup"><span data-stu-id="3d219-199">Applications that are deployed to the Cloud with Azure</span></span>](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a><span data-ttu-id="3d219-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d219-200">See also</span></span>

- [<span data-ttu-id="3d219-201">Novità di ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3d219-201">What's new in ASP.NET Core 2.0</span></span>](/aspnet/core/aspnetcore-2.0)
