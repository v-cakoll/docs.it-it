---
title: Installare .NET Core in Linux RHEL 8,1 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 8,1.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.openlocfilehash: 5b658fe4c56b945210534872fe3cc502eb31a763
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450975"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="9690f-103">Gestione pacchetti RHEL 8,1-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="9690f-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="9690f-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in RHEL 8,1.</span><span class="sxs-lookup"><span data-stu-id="9690f-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="9690f-105">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="9690f-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="9690f-106">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="9690f-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="9690f-107">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="9690f-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9690f-108">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9690f-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="9690f-109">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="9690f-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="9690f-110">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9690f-110">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9690f-111">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9690f-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="9690f-112">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9690f-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="9690f-113">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9690f-113">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9690f-114">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9690f-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="9690f-115">Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9690f-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="9690f-116">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9690f-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```
