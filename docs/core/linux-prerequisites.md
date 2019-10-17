---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
author: leecow
ms.author: leecow
ms.date: 10/11/2019
ms.openlocfilehash: bb9049059de9d8208fc92234b28acdfb3d7f0cb3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318335"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Prerequisiti per .NET Core in Linux

Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux. Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:

* [Riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> Il pacchetto .NET Core SDK non è richiesto per ambienti/server di produzione. È necessario solo il pacchetto di runtime di .NET Core per le app distribuite in ambienti di produzione. Il runtime di .NET Core viene distribuito con le app nell'ambito di una distribuzione indipendente, ma deve essere distribuito separatamente per le app dipendenti dal framework. Per altre informazioni sui tipi di distribuzione indipendenti e dipendenti dal framework, vedere [Distribuzione di applicazioni .NET Core](./deploying/index.md). Per linee guida specifiche, vedere anche [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux indipendenti).

## <a name="supported-linux-versions"></a>Versioni di Linux supportate

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3,0 considera Linux come un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate. 

Per i collegamenti di download e altre informazioni, vedere [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) (Download di .NET Core 3.0).

.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             | Versione               | Architetture    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6 + 7                 | X64 |
| Oracle Linux                   | 7                     | X64 |
| CentOS                         | 7                     | X64 |
| Fedora                         | 29 +                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18 +                   | X64 |
| openSUSE                       | 15 +                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportate da .NET Core 3.0, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0 - Versioni di sistemi operativi supportate).

Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2,2 considera Linux come un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.

Per i collegamenti al download e altre informazioni, vedere [download di .NET Core 2,2](https://dotnet.microsoft.com/download/dotnet-core/2.2).

.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | X64 |
| Oracle Linux                   |  7                      | X64 |
| CentOS                         |  7                      | X64 |
| Fedora                         |  29, 30                 | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16,04, 18,04, 18,10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | X64 |
| openSUSE                       |  15 +                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.7 +                   | X64 |

Vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) per un elenco completo di sistemi operativi, distribuzioni e versioni di .net core 2,2 supportati, versioni del sistema operativo supportate e collegamenti ai criteri del ciclo di vita.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2,1 considera Linux come un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.

Per i collegamenti al download e altre informazioni, vedere [download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:

| Sistema operativo                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | X64 |
| Oracle Linux                   |  7                      | X64 |
| CentOS                         |  7                      | X64 |
| Fedora                         |  29, 30                 | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16,04, 18,04, 19,04    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | X64 |
| openSUSE                       |  42.3+                  | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.7 +                   | X64 |

Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportati da .NET Core 2.1, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 - Versioni di sistemi operativi supportate).

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

Quelli che seguono sono esempi. Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.

### <a name="ubuntu"></a>Ubuntu

Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:

* liblttng-ust0
* libcurl3 (per 14.x e 16.x)
* libcurl4 (per 18.x)
* libssl1.0.0
* libkrb5-3
* zlib1g
* libicu52 (per 14.X)
* libicu55 (per 16.X)
* libicu57 (per 17.X)
* libicu60 (per 18.x)

Per le versioni precedenti a .NET Core 2.1, sono richieste anche le dipendenze seguenti:

* libunwind8
* libuuid1

Per le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

* libgdiplus (versione 6.0.1 o successiva)

> [!NOTE]
> La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema. Per ulteriori informazioni, vedere <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS e Fedora

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

* lttng-ust
* libcurl
* openssl-libs
* krb5-libs
* libicu
* zlib

Utenti di Fedora: se la versione di openssl in uso è maggiore o uguale a 1.1, è necessario installare compat-openssl10.

Per le versioni precedenti a .NET Core 2.1, sono richieste anche le dipendenze seguenti:

* libunwind
* libuuid

Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).

Per le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

* libgdiplus (versione 6.0.1 o successiva)

> [!NOTE]
> La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema. Per ulteriori informazioni, vedere <https://www.mono-project.com/download/stable/>.

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installazione delle dipendenze di .NET Core con i programmi di installazione nativi

Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate. I programmi di installazione richiedono l'accesso amministratore (sudo) al server. L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core. I programmi di installazione nativi installano.NET Core SDK a livello di sistema.

In Linux sono disponibili due opzioni relative al pacchetto di installazione:

* L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.
* L'utilizzo dei pacchetti stessi, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Gli script vengono installati con lo script di installazione di .NET Core

Gli [script dotnet-install](./tools/dotnet-install-script.md) vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso. È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.

Lo script assume come impostazione predefinita l'installazione della versione "LTS" più recente, che è attualmente .NET Core 1.1. Per installare .NET Core 2.1, eseguire lo script con l'opzione seguente:

```bash
./dotnet-install.sh -c Current
```

Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore. Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.

## <a name="troubleshoot"></a>Risolvere i problemi

Se si verificano problemi in fase di installazione di .NET Core in una distribuzione/versione Linux supportata, vedere i seguenti argomenti per le distribuzioni/versioni installate in uso:

* [Problemi noti relativi a .NET Core 3.0](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [Problemi noti relativi a .NET Core 2.2](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [Problemi noti relativi a .NET Core 2.1](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [Problemi noti relativi a .NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [Problemi noti relativi a .NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0)
