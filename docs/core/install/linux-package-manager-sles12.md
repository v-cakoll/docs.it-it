---
title: Installare .NET Core in SLES 12 - gestione pacchetti - .NET CoreInstall .NET Core on SLES 12 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in SLES 12.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a6c10c6b11bc57ae4bbe814c66c563b85ce3c22b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920742"
---
# <a name="sles-12-package-manager---install-net-core"></a>Gestione pacchetti SLES 12 - Installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in SLES 12. Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Registrare la chiave Microsoft e il feed

Prima di installare .NET, è necessario:

- Registrare la chiave Microsoft.
- Registrare l'archivio prodotti.
- Installare le dipendenze necessarie.

Questa operazione deve essere eseguita una volta sola per ogni computer.

Aprire un terminale ed eseguire il comando seguente.

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK.

Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK. Nel terminale, eseguire il seguente comando.

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime

Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime. Nel terminale, eseguire il seguente comando.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime. Nel terminale, eseguire il seguente comando.

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager

In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.

### <a name="failed-to-fetch"></a>Impossibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
