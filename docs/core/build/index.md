---
title: Compilare .NET Core dal codice sorgente
description: Informazioni su come compilare .NET Core e .NET Core CLI dal codice sorgente.
author: bleroy
ms.date: 06/28/2017
ms.openlocfilehash: fe5431667d861d830c2ec56252e6e3e2ca08a866
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740923"
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="98f5a-103">Compilare .NET Core dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="98f5a-103">Build .NET Core from source</span></span>

<span data-ttu-id="98f5a-104">La possibilità di compilare .NET Core dal relativo codice sorgente è importante per diversi motivi: rende più semplice il trasferimento di .NET Core sulle nuove piattaforme, abilita i contributi e le correzioni per il prodotto e consente la creazione di versioni personalizzate di .NET.</span><span class="sxs-lookup"><span data-stu-id="98f5a-104">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="98f5a-105">Questo articolo offre materiale sussidiario agli sviluppatori che vogliono compilare e distribuire le proprie versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f5a-105">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="98f5a-106">Compilare Common Language Runtime (CLR) dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="98f5a-106">Build the CLR from source</span></span>

<span data-ttu-id="98f5a-107">Il codice sorgente per .NET CoreCLR è reperibile nel repository [DotNet/Runtime](https://github.com/dotnet/runtime/) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="98f5a-107">The source code for the .NET CoreCLR can be found in the [dotnet/runtime](https://github.com/dotnet/runtime/) repository on GitHub.</span></span>

<span data-ttu-id="98f5a-108">La compilazione attualmente dipende dai prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="98f5a-108">The build currently depends on the following prerequisites:</span></span>

- [<span data-ttu-id="98f5a-109">Git</span><span class="sxs-lookup"><span data-stu-id="98f5a-109">Git</span></span>](https://git-scm.com/)
- [<span data-ttu-id="98f5a-110">CMake</span><span class="sxs-lookup"><span data-stu-id="98f5a-110">CMake</span></span>](https://cmake.org/)
- [<span data-ttu-id="98f5a-111">Python</span><span class="sxs-lookup"><span data-stu-id="98f5a-111">Python</span></span>](https://www.python.org/)
- <span data-ttu-id="98f5a-112">un compilatore C++.</span><span class="sxs-lookup"><span data-stu-id="98f5a-112">a C++ compiler.</span></span>

<span data-ttu-id="98f5a-113">Dopo aver installato questi prerequisiti, è possibile compilare CLR richiamando lo script di compilazione (`build.cmd` in Windows o `build.sh` in Linux e macOS) alla base del repository [DotNet/Runtime](https://github.com/dotnet/runtime/) .</span><span class="sxs-lookup"><span data-stu-id="98f5a-113">After you've installed these prerequisites, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of the [dotnet/runtime](https://github.com/dotnet/runtime/) repository.</span></span>

<span data-ttu-id="98f5a-114">L'installazione dei componenti varia in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98f5a-114">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="98f5a-115">Vedere le istruzioni di compilazione per il sistema operativo specifico:</span><span class="sxs-lookup"><span data-stu-id="98f5a-115">See the build instructions for your specific OS:</span></span>

- [<span data-ttu-id="98f5a-116">Windows</span><span class="sxs-lookup"><span data-stu-id="98f5a-116">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
- [<span data-ttu-id="98f5a-117">Linux</span><span class="sxs-lookup"><span data-stu-id="98f5a-117">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
- [<span data-ttu-id="98f5a-118">macOS</span><span class="sxs-lookup"><span data-stu-id="98f5a-118">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
- [<span data-ttu-id="98f5a-119">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="98f5a-119">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
- [<span data-ttu-id="98f5a-120">NetBSD</span><span class="sxs-lookup"><span data-stu-id="98f5a-120">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="98f5a-121">Non esiste alcuna compilazione incrociata tra sistemi operativi (solo per ARM, che è basato su X64).</span><span class="sxs-lookup"><span data-stu-id="98f5a-121">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="98f5a-122">È necessario essere sulla piattaforma specifica per compilare quella piattaforma.</span><span class="sxs-lookup"><span data-stu-id="98f5a-122">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="98f5a-123">La compilazione ha due `buildTypes` principali:</span><span class="sxs-lookup"><span data-stu-id="98f5a-123">The build has two main `buildTypes`:</span></span>

- <span data-ttu-id="98f5a-124">Debug (impostazione predefinita): compila il runtime con le ottimizzazioni minime e controlli di runtime aggiuntivi (asserzioni).</span><span class="sxs-lookup"><span data-stu-id="98f5a-124">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="98f5a-125">La riduzione del livello di ottimizzazione e i controlli aggiuntivi rallentano l'esecuzione di runtime, ma sono utili per il debug.</span><span class="sxs-lookup"><span data-stu-id="98f5a-125">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="98f5a-126">Questa è l'impostazione consigliata per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="98f5a-126">This is the recommended setting for development and testing environments.</span></span>
- <span data-ttu-id="98f5a-127">Release: compila il runtime con le ottimizzazioni complete e senza i controlli di runtime aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="98f5a-127">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="98f5a-128">Ciò produrrà prestazioni più veloci in fase di esecuzione, ma potrebbe richiedere un po' più tempo per la compilazione e può essere difficile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="98f5a-128">This will yield much faster run-time performance, but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="98f5a-129">Passare `release` allo script di compilazione per selezionare questo tipo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="98f5a-129">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="98f5a-130">Inoltre, per impostazione predefinita la compilazione non solo crea gli eseguibili di runtime, ma compila anche tutti i test.</span><span class="sxs-lookup"><span data-stu-id="98f5a-130">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="98f5a-131">I test sono piuttosto numerosi e richiedono una quantità significativa di tempo che non è necessaria se si vuole solo sperimentare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="98f5a-131">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="98f5a-132">È possibile ignorare le compilazioni dei test aggiungendo l'argomento `skiptests` allo script di compilazione, come nell'esempio seguente (sostituire `.\build` con `./build.sh` nei computer Unix):</span><span class="sxs-lookup"><span data-stu-id="98f5a-132">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests
```

<span data-ttu-id="98f5a-133">L'esempio precedente illustra come compilare la versione `Debug`, in cui sono abilitati i controlli della fase di sviluppo (asserzioni) e sono disabilitate le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="98f5a-133">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="98f5a-134">Per compilare la versione di rilascio (velocità completa), eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98f5a-134">To build the release (full speed) flavor, do the following:</span></span>

```bat
    .\build release skiptests
```

<span data-ttu-id="98f5a-135">Sono disponibili altre opzioni di compilazione se si esegue la compilazione con il qualificatore -?</span><span class="sxs-lookup"><span data-stu-id="98f5a-135">You can find more build options with build by using the -?</span></span> <span data-ttu-id="98f5a-136">o -help.</span><span class="sxs-lookup"><span data-stu-id="98f5a-136">or -help qualifier.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="98f5a-137">Uso della compilazione</span><span class="sxs-lookup"><span data-stu-id="98f5a-137">Using Your Build</span></span>

<span data-ttu-id="98f5a-138">La compilazione colloca tutti i file generati sotto la directory `bin` alla base dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="98f5a-138">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="98f5a-139">È presente una directory *bin\Log* che contiene i file di log generati durante la compilazione ed è particolarmente utile quando la compilazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="98f5a-139">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="98f5a-140">L'output effettivo viene inserito in una directory *bin\Product\[piattaforma]. [architettura CPU]. [tipo di compilazione]* , ad esempio *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="98f5a-140">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="98f5a-141">Benché l'output non elaborato della compilazione spesso sia utile, di solito interessano solo i pacchetti NuGet, che vengono inseriti nella sottodirectory `.nuget\pkg` della directory di output precedente.</span><span class="sxs-lookup"><span data-stu-id="98f5a-141">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="98f5a-142">Esistono due tecniche di base per l'uso del nuovo runtime:</span><span class="sxs-lookup"><span data-stu-id="98f5a-142">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="98f5a-143">**Usare dotnet.exe e NuGet per creare un'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="98f5a-143">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="98f5a-144">Vedere [Uso della compilazione](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) per istruzioni sulla creazione di un programma che usa il nuovo runtime con i pacchetti NuGet appena creati e l'interfaccia della riga di comando "dotnet" (CLI).</span><span class="sxs-lookup"><span data-stu-id="98f5a-144">See [Using Your Build](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="98f5a-145">Questa tecnica è probabilmente il modo in cui gli sviluppatori non di runtime preferiscono usare il nuovo runtime.</span><span class="sxs-lookup"><span data-stu-id="98f5a-145">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>

 2. <span data-ttu-id="98f5a-146">**Usare corerun.exe per eseguire un'applicazione con le DLL non in pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="98f5a-146">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="98f5a-147">Questo archivio definisce anche un host semplice denominato corerun.exe che NON accetta dipendenze in NuGet.</span><span class="sxs-lookup"><span data-stu-id="98f5a-147">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="98f5a-148">Si dovrà indicare all'host dove si ottengono le DLL necessarie in uso e raccogliere le DLL manualmente.</span><span class="sxs-lookup"><span data-stu-id="98f5a-148">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="98f5a-149">Questa tecnica viene usata da tutti i test nel repository [DotNet/Runtime](https://github.com/dotnet/runtime) ed è utile per il ciclo Quick "Edit-Compile-debug" locale, ad esempio il testing unità preliminare.</span><span class="sxs-lookup"><span data-stu-id="98f5a-149">This technique is used by all the tests in the [dotnet/runtime](https://github.com/dotnet/runtime) repo, and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="98f5a-150">Vedere l'argomento relativo all'[esecuzione delle app .NET Core con CoreRun.exe](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md) per informazioni dettagliate sull'uso di questa tecnica.</span><span class="sxs-lookup"><span data-stu-id="98f5a-150">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="98f5a-151">Compilare l'interfaccia della riga di comando dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="98f5a-151">Build the CLI from source</span></span>

<span data-ttu-id="98f5a-152">Il codice sorgente per l'interfaccia della riga di comando di .NET Core è reperibile nel repository [dotnet/cli](https://github.com/dotnet/cli/) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="98f5a-152">The source code for the .NET Core CLI can be found in the [dotnet/cli](https://github.com/dotnet/cli/) repository on GitHub.</span></span>

<span data-ttu-id="98f5a-153">Per compilare l'interfaccia della riga di comando di .NET Core, i seguenti componenti devono essere installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="98f5a-153">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

- <span data-ttu-id="98f5a-154">Windows e Linux:</span><span class="sxs-lookup"><span data-stu-id="98f5a-154">Windows & Linux:</span></span>
  - <span data-ttu-id="98f5a-155">git nel PERCORSO</span><span class="sxs-lookup"><span data-stu-id="98f5a-155">git on the PATH</span></span>
- <span data-ttu-id="98f5a-156">macOS:</span><span class="sxs-lookup"><span data-stu-id="98f5a-156">macOS:</span></span>
  - <span data-ttu-id="98f5a-157">git nel PERCORSO</span><span class="sxs-lookup"><span data-stu-id="98f5a-157">git on the PATH</span></span>
  - <span data-ttu-id="98f5a-158">Xcode</span><span class="sxs-lookup"><span data-stu-id="98f5a-158">Xcode</span></span>
  - <span data-ttu-id="98f5a-159">Openssl</span><span class="sxs-lookup"><span data-stu-id="98f5a-159">OpenSSL</span></span>

<span data-ttu-id="98f5a-160">Per compilare, eseguire `build.cmd` in Windows o `build.sh` in Linux e macOS dalla radice.</span><span class="sxs-lookup"><span data-stu-id="98f5a-160">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="98f5a-161">Per non eseguire i test, eseguire `build.cmd -t:Compile` o `./build.sh -t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="98f5a-161">If you don't want to execute tests, run `build.cmd -t:Compile` or `./build.sh -t:Compile`.</span></span> <span data-ttu-id="98f5a-162">Per compilare l'interfaccia della riga di comando in macOS Sierra, è necessario impostare la variabile di ambiente DOTNET_RUNTIME_ID eseguendo `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="98f5a-162">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="98f5a-163">Uso della compilazione</span><span class="sxs-lookup"><span data-stu-id="98f5a-163">Using your build</span></span>

<span data-ttu-id="98f5a-164">Usare l'eseguibile `dotnet` da *artifacts/{os}-{arch}/stage2* per provare l'interfaccia della riga di comando appena creata.</span><span class="sxs-lookup"><span data-stu-id="98f5a-164">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="98f5a-165">Per usare l'output della compilazione quando si chiama `dotnet` dalla console corrente, è anche possibile aggiungere *artifacts/{os}-{arch}/stage2* al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="98f5a-165">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="98f5a-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98f5a-166">See also</span></span>

- [<span data-ttu-id="98f5a-167">Runtime .NET</span><span class="sxs-lookup"><span data-stu-id="98f5a-167">.NET Runtime</span></span>](https://github.com/dotnet/runtime/blob/master/README.md)
- [<span data-ttu-id="98f5a-168">Guida per sviluppatori di .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="98f5a-168">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
- [<span data-ttu-id="98f5a-169">Pacchetti di distribuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="98f5a-169">.NET Core distribution packaging</span></span>](./distribution-packaging.md)
