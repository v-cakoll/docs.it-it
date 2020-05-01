---
title: Installare .NET Core in Fedora 32-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624966"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="5d145-103">Gestione pacchetti Fedora 32-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d145-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="5d145-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="5d145-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="5d145-105">A partire da Fedora 32, .NET Core 3,1 è disponibile nei repository dei pacchetti predefiniti in Fedora.</span><span class="sxs-lookup"><span data-stu-id="5d145-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5d145-106">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5d145-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="5d145-107">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5d145-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="5d145-108">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="5d145-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5d145-109">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5d145-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="5d145-110">Installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5d145-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="5d145-111">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="5d145-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5d145-112">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d145-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="5d145-113">Installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5d145-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="5d145-114">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="5d145-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5d145-115">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="5d145-115">How to install other versions</span></span>

<span data-ttu-id="5d145-116">Per installare altre versioni di .NET Core, installare manualmente [il .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) o [il runtime di .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="5d145-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
