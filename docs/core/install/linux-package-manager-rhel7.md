---
title: Installare .NET Core in Linux RHEL 7 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.openlocfilehash: 4893271ebd32036d8ec09e6b718c12b11acb8d59
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450982"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="e28d2-103">Gestione pacchetti RHEL 7-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="e28d2-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="e28d2-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="e28d2-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="e28d2-105">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="e28d2-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="e28d2-106">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="e28d2-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="e28d2-107">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="e28d2-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e28d2-108">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="e28d2-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="e28d2-109">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e28d2-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="e28d2-110">Nel terminale eseguire i comandi seguenti per abilitare il canale DotNet di RHEL 7 e installare.</span><span class="sxs-lookup"><span data-stu-id="e28d2-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install .</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e28d2-111">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e28d2-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="e28d2-112">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e28d2-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="e28d2-113">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e28d2-113">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e28d2-114">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="e28d2-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="e28d2-115">Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e28d2-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="e28d2-116">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e28d2-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```
