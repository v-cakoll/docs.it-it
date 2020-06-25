---
title: Installare .NET Core in SLES-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in SLES.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: e1a2490c1d653eb07aebdd51e34e1bf462906482
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324694"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="5bed7-103">Installare .NET Core SDK o runtime di .NET Core in SLES</span><span class="sxs-lookup"><span data-stu-id="5bed7-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="5bed7-104">.NET Core è supportato in SLES.</span><span class="sxs-lookup"><span data-stu-id="5bed7-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="5bed7-105">Questo articolo descrive come installare .NET Core in SLES.</span><span class="sxs-lookup"><span data-stu-id="5bed7-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5bed7-106">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="5bed7-106">Supported distributions</span></span>

<span data-ttu-id="5bed7-107">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in SLES 12 SP2 e SLES 15.</span><span class="sxs-lookup"><span data-stu-id="5bed7-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="5bed7-108">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di SLES non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="5bed7-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="5bed7-109">Un ✔️ indica che la versione di SLES o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="5bed7-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="5bed7-110">❌Indica che la versione di SLES o .NET Core non è supportata nella versione SLES.</span><span class="sxs-lookup"><span data-stu-id="5bed7-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="5bed7-111">Quando una versione di SLES e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="5bed7-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="5bed7-112">SLES</span><span class="sxs-lookup"><span data-stu-id="5bed7-112">SLES</span></span>                   | <span data-ttu-id="5bed7-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5bed7-113">.NET Core 2.1</span></span> | <span data-ttu-id="5bed7-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5bed7-114">.NET Core 3.1</span></span> | <span data-ttu-id="5bed7-115">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="5bed7-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5bed7-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="5bed7-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="5bed7-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5bed7-117">✔️ 2.1</span></span>        | <span data-ttu-id="5bed7-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5bed7-118">✔️ 3.1</span></span>        | <span data-ttu-id="5bed7-119">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5bed7-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5bed7-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="5bed7-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="5bed7-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5bed7-121">✔️ 2.1</span></span>        | <span data-ttu-id="5bed7-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5bed7-122">✔️ 3.1</span></span>        | <span data-ttu-id="5bed7-123">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5bed7-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="5bed7-124">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="5bed7-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="5bed7-125">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="5bed7-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5bed7-126">3.0</span><span class="sxs-lookup"><span data-stu-id="5bed7-126">3.0</span></span>
- <span data-ttu-id="5bed7-127">2.2</span><span class="sxs-lookup"><span data-stu-id="5bed7-127">2.2</span></span>
- <span data-ttu-id="5bed7-128">2.0</span><span class="sxs-lookup"><span data-stu-id="5bed7-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5bed7-129">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="5bed7-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="5bed7-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="5bed7-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="5bed7-131">Attualmente, il pacchetto di installazione del repository Microsoft SLES 15 installa il file *Microsoft-prod. repo* nella directory errata, impedendo a zypper di trovare i pacchetti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5bed7-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="5bed7-132">Per risolvere il problema, creare un collegamento simbolico nella directory corretta.</span><span class="sxs-lookup"><span data-stu-id="5bed7-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="5bed7-133">✔️ SLES 12</span><span class="sxs-lookup"><span data-stu-id="5bed7-133">SLES 12 ✔️</span></span>

<span data-ttu-id="5bed7-134">.NET Core richiede almeno SP2 per la famiglia SLES 12.</span><span class="sxs-lookup"><span data-stu-id="5bed7-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="5bed7-135">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="5bed7-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="5bed7-136">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5bed7-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="5bed7-137">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="5bed7-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="5bed7-138">Dependencies</span><span class="sxs-lookup"><span data-stu-id="5bed7-138">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="5bed7-139">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="5bed7-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5bed7-140">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="5bed7-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5bed7-141">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5bed7-141">Next steps</span></span>

- [<span data-ttu-id="5bed7-142">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5bed7-142">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
