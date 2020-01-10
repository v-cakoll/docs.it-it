---
title: Installare .NET Core in openSUSE 15-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740666"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>Gestione pacchetti openSUSE 15-installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in openSUSE 15. Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.

## <a name="register-microsoft-key-and-feed"></a>Registrare la chiave Microsoft e il feed

Prima di installare .NET, è necessario:

- Registrare la chiave Microsoft.
- Registrare il repository del prodotto.
- Installare le dipendenze necessarie.

Questa operazione deve essere eseguita una volta sola per ogni computer.

Aprire un terminale ed eseguire i comandi seguenti.

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a>Errore di dipendenza con .NET Core 3,1

Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** . Usare il comando seguente per installare le dipendenze corrette prima di installare .NET Core 3,1 o ASP.NET Core 3,1.

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** . Usare il comando seguente per installare le dipendenze corrette, quindi installare .NET Core 3,1 SDK.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** . Usare il comando seguente per installare le dipendenze corrette, quindi installare il runtime di ASP.NET Core 3,1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** . Usare il comando seguente per installare le dipendenze corrette, quindi installare il runtime di .NET Core 3,1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
