---
title: Installare .NET Core in SLES-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in SLES.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 8f64efcc8206b47855871104e5b6914570c06da0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619416"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a>Installare .NET Core SDK o runtime di .NET Core in SLES

.NET Core è supportato in SLES. Questo articolo descrive come installare .NET Core in SLES.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a>Distribuzioni supportate

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in SLES 12 SP2 e SLES 15. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di SLES non è più supportata.

- Un ✔️ indica che la versione di SLES o .NET Core è ancora supportata.
- ❌Indica che la versione di SLES o .NET Core non è supportata nella versione SLES.
- Quando una versione di SLES e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](#sles-15-)     | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [12 SP2](#sles-12-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

Le versioni seguenti di .NET Core non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a>SLES 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

Attualmente, il pacchetto di installazione del repository Microsoft SLES 15 installa il file *Microsoft-prod. repo* nella directory errata, impedendo a zypper di trovare i pacchetti di .NET Core. Per risolvere il problema, creare un collegamento simbolico nella directory corretta.

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a>✔️ SLES 12

.NET Core richiede almeno SP2 per la famiglia SLES 12.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a>Risolvere i problemi relativi a gestione pacchetti

Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.

### <a name="failed-to-fetch"></a>Non è stato possibile recuperare

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a>Dependencies

Quando si installa con una gestione pacchetti, queste librerie vengono installate. Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:

- krb5
- libicu
- libopenssl1_1

Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.

Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- [libgdiplus (versione 6.0.1 o successiva)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Installazione tramite script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Installazione manuale

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Passaggi successivi

- [Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code](../tutorials/with-visual-studio-code.md)
