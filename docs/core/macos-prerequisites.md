---
title: Prerequisiti per .NET Core in Mac
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
author: guardrex
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: bc6e0b20c61c474c7069b757528dbc1ea38354e3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656310"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="64aa3-103">Prerequisiti per .NET Core in macOS</span><span class="sxs-lookup"><span data-stu-id="64aa3-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="64aa3-104">Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.</span><span class="sxs-lookup"><span data-stu-id="64aa3-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="64aa3-105">Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="64aa3-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="64aa3-106">Versioni macOS supportate</span><span class="sxs-lookup"><span data-stu-id="64aa3-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="64aa3-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="64aa3-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="64aa3-108">.NET Core 2.x è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="64aa3-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="64aa3-109">macOS 10.12 "Sierra" e versioni successive</span><span class="sxs-lookup"><span data-stu-id="64aa3-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="64aa3-110">Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportati da .NET Core 2.1 e .NET Core 2.2, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 - Versioni di sistemi operativi supportate) e [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2 - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="64aa3-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="64aa3-111">Per i collegamenti per il download e altre informazioni, vedere [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Download di .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Download di .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="64aa3-111">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>


# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="64aa3-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="64aa3-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="64aa3-113">.NET Core 1.x è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="64aa3-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="64aa3-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="64aa3-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="64aa3-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="64aa3-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="64aa3-116">Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportati da .NET Core 1.1 e .NET Core 1.0, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) (.NET Core 1.1 - Versioni di sistemi operativi supportate) e [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.0 - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="64aa3-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="64aa3-117">Per i collegamenti per il download e altre informazioni, vedere [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Download di .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Download di .NET Core 1.0).</span><span class="sxs-lookup"><span data-stu-id="64aa3-117">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="64aa3-118">.NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="64aa3-118">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="64aa3-119">.NET Core 3.0 Preview 1 è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="64aa3-119">.NET Core 3.0 Preview 1 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="64aa3-120">macOS 10.12 "Sierra" e versioni successive</span><span class="sxs-lookup"><span data-stu-id="64aa3-120">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="64aa3-121">Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportati da .NET Core 3.0, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0 - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="64aa3-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="64aa3-122">Per i collegamenti di download e altre informazioni, vedere [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0) (Download di .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="64aa3-122">For download links and more information, see [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="64aa3-123">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="64aa3-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="64aa3-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="64aa3-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="64aa3-125">Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="64aa3-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="64aa3-126">In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) (Problemi noti) per la versione installata.</span><span class="sxs-lookup"><span data-stu-id="64aa3-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="64aa3-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="64aa3-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="64aa3-128">Per l'esecuzione di .NET Core 1.x in macOS è necessario OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="64aa3-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="64aa3-129">È possibile ottenere facilmente OpenSSL tramite il sistema di gestione pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS.</span><span class="sxs-lookup"><span data-stu-id="64aa3-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="64aa3-130">Dopo aver installato *brew*, installare OpenSSL eseguendo i comandi seguenti da un prompt (dei comandi) Terminal:</span><span class="sxs-lookup"><span data-stu-id="64aa3-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="64aa3-131">Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="64aa3-131">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="64aa3-132">In caso di problemi con l'installazione in macOS, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1).</span><span class="sxs-lookup"><span data-stu-id="64aa3-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="64aa3-133">.NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="64aa3-133">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="64aa3-134">Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="64aa3-134">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="64aa3-135">In caso di problemi con l'installazione in macOS, vedere l'argomento [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (Note sulla versione) per la versione installata.</span><span class="sxs-lookup"><span data-stu-id="64aa3-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="64aa3-136">Aumentare il limite massimo di file aperti (versioni di .NET Core prima di .NET Core SDK 2.0.2)</span><span class="sxs-lookup"><span data-stu-id="64aa3-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span> 

<span data-ttu-id="64aa3-137">Nelle versioni precedenti di .NET Core (prima di .NET Core SDK 2.0.2) il limite di file aperti predefinito per macOS potrebbe non essere sufficiente per alcuni carichi di lavoro di .NET Core, ad esempio il ripristino di progetti o l'esecuzione di unit test.</span><span class="sxs-lookup"><span data-stu-id="64aa3-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="64aa3-138">È possibile aumentare questo limite seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="64aa3-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="64aa3-139">Usare un editor di testo e creare un nuovo file _/Library/LaunchDaemons/limit.maxfiles.plist_, quindi salvare il file con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="64aa3-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. <span data-ttu-id="64aa3-140">Eseguire il comando seguente in un finestra del terminale:</span><span class="sxs-lookup"><span data-stu-id="64aa3-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="64aa3-141">Riavviare il computer Mac per applicare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="64aa3-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="64aa3-142">Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="64aa3-142">Visual Studio for Mac</span></span>

<span data-ttu-id="64aa3-143">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="64aa3-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="64aa3-144">Se si vuole tuttavia sviluppare applicazioni .NET Core in Mac in un ambiente di sviluppo integrato, è possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="64aa3-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="64aa3-145">Per lo sviluppo di .NET Core in macOS con Visual Studio per Mac sono previsti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="64aa3-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="64aa3-146">Versione supportata del sistema operativo macOS</span><span class="sxs-lookup"><span data-stu-id="64aa3-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="64aa3-147">OpenSSL (.NET Core 1.x solo ; .NET Core 2.x usa servizi di sicurezza disponibili in modo nativo in macOS)</span><span class="sxs-lookup"><span data-stu-id="64aa3-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="64aa3-148">.NET core SDK per Mac</span><span class="sxs-lookup"><span data-stu-id="64aa3-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="64aa3-149">Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="64aa3-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/visual-studio-mac/)
