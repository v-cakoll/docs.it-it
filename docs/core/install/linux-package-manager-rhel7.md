---
title: Installare .NET Core in Linux RHEL 7 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: bcc41bfcd7c6d03038952e3faaf07952c3deb69d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715541"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="40f21-103">Gestione pacchetti RHEL 7-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="40f21-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="40f21-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="40f21-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="40f21-105">.NET Core 3,1 non è ancora disponibile per RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="40f21-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="40f21-106">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="40f21-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="40f21-107">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="40f21-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="40f21-108">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="40f21-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="40f21-109">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="40f21-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="40f21-110">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="40f21-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="40f21-111">Nel terminale eseguire i comandi seguenti per abilitare il canale DotNet di RHEL 7 e installare.</span><span class="sxs-lookup"><span data-stu-id="40f21-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="40f21-112">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="40f21-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="40f21-113">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="40f21-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="40f21-114">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="40f21-114">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="40f21-115">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="40f21-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="40f21-116">Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40f21-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="40f21-117">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="40f21-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="40f21-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40f21-118">See also</span></span>

- [<span data-ttu-id="40f21-119">Uso di .NET Core 3,0 in Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="40f21-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
