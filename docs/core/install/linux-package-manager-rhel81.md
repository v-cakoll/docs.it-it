---
title: Installare .NET Core in Linux RHEL 8,1 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in RHEL 8,1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8674b5d9d0f0ee384ca6798a7ea699bad67c5e5e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341179"
---
# <a name="rhel-81-package-manager---install-net-core"></a>Gestione pacchetti RHEL 8,1-installare .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in RHEL 8,1. .NET Core 3,1 non è ancora disponibile per RHEL 8,1.

> [!NOTE]
> RHEL 8,0 non include .NET Core 3,0. Usare il comando `yum upgrade` per eseguire l'aggiornamento a RHEL 8,1.

## <a name="register-your-red-hat-subscription"></a>Registrare la sottoscrizione di Red Hat

Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager. Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare la .NET Core SDK. Nel terminale eseguire i comandi seguenti.

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET Core

Dopo la registrazione con Gestione sottoscrizioni, si è pronti per installare e abilitare il runtime di ASP.NET Core. Nel terminale eseguire i comandi seguenti.

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Dopo la registrazione con Subscription Manager, si è pronti per installare e abilitare il runtime di .NET Core. Nel terminale eseguire i comandi seguenti.

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a>Vedere anche

- [Uso di .NET Core 3,0 in Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
