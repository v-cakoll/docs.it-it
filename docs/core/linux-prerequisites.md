---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="5453f-104">Prerequisiti per .NET Core in Linux</span><span class="sxs-lookup"><span data-stu-id="5453f-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="5453f-105">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux.</span><span class="sxs-lookup"><span data-stu-id="5453f-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="5453f-106">Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:</span><span class="sxs-lookup"><span data-stu-id="5453f-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="5453f-107">Riga di comando con l'editor preferito</span><span class="sxs-lookup"><span data-stu-id="5453f-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="5453f-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5453f-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="5453f-109">Versioni di Linux supportate</span><span class="sxs-lookup"><span data-stu-id="5453f-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="5453f-111">.NET core 2.0 considera Linux un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5453f-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="5453f-112">Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="5453f-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="5453f-113">NET Core 2.x è supportato nelle versioni/distribuzioni di Linux x64 seguenti:</span><span class="sxs-lookup"><span data-stu-id="5453f-113">NET Core 2.x is supported on the following Linux x64 distributions/versions:</span></span>

 * <span data-ttu-id="5453f-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="5453f-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="5453f-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="5453f-115">CentOS 7</span></span>
 * <span data-ttu-id="5453f-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="5453f-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="5453f-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="5453f-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="5453f-118">Debian 8.7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="5453f-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="5453f-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="5453f-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="5453f-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="5453f-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="5453f-121">openSUSE 42.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="5453f-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="5453f-122">SUSE Enterprise Linux (SLES) 12 SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="5453f-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="5453f-123">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="5453f-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5453f-125">NET Core 1.x è supportato nelle versioni/distribuzioni di Linux x64 seguenti:</span><span class="sxs-lookup"><span data-stu-id="5453f-125">.NET Core 1.x is supported on the following Linux x64 distributions/versions:</span></span>

* <span data-ttu-id="5453f-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="5453f-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="5453f-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="5453f-127">CentOS 7</span></span>
* <span data-ttu-id="5453f-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="5453f-128">Oracle Linux 7</span></span>
* <span data-ttu-id="5453f-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="5453f-129">Fedora 24</span></span>
* <span data-ttu-id="5453f-130">Debian 8.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="5453f-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="5453f-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="5453f-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="5453f-132">Ubuntu 16.10 è supportato dalla versione patch più recente di .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="5453f-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="5453f-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="5453f-133">Linux Mint 17</span></span>
* <span data-ttu-id="5453f-134">openSUSE 42.1 o versioni successive (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="5453f-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="5453f-135">Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="5453f-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="5453f-136">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="5453f-136">Linux distribution dependencies</span></span>

### <a name="ubuntu"></a><span data-ttu-id="5453f-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5453f-137">Ubuntu</span></span>

<span data-ttu-id="5453f-138">Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="5453f-138">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="5453f-139">libunwind8</span><span class="sxs-lookup"><span data-stu-id="5453f-139">libunwind8</span></span>
* <span data-ttu-id="5453f-140">libunwind8-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-140">libunwind8-dev</span></span>
* <span data-ttu-id="5453f-141">gettext</span><span class="sxs-lookup"><span data-stu-id="5453f-141">gettext</span></span>
* <span data-ttu-id="5453f-142">libicu-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-142">libicu-dev</span></span>
* <span data-ttu-id="5453f-143">liblttng-ust-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-143">liblttng-ust-dev</span></span>
* <span data-ttu-id="5453f-144">libcurl4-openssl-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-144">libcurl4-openssl-dev</span></span>
* <span data-ttu-id="5453f-145">libssl-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-145">libssl-dev</span></span>
* <span data-ttu-id="5453f-146">uuid-dev</span><span class="sxs-lookup"><span data-stu-id="5453f-146">uuid-dev</span></span>
* <span data-ttu-id="5453f-147">unzip</span><span class="sxs-lookup"><span data-stu-id="5453f-147">unzip</span></span>

### <a name="centos"></a><span data-ttu-id="5453f-148">CentOS</span><span class="sxs-lookup"><span data-stu-id="5453f-148">CentOS</span></span>

<span data-ttu-id="5453f-149">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="5453f-149">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="5453f-150">deltarpm</span><span class="sxs-lookup"><span data-stu-id="5453f-150">deltarpm</span></span>
* <span data-ttu-id="5453f-151">epel-release</span><span class="sxs-lookup"><span data-stu-id="5453f-151">epel-release</span></span>
* <span data-ttu-id="5453f-152">unzip</span><span class="sxs-lookup"><span data-stu-id="5453f-152">unzip</span></span>
* <span data-ttu-id="5453f-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="5453f-153">libunwind</span></span>
* <span data-ttu-id="5453f-154">gettext</span><span class="sxs-lookup"><span data-stu-id="5453f-154">gettext</span></span>
* <span data-ttu-id="5453f-155">libcurl-devel</span><span class="sxs-lookup"><span data-stu-id="5453f-155">libcurl-devel</span></span>
* <span data-ttu-id="5453f-156">openssl-devel</span><span class="sxs-lookup"><span data-stu-id="5453f-156">openssl-devel</span></span>
* <span data-ttu-id="5453f-157">zlib</span><span class="sxs-lookup"><span data-stu-id="5453f-157">zlib</span></span>
* <span data-ttu-id="5453f-158">libicu-devel</span><span class="sxs-lookup"><span data-stu-id="5453f-158">libicu-devel</span></span>

<span data-ttu-id="5453f-159">Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).</span><span class="sxs-lookup"><span data-stu-id="5453f-159">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="5453f-160">Installazione delle dipendenze di .NET Core con i programmi di installazione nativi</span><span class="sxs-lookup"><span data-stu-id="5453f-160">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="5453f-161">Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="5453f-161">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="5453f-162">I programmi di installazione richiedono l'accesso amministratore (sudo) al server.</span><span class="sxs-lookup"><span data-stu-id="5453f-162">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="5453f-163">L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5453f-163">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="5453f-164">I programmi di installazione nativi installano.NET Core SDK a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-164">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="5453f-165">In Linux sono disponibili due opzioni relative al pacchetto di installazione:</span><span class="sxs-lookup"><span data-stu-id="5453f-165">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="5453f-166">L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="5453f-166">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="5453f-167">L'utilizzo dei pacchetti stessi, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="5453f-167">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="5453f-168">Gli script vengono installati con lo script di installazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="5453f-168">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="5453f-169">Gli script `dotnet-install` vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="5453f-169">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="5453f-170">È possibile scaricare gli script dal [repository di GitHub dell'interfaccia della riga di comando](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span><span class="sxs-lookup"><span data-stu-id="5453f-170">You can download the scripts from the [CLI GitHub repo](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span></span>

<span data-ttu-id="5453f-171">Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5453f-171">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="5453f-172">Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.</span><span class="sxs-lookup"><span data-stu-id="5453f-172">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5453f-173">Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="5453f-173">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="5453f-174">Installare .NET Core per Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="5453f-174">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="5453f-175">Per installare .NET Core in RHEL 7:</span><span class="sxs-lookup"><span data-stu-id="5453f-175">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="5453f-176">Abilitare il canale di Red Hat .NET, disponibile nella sottoscrizione di RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="5453f-176">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="5453f-177">Per Red Hat Enterprise Server 7, usare:</span><span class="sxs-lookup"><span data-stu-id="5453f-177">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="5453f-178">Per Red Hat Enterprise 7 Workstation, usare:</span><span class="sxs-lookup"><span data-stu-id="5453f-178">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="5453f-179">Per il nodo di calcolo HPC di Red Hat Enterprise 7, usare:</span><span class="sxs-lookup"><span data-stu-id="5453f-179">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="5453f-180">Installare lo strumento scl.</span><span class="sxs-lookup"><span data-stu-id="5453f-180">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="5453f-181">Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="5453f-181">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-182">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-182">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="5453f-183">Installare .NET Core 2.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="5453f-183">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="5453f-184">Abilitare .NET Core 2.0 SDK/Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="5453f-184">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-185">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-185">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5453f-186">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="5453f-186">**.NET Core 1.1**</span></span>

<span data-ttu-id="5453f-187">Installare .NET Core 1.1 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="5453f-187">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="5453f-188">Abilitare .NET Core 1.1 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="5453f-188">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="5453f-189">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="5453f-189">**.NET Core 1.0**</span></span>

<span data-ttu-id="5453f-190">Installare .NET Core 1.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="5453f-190">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="5453f-191">Abilitare .NET Core 1.0 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="5453f-191">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="5453f-192">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-192">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="5453f-193">Per informazioni sulla registrazione dell'accesso al canale Red Hat .NET, vedere [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) (Capitolo 1 dell'Introduzione a .NET Core 1.1) in Red Hat.</span><span class="sxs-lookup"><span data-stu-id="5453f-193">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="5453f-194">Installare .NET Core per Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-194">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="5453f-195">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-195">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-196">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-196">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="5453f-197">Registrare il codice Product Key Microsoft come attendibile.</span><span class="sxs-lookup"><span data-stu-id="5453f-197">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="5453f-198">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="5453f-198">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="5453f-199">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="5453f-199">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="5453f-200">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="5453f-200">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="5453f-201">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="5453f-201">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="5453f-202">Installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5453f-202">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="5453f-203">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-203">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-204">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-204">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="5453f-205">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="5453f-205">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="5453f-206">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="5453f-206">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="5453f-207">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="5453f-207">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="5453f-208">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="5453f-208">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="5453f-209">Installare .NET Core 1.x in Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="5453f-209">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="5453f-210">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-210">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="5453f-211">Installare .NET Core per Debian 8 o Debian 9 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-211">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="5453f-212">Per installare .NET Core in Debian 8 o Debian 9 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="5453f-212">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="5453f-213">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-213">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="5453f-214">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="5453f-214">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-215">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-215">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="5453f-216">Installare i componenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-216">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="5453f-217">Registrare il codice Product Key Microsoft attendibile.</span><span class="sxs-lookup"><span data-stu-id="5453f-217">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="5453f-218">Registrare il feed per il prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5453f-218">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="5453f-219">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="5453f-219">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="5453f-220">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="5453f-220">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="5453f-221">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-221">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="5453f-222">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-222">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-223">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-223">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="5453f-224">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="5453f-224">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="5453f-225">Scaricare i binari di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="5453f-225">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="5453f-226">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-226">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="5453f-227">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-227">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="5453f-228">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-228">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="5453f-229">Installare .NET Core per Fedora 24, Fedora 25 o Fedora 26 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-229">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="5453f-230">Per installare .NET Core per Fedora 26, Fedora 25 (.NET Core 2.x) o Fedora 24 (.NET Core 1.x):</span><span class="sxs-lookup"><span data-stu-id="5453f-230">To Install .NET Core for Fedora 26, Fedora 25 (.NET Core 2.x) or Fedora 24 (.NET Core 1.x):</span></span>

1. <span data-ttu-id="5453f-231">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-231">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="5453f-232">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="5453f-232">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-233">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-233">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="5453f-234">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="5453f-234">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="5453f-235">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5453f-235">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="5453f-236">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="5453f-236">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="5453f-237">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-237">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="5453f-238">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-238">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-239">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-239">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5453f-240">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="5453f-240">**Fedora 24**</span></span>

2. <span data-ttu-id="5453f-241">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="5453f-241">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="5453f-242">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="5453f-242">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="5453f-243">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-243">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="5453f-244">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-244">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="5453f-245">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-245">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="5453f-246">Installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-246">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="5453f-247">Per installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="5453f-247">To Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="5453f-248">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-248">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="5453f-249">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="5453f-249">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-250">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="5453f-251">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5453f-251">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="5453f-252">Aggiungere il feed del prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5453f-252">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="5453f-253">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-253">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="5453f-254">Aggiungere dotnet a PATH</span><span class="sxs-lookup"><span data-stu-id="5453f-254">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-255">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-255">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="5453f-256">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="5453f-256">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="5453f-257">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="5453f-257">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="5453f-258">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-258">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="5453f-259">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-259">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="5453f-260">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-260">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="5453f-261">Installare .NET Core per SUSE Linux Enterprise Server (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-261">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="5453f-262">Per installare .NET Core 2.x per SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="5453f-262">To Install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="5453f-263">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-263">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="5453f-264">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="5453f-264">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="5453f-265">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-265">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="5453f-266">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-266">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="5453f-267">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-267">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="5453f-268">Installare .NET Core per openSUSE (64 bit)</span><span class="sxs-lookup"><span data-stu-id="5453f-268">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="5453f-269">Per installare .NET Core 2.x per openSUSE o .NET Core 1.x per openSUSE (64 bit):</span><span class="sxs-lookup"><span data-stu-id="5453f-269">To Install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="5453f-270">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5453f-270">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="5453f-271">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="5453f-271">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5453f-272">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5453f-272">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="5453f-273">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5453f-273">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="5453f-274">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="5453f-274">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="5453f-275">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-275">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="5453f-276">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-276">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5453f-277">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5453f-277">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="5453f-278">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="5453f-278">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="5453f-279">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="5453f-279">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="5453f-280">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5453f-280">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="5453f-281">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="5453f-281">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="5453f-282">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5453f-282">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="5453f-283">Se si verificano problemi in fase di installazione di .NET Core 2.x in una distribuzione/versione Linux supportata, vedere l'argomento [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti della versione 2.0) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="5453f-283">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="5453f-284">Se si verificano problemi in fase di installazione di .NET Core 1.x in una distribuzione/versione Linux supportata, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="5453f-284">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>

