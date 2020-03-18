---
title: Installare .NET Core in Debian 9 - gestione pacchetti - .NET CoreInstall .NET Core on Debian 9 - package manager - .NET Core
description: Usare un gestore di pacchetti per installare .NET Core SDK e runtime in Debian 9.Use a package manager to install .NET Core SDK and runtime on Debian 9.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 32b152ff9be5135cf0ca7f8914bc9ee4f78000be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920843"
---
# <a name="debian-9-package-manager---install-net-core"></a>Debian 9 Gestione pacchetti - Installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Debian 9.This article describes how to use a package manager to install .NET Core on Debian 9. Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Registrare la chiave Microsoft e il feed

Prima di installare .NET, è necessario:

- Registrare la chiave Microsoft.
- Registrare l'archivio prodotti.
- Installare le dipendenze necessarie.

Questa operazione deve essere eseguita una volta sola per ogni computer.

Aprire un terminale ed eseguire i seguenti comandi.

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK.

Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime

Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager

In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.

### <a name="failed-to-fetch"></a>Impossibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
