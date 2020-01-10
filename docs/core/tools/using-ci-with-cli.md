---
title: Integrazione continua (CI) con .NET Core SDK e strumenti
description: Informazioni su come usare il .NET Core SDK e i relativi strumenti nel server di compilazione con integrazione continua.
author: mairaw
ms.date: 05/18/2017
ms.openlocfilehash: 65d062fce2f364932ebf8091bd9c6cdef561b633
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714125"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="29603-103">Uso di .NET Core SDK e dei relativi strumenti in integrazione continua</span><span class="sxs-lookup"><span data-stu-id="29603-103">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

<span data-ttu-id="29603-104">Questo documento illustra l'uso di .NET Core SDK e dei relativi strumenti in un server di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-104">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="29603-105">Il set di strumenti di .NET Core funziona interattivamente, quando uno sviluppatore digita i comandi al prompt dei comandi, e automaticamente, quando un server di integrazione continua (CI) esegue uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-105">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="29603-106">I comandi, le opzioni, gli input e gli output sono uguali, e gli unici elementi da specificare sono un modo per acquisire gli strumenti e un sistema per compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="29603-106">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="29603-107">Questo documento illustra specificatamente gli scenari di acquisizione degli strumenti per CI e include consigli su come progettare e strutturare gli script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-107">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="29603-108">Opzioni di installazione per i server di compilazione di integrazione continua</span><span class="sxs-lookup"><span data-stu-id="29603-108">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="29603-109">Uso di programmi di installazione nativi</span><span class="sxs-lookup"><span data-stu-id="29603-109">Using the native installers</span></span>

<span data-ttu-id="29603-110">Sono disponibili programmi di installazione nativi per macOS, Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="29603-110">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="29603-111">I programmi di installazione richiedono l'accesso amministratore (sudo) al server di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-111">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="29603-112">L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native necessarie per l'esecuzione degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="29603-112">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="29603-113">I programmi di installazione nativi offrono anche un'installazione a livello di sistema dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="29603-113">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="29603-114">Gli utenti di macOS devono usare i programmi di installazione PKG.</span><span class="sxs-lookup"><span data-stu-id="29603-114">macOS users should use the PKG installers.</span></span> <span data-ttu-id="29603-115">In Linux è possibile scegliere di usare un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS, oppure i pacchetti stessi DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="29603-115">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="29603-116">In Windows usare il programma di installazione MSI.</span><span class="sxs-lookup"><span data-stu-id="29603-116">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="29603-117">I file binari stabili più recenti sono reperibili in [.NET downloads](https://dotnet.microsoft.com/download) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="29603-117">The latest stable binaries are found at [.NET downloads](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="29603-118">Se si vuole usare gli strumenti della versione non definitiva più recente (e potenzialmente instabile), vedere i collegamenti riportati nel [repository GitHub dotnet/core-sdk](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="29603-118">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/core-sdk GitHub repository](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span> <span data-ttu-id="29603-119">Per le distribuzioni di Linux, sono disponibili gli archivi `tar.gz` (noti anche come `tarballs`). Usare gli script di installazione all'interno degli archivi per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="29603-119">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="29603-120">Uso dello script di installazione</span><span class="sxs-lookup"><span data-stu-id="29603-120">Using the installer script</span></span>

<span data-ttu-id="29603-121">L'uso dello script di installazione consente di installare il sistema senza privilegi amministrativi nel server di compilazione e offre un'automazione semplice per ottenere gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="29603-121">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="29603-122">Lo script esegue automaticamente il download e l'estrazione degli strumenti in un percorso predefinito o specificato per l'uso.</span><span class="sxs-lookup"><span data-stu-id="29603-122">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="29603-123">È anche possibile specificare la versione degli strumenti che si vogliono installare e se si vuole installare l'intero SDK o solo il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="29603-123">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="29603-124">Lo script di installazione viene automatizzato per essere eseguito all'inizio della compilazione per recuperare e installare la versione necessaria dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="29603-124">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="29603-125">La *versione necessaria* è la versione dell'SDK più adatta per compilare i progetti.</span><span class="sxs-lookup"><span data-stu-id="29603-125">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="29603-126">Lo script consente di installare l'SDK in una directory locale del server, eseguire gli strumenti dal percorso di installazione e quindi pulire (o consentire al servizio CI di eseguire la pulizia) al termine della compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-126">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="29603-127">Ciò consente incapsulamento e isolamento per l'intero processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-127">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="29603-128">I riferimenti agli script di installazione sono reperibili nell'articolo [dotnet-install](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="29603-128">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) article.</span></span>

> [!NOTE]
> <span data-ttu-id="29603-129">**Azure DevOps Services**</span><span class="sxs-lookup"><span data-stu-id="29603-129">**Azure DevOps Services**</span></span>
>
> <span data-ttu-id="29603-130">Quando si usa lo script di installazione, le dipendenze native non vengono installate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29603-130">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="29603-131">È necessario installare le dipendenze native, se non sono già presenti nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="29603-131">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="29603-132">Per altre informazioni, vedere [dipendenze e requisiti di .NET Core](../install/dependencies.md?tabs=netcore30&pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="29603-132">For more information, see [.NET Core dependencies and requirements](../install/dependencies.md?tabs=netcore30&pivots=os-linux).</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="29603-133">Esempi di installazione di CI</span><span class="sxs-lookup"><span data-stu-id="29603-133">CI setup examples</span></span>

<span data-ttu-id="29603-134">Questa sezione illustra un'installazione manuale tramite uno script di PowerShell o Bash e include la descrizione di alcune soluzioni CI SaaS (software come un servizio).</span><span class="sxs-lookup"><span data-stu-id="29603-134">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="29603-135">Le soluzioni CI SaaS illustrate sono [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) e [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="29603-135">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="29603-136">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="29603-136">Manual setup</span></span>

<span data-ttu-id="29603-137">Ogni servizio SaaS ha i propri metodi per la creazione e la configurazione di un processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-137">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="29603-138">Se si usano soluzioni SaaS diversi da quelli elencati o è necessaria una personalizzazione del supporto non inclusa nei pacchetti predefiniti, si devono eseguire alcune configurazioni manuali.</span><span class="sxs-lookup"><span data-stu-id="29603-138">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="29603-139">In genere, un'installazione manuale deve ottenere una versione di strumenti (o le compilazioni notturne più recente degli strumenti) ed eseguire lo script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-139">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="29603-140">È possibile usare uno script di PowerShell o Bash per orchestrare i comandi di .NET Core o usare un file di progetto che descriva il processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-140">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="29603-141">La [sezione sull'orchestrazione](#orchestrating-the-build) offre più dettagli su queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="29603-141">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="29603-142">Dopo aver creato uno script che esegue un'installazione manuale del server di compilazione CI, usarlo nel computer di sviluppo per compilare il codice localmente a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="29603-142">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="29603-143">Dopo aver verificato che lo script viene eseguito correttamente nel computer locale, distribuirlo al server di compilazione CI.</span><span class="sxs-lookup"><span data-stu-id="29603-143">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="29603-144">Di seguito viene specificato uno script di PowerShell relativamente semplice che illustra come ottenere .NET Core SDK e installarlo in un server di compilazione di Windows:</span><span class="sxs-lookup"><span data-stu-id="29603-144">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="29603-145">L'implementazione per il processo di compilazione viene specificata alla fine dello script.</span><span class="sxs-lookup"><span data-stu-id="29603-145">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="29603-146">Lo script acquisisce gli strumenti e quindi esegue il processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-146">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="29603-147">Per i computer UNIX, lo script Bash seguente esegue le azioni descritte nello script di PowerShell allo stesso modo:</span><span class="sxs-lookup"><span data-stu-id="29603-147">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="29603-148">Travis CI</span><span class="sxs-lookup"><span data-stu-id="29603-148">Travis CI</span></span>

<span data-ttu-id="29603-149">È possibile configurare [Travis CI](https://travis-ci.org/) per installare .NET Core SDK usando il linguaggio `csharp` e la chiave `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="29603-149">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="29603-150">Per altre informazioni, vedere i documenti ufficiali di Travis CI in [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilazione di un progetto C#, F# o Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="29603-150">For more information, see the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/).</span></span> <span data-ttu-id="29603-151">Quando si accede alle informazioni su Travis CI si noti che l'identificatore del linguaggio `language: csharp` gestito dalla community funziona per tutti i linguaggi .NET, inclusi F# e Mono.</span><span class="sxs-lookup"><span data-stu-id="29603-151">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="29603-152">Travis CI esegue entrambi i processi macOS e Linux in una *matrice di compilazione*, in cui si specifica una combinazione di runtime, ambiente ed esclusioni/inclusioni per includere le combinazioni di compilazione per l'app.</span><span class="sxs-lookup"><span data-stu-id="29603-152">Travis CI runs both macOS and Linux jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="29603-153">Per altre informazioni, vedere [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalizzazione della compilazione) nella documentazione di Travis CI.</span><span class="sxs-lookup"><span data-stu-id="29603-153">For more information, see the [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) article in the Travis CI documentation.</span></span> <span data-ttu-id="29603-154">Gli strumenti basati su MSBuild includono i runtime LTS (1.0.x) e Current (1.1.x) nel pacchetto. Per questo motivo, l'installazione dell'SDK installa tutti gli elementi necessari per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-154">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="29603-155">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="29603-155">AppVeyor</span></span>

<span data-ttu-id="29603-156">[AppVeyor](https://www.appveyor.com/) installa .NET Core 1.0.1 SDK con l'immagine di lavoro della build `Visual Studio 2017`.</span><span class="sxs-lookup"><span data-stu-id="29603-156">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="29603-157">Sono disponibili altre immagini di compilazione con versioni diverse di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="29603-157">Other build images with different versions of the .NET Core SDK are available.</span></span> <span data-ttu-id="29603-158">Per altre informazioni, vedere l'esempio [appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) e l'articolo [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Compilare immagini di lavoro) nella documentazione di AppVeyor.</span><span class="sxs-lookup"><span data-stu-id="29603-158">For more information, see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) article in the AppVeyor docs.</span></span>

<span data-ttu-id="29603-159">I file binari di .NET Core SDK vengono scaricati ed estratti in una sottodirectory tramite lo script di installazione e aggiunti alla variabile di ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="29603-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="29603-160">Aggiungere una matrice di compilazione per eseguire test di integrazione con più versioni di .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="29603-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a><span data-ttu-id="29603-161">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="29603-161">Azure DevOps Services</span></span>

<span data-ttu-id="29603-162">Configurare Azure DevOps Services per compilare i progetti .NET Core usando uno di questi approcci:</span><span class="sxs-lookup"><span data-stu-id="29603-162">Configure Azure DevOps Services to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="29603-163">Eseguire lo script del [passaggio di installazione manuale](#manual-setup) usando i comandi.</span><span class="sxs-lookup"><span data-stu-id="29603-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="29603-164">Creare una build composta da diverse attività di compilazione incorporate di Azure DevOps Services configurate per usare gli strumenti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="29603-164">Create a build composed of several Azure DevOps Services built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="29603-165">Entrambe le soluzioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="29603-165">Both solutions are valid.</span></span> <span data-ttu-id="29603-166">Tramite uno script di installazione manuale, si controlla la versione degli strumenti ricevuti, dopo averli scaricati come parte della compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="29603-167">La compilazione viene eseguita da uno script che deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="29603-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="29603-168">Questo articolo descrive solo l'opzione manuale.</span><span class="sxs-lookup"><span data-stu-id="29603-168">This article only covers the manual option.</span></span> <span data-ttu-id="29603-169">Per altre informazioni sulla creazione di una build con le attività di compilazione di Azure DevOps Services, vedere la documentazione di [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="29603-169">For more information on composing a build with Azure DevOps Services build tasks, see the [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index) documentation.</span></span>

<span data-ttu-id="29603-170">Per usare uno script di installazione manuale in Azure DevOps Services, creare una nuova definizione di compilazione e specificare lo script da eseguire per l'istruzione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-170">To use a manual setup script in Azure DevOps Services, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="29603-171">Questa operazione viene eseguita tramite l'interfaccia utente di Azure DevOps Services:</span><span class="sxs-lookup"><span data-stu-id="29603-171">This is accomplished using the Azure DevOps Services user interface:</span></span>

1. <span data-ttu-id="29603-172">Iniziare con la creazione di una nuova definizione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-172">Start by creating a new build definition.</span></span> <span data-ttu-id="29603-173">Quando viene visualizzata la schermata che offre un'opzione per definire il tipo di compilazione da creare, selezionare **Vuota**.</span><span class="sxs-lookup"><span data-stu-id="29603-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![Selezione di una definizione vuota di compilazione](./media/using-ci-with-cli/select-empty-build-definition.png)

1. <span data-ttu-id="29603-175">Dopo aver configurato il repository per la compilazione, si viene indirizzati alle definizioni della compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="29603-176">Selezionare **Aggiungi istruzione di compilazione**:</span><span class="sxs-lookup"><span data-stu-id="29603-176">Select **Add build step**:</span></span>

   ![Aggiunta di un'istruzione di compilazione](./media/using-ci-with-cli/add-build-step.png)

1. <span data-ttu-id="29603-178">Viene visualizzato il **catalogo delle attività**.</span><span class="sxs-lookup"><span data-stu-id="29603-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="29603-179">Il catalogo include le attività da usare nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="29603-180">Poiché è disponibile uno script, selezionare il pulsante **Aggiungi** di **PowerShell: Consente di eseguire uno script PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="29603-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![Aggiunta di un'istruzione di script di PowerShell](./media/using-ci-with-cli/add-powershell-script.png)

1. <span data-ttu-id="29603-182">Configurare l'istruzione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29603-182">Configure the build step.</span></span> <span data-ttu-id="29603-183">Aggiungere lo script dal repository che si sta creando:</span><span class="sxs-lookup"><span data-stu-id="29603-183">Add the script from the repository that you're building:</span></span>

   ![Specifica dello script di PowerShell da eseguire](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="29603-185">Orchestrazione della compilazione</span><span class="sxs-lookup"><span data-stu-id="29603-185">Orchestrating the build</span></span>

<span data-ttu-id="29603-186">La maggior parte di questo documento illustra come acquisire gli strumenti di .NET Core e configurare i vari servizi CI senza specificare le informazioni su come orchestrare, o *compilare effettivamente*, il codice con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="29603-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="29603-187">Le scelte su come strutturare il processo di compilazione dipendono da molti fattori che non possono essere illustrati in modo generico.</span><span class="sxs-lookup"><span data-stu-id="29603-187">The choices on how to structure the build process depend on many factors that can't be covered in a general way here.</span></span> <span data-ttu-id="29603-188">Per altre informazioni sull'orchestrazione delle compilazioni con ogni tecnologia, vedere le risorse e gli esempi inclusi nei set di documentazione di [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) e [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="29603-188">For more information on orchestrating your builds with each technology, explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span></span>

<span data-ttu-id="29603-189">Due approcci generali accettati nella strutturazione del processo di compilazione per il codice .NET Core tramite gli strumenti di .NET Core consistono nell'usare MSBuild direttamente o i comandi della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="29603-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="29603-190">L'approccio da adottare è determinato dal livello di esperienza con gli approcci e dai pro e contro in termini di complessità.</span><span class="sxs-lookup"><span data-stu-id="29603-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="29603-191">MSBuild offre la possibilità di esprimere il processo di compilazione come attività e destinazioni, ma è accompagnato dalla complessità nel dover imparare la sintassi dei file di progetto di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="29603-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="29603-192">L'uso degli strumenti da riga di comando di .NET Core è probabilmente più semplice, ma richiede la scrittura logica di orchestrazione in un linguaggio di scripting, ad esempio `bash` o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29603-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="29603-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29603-193">See also</span></span>

- <span data-ttu-id="29603-194">[.NET Downloads - Linux](https://dotnet.microsoft.com/download?initial-os=linux) (Download di .NET - Linux)</span><span class="sxs-lookup"><span data-stu-id="29603-194">[.NET downloads - Linux](https://dotnet.microsoft.com/download?initial-os=linux)</span></span>
