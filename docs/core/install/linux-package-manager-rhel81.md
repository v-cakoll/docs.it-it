---
title: Installare .NET Core in Linux RHEL 8,1 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 8,1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714383"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="06277-103">Gestione pacchetti RHEL 8,1-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="06277-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="06277-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in RHEL 8,1.</span><span class="sxs-lookup"><span data-stu-id="06277-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="06277-105">.NET Core 3,1 non è ancora disponibile per RHEL 8,1.</span><span class="sxs-lookup"><span data-stu-id="06277-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="06277-106">RHEL 8,0 non include .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="06277-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="06277-107">Usare il comando `yum upgrade` per eseguire l'aggiornamento a RHEL 8,1.</span><span class="sxs-lookup"><span data-stu-id="06277-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="06277-108">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="06277-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="06277-109">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="06277-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="06277-110">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="06277-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="06277-111">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="06277-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="06277-112">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="06277-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="06277-113">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="06277-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="06277-114">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="06277-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="06277-115">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="06277-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="06277-116">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="06277-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="06277-117">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="06277-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="06277-118">Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="06277-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="06277-119">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="06277-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="06277-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06277-120">See also</span></span>

- [<span data-ttu-id="06277-121">Uso di .NET Core 3,0 in Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="06277-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
