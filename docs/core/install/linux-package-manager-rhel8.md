---
title: Installare .NET Core in Linux RHEL 8 gestione pacchetti - .NET CoreInstall .NET Core on Linux RHEL 8 package manager - .NET Core
description: Usare un gestore di pacchetti per installare .NET Core SDK e runtime in RHEL 8.Use a package manager to install .NET Core SDK and runtime on RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b564a386eb67b6e414a832ad3bca10d3d09022bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134188"
---
# <a name="rhel-8-package-manager---install-net-core"></a>RHEL 8 Gestione pacchetti - Installare .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in RHEL 8.This article describes how to use a package manager to install .NET Core on RHEL 8.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Registra il tuo abbonamento Red Hat

Per installare .NET Core da Red Hat in RHEL, è innanzitutto necessario eseguire la registrazione utilizzando Red Hat Subscription Manager. Se questa operazione non è stata eseguita nel sistema o se non si è sicuri, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK.

Dopo la registrazione con Gestione sottoscrizioni, è possibile installare e abilitare .NET Core SDK. Nel terminale, eseguire i seguenti comandi.

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET CoreInstall the ASP.NET Core Runtime

Dopo la registrazione con Subscription Manager, è possibile installare e abilitare il ASP.NET Core Runtime. Nel terminale, eseguire i seguenti comandi.

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installare .NET Core Runtime

Dopo la registrazione con Subscription Manager, è possibile installare e abilitare .NET Core Runtime. Nel terminale, eseguire i seguenti comandi.

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a>Vedere anche

- [Utilizzo di .NET Core 3.1 in Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
