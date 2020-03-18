---
title: Installare .NET Core in Linux RHEL 7 gestore di pacchetti - .NET CoreInstall .NET Core on Linux RHEL 7 package manager - .NET Core
description: Usare un gestore di pacchetti per installare .NET Core SDK e runtime in RHEL 7.Use a package manager to install .NET Core SDK and runtime on RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 4f85ed3da8a434fcd5b6ee88491daf623c3c8b31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76980184"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="61307-103">RHEL 7 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="61307-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="61307-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in RHEL 7.This article describes how to use a package manager to install .NET Core on RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="61307-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="61307-105">Registra il tuo abbonamento Red Hat</span><span class="sxs-lookup"><span data-stu-id="61307-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="61307-106">Per installare .NET Core da Red Hat in RHEL, è innanzitutto necessario eseguire la registrazione utilizzando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="61307-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="61307-107">Se questa operazione non è stata eseguita nel sistema o se non si è sicuri, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="61307-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="61307-108">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="61307-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="61307-109">Dopo la registrazione con Gestione sottoscrizioni, è possibile installare e abilitare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="61307-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="61307-110">Nel terminale, eseguire i seguenti comandi per abilitare il canale dotnet RHEL 7 e installare.</span><span class="sxs-lookup"><span data-stu-id="61307-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="61307-111">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="61307-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="61307-112">Dopo la registrazione con Subscription Manager, è possibile installare e abilitare il ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="61307-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="61307-113">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="61307-113">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="61307-114">Installare .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="61307-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="61307-115">Dopo la registrazione con Subscription Manager, è possibile installare e abilitare .NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="61307-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="61307-116">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="61307-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a><span data-ttu-id="61307-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61307-117">See also</span></span>

- [<span data-ttu-id="61307-118">Utilizzo di .NET Core 3.1 su Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="61307-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
