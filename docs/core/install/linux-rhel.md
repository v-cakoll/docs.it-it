---
title: Installare .NET Core in RHEL-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in RHEL.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 9e4d0ab86355329b898a82f135b9eeb839eab1cb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619448"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="04e47-103">Installare .NET Core SDK o runtime di .NET Core in RHEL</span><span class="sxs-lookup"><span data-stu-id="04e47-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="04e47-104">.NET Core è supportato in RHEL.</span><span class="sxs-lookup"><span data-stu-id="04e47-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="04e47-105">Questo articolo descrive come installare .NET Core in RHEL.</span><span class="sxs-lookup"><span data-stu-id="04e47-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="04e47-106">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="04e47-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="04e47-107">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="04e47-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="04e47-108">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="04e47-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="04e47-109">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="04e47-109">Supported distributions</span></span>

<span data-ttu-id="04e47-110">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in RHEL 7 e RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="04e47-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="04e47-111">Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di RHEL non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="04e47-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="04e47-112">Un ✔️ indica che la versione di RHEL o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="04e47-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="04e47-113">❌Indica che la versione di RHEL o .NET Core non è supportata nella versione RHEL.</span><span class="sxs-lookup"><span data-stu-id="04e47-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="04e47-114">Quando una versione di RHEL e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="04e47-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="04e47-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="04e47-115">RHEL</span></span>                   | <span data-ttu-id="04e47-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04e47-116">.NET Core 2.1</span></span> | <span data-ttu-id="04e47-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="04e47-117">.NET Core 3.1</span></span> | <span data-ttu-id="04e47-118">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="04e47-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="04e47-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="04e47-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="04e47-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="04e47-120">✔️ 2.1</span></span>        | <span data-ttu-id="04e47-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="04e47-121">✔️ 3.1</span></span>        | <span data-ttu-id="04e47-122">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="04e47-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="04e47-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="04e47-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="04e47-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="04e47-124">✔️ 2.1</span></span>        | <span data-ttu-id="04e47-125">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="04e47-125">✔️ 3.1</span></span>        | <span data-ttu-id="04e47-126">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="04e47-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="04e47-127">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="04e47-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="04e47-128">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="04e47-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="04e47-129">3.0</span><span class="sxs-lookup"><span data-stu-id="04e47-129">3.0</span></span>
- <span data-ttu-id="04e47-130">2.2</span><span class="sxs-lookup"><span data-stu-id="04e47-130">2.2</span></span>
- <span data-ttu-id="04e47-131">2.0</span><span class="sxs-lookup"><span data-stu-id="04e47-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="04e47-132">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="04e47-132">How to install other versions</span></span>

<span data-ttu-id="04e47-133">Per informazioni sui passaggi necessari per installare altre versioni di .NET Core, vedere la [documentazione di Red Hat relativa a .NET Core](https://access.redhat.com/documentation/net_core/) .</span><span class="sxs-lookup"><span data-stu-id="04e47-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="04e47-134">✔️ RHEL 8</span><span class="sxs-lookup"><span data-stu-id="04e47-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="04e47-135">.NET Core è incluso nei repository FlussoApp per RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="04e47-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="04e47-136">✔️ RHEL 7</span><span class="sxs-lookup"><span data-stu-id="04e47-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="04e47-137">Il comando seguente consente di installare il `scl-utils` pacchetto:</span><span class="sxs-lookup"><span data-stu-id="04e47-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="04e47-138">Installare l'SDK</span><span class="sxs-lookup"><span data-stu-id="04e47-138">Install the SDK</span></span>

<span data-ttu-id="04e47-139">.NET Core SDK consente di sviluppare app con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04e47-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="04e47-140">Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente.</span><span class="sxs-lookup"><span data-stu-id="04e47-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="04e47-141">Per installare .NET Core SDK, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="04e47-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="04e47-142">Red Hat non consiglia l'abilitazione in modo permanente `rh-dotnet31` perché potrebbe influire su altri programmi.</span><span class="sxs-lookup"><span data-stu-id="04e47-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="04e47-143">Ad esempio, `rh-dotnet31` include una versione di `libcurl` che differisce dalla versione RHEL di base.</span><span class="sxs-lookup"><span data-stu-id="04e47-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="04e47-144">Questo può causare problemi nei programmi che non prevedono una versione diversa di `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="04e47-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="04e47-145">Se si vuole abilitare in `rh-dotnet` modo permanente, aggiungere la riga seguente al file _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="04e47-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="04e47-146">Installare il runtime</span><span class="sxs-lookup"><span data-stu-id="04e47-146">Install the runtime</span></span>

<span data-ttu-id="04e47-147">Il runtime di .NET Core consente di eseguire app eseguite con .NET Core che non includevano il Runtime.</span><span class="sxs-lookup"><span data-stu-id="04e47-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="04e47-148">I comandi seguenti consentono di installare il runtime di ASP.NET Core, che è il runtime più compatibile per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04e47-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="04e47-149">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="04e47-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="04e47-150">Red Hat non consiglia l'abilitazione in modo permanente `rh-dotnet31-aspnetcore-runtime-3.1` perché potrebbe influire su altri programmi.</span><span class="sxs-lookup"><span data-stu-id="04e47-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="04e47-151">Ad esempio, `rh-dotnet31-aspnetcore-runtime-3.1` include una versione di `libcurl` che differisce dalla versione RHEL di base.</span><span class="sxs-lookup"><span data-stu-id="04e47-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="04e47-152">Questo può causare problemi nei programmi che non prevedono una versione diversa di `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="04e47-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="04e47-153">Se si vuole abilitare in `rh-dotnet31-aspnetcore-runtime-3.1` modo permanente, aggiungere la riga seguente al file _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="04e47-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="04e47-154">In alternativa al runtime di ASP.NET Core, è possibile installare il runtime di .NET Core che non include ASP.NET Core supporto: sostituire `rh-dotnet31-aspnetcore-runtime-3.1` nei comandi precedenti con `rh-dotnet31-dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="04e47-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="04e47-155">Snap</span><span class="sxs-lookup"><span data-stu-id="04e47-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="04e47-156">Dependencies</span><span class="sxs-lookup"><span data-stu-id="04e47-156">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="04e47-157">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="04e47-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="04e47-158">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="04e47-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="04e47-159">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="04e47-159">Next steps</span></span>

- [<span data-ttu-id="04e47-160">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="04e47-160">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
