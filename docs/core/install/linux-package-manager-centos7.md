---
title: Installare .NET Core in CentOS 7-Gestione pacchetti-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in CentOS 7.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 66e78aadf933d3e10b99e3d2c7258733e96164f6
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920859"
---
# <a name="centos-7-package-manager---install-net-core"></a>Gestione pacchetti CentOS 7-installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in CentOS 7. Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.

## <a name="register-microsoft-key-and-feed"></a>Registrare la chiave e il feed Microsoft

Prima di installare .NET, è necessario:

- Registrare la chiave Microsoft.
- Registrare il repository del prodotto.
- Installare le dipendenze necessarie.

Questa operazione deve essere eseguita solo una volta per ogni computer.

Aprire un terminale ed eseguire il comando seguente.

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK. Nel terminale eseguire il comando seguente.

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET. Nel terminale eseguire il comando seguente.

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core. Nel terminale eseguire il comando seguente.

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Risolvere i problemi relativi a gestione pacchetti

Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.

### <a name="failed-to-fetch"></a>Non è stato possibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
