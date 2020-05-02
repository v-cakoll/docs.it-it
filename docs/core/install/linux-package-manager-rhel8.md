---
title: Installare .NET Core in Linux RHEL 8 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: 8829e842e920e6abd4184b5140f80bb016acace2
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728235"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="33059-103">Gestione pacchetti RHEL 8-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="33059-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="33059-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Red Hat Enterprise Linux (RHEL) 8.</span><span class="sxs-lookup"><span data-stu-id="33059-104">This article describes how to use a package manager to install .NET Core on Red Hat Enterprise Linux (RHEL) 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="33059-105">Registrare la sottoscrizione di Red Hat</span><span class="sxs-lookup"><span data-stu-id="33059-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="33059-106">Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager.</span><span class="sxs-lookup"><span data-stu-id="33059-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="33059-107">Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="33059-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="33059-108">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="33059-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="33059-109">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="33059-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="33059-110">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="33059-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="33059-111">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="33059-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="33059-112">Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="33059-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="33059-113">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="33059-113">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="33059-114">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="33059-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="33059-115">Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33059-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="33059-116">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="33059-116">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="33059-117">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="33059-117">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="see-also"></a><span data-ttu-id="33059-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33059-118">See also</span></span>

- [<span data-ttu-id="33059-119">Uso di .NET Core 3,1 in Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="33059-119">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
