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
# <a name="rhel-7-package-manager---install-net-core"></a>RHEL 7 Gestione pacchetti - Installare .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in RHEL 7.This article describes how to use a package manager to install .NET Core on RHEL 7.

## <a name="register-your-red-hat-subscription"></a>Registra il tuo abbonamento Red Hat

Per installare .NET Core da Red Hat in RHEL, è innanzitutto necessario eseguire la registrazione utilizzando Red Hat Subscription Manager. Se questa operazione non è stata eseguita nel sistema o se non si è sicuri, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK.

Dopo la registrazione con Gestione sottoscrizioni, è possibile installare e abilitare .NET Core SDK. Nel terminale, eseguire i seguenti comandi per abilitare il canale dotnet RHEL 7 e installare.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET CoreInstall the ASP.NET Core Runtime

Dopo la registrazione con Subscription Manager, è possibile installare e abilitare il ASP.NET Core Runtime. Nel terminale, eseguire i seguenti comandi.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a>Installare .NET Core Runtime

Dopo la registrazione con Subscription Manager, è possibile installare e abilitare .NET Core Runtime. Nel terminale, eseguire i seguenti comandi.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a>Vedere anche

- [Utilizzo di .NET Core 3.1 su Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
