---
title: Installare .NET Core in Debian-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 68a3e848b3d80806e875dfb2fb7e2cbf223f8ad5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619494"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a>Installare .NET Core SDK o runtime di .NET Core in Debian

Questo articolo descrive come installare .NET Core in Debian. Quando una versione di Debian non è supportata, .NET Core non è più supportato con tale versione. Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuzioni supportate

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Debian su cui sono supportate. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Debian raggiunge la fine del ciclo di vita](https://wiki.debian.org/DebianReleases).

- Un ✔️ indica che la versione di Debian o .NET Core è ancora supportata.
- ❌Indica che la versione di Debian o .NET Core non è supportata in questa versione Debian.
- Quando una versione di Debian e una versione di .NET Core sono ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](#debian-10-)     | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [9](#debian-9-)       | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌[8](#debian-8-)       | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |

Le versioni seguenti di .NET Core non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a>✔️ Debian 10

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a>✔️ Debian 9

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a>Debian 8❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a>SDK o runtime di aggiornamento APT

Quando è disponibile una nuova versione patch per .NET Core, è possibile aggiornarla semplicemente tramite APT con i comandi seguenti:

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a>Risoluzione dei problemi di APT

Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di APT per installare .NET Core.

### <a name="unable-to-locate"></a>Impossibile individuare

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a>Non è stato possibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Dependencies

Quando si installa con una gestione pacchetti, queste librerie vengono installate. Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu52 (per 8. x)
- libicu57 (per 9. x)
- libicu63 (per 10. x)
- libicu67 (per 11. x)
- libssl 1.0.0 (per 8. x)
- libssl 1.1 (per 9. x-11. x)
- libstdc + + 6
- zlib1g

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- libgdiplus (versione 6.0.1 o successiva)

  > [!WARNING]
  > È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Installazione tramite script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Installazione manuale

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Passaggi successivi

- [Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code](../tutorials/with-visual-studio-code.md)
