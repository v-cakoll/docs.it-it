---
title: Prerequisiti per .NET Core in Mac
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="d850e-104">Prerequisiti per .NET Core in Mac</span><span class="sxs-lookup"><span data-stu-id="d850e-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="d850e-105">Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.</span><span class="sxs-lookup"><span data-stu-id="d850e-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="d850e-106">Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="d850e-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="d850e-107">Versioni macOS supportate</span><span class="sxs-lookup"><span data-stu-id="d850e-107">Supported macOS versions</span></span>

<span data-ttu-id="d850e-108">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="d850e-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d850e-109">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="d850e-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="d850e-110">macOS 10.11 "El Capitan" (solo .NET Core 1.x)</span><span class="sxs-lookup"><span data-stu-id="d850e-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="d850e-111">Per l'elenco completo dei sistemi operativi supportati, vedere [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) (Versioni supportate dei sistemi operativi).</span><span class="sxs-lookup"><span data-stu-id="d850e-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="d850e-112">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="d850e-112">.NET Core dependencies</span></span>

<span data-ttu-id="d850e-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="d850e-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="d850e-114">Per l'esecuzione di .NET Core 1.x in macOS è necessario OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="d850e-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="d850e-115">È possibile ottenere facilmente OpenSSL tramite il sistema di gestione pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS.</span><span class="sxs-lookup"><span data-stu-id="d850e-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="d850e-116">Dopo aver installato *brew*, installare OpenSSL eseguendo i comandi seguenti da un prompt (dei comandi) Terminal:</span><span class="sxs-lookup"><span data-stu-id="d850e-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="d850e-117">Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="d850e-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d850e-118">In caso di problemi con l'installazione in macOS, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1).</span><span class="sxs-lookup"><span data-stu-id="d850e-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="d850e-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="d850e-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="d850e-120">Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET).</span><span class="sxs-lookup"><span data-stu-id="d850e-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d850e-121">In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti) per la versione installata.</span><span class="sxs-lookup"><span data-stu-id="d850e-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="d850e-122">Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="d850e-122">Visual Studio for Mac</span></span>

<span data-ttu-id="d850e-123">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="d850e-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="d850e-124">Se si vuole tuttavia sviluppare applicazioni .NET Core in Mac in un ambiente di sviluppo integrato, è possibile usare [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="d850e-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="d850e-125">Per lo sviluppo di .NET Core in macOS con Visual Studio per Mac sono previsti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d850e-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="d850e-126">Versione supportata del sistema operativo macOS</span><span class="sxs-lookup"><span data-stu-id="d850e-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="d850e-127">OpenSSL (.NET Core 1.x solo ; .NET Core 2.x usa servizi di sicurezza disponibili in modo nativo in macOS)</span><span class="sxs-lookup"><span data-stu-id="d850e-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="d850e-128">.NET core SDK per Mac</span><span class="sxs-lookup"><span data-stu-id="d850e-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="d850e-129">Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="d850e-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

