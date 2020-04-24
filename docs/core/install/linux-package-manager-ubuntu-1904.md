---
title: Installare .NET Core in Ubuntu 19.04 Package Manager - .NET CoreInstall .NET Core on Ubuntu 19.04 package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime su Ubuntu 19.04.Use a package manager to install .NET Core SDK and runtime on Ubuntu 19.04.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 3f338832185ed626289141f48cec88c1bf2e3a33
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645595"
---
# <a name="ubuntu-1904-package-manager---install-net-core"></a>Ubuntu 19.04 Gestione pacchetti - Installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Ubuntu 19.04.This article describes how to use a package manager to install .NET Core on Ubuntu 19.04.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a>Aggiungere la chiave e il feed del repository Microsoft

Prima di installare .NET, è necessario:

- Aggiungere la chiave di firma del pacchetto Microsoft all'elenco delle chiavi attendibili.
- Aggiungere il repository al gestore di pacchetti.
- Installare le dipendenze necessarie.

Questa operazione deve essere eseguita una volta sola per ogni computer.

Aprire un terminale ed eseguire i seguenti comandi.

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK

Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto dotnet-sdk-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET Core. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto aspnetcore-runtime-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime. Nel terminale, eseguire i seguenti comandi.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto dotnet-runtime-3.1**, vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti .

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager

In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.

### <a name="unable-to-locate"></a>Impossibile individuare

Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto .**

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

Se il sistema non funziona, è possibile eseguire un'installazione manuale con i seguenti comandi.

```bash
sudo apt-get install -y gpg
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/19.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a>Impossibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
