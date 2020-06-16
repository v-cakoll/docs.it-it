---
title: Installare .NET Core su Alpine-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Alpine.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: bbaf4ee9020dcd33c894b5376bf04ad65db8d378
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84771503"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="b7770-103">Installare .NET Core SDK o runtime di .NET Core in Alpine</span><span class="sxs-lookup"><span data-stu-id="b7770-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="b7770-104">Questo articolo descrive come installare .NET Core su Alpine.</span><span class="sxs-lookup"><span data-stu-id="b7770-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="b7770-105">Quando una versione alpina non è più supportata, .NET Core non è più supportato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="b7770-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="b7770-106">Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b7770-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="b7770-107">Non sono disponibili programmi di installazione per Alpine.</span><span class="sxs-lookup"><span data-stu-id="b7770-107">There are no installers for Alpine.</span></span> <span data-ttu-id="b7770-108">È necessario utilizzare lo [script di installazione](#scripted-install) o seguire le istruzioni di [installazione manuale](#manual-install) .</span><span class="sxs-lookup"><span data-stu-id="b7770-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="b7770-109">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="b7770-109">Supported distributions</span></span>

<span data-ttu-id="b7770-110">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni Alpine su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b7770-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="b7770-111">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Alpine raggiunge la fine del ciclo di vita](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="b7770-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="b7770-112">Un ✔️ indica che la versione di Alpine o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="b7770-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="b7770-113">❌Indica che la versione di Alpine o .NET Core non è supportata nella versione alpina.</span><span class="sxs-lookup"><span data-stu-id="b7770-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="b7770-114">Quando una versione di Alpine e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="b7770-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b7770-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="b7770-115">Alpine</span></span>                   | <span data-ttu-id="b7770-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7770-116">.NET Core 2.1</span></span> | <span data-ttu-id="b7770-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b7770-117">.NET Core 3.1</span></span> | <span data-ttu-id="b7770-118">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="b7770-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b7770-119">✔️ 3,12</span><span class="sxs-lookup"><span data-stu-id="b7770-119">✔️ 3.12</span></span>  | <span data-ttu-id="b7770-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b7770-120">✔️ 2.1</span></span>        | <span data-ttu-id="b7770-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b7770-121">✔️ 3.1</span></span>        | <span data-ttu-id="b7770-122">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b7770-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b7770-123">✔️ 3,11</span><span class="sxs-lookup"><span data-stu-id="b7770-123">✔️ 3.11</span></span>  | <span data-ttu-id="b7770-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b7770-124">✔️ 2.1</span></span>        | <span data-ttu-id="b7770-125">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b7770-125">✔️ 3.1</span></span>        | <span data-ttu-id="b7770-126">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b7770-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b7770-127">✔️ 3,10</span><span class="sxs-lookup"><span data-stu-id="b7770-127">✔️ 3.10</span></span>  | <span data-ttu-id="b7770-128">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b7770-128">✔️ 2.1</span></span>        | <span data-ttu-id="b7770-129">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b7770-129">✔️ 3.1</span></span>        | <span data-ttu-id="b7770-130">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b7770-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b7770-131">✔️ 3,9</span><span class="sxs-lookup"><span data-stu-id="b7770-131">✔️ 3.9</span></span>   | <span data-ttu-id="b7770-132">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b7770-132">✔️ 2.1</span></span>        | <span data-ttu-id="b7770-133">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b7770-133">✔️ 3.1</span></span>        | <span data-ttu-id="b7770-134">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b7770-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b7770-135">❌3,8</span><span class="sxs-lookup"><span data-stu-id="b7770-135">❌ 3.8</span></span>   | <span data-ttu-id="b7770-136">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b7770-136">✔️ 2.1</span></span>        | <span data-ttu-id="b7770-137">❌3,1</span><span class="sxs-lookup"><span data-stu-id="b7770-137">❌ 3.1</span></span>        | <span data-ttu-id="b7770-138">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="b7770-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="b7770-139">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="b7770-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b7770-140">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="b7770-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b7770-141">3.0</span><span class="sxs-lookup"><span data-stu-id="b7770-141">3.0</span></span>
- <span data-ttu-id="b7770-142">2.2</span><span class="sxs-lookup"><span data-stu-id="b7770-142">2.2</span></span>
- <span data-ttu-id="b7770-143">2.0</span><span class="sxs-lookup"><span data-stu-id="b7770-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="b7770-144">Dependencies</span><span class="sxs-lookup"><span data-stu-id="b7770-144">Dependencies</span></span>

<span data-ttu-id="b7770-145">.NET Core su Alpine Linux richiede l'installazione delle seguenti dipendenze:</span><span class="sxs-lookup"><span data-stu-id="b7770-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="b7770-146">le librerie ICU</span><span class="sxs-lookup"><span data-stu-id="b7770-146">icu-libs</span></span>
- <span data-ttu-id="b7770-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="b7770-147">krb5-libs</span></span>
- <span data-ttu-id="b7770-148">libintl</span><span class="sxs-lookup"><span data-stu-id="b7770-148">libintl</span></span>
- <span data-ttu-id="b7770-149">libssl 1.1 (Alpine v 3.9 o versione successiva)</span><span class="sxs-lookup"><span data-stu-id="b7770-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="b7770-150">libssl 1.0 (Alpine v 3.8)</span><span class="sxs-lookup"><span data-stu-id="b7770-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="b7770-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="b7770-151">libstdc++</span></span>
- <span data-ttu-id="b7770-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="b7770-152">lttng-ust</span></span>
- <span data-ttu-id="b7770-153">numactl (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b7770-153">numactl (optional)</span></span>
- <span data-ttu-id="b7770-154">zlib</span><span class="sxs-lookup"><span data-stu-id="b7770-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b7770-155">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="b7770-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b7770-156">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="b7770-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b7770-157">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b7770-157">Next steps</span></span>

- [<span data-ttu-id="b7770-158">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b7770-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
