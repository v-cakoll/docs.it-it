---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="c085e-104">Prerequisiti per .NET Core in Linux</span><span class="sxs-lookup"><span data-stu-id="c085e-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="c085e-105">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux.</span><span class="sxs-lookup"><span data-stu-id="c085e-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="c085e-106">Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:</span><span class="sxs-lookup"><span data-stu-id="c085e-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="c085e-107">Riga di comando con l'editor preferito</span><span class="sxs-lookup"><span data-stu-id="c085e-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="c085e-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c085e-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="c085e-109">Versioni di Linux supportate</span><span class="sxs-lookup"><span data-stu-id="c085e-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c085e-111">.NET core 2.0 considera Linux un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c085e-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c085e-112">Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c085e-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="c085e-113">NET Core 2.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:</span><span class="sxs-lookup"><span data-stu-id="c085e-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="c085e-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="c085e-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="c085e-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c085e-115">CentOS 7</span></span>
 * <span data-ttu-id="c085e-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="c085e-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="c085e-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="c085e-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="c085e-118">Debian 8.7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="c085e-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="c085e-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c085e-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="c085e-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="c085e-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="c085e-121">openSUSE 42.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="c085e-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="c085e-122">SUSE Enterprise Linux (SLES) 12 SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="c085e-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="c085e-123">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="c085e-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c085e-125">NET Core 1.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:</span><span class="sxs-lookup"><span data-stu-id="c085e-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="c085e-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="c085e-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="c085e-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c085e-127">CentOS 7</span></span>
* <span data-ttu-id="c085e-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="c085e-128">Oracle Linux 7</span></span>
* <span data-ttu-id="c085e-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="c085e-129">Fedora 24</span></span>
* <span data-ttu-id="c085e-130">Debian 8.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="c085e-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="c085e-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="c085e-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="c085e-132">Ubuntu 16.10 è supportato dalla versione patch più recente di .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="c085e-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="c085e-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="c085e-133">Linux Mint 17</span></span>
* <span data-ttu-id="c085e-134">openSUSE 42.1 o versioni successive (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="c085e-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="c085e-135">Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="c085e-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c085e-136">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="c085e-136">Linux distribution dependencies</span></span>

<span data-ttu-id="c085e-137">Di seguito è destinati a essere esempi.</span><span class="sxs-lookup"><span data-stu-id="c085e-137">The following are intended to be examples.</span></span> <span data-ttu-id="c085e-138">Le versioni esatte e nomi possono variare leggermente la distribuzione di Linux di scelta.</span><span class="sxs-lookup"><span data-stu-id="c085e-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c085e-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c085e-139">Ubuntu</span></span>

<span data-ttu-id="c085e-140">Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c085e-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="c085e-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="c085e-141">libunwind8</span></span>
* <span data-ttu-id="c085e-142">liblttng ust0</span><span class="sxs-lookup"><span data-stu-id="c085e-142">liblttng-ust0</span></span>
* <span data-ttu-id="c085e-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="c085e-143">libcurl3</span></span>
* <span data-ttu-id="c085e-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c085e-144">libssl1.0.0</span></span>
* <span data-ttu-id="c085e-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="c085e-145">libuuid1</span></span>
* <span data-ttu-id="c085e-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="c085e-146">libkrb5</span></span>
* <span data-ttu-id="c085e-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c085e-147">zlib1g</span></span>
* <span data-ttu-id="c085e-148">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="c085e-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="c085e-149">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="c085e-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="c085e-150">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="c085e-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="c085e-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="c085e-151">CentOS</span></span>

<span data-ttu-id="c085e-152">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c085e-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="c085e-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="c085e-153">libunwind</span></span>
* <span data-ttu-id="c085e-154">lttng ust</span><span class="sxs-lookup"><span data-stu-id="c085e-154">lttng-ust</span></span>
* <span data-ttu-id="c085e-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="c085e-155">libcurl</span></span>
* <span data-ttu-id="c085e-156">librerie OpenSSL</span><span class="sxs-lookup"><span data-stu-id="c085e-156">openssl-libs</span></span>
* <span data-ttu-id="c085e-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="c085e-157">libuuid</span></span>
* <span data-ttu-id="c085e-158">krb5 librerie</span><span class="sxs-lookup"><span data-stu-id="c085e-158">krb5-libs</span></span>
* <span data-ttu-id="c085e-159">libicu</span><span class="sxs-lookup"><span data-stu-id="c085e-159">libicu</span></span>
* <span data-ttu-id="c085e-160">zlib</span><span class="sxs-lookup"><span data-stu-id="c085e-160">zlib</span></span>

<span data-ttu-id="c085e-161">Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).</span><span class="sxs-lookup"><span data-stu-id="c085e-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="c085e-162">Installazione delle dipendenze di .NET Core con i programmi di installazione nativi</span><span class="sxs-lookup"><span data-stu-id="c085e-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="c085e-163">Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c085e-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="c085e-164">I programmi di installazione richiedono l'accesso amministratore (sudo) al server.</span><span class="sxs-lookup"><span data-stu-id="c085e-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="c085e-165">L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c085e-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="c085e-166">I programmi di installazione nativi installano.NET Core SDK a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="c085e-167">In Linux sono disponibili due opzioni relative al pacchetto di installazione:</span><span class="sxs-lookup"><span data-stu-id="c085e-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="c085e-168">L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="c085e-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="c085e-169">L'utilizzo dei pacchetti stessi, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="c085e-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="c085e-170">Gli script vengono installati con lo script di installazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="c085e-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="c085e-171">Gli script `dotnet-install` vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="c085e-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="c085e-172">È possibile scaricare lo script da: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="c085e-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="c085e-173">Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c085e-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="c085e-174">Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.</span><span class="sxs-lookup"><span data-stu-id="c085e-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c085e-175">Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="c085e-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="c085e-176">Installare .NET Core per Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="c085e-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="c085e-177">Per installare .NET Core in RHEL 7:</span><span class="sxs-lookup"><span data-stu-id="c085e-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="c085e-178">Abilitare il canale di Red Hat .NET, disponibile nella sottoscrizione di RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="c085e-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="c085e-179">Per Red Hat Enterprise Server 7, usare:</span><span class="sxs-lookup"><span data-stu-id="c085e-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="c085e-180">Per Red Hat Enterprise 7 Workstation, usare:</span><span class="sxs-lookup"><span data-stu-id="c085e-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="c085e-181">Per il nodo di calcolo HPC di Red Hat Enterprise 7, usare:</span><span class="sxs-lookup"><span data-stu-id="c085e-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="c085e-182">Installare lo strumento scl.</span><span class="sxs-lookup"><span data-stu-id="c085e-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="c085e-183">Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="c085e-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c085e-185">Installare .NET Core 2.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="c085e-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="c085e-186">Abilitare .NET Core 2.0 SDK/Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="c085e-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c085e-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="c085e-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="c085e-189">Installare .NET Core 1.1 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="c085e-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="c085e-190">Abilitare .NET Core 1.1 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="c085e-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="c085e-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="c085e-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="c085e-192">Installare .NET Core 1.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="c085e-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="c085e-193">Abilitare .NET Core 1.0 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="c085e-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="c085e-194">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="c085e-195">Per informazioni sulla registrazione dell'accesso al canale Red Hat .NET, vedere [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) (Capitolo 1 dell'Introduzione a .NET Core 1.1) in Red Hat.</span><span class="sxs-lookup"><span data-stu-id="c085e-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="c085e-196">Installare .NET Core per Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="c085e-197">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="c085e-199">Registrare il codice Product Key Microsoft come attendibile.</span><span class="sxs-lookup"><span data-stu-id="c085e-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="c085e-200">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="c085e-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="c085e-201">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="c085e-201">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="c085e-202">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="c085e-202">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="c085e-203">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="c085e-203">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="c085e-204">Installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c085e-204">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="c085e-205">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-205">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-206">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-206">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="c085e-207">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="c085e-207">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="c085e-208">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="c085e-208">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="c085e-209">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="c085e-209">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="c085e-210">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="c085e-210">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="c085e-211">Installare .NET Core 1.x in Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="c085e-211">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="c085e-212">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-212">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="c085e-213">Installare .NET Core per Debian 8 o Debian 9 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-213">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="c085e-214">Per installare .NET Core in Debian 8 o Debian 9 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="c085e-214">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="c085e-215">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-215">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="c085e-216">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="c085e-216">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-217">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-217">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="c085e-218">Installare i componenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-218">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="c085e-219">Registrare il codice Product Key Microsoft attendibile.</span><span class="sxs-lookup"><span data-stu-id="c085e-219">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="c085e-220">Registrare il feed per il prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c085e-220">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="c085e-221">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="c085e-221">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="c085e-222">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="c085e-222">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="c085e-223">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-223">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="c085e-224">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-224">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="c085e-225">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-225">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-226">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="c085e-227">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="c085e-227">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="c085e-228">Scaricare i binari di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="c085e-228">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="c085e-229">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-229">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="c085e-230">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-230">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="c085e-231">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-231">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="c085e-232">Installare .NET Core per Fedora 24, Fedora 25 o Fedora 26 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-232">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="c085e-233">Per installare .NET Core 2.x in Fedora 26 o Fedora 25 oppure .NET Core 1.x in Fedora 24:</span><span class="sxs-lookup"><span data-stu-id="c085e-233">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="c085e-234">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-234">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="c085e-235">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="c085e-235">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-236">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-236">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c085e-237">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="c085e-237">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="c085e-238">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c085e-238">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="c085e-239">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="c085e-239">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="c085e-240">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-240">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="c085e-241">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-241">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-242">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-242">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c085e-243">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="c085e-243">**Fedora 24**</span></span>

2. <span data-ttu-id="c085e-244">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="c085e-244">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="c085e-245">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="c085e-245">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="c085e-246">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-246">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="c085e-247">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-247">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="c085e-248">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-248">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="c085e-249">Installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-249">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="c085e-250">Per installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="c085e-250">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="c085e-251">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-251">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="c085e-252">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="c085e-252">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-253">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-253">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="c085e-254">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c085e-254">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="c085e-255">Aggiungere il feed del prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c085e-255">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="c085e-256">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-256">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="c085e-257">Aggiungere dotnet a PATH</span><span class="sxs-lookup"><span data-stu-id="c085e-257">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-258">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-258">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="c085e-259">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="c085e-259">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="c085e-260">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="c085e-260">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="c085e-261">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-261">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="c085e-262">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-262">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="c085e-263">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-263">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="c085e-264">Installare .NET Core per SUSE Linux Enterprise Server (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-264">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="c085e-265">Per installare .NET Core 2.x per SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="c085e-265">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="c085e-266">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-266">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="c085e-267">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="c085e-267">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="c085e-268">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-268">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="c085e-269">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-269">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="c085e-270">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-270">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="c085e-271">Installare .NET Core per openSUSE (64 bit)</span><span class="sxs-lookup"><span data-stu-id="c085e-271">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="c085e-272">Per installare .NET Core 2.x per openSUSE o .NET Core 1.x per openSUSE (64 bit):</span><span class="sxs-lookup"><span data-stu-id="c085e-272">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="c085e-273">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c085e-273">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="c085e-274">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="c085e-274">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c085e-275">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c085e-275">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="c085e-276">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c085e-276">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="c085e-277">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="c085e-277">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="c085e-278">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-278">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="c085e-279">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-279">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c085e-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c085e-280">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="c085e-281">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="c085e-281">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="c085e-282">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="c085e-282">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="c085e-283">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c085e-283">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="c085e-284">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="c085e-284">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="c085e-285">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c085e-285">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="c085e-286">Se si verificano problemi in fase di installazione di .NET Core 2.x in una distribuzione/versione Linux supportata, vedere l'argomento [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti della versione 2.0) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="c085e-286">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="c085e-287">Se si verificano problemi in fase di installazione di .NET Core 1.x in una distribuzione/versione Linux supportata, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="c085e-287">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
