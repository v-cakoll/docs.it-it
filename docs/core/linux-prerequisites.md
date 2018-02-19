---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 12/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 913d3869559b10af508e695a06d06021f8f90175
ms.sourcegitcommit: adcf9bdafeaa6bc243af7bf70b45f3df954f256a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="3877a-104">Prerequisiti per .NET Core in Linux</span><span class="sxs-lookup"><span data-stu-id="3877a-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="3877a-105">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux.</span><span class="sxs-lookup"><span data-stu-id="3877a-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="3877a-106">Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:</span><span class="sxs-lookup"><span data-stu-id="3877a-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="3877a-107">Riga di comando con l'editor preferito</span><span class="sxs-lookup"><span data-stu-id="3877a-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="3877a-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3877a-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="3877a-109">Versioni di Linux supportate</span><span class="sxs-lookup"><span data-stu-id="3877a-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="3877a-111">.NET core 2.0 considera Linux un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3877a-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="3877a-112">Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="3877a-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="3877a-113">NET Core 2.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:</span><span class="sxs-lookup"><span data-stu-id="3877a-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="3877a-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="3877a-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="3877a-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="3877a-115">CentOS 7</span></span>
 * <span data-ttu-id="3877a-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="3877a-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="3877a-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="3877a-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="3877a-118">Debian 8.7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="3877a-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="3877a-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="3877a-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="3877a-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="3877a-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="3877a-121">openSUSE 42.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="3877a-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="3877a-122">SUSE Enterprise Linux (SLES) 12 SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="3877a-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="3877a-123">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="3877a-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3877a-125">NET Core 1.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:</span><span class="sxs-lookup"><span data-stu-id="3877a-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="3877a-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="3877a-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="3877a-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="3877a-127">CentOS 7</span></span>
* <span data-ttu-id="3877a-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="3877a-128">Oracle Linux 7</span></span>
* <span data-ttu-id="3877a-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="3877a-129">Fedora 24</span></span>
* <span data-ttu-id="3877a-130">Debian 8.2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="3877a-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="3877a-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="3877a-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="3877a-132">Ubuntu 16.10 è supportato dalla versione patch più recente di .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="3877a-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="3877a-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="3877a-133">Linux Mint 17</span></span>
* <span data-ttu-id="3877a-134">openSUSE 42.1 o versioni successive (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="3877a-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="3877a-135">Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="3877a-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="3877a-136">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="3877a-136">Linux distribution dependencies</span></span>

<span data-ttu-id="3877a-137">Quelli che seguono sono esempi.</span><span class="sxs-lookup"><span data-stu-id="3877a-137">The following are intended to be examples.</span></span> <span data-ttu-id="3877a-138">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="3877a-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="3877a-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="3877a-139">Ubuntu</span></span>

<span data-ttu-id="3877a-140">Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="3877a-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="3877a-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="3877a-141">libunwind8</span></span>
* <span data-ttu-id="3877a-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="3877a-142">liblttng-ust0</span></span>
* <span data-ttu-id="3877a-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="3877a-143">libcurl3</span></span>
* <span data-ttu-id="3877a-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="3877a-144">libssl1.0.0</span></span>
* <span data-ttu-id="3877a-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="3877a-145">libuuid1</span></span>
* <span data-ttu-id="3877a-146">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="3877a-146">libkrb5-3</span></span>
* <span data-ttu-id="3877a-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="3877a-147">zlib1g</span></span>
* <span data-ttu-id="3877a-148">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="3877a-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="3877a-149">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="3877a-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="3877a-150">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="3877a-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="3877a-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="3877a-151">CentOS</span></span>

<span data-ttu-id="3877a-152">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="3877a-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="3877a-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="3877a-153">libunwind</span></span>
* <span data-ttu-id="3877a-154">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="3877a-154">lttng-ust</span></span>
* <span data-ttu-id="3877a-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="3877a-155">libcurl</span></span>
* <span data-ttu-id="3877a-156">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="3877a-156">openssl-libs</span></span>
* <span data-ttu-id="3877a-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="3877a-157">libuuid</span></span>
* <span data-ttu-id="3877a-158">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="3877a-158">krb5-libs</span></span>
* <span data-ttu-id="3877a-159">libicu</span><span class="sxs-lookup"><span data-stu-id="3877a-159">libicu</span></span>
* <span data-ttu-id="3877a-160">zlib</span><span class="sxs-lookup"><span data-stu-id="3877a-160">zlib</span></span>

<span data-ttu-id="3877a-161">Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).</span><span class="sxs-lookup"><span data-stu-id="3877a-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="3877a-162">Installazione delle dipendenze di .NET Core con i programmi di installazione nativi</span><span class="sxs-lookup"><span data-stu-id="3877a-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="3877a-163">Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="3877a-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="3877a-164">I programmi di installazione richiedono l'accesso amministratore (sudo) al server.</span><span class="sxs-lookup"><span data-stu-id="3877a-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="3877a-165">L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3877a-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="3877a-166">I programmi di installazione nativi installano.NET Core SDK a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="3877a-167">In Linux sono disponibili due opzioni relative al pacchetto di installazione:</span><span class="sxs-lookup"><span data-stu-id="3877a-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="3877a-168">L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="3877a-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="3877a-169">L'utilizzo dei pacchetti stessi, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="3877a-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="3877a-170">Gli script vengono installati con lo script di installazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3877a-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="3877a-171">Gli script `dotnet-install` vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="3877a-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="3877a-172">È possibile scaricare lo script da: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="3877a-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="3877a-173">Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3877a-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="3877a-174">Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.</span><span class="sxs-lookup"><span data-stu-id="3877a-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3877a-175">Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="3877a-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="3877a-176">Installare .NET Core per Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="3877a-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="3877a-177">Per installare .NET Core in RHEL 7:</span><span class="sxs-lookup"><span data-stu-id="3877a-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="3877a-178">Abilitare il canale di Red Hat .NET, disponibile nella sottoscrizione di RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="3877a-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="3877a-179">Per Red Hat Enterprise Server 7, usare:</span><span class="sxs-lookup"><span data-stu-id="3877a-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="3877a-180">Per Red Hat Enterprise 7 Workstation, usare:</span><span class="sxs-lookup"><span data-stu-id="3877a-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="3877a-181">Per il nodo di calcolo HPC di Red Hat Enterprise 7, usare:</span><span class="sxs-lookup"><span data-stu-id="3877a-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="3877a-182">Installare lo strumento scl.</span><span class="sxs-lookup"><span data-stu-id="3877a-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="3877a-183">Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="3877a-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="3877a-185">Installare .NET Core 2.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="3877a-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="3877a-186">Abilitare .NET Core 2.0 SDK/Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="3877a-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3877a-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="3877a-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="3877a-189">Installare .NET Core 1.1 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="3877a-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="3877a-190">Abilitare .NET Core 1.1 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="3877a-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="3877a-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="3877a-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="3877a-192">Installare .NET Core 1.0 SDK e Runtime:</span><span class="sxs-lookup"><span data-stu-id="3877a-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="3877a-193">Abilitare .NET Core 1.0 SDK e Runtime per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="3877a-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="3877a-194">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="3877a-195">Per informazioni sulla registrazione dell'accesso al canale Red Hat .NET, vedere [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) (Capitolo 1 dell'Introduzione a .NET Core 1.1) in Red Hat.</span><span class="sxs-lookup"><span data-stu-id="3877a-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="3877a-196">Installare .NET Core per Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="3877a-197">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="3877a-199">Registrare il codice Product Key Microsoft come attendibile.</span><span class="sxs-lookup"><span data-stu-id="3877a-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="3877a-200">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="3877a-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="3877a-201">**Ubuntu 17.10**</span><span class="sxs-lookup"><span data-stu-id="3877a-201">**Ubuntu 17.10**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   <span data-ttu-id="3877a-202">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="3877a-202">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="3877a-203">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="3877a-203">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="3877a-204">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="3877a-204">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="3877a-205">Installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3877a-205">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.1.4
   ```

4. <span data-ttu-id="3877a-206">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-206">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-207">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-207">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="3877a-208">Impostare il feed di pacchetti host della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="3877a-208">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="3877a-209">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="3877a-209">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="3877a-210">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="3877a-210">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="3877a-211">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="3877a-211">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="3877a-212">Installare .NET Core 1.x in Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="3877a-212">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="3877a-213">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-213">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="3877a-214">Installare .NET Core per Debian 8 o Debian 9 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-214">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="3877a-215">Per installare .NET Core in Debian 8 o Debian 9 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="3877a-215">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="3877a-216">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-216">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="3877a-217">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="3877a-217">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-218">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-218">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="3877a-219">Installare i componenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-219">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="3877a-220">Registrare il codice Product Key Microsoft attendibile.</span><span class="sxs-lookup"><span data-stu-id="3877a-220">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="3877a-221">Registrare il feed per il prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3877a-221">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="3877a-222">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="3877a-222">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="3877a-223">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="3877a-223">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="3877a-224">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-224">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="3877a-225">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-225">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="3877a-226">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-226">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-227">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-227">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="3877a-228">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="3877a-228">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="3877a-229">Scaricare i binari di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="3877a-229">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="3877a-230">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-230">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="3877a-231">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-231">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="3877a-232">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-232">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="3877a-233">Installare .NET Core per Fedora 24, Fedora 25 o Fedora 26 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-233">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="3877a-234">Per installare .NET Core 2.x in Fedora 26 o Fedora 25 oppure .NET Core 1.x in Fedora 24:</span><span class="sxs-lookup"><span data-stu-id="3877a-234">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="3877a-235">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-235">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="3877a-236">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="3877a-236">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-237">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-237">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="3877a-238">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="3877a-238">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="3877a-239">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3877a-239">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="3877a-240">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="3877a-240">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="3877a-241">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-241">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="3877a-242">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-242">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-243">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-243">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3877a-244">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="3877a-244">**Fedora 24**</span></span>

2. <span data-ttu-id="3877a-245">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="3877a-245">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="3877a-246">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="3877a-246">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="3877a-247">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-247">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="3877a-248">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-248">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="3877a-249">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-249">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="3877a-250">Installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-250">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="3877a-251">Per installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="3877a-251">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="3877a-252">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-252">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="3877a-253">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="3877a-253">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-254">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-254">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="3877a-255">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3877a-255">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="3877a-256">Aggiungere il feed del prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3877a-256">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="3877a-257">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-257">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="3877a-258">Aggiungere dotnet a PATH</span><span class="sxs-lookup"><span data-stu-id="3877a-258">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-259">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-259">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="3877a-260">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="3877a-260">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="3877a-261">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="3877a-261">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="3877a-262">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-262">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="3877a-263">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-263">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="3877a-264">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-264">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="3877a-265">Installare .NET Core per SUSE Linux Enterprise Server (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-265">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="3877a-266">Per installare .NET Core 2.x per SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span><span class="sxs-lookup"><span data-stu-id="3877a-266">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="3877a-267">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-267">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="3877a-268">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="3877a-268">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="3877a-269">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-269">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="3877a-270">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-270">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="3877a-271">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-271">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="3877a-272">Installare .NET Core per openSUSE (64 bit)</span><span class="sxs-lookup"><span data-stu-id="3877a-272">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="3877a-273">Per installare .NET Core 2.x per openSUSE o .NET Core 1.x per openSUSE (64 bit):</span><span class="sxs-lookup"><span data-stu-id="3877a-273">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="3877a-274">Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3877a-274">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="3877a-275">È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.</span><span class="sxs-lookup"><span data-stu-id="3877a-275">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3877a-276">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3877a-276">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="3877a-277">Registrare la chiave di firma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3877a-277">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="3877a-278">Aggiungere il feed del prodotto dotnet.</span><span class="sxs-lookup"><span data-stu-id="3877a-278">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="3877a-279">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-279">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="3877a-280">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-280">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3877a-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3877a-281">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="3877a-282">Ottenere i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="3877a-282">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="3877a-283">Scaricare il binario di .NET Core SDK (tarball).</span><span class="sxs-lookup"><span data-stu-id="3877a-283">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="3877a-284">Estrarre i binari di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3877a-284">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="3877a-285">Aggiungere dotnet al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="3877a-285">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="3877a-286">Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3877a-286">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="3877a-287">Se si verificano problemi in fase di installazione di .NET Core 2.x in una distribuzione/versione Linux supportata, vedere l'argomento [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti della versione 2.0) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="3877a-287">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="3877a-288">Se si verificano problemi in fase di installazione di .NET Core 1.x in una distribuzione/versione Linux supportata, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1) per le distribuzioni/versioni installate in uso.</span><span class="sxs-lookup"><span data-stu-id="3877a-288">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
